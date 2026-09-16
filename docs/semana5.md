# Semana 5 — Diseño de producto: PDS y arquitectura del sistema

!!! abstract "Blueprint: Creación de valor → Factible · DVF: 🟢 Factible"
    Hasta ahora el equipo sabe *qué* va a construir y *para quién*. Esta semana responde *cómo*: qué requiere técnicamente el producto, cómo se articulan sus tres componentes, y dónde corre cada parte de la inteligencia. El entregable no es código — es la hoja de ruta técnica que hace que el código de las semanas siguientes tenga dirección.

---

## Distribución de tiempo presencial

| # | Bloque | Contenido | Tiempo |
|---|--------|-----------|:------:|
| 1 | PDS | Qué es y por qué existe antes del diseño | 20 min |
| 2 | Arquitectura | Ejemplo real de sistema mecatrónico con IA | 40 min |
| 3 | Taller | El equipo diseña su propia arquitectura | 60 min |
| | **Total** | | **120 min** |

!!! tip "La nota más importante"
    Ya saben programar ESP32 y Raspberry Pi. El foco de esta semana **no es el cómo implementar** — es el **por qué decidir** de una forma y no de otra. ¿Por qué MQTT y no HTTP? ¿Por qué cloud y no edge? ¿Por qué este sensor y no aquel? Cada decisión de arquitectura debe tener justificación técnica explícita. Las arquitecturas sin justificación se regresan.

---

## Bloque 1 — Product Design Specification (PDS)
**Duración: 20 min · Min 0:00 – 0:20**

### Por qué existe el PDS — y qué pasa cuando no existe


> *"¿Cuántas veces hemos empezado a programar o a diseñar algo antes de tener claro exactamente qué debe hacer, bajo qué condiciones, con qué restricciones y cómo saben si funcionó? Muchas. Ese es el problema que el PDS resuelve."*

El **Product Design Specification (PDS)** es el documento que **traduce la propuesta de valor en requerimientos técnicos formales.** No describe cómo construir el producto — describe exactamente qué debe hacer el producto y bajo qué condiciones para considerarse exitoso.

Sin PDS, los equipos diseñan para su imaginación del usuario, no para el usuario real. Cambian de dirección cada semana según la última conversación. Llegan a semana 12 con un producto que "casi funciona" pero no cumple ningún criterio verificable de éxito.

Con PDS, cada decisión de diseño tiene un criterio de evaluación. Si alguien propone cambiar el microcontrolador, el PDS dice si ese cambio viola algún requerimiento. Si el cliente pregunta "¿ya está listo?", el PDS dice exactamente qué falta.

> *"El PDS es el contrato técnico del equipo consigo mismo, o con el cliente. Si no pueden escribirlo, no entienden suficientemente bien lo que van a construir."*

---

### Las cuatro categorías de requerimientos

Ejemplo del sensor agrícola:

=== "Requerimientos funcionales"

    **¿Qué debe hacer el producto?**

    Describen el comportamiento observable del sistema — las funciones que el usuario puede ver, medir o experimentar.

    Formato: *"El sistema debe [verbo] [qué] [condición]."*

    Ejemplos para el sensor agrícola:
    - El sistema debe medir la humedad volumétrica del suelo con una resolución mínima de ±2%
    - El sistema debe enviar una alerta al usuario en menos de 60 segundos después de detectar un nivel crítico de humedad
    - La app debe mostrar el historial de mediciones de los últimos 30 días sin conexión a internet
    - El sistema debe diferenciar entre 3 tipos de cultivo con umbrales de riego distintos configurables por el usuario

    **Error más común:** escribir requerimientos funcionales tan vagos que no son verificables. *"El sistema debe funcionar bien"* no es un requerimiento funcional — no dice qué significa "bien" ni cómo verificarlo.

=== "Requerimientos de desempeño"

    **¿Qué tan bien debe hacerlo?**

    Cuantifican el comportamiento del sistema — velocidad, precisión, duración, consumo, rango.

    Ejemplos para el sensor agrícola:
    - Frecuencia de muestreo: mínimo 1 lectura cada 15 minutos en modo normal, 1 cada 5 minutos en modo alerta
    - Vida de batería: mínimo 6 meses en campo sin recarga con el perfil de uso normal
    - Latencia de alerta: máximo 60 segundos desde detección hasta notificación en app
    - Precisión del modelo de IA: mínimo 85% de acierto en la recomendación de riego validada contra datos agronómicos reales
    - Temperatura de operación: -5°C a 55°C (condiciones de invernadero en verano en el Bajío)

    **Error más común:** omitir los requerimientos de desempeño porque "eso se ve después". El desempeño define la arquitectura — si necesitas 6 meses de batería, eso elimina opciones de microcontrolador y protocolo de comunicación desde el inicio.

=== "Requerimientos de interfaz"

    **¿Cómo interactúa con el mundo exterior?**

    Describen las interfaces del sistema: con el usuario, con otros sistemas, con el entorno físico.

    Interfaces de usuario:
    - La app debe ser operable con una sola mano y guante de trabajo puesto
    - El artefacto debe indicar estado (normal / alerta / sin conexión) con LED visible a 5 metros bajo luz solar directa
    - Las alertas deben llegar como notificación push en WhatsApp o SMS — no solo en la app

    Interfaces con otros sistemas:
    - La API debe ser compatible con REST para integración futura con sistemas de riego automatizado
    - Los datos deben exportarse en formato CSV para compatibilidad con hojas de cálculo del usuario

    Interfaces físicas:
    - El sensor debe instalarse a profundidades de 10, 20 y 30 cm sin herramienta especializada
    - El artefacto debe resistir lavado con manguera (IPX5 mínimo)

=== "Requerimientos de restricción"

    **¿Qué no puede hacer o qué límites debe respetar?**

    Definen las fronteras del diseño — regulaciones, presupuesto, tiempo, materiales, compatibilidad.

    Restricciones de manufactura:
    - Todos los componentes deben estar disponibles en MercadoLibre México o Mouser con entrega en menos de 2 semanas
    - El costo de materiales del prototipo no debe exceder $2,500 MXN
    - El PCB debe poder fabricarse con el equipo del laboratorio (máximo 2 capas, pitch mínimo de componentes: 0.8mm)

    Restricciones regulatorias:
    - El dispositivo debe operar en la banda ISM de 915 MHz (LoRa) o 2.4 GHz (WiFi/BLE) sin requerir certificación especial para prototipo

    Restricciones de tiempo:
    - La primera versión funcional debe estar lista en semana 13 — 8 semanas de desarrollo efectivo desde hoy

    Restricciones de compatibilidad:
    - La app debe funcionar en Android 8+ e iOS 14+ sin necesidad de instalar aplicaciones adicionales

---

### La diferencia entre prototipo de exploración y first-iteration product

Este punto es crítico:

```
PROTOTIPO DE EXPLORACIÓN
→ Sirve para aprender: ¿funciona el principio?
→ Puede ser feo, inestable, manual en partes
→ Lo usa el equipo, no el usuario final
→ Éxito = aprendizaje técnico, no funcionamiento completo
→ Ejemplo: un sensor conectado a una laptop que muestra
  datos crudos en terminal

FIRST-ITERATION PRODUCT (lo que entrega este curso)
→ Sirve para validar: ¿lo compraría alguien?
→ Debe funcionar de forma autónoma sin intervención del equipo
→ Lo usa un usuario real en condiciones reales
→ Éxito = el usuario puede usarlo sin instrucciones del equipo
→ Ejemplo: el sensor completo con app funcionando,
  instalado en el campo del agricultor durante 2 semanas
```

> *"Cuando escriban su PDS, están describiendo el first-iteration product — no el prototipo de exploración. Esa distinción define el nivel de ambición del documento. Si su PDS describe algo que no podría usarse sin que ustedes estén presentes explicando cómo funciona, necesitan revisarlo."*

---

### Instrucción de taller — PDS propio (parte del Bloque 3)

El PDS completo se escribe en casa. En clase el equipo define el esqueleto: mínimo 3 requerimientos por categoría, con criterio de verificación explícito para cada uno.

**Criterio de un buen requerimiento:** ¿puede otra persona verificar si se cumple o no sin preguntarle al equipo? Si la respuesta es no, el requerimiento necesita más especificidad.

---

## Bloque 2 — Ejemplo de arquitectura de sistema con producto real
**Duración: 40 min · Min 0:20 – 1:00**

### Por qué la arquitectura antes de la implementación

La arquitectura de sistema es el mapa del producto antes de construirlo. Define qué hace cada componente, cómo se comunican, dónde vive la inteligencia, y qué pasa con los datos desde que el sensor los genera hasta que el usuario ve la información en la app.

Diseñar la arquitectura mal — o no diseñarla — produce los problemas más costosos del desarrollo: incompatibilidades entre componentes que se descubren en semana 10, latencias que hacen inutilizable la app, consumo de batería que no permite usar el producto en campo, o modelos de IA que no pueden correr en el hardware elegido.

---

### La decisión más importante: ¿dónde corre el modelo de IA?

Antes de dibujar cualquier diagrama, la pregunta central:

> *"Para cualquier producto con IA, la decisión más importante de arquitectura no es qué modelo usar — es dónde corre ese modelo. Edge, cloud o híbrido. Cada opción tiene consecuencias en latencia, costo, conectividad, privacidad y complejidad. No hay respuesta universalmente correcta — hay una respuesta correcta para cada producto y cada usuario."*

=== "Edge (ESP32 / Raspberry Pi)"

    El modelo de IA corre directamente en el microcontrolador o SBC, sin necesidad de conexión a internet para inferencia.

    **Cuándo tiene sentido:**
    - El usuario final tiene conectividad intermitente o nula (campo agrícola sin señal, zona industrial sin WiFi estable)
    - La latencia de inferencia es crítica — decisiones en milisegundos que no pueden esperar un round-trip a la nube
    - Los datos son sensibles y no pueden salir del dispositivo por regulación o por confianza del usuario
    - El costo de operación en la nube haría inviable el modelo de negocio a escala

    **Las limitaciones reales:**
    - ESP32: modelos muy pequeños únicamente (TensorFlow Lite Micro, máximo ~100KB de parámetros). Clasificación simple, detección de anomalías básica.
    - Raspberry Pi 4: modelos medianos funcionan bien (hasta ~500MB). Visión computacional ligera, NLP pequeño.
    - Consumo de energía: la inferencia en edge consume más batería que solo sensar y transmitir datos crudos
    - Actualizar el modelo requiere OTA update al dispositivo — más complejo que actualizar un endpoint en la nube

    **Ejemplo de decisión bien justificada:**
    > *"Usamos TFLite Micro en el ESP32 para la detección de anomalías en el patrón de humedad porque los agricultores de nuestro segmento tienen cobertura celular intermitente y necesitan que el sistema funcione aunque no haya señal. El modelo tiene 47KB y corre en 80ms en el ESP32 — suficiente para nuestros requerimientos."*

=== "Cloud (API externa)"

    El modelo corre en servidores remotos — puede ser un modelo propio desplegado en AWS/GCP/Azure, o una API de terceros (OpenAI, Anthropic, Google Gemini).

    **Cuándo tiene sentido:**
    - El usuario tiene conectividad estable y la latencia de red es aceptable para el caso de uso
    - El modelo es demasiado grande para correr en el dispositivo disponible
    - Los datos se necesitan agregar de múltiples dispositivos para hacer inferencia (análisis de flota, benchmarking entre usuarios)
    - La iteración del modelo es frecuente — en cloud se actualiza sin tocar los dispositivos en campo

    **Las limitaciones reales:**
    - Costo operativo: cada llamada a la API tiene costo. A escala, el costo de inferencia puede destruir el margen del negocio
    - Latencia: round-trip a la nube agrega 100–500ms. Para aplicaciones de tiempo real, esto puede ser inaceptable
    - Dependencia: si la API de terceros cambia sus precios, sus términos o deja de operar, el producto falla
    - Privacidad: los datos del usuario salen del dispositivo. Para datos médicos, industriales o agrícolas sensibles, esto puede ser un problema legal o de confianza

    **Ejemplo de decisión bien justificada:**
    > *"Usamos la API de Claude para generar las recomendaciones agronómicas porque el contexto que necesita el modelo (historial de 30 días, tipo de cultivo, etapa del ciclo, clima regional) supera la capacidad de cualquier modelo que quepa en el ESP32. La latencia de 2–3 segundos es aceptable para una recomendación que el agricultor consulta una vez por día, no en tiempo real."*

=== "Híbrido"

    La inferencia se divide entre el dispositivo y la nube según el tipo de decisión.

    **La lógica del híbrido:**
    - **En el dispositivo:** decisiones rápidas, locales, críticas para seguridad o funcionamiento básico. Modelos pequeños, baja latencia, funciona sin conexión.
    - **En la nube:** análisis profundo, recomendaciones complejas, agregación de datos de múltiples dispositivos, modelos grandes. Requiere conexión, mayor latencia aceptable.

    **Ejemplo aplicado:**
    ```
    ESP32 (edge):
    → Detección de anomalía en lectura de sensor (TFLite Micro)
    → Si anomalía detectada: alerta local inmediata
    → Transmite datos crudos + flag de anomalía a la nube

    Cloud (AWS Lambda + Claude API):
    → Recibe datos del ESP32 cada 15 minutos
    → Analiza patrón histórico de 30 días
    → Genera recomendación de riego con contexto agronómico
    → Envía notificación a la app del agricultor
    ```

    **Cuándo tiene más sentido que las otras dos opciones:**
    Cuando el caso de uso tiene dos tipos de decisión con requerimientos opuestos: algunas decisiones necesitan ser rápidas y funcionar sin conexión, otras necesitan ser sofisticadas y usan datos que no caben en el dispositivo.

---

### El diagrama de bloques — construido en vivo

El instructor dibuja el diagrama del sensor agrícola mientras lo explica. No es un slide — es una construcción en tiempo real que el alumno puede replicar para su propio producto.

```
┌─────────────────────────────────────────────────────────────────┐
│                    CAPA FÍSICA (Hardware)                        │
│                                                                  │
│  [Sensor humedad]──[ESP32]──[LoRa SX1276]──[Gateway LoRa]      │
│  [Sensor temp]    └─[TFLite]                                    │
│  [Batería LiPo]    Anomalía detection                           │
└─────────────────────────────────┬───────────────────────────────┘
                                  │ MQTT over LoRaWAN
┌─────────────────────────────────▼───────────────────────────────┐
│                    CAPA DE DATOS (Cloud)                         │
│                                                                  │
│  [MQTT Broker]──[AWS IoT Core]──[Lambda]──[DynamoDB]            │
│                                    │                             │
│                              [Claude API]                        │
│                          (recomendación de riego)               │
└─────────────────────────────────┬───────────────────────────────┘
                                  │ REST API / WebSocket
┌─────────────────────────────────▼───────────────────────────────┐
│                    CAPA DE PRESENTACIÓN (App)                    │
│                                                                  │
│  [React Native]──[Push notifications]──[Dashboard]              │
│  Android + iOS    WhatsApp / SMS         Historial 30d           │
│                   (Twilio API)                                   │
└─────────────────────────────────────────────────────────────────┘
```

**Lo que el instructor señala al construirlo:**

1. **Cada flecha tiene un protocolo.** No "se comunican" — se comunican por MQTT, por REST, por WebSocket. El protocolo no es un detalle — es una decisión de diseño.

2. **Cada caja tiene responsabilidades claras.** El ESP32 hace detección de anomalías. La Lambda orquesta. Claude genera recomendaciones. La app presenta. Nadie hace todo.

3. **Los datos fluyen en una dirección principal** (sensor → cloud → app) pero también en reversa (app → cloud → dispositivo para configuración). Ambas direcciones deben estar en el diagrama.

4. **Las dependencias externas están marcadas.** Claude API, Twilio, AWS — si alguna falla, ¿qué parte del sistema sigue funcionando?

---

### Criterios de selección de protocolo de comunicación

El instructor explica los cuatro protocolos con criterio de elección — no con descripción técnica que ya conocen:

| Protocolo | Úsalo cuando... | No lo uses cuando... |
|-----------|----------------|----------------------|
| **MQTT** | Dispositivos con ancho de banda limitado, mensajes frecuentes y pequeños, necesitas pub/sub entre múltiples dispositivos, conexión intermitente | Necesitas respuesta síncrona inmediata, o transfieres archivos grandes |
| **BLE** | Comunicación local de corto alcance (<10m), bajo consumo de energía es crítico, no hay infraestructura de red en el punto de uso | Necesitas comunicación a más de 10m, o múltiples dispositivos simultáneos sin gateway |
| **HTTP REST** | Comunicación entre servicios en la nube, integraciones con APIs de terceros, cuando la latencia de segundos es aceptable | Dispositivos con batería y conexión limitada, mensajes muy frecuentes (costo por request) |
| **WebSocket** | La app necesita recibir datos del servidor en tiempo real sin polling, dashboards en vivo | Dispositivos IoT con batería — el overhead de mantener conexión abierta consume energía |

> *"La pregunta no es '¿cuál protocolo es mejor?' — es '¿cuál resuelve mejor el problema de comunicación específico de este componente de mi sistema?' Un producto bien diseñado típicamente usa más de un protocolo, cada uno donde tiene sentido."*

---

### Viabilidad de prototipo y primera tirada

El instructor hace un punto que los equipos suelen ignorar hasta que ya es tarde:

> *"El diseño más elegante del mundo que no pueden fabricar no sirve. Pero hay una pregunta más que la mayoría no se hace en semana 5 y que define si el producto puede salir del laboratorio: ¿cuántas unidades necesitan para hacer una prueba de mercado real con usuarios pagando? Cinco, diez, veinte — ese número define qué proceso de manufactura es viable, y algunas decisiones de diseño que toman hoy facilitan o imposibilitan llegar a ese número."*

Esto no es DFM — no están optimizando para producción en serie. Es una pregunta más inmediata: **¿el diseño que están eligiendo hoy puede reproducirse el número de veces que necesitan para validar el modelo de negocio?**

**La pregunta cero — antes de las tres de siempre:**

> *"¿Cuántas unidades necesitan para hacer una prueba de mercado real — no un demo, sino usuarios reales usando el producto durante semanas y pagando por él?"*

Para la mayoría de los proyectos de este curso la respuesta está entre 5 y 20 unidades. Ese número no es arbitrario — es el mínimo que permite observar patrones de uso, identificar fallas de campo, y tener conversaciones de precio reales con usuarios. Menos de 5 es un demo. Más de 50 es producción prematura.

**El proceso de manufactura viable según volumen:**

| Volumen | Proceso de PCB | Proceso de ensamble | Implicación de diseño |
|---------|----------------|--------------------|-----------------------|
| **1–3 unidades** | Fabricación en laboratorio (2 capas, CNC o transferencia) | Soldadura manual, componentes THT o SMD grandes | Componentes 0805 o mayores, pitch ≥ 1.27mm, THT donde sea posible |
| **5–20 unidades** | JLCPCB / PCBWay (~$15–30 USD por 5 PCBs, 7–10 días) | Stencil + pasta de soldar + horno de reflujo o hot air | SMD 0603 viable, pitch ≥ 0.8mm, evitar BGA |
| **20–100 unidades** | JLCPCB con servicio PCBA (ensamble incluido) | Ensamble externo — el laboratorio no escala aquí | Todos los componentes deben estar en la librería de JLCPCB, diseño para pick and place |
| **100+ unidades** | Manufactura local o importada con maquila | Proceso industrial — fuera del alcance del curso | — |

> *"Para la primera iteración funcional que entrega este curso, el objetivo realista es entre 3 y 10 unidades. Diseñen para ese rango. Si quieren hacer una prueba de mercado real en semana 14, apunten a 5–10 unidades con JLCPCB + PCBA — es la opción más viable en costo y tiempo para ese volumen."*

**Las cuatro preguntas de viabilidad que el equipo responde antes de cerrar su arquitectura:**

1. **¿Cuántas unidades necesitan para validar el modelo de negocio?**
No el número ideal — el mínimo que permite tener usuarios reales usando el producto y pagando. Ese número define el proceso.

2. **Disponibilidad de componentes a ese volumen:** ¿todos los componentes están disponibles en la cantidad que necesitan — no solo 2 o 3 unidades — en MercadoLibre, Mouser o DigiKey con entrega en menos de 2 semanas? Si JLCPCB hace el ensamble, ¿los componentes están en su librería?

3. **Fabricabilidad del PCB con el proceso elegido:** ¿el diseño es compatible con el proceso que corresponde al volumen? Un PCB diseñado para soldadura manual en laboratorio puede no ser fabricable con PCBA externo si tiene componentes fuera del estándar.

4. **Costo por unidad a ese volumen:** ¿el costo de materiales + manufactura por unidad permite un precio de venta que el segmento pagaría? Si el BOM de una unidad cuesta $2,000 MXN y el usuario pagaría $800 MXN/mes, el modelo de negocio necesita revisarse antes de construir.

!!! warning "La trampa del diseño no reproducible"
    El error más frecuente: un equipo hace una unidad perfecta en semana 13, soldada a mano en 40 horas de trabajo, con componentes comprados de uno en uno en tres tiendas diferentes. Cuando el instructor pide hacer 3 más para la prueba de mercado, descubren que no pueden. El diseño que no puede reproducirse en volumen razonable no es un producto — es una escultura.

!!! tip "JLCPCB + PCBA es el punto dulce para este curso"
    Para 5–20 unidades con componentes estándar, JLCPCB con servicio de ensamble (PCBA) produce PCBs ensamblados en 10–15 días hábiles a un costo por unidad que generalmente cabe en el presupuesto del proyecto. El requisito: todos los componentes del diseño deben estar en su librería de partes, y el diseño debe seguir sus reglas de fabricación (DRC). Verificar esto en semana 5 evita rediseños costosos en semana 11.

---

## Bloque 3 — Taller: el equipo diseña su propia arquitectura
**Duración: 60 min · Min 1:00 – 2:00**

### Estructura del taller

El taller tiene tres momentos con tiempos definidos:

```
1:00 – 1:15  Decisión de arquitectura de IA (15 min)
             → Cada equipo decide: edge / cloud / híbrido
             → Justificación técnica escrita en 3 puntos

1:15 – 1:45  Diagrama de bloques propio (30 min)
             → Con ayuda de Claude (Prompt 1)
             → Dibujado en papel o draw.io

1:45 – 2:00  Defensa de arquitectura (15 min)
             → Cada equipo: 5 minutos
             → El instructor desafía las decisiones sin justificación
```

---

### 1:00 – 1:15 · Decisión de arquitectura de IA

**Instrucción al grupo:**

> *"Antes de abrir Claude, el equipo toma una decisión: ¿dónde corre el modelo de IA de su producto? Edge, cloud o híbrido. Escriban la decisión y tres puntos de justificación técnica. Tres minutos para discutirlo, luego lo escriben. No hay respuesta correcta — hay respuestas justificadas y respuestas sin justificar."*

El instructor circula. Señala equipos que eligen edge "porque suena más técnico" sin considerar el tamaño del modelo, o equipos que eligen cloud sin considerar el costo por llamada a escala o la conectividad del usuario final.

**Las tres preguntas que guían la decisión:**

1. ¿Tu usuario tiene conectividad estable en el punto de uso del producto?
2. ¿La decisión del modelo necesita respuesta en menos de 1 segundo, o puede esperar 2–5 segundos?
3. ¿Los datos del usuario pueden salir del dispositivo, o hay restricción de privacidad o confianza?

---

### 1:15 – 1:45 · Diagrama de bloques con IA

### Prompt 1 — Claude: arquitectura del sistema

```
Actúa como un arquitecto de sistemas embebidos con experiencia
en productos mecatrónicos con inteligencia artificial para
mercados latinoamericanos. Tu especialidad es diseñar
arquitecturas de sistema que equilibran capacidad técnica,
restricciones de manufactura y viabilidad económica para
equipos de desarrollo universitario con presupuesto limitado.
No propones la arquitectura más sofisticada — propones la más
adecuada para las capacidades del equipo y los requerimientos
del producto. Cuando hay una decisión de arquitectura sin
justificación técnica, la señalas directamente.

Somos un equipo de ingeniería en México desarrollando un
producto mecatrónico con tres componentes: un artefacto físico
inteligente, una aplicación móvil/web, y una página de venta.
Tenemos 8 semanas de desarrollo efectivo para llegar a una
primera versión funcional que un usuario real pueda usar sin
que nosotros estemos presentes.

Nuestras capacidades técnicas:
- Hardware: ESP32, Raspberry Pi, diseño de PCB (2 capas),
  impresión 3D para carcasas, soldadura SMD
- Software: Python, C/C++, JavaScript/React, React Native
- IA: TensorFlow Lite, PyTorch, APIs de modelos (OpenAI,
  Anthropic, Google), bases de datos vectoriales básicas
- Presupuesto de materiales: máximo $3,000 MXN para prototipo

Nuestro producto:
Nombre: [nombre del concepto de semana 4]
Descripción: [descripción en 3–4 oraciones — qué hace, para quién,
  qué problema resuelve]
Propuesta de valor: [la Versión 3 del prompt de semana 4]

Requerimientos técnicos clave (del PDS preliminar):
[Listar 3–5 requerimientos funcionales y de desempeño más
  importantes — los que más impactan la arquitectura]

Nuestra decisión de arquitectura de IA:
[Edge / Cloud / Híbrido]
Justificación (3 puntos):
1. [primer punto]
2. [segundo punto]
3. [tercer punto]

Con esta información, diseña la arquitectura del sistema
completo y entrega exactamente lo que se indica:

PASO 1 — VALIDACIÓN DE LA DECISIÓN DE IA:
¿La decisión de edge/cloud/híbrido está bien justificada
dados los requerimientos del producto y las capacidades del
equipo? Si hay un problema con la decisión, señálalo antes
de continuar. Si está bien justificada, confírmalo y explica
por qué.

PASO 2 — ARQUITECTURA DEL SISTEMA:
Diseña la arquitectura completa en tres capas:

Capa física (Hardware):
- Microcontrolador/SBC principal y por qué ese y no otro
- Sensores y actuadores necesarios con modelo o especificación
- Módulo de comunicación y protocolo elegido con justificación
- Alimentación (batería / cable / solar) con estimación de vida

Capa de datos (Backend/Cloud):
- Dónde viven los datos (servicio específico, no genérico)
- Cómo fluyen los datos desde el sensor hasta el almacenamiento
- El modelo de IA: qué hace exactamente, dónde corre, qué
  input recibe y qué output produce
- Protocolo de comunicación entre hardware y backend

Capa de presentación (App/Web):
- Tipo de app y por qué (nativa / React Native / PWA)
- Las 3 pantallas o vistas más importantes que necesita el usuario
- Cómo recibe datos del backend (polling / WebSocket / push)
- Integración de notificaciones (push / WhatsApp / SMS)

PASO 3 — FLUJO DE DATOS COMPLETO:
Describe el flujo de datos de extremo a extremo para el
caso de uso principal — desde el momento en que el sensor
toma una lectura hasta que el usuario recibe información
accionable en la app. Incluir:
- Cada paso del flujo con el componente responsable
- El protocolo o mecanismo de cada transferencia
- La latencia estimada de cada paso
- Qué pasa si algún paso falla (fallback o degradación)

PASO 4 — VIABILIDAD DE PROTOTIPO Y PRIMERA TIRADA:
El equipo necesita entre 5 y 10 unidades para una prueba
de mercado real. Evalúa la arquitectura propuesta desde
esa perspectiva — no desde 1 unidad sino desde 5–10.

Para los 3 componentes más críticos de la arquitectura:
- ¿Están disponibles en México en cantidad suficiente
  (mínimo 10 unidades) con entrega < 2 semanas?
- ¿Si se usa JLCPCB PCBA, los componentes están en su
  librería de partes estándar?
- ¿El diseño del PCB es compatible con el proceso de
  manufactura que corresponde al volumen objetivo?
  (laboratotio manual para 1–3 / JLCPCB+PCBA para 5–20)

Costo por unidad:
- ¿Cuál es el BOM estimado por unidad a volumen de 10?
- ¿Ese costo permite un precio de venta que el segmento
  pagaría? (regla: costo de materiales ≤ 30% del precio
  de venta para hardware con software incluido)

Si hay componentes que violan estas restricciones a escala
de 5–10 unidades, proponer alternativa viable que sí funcione.

FORMATO DE SALIDA:

════════════════════════════════════════════════════════
ARQUITECTURA DEL SISTEMA
Producto: [nombre] · Decisión de IA: [Edge/Cloud/Híbrido]
════════════════════════════════════════════════════════

VALIDACIÓN DE DECISIÓN DE IA:
[Confirmada ✅ / Problema detectado ⚠️]
[Justificación en 2–3 oraciones]

────────────────────────────────────────────────────────
CAPA FÍSICA — Hardware

Microcontrolador principal: [modelo específico]
Por qué este: [justificación técnica, no solo "es popular"]

Sensores:
· [sensor] — [modelo/especificación] — [razón de elección]
· [sensor] — [modelo/especificación] — [razón de elección]

Actuadores (si aplica):
· [actuador] — [especificación] — [razón]

Comunicación: [protocolo] vía [módulo]
Por qué [protocolo] y no [alternativa]: [justificación]

Alimentación: [tipo] — Vida estimada: [duración]
Supuesto de consumo: [mA promedio]

────────────────────────────────────────────────────────
CAPA DE DATOS — Backend/Cloud

Servicio de datos: [servicio específico — AWS IoT / Firebase /
  Supabase / etc.]
Por qué este: [justificación]

Modelo de IA:
· Qué hace: [tarea específica]
· Dónde corre: [Edge ESP32 / Edge RPi / Cloud API / Híbrido]
· Input: [qué datos recibe]
· Output: [qué produce — clasificación, recomendación, alerta]
· Modelo específico o framework: [TFLite / PyTorch / Claude API /
  etc.]

Protocolo hardware → backend: [protocolo] — Latencia estimada: [ms]

────────────────────────────────────────────────────────
CAPA DE PRESENTACIÓN — App

Tipo: [React Native / Flutter / PWA / otra] — Por qué: [razón]

Vistas principales:
1. [nombre de vista] — [qué muestra y permite hacer]
2. [nombre de vista] — [qué muestra y permite hacer]
3. [nombre de vista] — [qué muestra y permite hacer]

Actualización de datos: [polling cada Xmin / WebSocket / push]
Notificaciones: [método] vía [servicio específico]

────────────────────────────────────────────────────────
FLUJO DE DATOS — Caso de uso principal

[Paso 1] Sensor → [componente]: [dato] vía [protocolo] — ~[X]ms
[Paso 2] [componente] → [componente]: [dato] vía [protocolo] — ~[X]ms
[Paso 3] [componente] → modelo IA: [input] — inferencia ~[X]ms
[Paso 4] modelo IA → [componente]: [output] — ~[X]ms
[Paso 5] [componente] → app usuario: [información] vía [protocolo] — ~[X]ms

Latencia total extremo a extremo: ~[X] segundos
Funcionamiento sin conexión: [sí — qué funciona / no — por qué]

────────────────────────────────────────────────────────
VIABILIDAD DE PROTOTIPO Y PRIMERA TIRADA

Volumen objetivo para prueba de mercado: [5–10 / otro] unidades

Componente crítico 1: [nombre]
· Disponibilidad MX (cantidad ≥10): ✅/⚠️/❌ — [fuente y plazo]
· En librería JLCPCB PCBA: ✅/⚠️/❌
· Costo unitario: $[MXN]
· Alternativa si no cumple: [cuál]

Componente crítico 2: [nombre]
[mismo formato]

Componente crítico 3: [nombre]
[mismo formato]

Proceso de manufactura recomendado para [N] unidades:
[Laboratorio manual / JLCPCB+PCBA / otro] — Por qué: [razón]

BOM por unidad (a volumen de [N] unidades): $[MXN]
BOM total para [N] unidades: $[MXN]
Precio de venta mínimo viable (BOM ÷ 30%): $[MXN/unidad]
¿El segmento pagaría ese precio? ✅/⚠️/❌ — [justificación]

PCB compatible con proceso elegido: ✅ sí / ⚠️ con ajuste / ❌ no
[Si ajuste: qué cambiar en el diseño para que sea compatible]
════════════════════════════════════════════════════════
```

---

### 1:45 – 2:00 · Defensa de arquitectura — 5 minutos por equipo

Cada equipo presenta su diagrama de bloques y explica **una sola decisión**: la más importante de su arquitectura. No presentan todo el diagrama — presentan la decisión que más define el producto.

**Formato de los 5 minutos:**

```
Minuto 1–2: La decisión
"Elegimos [edge/cloud/híbrido] para el modelo de IA porque
[requerimiento del producto que lo justifica]. La alternativa
era [otra opción] pero la descartamos porque [razón técnica]."

Minuto 3–4: La consecuencia
"Esta decisión implica que [consecuencia en el hardware],
[consecuencia en el protocolo], y [consecuencia en la app].
El riesgo principal es [cuál] y lo mitigamos con [cómo]."

Minuto 5: Pregunta del instructor
```

**El banco de preguntas del instructor — solo hace una por equipo:**

Preguntas sobre la decisión de IA:
- *"¿Cuántos KB ocupa el modelo de IA en el ESP32? ¿Cuánta RAM queda disponible para el resto del firmware?"*
- *"Si la API de [servicio] sube su precio 10x el año que entra, ¿qué parte de su arquitectura falla?"*
- *"¿Qué pasa si el usuario está en zona sin señal? ¿El producto funciona o se vuelve un ladrillo?"*

Preguntas sobre el protocolo:
- *"¿Por qué MQTT y no HTTP REST para esta comunicación específica? ¿Cuántos mensajes por hora envía el dispositivo?"*
- *"¿El broker MQTT es propio o de terceros? Si es de terceros, ¿cuánto cuesta a 1,000 dispositivos?"*

Preguntas sobre manufactura:
- *"¿Ya verificaron que ese sensor está en stock en MercadoLibre? ¿Cuántos días de entrega?"*
- *"¿El PCB de este diseño lo pueden fabricar en el laboratorio o necesitan mandarlo a fabricar? ¿Cuánto tiempo agrega eso?"*

**Criterios de aprobación:**

✅ **Aprobada** — La arquitectura tiene justificación técnica para las decisiones principales. El equipo puede responder las preguntas del instructor sin improvisar.

⚠️ **Aprobada con ajuste** — La arquitectura es viable pero hay una decisión sin justificación técnica. El equipo la documenta y la justifica como parte de la tarea.

❌ **Regresada** — La arquitectura tiene decisiones que violan los requerimientos del producto, las capacidades del equipo, o las restricciones de manufactura. El equipo rehace la sección afectada antes de continuar con el PDS.

---

## Tarea en casa (4 horas)

| Tarea | Tiempo | Entregable |
|-------|:------:|-----------| 
| PDS completo — mínimo 4 requerimientos por categoría, con criterio de verificación explícito para cada uno | 1.5h | Documento PDS (1 página) en el formato indicado |
| Diagrama de arquitectura anotado en draw.io o Miro | 1.5h | Diagrama con: cajas etiquetadas, flechas con protocolo, capa de IA marcada, flujo de datos indicado |
| Investigación de componentes clave: disponibilidad, precio, tiempo de entrega | 1h | BOM preliminar con fuente y precio de cada componente crítico |

### Prompt 2 — Claude: validar y completar el PDS

```
Actúa como un ingeniero de producto senior con experiencia
en redactar Product Design Specifications para productos
de hardware + software en etapa de prototipo avanzado.
Tu especialidad es identificar requerimientos mal redactados
— demasiado vagos para verificarse, demasiado restrictivos
para ser alcanzables, o que faltan y harán falta en el
desarrollo. No eres condescendiente: señalas el problema
y propones la corrección específica.

Somos un equipo de ingeniería en México desarrollando:
[nombre del producto + descripción en 2–3 oraciones]
Usuario final: [perfil accionable de semana 4]
First-iteration product: [descripción de lo que entrega
  el curso — no prototipo de exploración]

Este es nuestro PDS preliminar:

REQUERIMIENTOS FUNCIONALES:
1. [requerimiento]
2. [requerimiento]
3. [requerimiento]
[agregar los que tengan]

REQUERIMIENTOS DE DESEMPEÑO:
1. [requerimiento]
2. [requerimiento]
[agregar los que tengan]

REQUERIMIENTOS DE INTERFAZ:
1. [requerimiento]
2. [requerimiento]
[agregar los que tengan]

REQUERIMIENTOS DE RESTRICCIÓN:
1. [requerimiento]
2. [requerimiento]
[agregar los que tengan]

Revisa el PDS completo y entrega:

1. DIAGNÓSTICO POR CATEGORÍA:
Para cada categoría: ¿qué requerimientos están bien redactados
(verificables, específicos, alcanzables), cuáles tienen problemas
y cuáles faltan para un producto como este?

2. CORRECCIONES:
Para cada requerimiento con problema, la versión corregida
con el criterio de verificación explícito.

3. REQUERIMIENTOS FALTANTES:
Los requerimientos que no están en el PDS pero que un
producto como este necesita para llegar a first-iteration
product. Mínimo 2 por categoría.

FORMATO DE SALIDA:

════════════════════════════════════════════════════════
REVISIÓN DE PDS
Producto: [nombre]
════════════════════════════════════════════════════════

REQUERIMIENTOS FUNCIONALES
✅ Bien redactados: [cuáles y por qué]
⚠️ Con problema: [cuáles]
  → Corrección: [versión corregida]
❌ Faltantes: [qué debería estar y no está]

REQUERIMIENTOS DE DESEMPEÑO
[mismo formato]

REQUERIMIENTOS DE INTERFAZ
[mismo formato]

REQUERIMIENTOS DE RESTRICCIÓN
[mismo formato]

────────────────────────────────────────────────────────
PDS COMPLETO CORREGIDO:
[El PDS completo con todos los requerimientos corregidos
y los faltantes agregados — listo para entregar]
════════════════════════════════════════════════════════
```

### Estructura del entregable PDS

```
PRODUCT DESIGN SPECIFICATION
Producto: _____________________ Versión: 1.0
Equipo: _______________________ Fecha: _______

REQUERIMIENTOS FUNCIONALES
RF-01: [El sistema debe...] — Verificación: [cómo se verifica]
RF-02: [El sistema debe...] — Verificación: [cómo se verifica]
RF-03: [El sistema debe...] — Verificación: [cómo se verifica]
RF-04: [El sistema debe...] — Verificación: [cómo se verifica]

REQUERIMIENTOS DE DESEMPEÑO
RD-01: [El sistema debe...] — Criterio: [valor numérico + condición]
RD-02: [El sistema debe...] — Criterio: [valor numérico + condición]
RD-03: [El sistema debe...] — Criterio: [valor numérico + condición]
RD-04: [El sistema debe...] — Criterio: [valor numérico + condición]

REQUERIMIENTOS DE INTERFAZ
RI-01: [La interfaz debe...] — Verificación: [cómo se verifica]
RI-02: [La interfaz debe...] — Verificación: [cómo se verifica]
RI-03: [La interfaz debe...] — Verificación: [cómo se verifica]
RI-04: [La interfaz debe...] — Verificación: [cómo se verifica]

REQUERIMIENTOS DE RESTRICCIÓN
RR-01: [El sistema no debe / debe cumplir...] — Verificación:
RR-02: [El sistema no debe / debe cumplir...] — Verificación:
RR-03: [El sistema no debe / debe cumplir...] — Verificación:
RR-04: [El sistema no debe / debe cumplir...] — Verificación:

DIAGRAMA DE ARQUITECTURA: [link a draw.io / Miro / imagen]
BOM PRELIMINAR: [link a hoja de cálculo]
```

---

## Lo que el equipo debe poder responder al salir

- [ ] ¿Dónde corre el modelo de IA de su producto y por qué esa decisión?
- [ ] ¿Qué protocolo de comunicación usa entre el artefacto y el backend, y por qué ese y no otro?
- [ ] ¿Cuál es el componente de hardware más difícil de conseguir en México y cuál es el plan B?
- [ ] ¿Cuál es la diferencia entre lo que entregarán en semana 13 y un prototipo de exploración?


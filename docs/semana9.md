# Semana 9 — Integración, go-to-market y pitch

!!! abstract "Blueprint: Entrega y captura de valor · DVF: 🟢 Factible · 🟡 Viable · 🔴 Deseable"
    Esta es la última clase de contenido. Después vienen dos semanas de trabajo propio y la evaluación final. Lo que se decide hoy es cómo el equipo usa ese tiempo: qué integra, con quién lo prueba, cómo lo lanza y cómo lo cuenta en 3 minutos. Los tres componentes (artefacto, app y landing) tienen que funcionar juntos, y el equipo tiene que demostrar con evidencia que alguien lo usaría y pagaría por él.

!!! warning "Esta clase condensa tres semanas del temario original"
    Integración y pruebas, go-to-market y pitch, y regulación caben en 2 horas porque la construcción sale del aula. En clase se decide, se calcula y se ensaya. La app, la landing y la integración se construyen en las dos semanas de trabajo, guiadas por los prompts y la ruta de este documento. 

---

## Distribución de tiempo presencial

| # | Bloque | Contenido | Tiempo |
|---|--------|-----------|:------:|
| 1 | Integración | Fronteras del sistema, bugs comunes, pruebas de punta a punta | 20 min |
| 2 | Pruebas con usuarios | Protocolo de 30 min, severidad, síntesis | 15 min |
| 3 | Go-to-market | Early adopters, canales, preventa, CAC, LTV, churn, landing | 35 min |
| 4 | Regulación | Lo mínimo para saber qué se necesita para vender | 10 min |
| 5 | Pitch | Estructura de 3 minutos, ejemplo, práctica en parejas | 25 min |
| 6 | Ruta de cierre | Plan hacia atrás para las dos semanas de trabajo | 15 min |
| | **Total** | | **120 min** |

!!! tip "El hilo conductor"
    Integrar, probar con usuarios, lanzar y contar. Cada bloque produce el insumo del siguiente: las pruebas de integración producen un sistema que se puede probar con personas, las pruebas producen evidencia, la evidencia alimenta los números del lanzamiento, y los números y la evidencia son lo que sostiene el pitch.

---

## Bloque 1 — Integración del sistema


### Las fallas viven en las fronteras


> *"Cada parte de su sistema funciona. El sensor mide, el firmware transmite, el backend recibe, la app dibuja. Y juntos no funcionan. Eso no es mala suerte: es la regla. Las fallas de un sistema integrado casi nunca están dentro de un componente, están en la frontera entre dos."*

Un producto con artefacto, app, backend y modelo de IA tiene cuatro fronteras. El equipo las nombra antes de probar nada:

```
F1  Sensor → microcontrolador       ¿la lectura es confiable?
F2  Dispositivo → red / broker      ¿el dato sale y llega?
F3  Backend → modelo de IA          ¿la respuesta es utilizable?
F4  Backend → app (y landing)       ¿el usuario ve lo correcto, a tiempo?
```

**El método es bisección por fronteras.** Cuando algo falla, no se revisa el sistema completo: se pone un registro (log, captura, medición) en cada frontera y se busca la primera donde el dato ya viene mal. Con cuatro fronteras, el problema se encuentra en cuatro verificaciones, no en cuatro días.

### 0:05 – 0:12 · Los bugs más comunes en productos mecatrónicos con IA

| Síntoma | Causa frecuente | Primera prueba |
|---------|-----------------|----------------|
| Los datos llegan con minutos de retraso | Polling lento, cola en el broker, ahorro de energía del WiFi | Registrar el timestamp en cada salto y ver dónde se acumula el retraso |
| El dispositivo se reinicia al transmitir | Caída de tensión en los picos de corriente de la radio, regulador o batería débiles | Medir el riel de 3.3 V durante la transmisión; agregar capacitor de desacople |
| Se pierde la conexión y no vuelve | No hay lógica de reconexión, keepalive mal ajustado | Apagar el router 10 min y observar si el sistema se recupera solo |
| La app muestra datos viejos como si fueran actuales | No se muestra la hora del dato ni hay estado "sin conexión" | Forzar una desconexión y mirar qué dice la app |
| La recomendación de IA llega vacía, absurda o con formato roto | Timeout, límite de tasa de la API, salida fuera del formato esperado | Guardar entrada y salida crudas de cada llamada; validar la salida contra un esquema |
| Las lecturas tienen deriva o ruido | Sensor sin calibrar, alimentación ruidosa | Comparar contra una referencia conocida; promediar varias muestras |
| Funciona en el laboratorio y falla en campo | WiFi débil, temperatura, humedad, polvo | Prueba continua de 48 h en el entorno real |

> *"Si su sistema falla y no pueden decir en qué frontera, el problema no es el bug: es que no tienen registros. Pongan registros antes de necesitarlos."*

### Pruebas mínimas y definición de listo

Seis pruebas de sistema, de la más barata a la más cara. Los criterios salen del PDS de la semana 5, no de la intuición. El ejemplo usa los requerimientos del sensor agrícola:

| # | Prueba | Qué se mide | Aprobado si |
|---|--------|-------------|-------------|
| T1 | Instalación sin ayuda | Tiempo y errores de una persona que no conoce el producto | Completa en menos de 5 minutos sin intervención |
| T2 | Latencia de punta a punta | Tiempo desde que el sensor detecta hasta que la app muestra la alerta | Máximo 60 segundos (requerimiento de desempeño del PDS) |
| T3 | Desconexión y recuperación | Qué pasa al cortar la red 10 minutos | Se recupera sin intervención y no pierde lecturas |
| T4 | Autonomía de batería | Corriente promedio en un ciclo completo de sueño, lectura y transmisión | Proyección de 6 meses o más |
| T5 | Falla de la API de IA | Qué hace el sistema si el modelo no responde | Degrada con un mensaje claro, no se rompe |
| T6 | Operación continua en campo | 48 h en el entorno real de uso | Sin reinicios ni datos perdidos |

**Cómo se calcula T4, con números.** La autonomía no se adivina, se mide la corriente y se calcula:

```
Supuestos del ejemplo (el equipo los reemplaza por sus mediciones):
  Batería 18650 de 3,000 mAh, con 80% de capacidad útil = 2,400 mAh
  Objetivo del PDS: 6 meses = 6 x 30 x 24 = 4,320 h
  Consumo promedio máximo permitido = 2,400 / 4,320 = 0.556 mA

Ciclo medido cada 15 minutos (900 s):
  Activo: 3 s a 120 mA        = 360 mA·s
  Sueño: 897 s a 0.010 mA     = 8.97 mA·s
  Consumo promedio = (360 + 8.97) / 900 = 0.410 mA

Autonomía = 2,400 mAh / 0.410 mA = 5,854 h = 8.1 meses  →  cumple (> 6 meses)
```

**Definición de listo.** Un sistema integrado está listo cuando cumple las cuatro condiciones del checklist técnico de entrega:

1. El hardware funciona sin la laptop del equipo.
2. La app está desplegada o en un APK distribuible, no corriendo en el entorno de desarrollo.
3. La landing está publicada en internet, no en localhost.
4. El dato fluye del sensor a la pantalla sin que nadie intervenga a mano.

!!! note "Si no integra completo"
    Se documenta qué funciona, qué no y en qué frontera falla. Un equipo que sabe diagnosticar su propio sistema vale más que uno que esconde los bugs el día de la demo.

### Prompt 1 — Claude: plan de integración y pruebas (se ejecuta en casa)

```
Actúa como ingeniero de pruebas de sistemas embebidos conectados,
con experiencia en productos IoT con componentes de IA. Tu método
es la bisección por fronteras: probar cada interfaz entre
componentes con evidencia (log, medición, captura) antes de
culpar al sistema completo. No propones pruebas que el equipo no
pueda ejecutar con sus medios: laboratorio universitario,
multímetro, laptop y teléfonos.

Somos un equipo de ingeniería en México. Nuestro producto:
Nombre y qué hace: [2 oraciones]
Arquitectura (semana 5): [componentes, protocolos y dónde
  corre la IA, en texto]
Requerimientos de desempeño del PDS: [3 a 5, con valores numéricos]
Qué ya funciona por separado: [lista]
Qué nunca hemos probado junto: [lista]

Entrega:
1. Las fronteras de nuestro sistema, numeradas, con el componente
   de cada lado y el protocolo.
2. Seis pruebas de sistema ordenadas de la más barata a la más
   cara. Para cada una: qué se hace, qué se mide, criterio de
   aprobado con número (sale del PDS) y qué evidencia se guarda.
3. Para cada frontera, los dos fallos más probables en nuestro
   caso y la primera prueba para distinguirlos.
4. Cómo debe degradarse el sistema si falla internet y si falla
   la API de IA.
Si falta un número en el PDS para una prueba, dilo y propone
cómo medirlo. No inventes requerimientos.
```

---

## Bloque 2 — Pruebas con usuarios


### Qué se prueba y con quién

En la semana 8 el equipo probó un supuesto con un prototipo. Ahora prueba **el sistema completo** con alguien que nunca lo ha visto. La diferencia importa: ya no se pregunta si una idea tiene sentido, se pregunta si el producto funciona en manos de otra persona.

**Con quién:** cinco personas. Con cinco usuarios aparece la mayoría de los problemas de usabilidad (regla de Nielsen); más usuarios repiten lo mismo. De esas cinco, tres deben ser del segmento objetivo. Las otras dos pueden ser integrantes de otro equipo: **cada equipo es el usuario externo de otro**. Eso cumple la función de revisión entre pares sin gastar una clase.

### El protocolo de 30 minutos

| Min | Qué pasa | Qué se observa |
|-----|----------|----------------|
| 0–3 | Introducción con un guion fijo: "estamos probando el producto, no a usted; piense en voz alta" | Nada que explicar del producto |
| 3–10 | Tarea 1: instalar el dispositivo desde la caja | ¿Lo logra sin ayuda? Tiempo, errores, dudas |
| 10–20 | Tarea 2: conectar la app e interpretar una alerta | ¿Entiende qué le dice el sistema y qué debe hacer? |
| 20–25 | Tarea 3: encontrar el precio y dejar su interés (pre-registro) | ¿Encuentra la landing? ¿Completa el CTA? |
| 25–30 | Entrevista de cierre | Qué esperaba, qué le costó, cuánto pagaría y a quién se lo recomendaría |

**Reglas del observador:** no ayuda, no explica, no defiende el diseño. Si el usuario se atora, anota el minuto exacto y espera 30 segundos antes de intervenir. Cuando pregunte "¿esto qué hace?", responde con otra pregunta: "¿qué esperaba que hiciera?".

**Qué se registra por tarea:**
- ¿Completó sin ayuda? (sí o no)
- Tiempo en completar.
- Errores y cuántas veces dudó.
- SEQ: "¿qué tan fácil fue esta tarea?", de 1 a 7.
- Citas textuales.

**Sobre precio y recomendación:** se pregunta por comportamiento y compromisos, no por opiniones. "¿Le gustaría?" produce cortesía. "¿Dejó su teléfono para el piloto?" produce evidencia.

### Severidad y síntesis

Cada hallazgo se clasifica antes de corregir nada:

- **Crítico:** impide completar la tarea. Se corrige primero.
- **Mayor:** se completa con ayuda o con un error recuperable.
- **Menor:** molestia sin consecuencia para la tarea.

### Prompt 2 — Claude: síntesis de pruebas de usuario (se ejecuta en casa)

```
Actúa como investigador de usabilidad de productos de hardware
conectado. Sintetizas observaciones sin defender el diseño:
reportas lo que la gente hizo, no lo que dijo que le gustaba.
Distingues el problema de su causa y no propones rediseños sin
evidencia.

Notas de [N] sesiones de prueba, una por usuario. Por cada tarea
registramos: si completó sin ayuda, tiempo, errores, SEQ (1 a 7)
y citas textuales.
[pegar las notas]

Entrega:
1. Tabla por tarea: tasa de éxito sin ayuda, tiempo mediano y
   SEQ promedio.
2. Hallazgos ordenados por severidad (crítico, mayor, menor),
   cada uno con cuántos usuarios lo vivieron y una cita.
3. Los tres cambios de mayor impacto con menor esfuerzo, cada uno
   con la hipótesis que prueba.
4. Lo que NO podemos concluir con esta muestra.
5. Señal de negocio: qué dijeron sobre precio y recomendación,
   separando compromisos reales (dejó datos, pre-registró, pagó)
   de opiniones.
```

---

## Bloque 3 — Go-to-market y economía unitaria


### Early adopters: los primeros 20

El go-to-market no empieza con "todo el mercado". Empieza con los primeros 20 clientes. Un early adopter es la persona que tiene el problema con tanta intensidad que acepta un producto imperfecto a cambio de resolverlo hoy. Cuatro rasgos para encontrarlo:

1. **Tiene el dolor agudo:** perdió dinero o tiempo por el problema recientemente.
2. **Ya intentó resolverlo:** improvisó algo, compró algo que no funcionó, o lo busca activamente.
3. **Tiene acceso y poder de decisión:** puede instalar y pagar sin pedir permiso a nadie más.
4. **Habla con otros como él:** su opinión viaja. En el segmento del sensor agrícola, la referencia entre productores es el canal de adopción (lo que revelaron las capas psicográfica y económica del perfil de la semana 4).

> *"Si no pueden describir a su cliente número 1 por nombre y apellido, todavía no tienen estrategia de lanzamiento: tienen un mercado."*

### Canales y preventa

| Canal | Cuándo conviene | Qué aprende el equipo | Riesgo |
|-------|-----------------|-----------------------|--------|
| **Venta directa** | Primeros 20 clientes | Todo: objeciones, instalación, uso real | No escala; consume horas del equipo |
| **Distribuidor o punto físico** (por ejemplo, una agrotienda) | Cuando el cliente ya compra ahí | Qué dice el vendedor del mostrador, qué objeciones aparecen | Cede control de la experiencia y margen |
| **Landing con pre-registro o preventa** | Desde ya, antes de fabricar | Si alguien deja datos o dinero por una promesa | Sin demo creíble, no convierte |
| **Crowdfunding** | Producto con demo visual fuerte | Demanda a mayor escala | Obliga a cumplir entregas; exige video y comunidad previa |

El prototipo de negocio de la semana 8 es el centro de esta estrategia: una landing con precio real y un CTA mide la demanda antes de comprometer inventario. El caso de Bird Buddy en Kickstarter, que viste en la semana 8, es esa lógica llevada a escala.

!!! warning "Sobre cobrar antes de entregar"
    Un pre-registro con datos de contacto no compromete a nadie. Recibir un anticipo sí: implica obligaciones fiscales y de entrega. Durante el curso, el equipo mide intención con pre-registro y precio visible. Si quiere explorar anticipos reales, lo consulta primero.

### Las métricas: CAC, LTV, churn y payback

Cuatro números responden la pregunta del inversionista: ¿cuánto cuesta conseguir un cliente y cuánto deja?

```
CAC (costo de adquisición de cliente) =
  Todo lo gastado en conseguir clientes ÷ Clientes nuevos conseguidos
  (horas del equipo valuadas, viáticos, muestras, publicidad)

Churn mensual = Clientes que cancelan en el mes ÷ Clientes al inicio del mes

Vida media del cliente = 1 ÷ churn mensual

LTV (valor de vida del cliente) = Contribución mensual × Vida media
  Contribución mensual = Precio de suscripción − Costo operativo mensual por usuario

Inversión por cliente = CAC + Costo del hardware subsidiado

Payback (meses) = Inversión por cliente ÷ Contribución mensual
```

**Regla práctica de la industria de software por suscripción** (una referencia, no una ley): LTV dividido entre la inversión por cliente debería ser de 3 o más, y el payback menor a 12 meses.

**Ejemplo resuelto: el sensor agrícola.** Los datos vienen de la semana 7 (modelo de hardware subsidiado y recuperado con la suscripción). Lo marcado como supuesto lo debe reemplazar cada equipo con datos medidos.

```
DATOS HEREDADOS DE LA SEMANA 7
  Costo operativo por usuario (nube 18 + IA 0.27 + soporte 12) = $30.27 MXN/mes
  Costo unitario del hardware                                  = $532 MXN
  Tarifa de horas del equipo (la misma del ejemplo de ciclos)  = $80 MXN/h

SUPUESTOS DEL EJEMPLO
  Precio de suscripción: $199 MXN/mes (dentro del rango de la semana 7:
    piso $119, techo $375; decisión del equipo, se valida con la landing)
  Cierre de ventas: 1 de cada 4 demos
  Cada demo, con traslado: 2.5 h
  Viáticos y muestras por cliente cerrado: $300
  Churn mensual: 8%

CÁLCULO
  Contribución mensual = 199 − 30.27                  = $168.73
  CAC = 4 demos × 2.5 h × $80 + $300                  = $1,100
  Inversión por cliente = 1,100 + 532                 = $1,632
  Vida media = 1 ÷ 0.08                               = 12.5 meses
  LTV = 168.73 × 12.5                                 = $2,109
  LTV ÷ inversión = 2,109 ÷ 1,632                     = 1.29
  Payback = 1,632 ÷ 168.73                            = 9.7 meses
```

**Lectura:** el payback de 9.7 meses está por debajo de los 12, pero la relación LTV/inversión de 1.29 está muy lejos del 3. El modelo, con estos supuestos, **no cierra**. Eso no es un fracaso: es exactamente la información que se quiere tener antes de fabricar. Ahora se buscan las palancas.

**Qué palanca mueve más:** cada insumo se cambia 25% por separado, manteniendo los demás.

| Cambio de 25% | LTV ÷ inversión |
|---------------|:---------------:|
| Caso base | 1.29 |
| Precio sube a $249 | 1.67 |
| Precio baja a $149 | 0.91 |
| Churn baja de 8% a 6% | 1.72 |
| Churn sube de 8% a 10% | 1.03 |
| CAC baja a $825 | 1.55 |
| CAC sube a $1,375 | 1.11 |

El precio es la palanca que más mueve el resultado, seguida del churn y luego del CAC. Pero el precio también es la que más fricción genera con el cliente: se valida con la landing, no se asume.

**Dos palancas combinadas, ambas con lógica de negocio:**

```
Escenario con referidos: los productores confían en otros productores,
  así que el cierre sube a 1 de cada 2 demos y bajan los viáticos.
  CAC = 2 demos × 2.5 h × $80 + $200 = $600
  Inversión = 600 + 532 = $1,132

Escenario con menos deserción: onboarding y valor que se acumula
  (historial, recomendaciones que mejoran). Churn de 8% a 5%.
  Vida media = 20 meses; LTV = 168.73 × 20 = $3,375

Resultados:
                                   LTV ÷ inversión    Payback
  Caso base                              1.29         9.7 meses
  Solo menos churn (5%)                  2.07         9.7 meses
  Solo referidos (CAC $600)              1.86         6.7 meses
  Referidos + menos churn                2.98         6.7 meses
```

> *"Con las dos palancas llegan a 3. Pero fíjense en lo que acaban de hacer: no ajustaron los números hasta que salieran bien. Identificaron qué tendría que ser verdad en el mundo real para que el negocio cierre, y eso es lo que van a ir a medir en el piloto."*

**Los equipos ejecutan el Prompt 3 con sus propios datos de la semana 7 (7 min).**

### Prompt 3 — Claude: economía unitaria de lanzamiento (se ejecuta en clase)

```
Actúa como analista financiero de startups de hardware con
suscripción. Calculas con los números que te dan, muestras la
aritmética completa y no completas datos faltantes con supuestos
propios: si falta uno, lo pides. Cuando el resultado no cierra,
no lo suavizas.

Datos de nuestro modelo (semana 7):
Precio de suscripción mensual: $[MXN]
Costo operativo mensual por usuario (nube, IA, soporte): $[MXN]
Costo unitario del hardware (subsidiado, se recupera con la
  suscripción): $[MXN]

Datos de adquisición (indica cuáles son medidos y cuáles supuestos):
Demos por cliente cerrado: [N]
Horas por demo, traslado incluido, y costo por hora: [h] y $[MXN]
Viáticos, muestras y otros por cliente cerrado: $[MXN]
Churn mensual esperado: [%]

Calcula: CAC, contribución mensual, vida media (1 ÷ churn), LTV,
inversión por cliente (CAC + hardware), LTV ÷ inversión y payback
en meses.
Después: si cumple la regla práctica (LTV ÷ inversión de 3 o más y
payback menor a 12 meses); cuál de los tres insumos (precio,
churn, CAC) mueve más el resultado, cambiando cada uno 25% por
separado; y tres palancas concretas con su efecto numérico.
Formato: tabla de cálculo y después máximo 8 líneas de lectura.
```

### La landing y el contenido de lanzamiento

La landing es el prototipo de negocio hecho visible. Su trabajo es uno: convertir a un visitante del segmento en un contacto con nombre. Se construye en las semanas de trabajo; hoy se define qué debe tener.

**Anatomía de una landing que convierte:**

1. **Headline:** la propuesta de valor de la semana 4, en una oración, sin describir el producto.
2. **Visual principal:** el producto en su contexto de uso real (el que salió del concepto de la semana 6).
3. **Tres beneficios:** resultados para el usuario, no características técnicas.
4. **Demo corta:** un video de 30 segundos del producto funcionando.
5. **Evidencia:** una cita real de las pruebas o una cifra de las entrevistas.
6. **Precio visible.**
7. **Un solo CTA:** pre-registro o interés. Una página, una acción.

**Publicación y presencia mínima:**
- Publicada en internet real: GitHub Pages (que el grupo ya usa), Netlify o Vercel. No localhost.
- Metadatos: título, descripción y Open Graph para que se vea bien al compartirla por WhatsApp o redes.
- Qué se mide: visitas, clics en el CTA y pre-registros. Esos tres números son el embudo de la demanda.

**Tres publicaciones que todo producto de hardware debe hacer al lanzar:**
1. **El problema:** una historia real de un usuario, con su cita textual.
2. **El producto en uso:** el video de 30 segundos de la instalación.
3. **Cómo se construye:** una mirada al proceso del equipo (prototipos, pruebas, fallas).

---

## Bloque 4 — Regulación mínima viable


El objetivo no es que el equipo sea experto en regulación. Es que sepan que existe, dónde buscar y tengan una ruta cuando llegue el momento de vender.

!!! warning "Verificar siempre contra la fuente vigente"
    Dos marcos cambiaron en 2025 y cualquier plantilla o artículo anterior puede estar desactualizado. La Ley Federal de Protección de Datos Personales en Posesión de los Particulares se reemplazó con una ley nueva, en vigor desde el 21 de marzo de 2025, y la autoridad ya no es el INAI sino la Secretaría Anticorrupción y Buen Gobierno. Y la autoridad de telecomunicaciones que homologa los equipos con radio está en transición del IFT a la Comisión Reguladora de Telecomunicaciones (CRT). Por eso este bloque enseña a verificar, no a memorizar cifras.

| Tema | La pregunta que el equipo responde | Dónde verificar |
|------|------------------------------------|-----------------|
| **Radio y homologación** | ¿El producto usa WiFi, Bluetooth, LoRa o celular? ¿Los módulos ya traen certificado de homologación? | Autoridad de telecomunicaciones (CRT) y organismos de certificación como ANCE o NYCE |
| **Datos personales** | ¿La app recolecta contacto, ubicación, uso o imágenes? ¿Hay aviso de privacidad vigente? | Ley Federal de Protección de Datos Personales en Posesión de los Particulares (2025), Secretaría Anticorrupción y Buen Gobierno |
| **Seguridad y etiquetado** | ¿Qué NOM aplican al producto, a su batería y a su etiqueta? | Directorio de normas oficiales mexicanas, organismos de certificación |
| **Licencias de software y modelos de IA** | ¿Qué licencia tiene cada dependencia y cada modelo? ¿Permiten uso comercial? | Archivo de licencia de cada repositorio o modelo; términos de uso de cada API |
| **Términos de venta y consumidor** | ¿Hay términos de servicio, garantía y política de devolución? | Ley Federal de Protección al Consumidor, PROFECO |
| **Economía circular** | ¿Qué dice la REP sobre el fin de vida del producto? | Ley General de Economía Circular (semana 8) |
| **Exportación, si aplica** | ¿Vamos a vender en EE. UU. o Europa? | Requisitos FCC (EE. UU.) y marcado CE (Unión Europea) |
| **Marca** | ¿La marca está registrada o en trámite? | IMPI (semana 3) |

> *"Un módulo de radio con certificado facilita el trámite del producto final, pero no lo sustituye. Antes de vender a un tercero, confirmen con un organismo de certificación qué se necesita para su producto completo."*

### Prompt 4 — Claude: checklist regulatorio (se ejecuta en casa)

```
Actúa como asesor regulatorio de productos electrónicos
conectados para venta en México, con enfoque práctico para
emprendedores de primera iteración. No eres abogado y no emites
dictámenes: das una ruta de verificación. Regla central: usa
búsqueda web en fuentes oficiales (DOF, autoridad de
telecomunicaciones, Secretaría Anticorrupción y Buen Gobierno,
organismos de certificación) y marca cada afirmación como
VERIFICADO (con enlace) o POR VERIFICAR. El marco de datos
personales y la autoridad de telecomunicaciones cambiaron en
2025: desconfía de plantillas y artículos anteriores.

Nuestro producto: [qué es y qué hace]
Radios que usa: [WiFi / BLE / LoRa / celular / ninguno] y si los
  módulos ya están certificados: [sí o no, cuáles]
Datos que recolecta la app: [contacto, ubicación, uso, imágenes]
Modelo de IA: [API de terceros o modelo abierto, cuál]
Alimentación: [tipo de batería o red eléctrica]
Dónde venderemos primero: [México u otros]

Entrega una tabla con una fila por tema (radio y homologación,
datos personales, seguridad y etiquetado, baterías, licencias de
software y del modelo de IA, términos de venta y consumidor,
economía circular, exportación si aplica) con: ¿aplica?, qué
exige, qué documento o trámite resulta, quién lo emite, costo y
tiempo si hay fuente (si no la hay, escribe "sin dato
verificado") y estatus VERIFICADO o POR VERIFICAR.
Cierra con dos listas: qué se puede hacer durante una prueba de
mercado de 5 a 10 unidades y qué debe estar resuelto antes de
vender a un tercero. Si no tienes fuente para separar ambas
listas, dilo.
```

---

## Bloque 5 — El pitch de 3 minutos

### Qué tiene que lograr un pitch de 3 minutos

Cada equipo tiene **15 minutos** en la evaluación: 3 de pitch, 7 de demostración y 5 de retroalimentación. Eso define el trabajo del pitch: **no demuestra, vende.** La demostración ocupa sus propios 7 minutos; el pitch solo la anuncia.

Un jurado que escucha 8 pitches seguidos no recuerda datos, recuerda una imagen y una frase. Por eso el pitch persigue cuatro efectos, uno por tramo:

| El jurado debe... | Lo logra la parte | Cómo |
|-------------------|-------------------|------|
| **Sentir** el problema | Impacto y problema | Una persona concreta y lo que le cuesta, en pesos |
| **Querer** el producto | Solución y por qué nosotros | Una promesa simple y el contraste con lo que el usuario usa hoy |
| **Creer** los números | Mercado y modelo, tracción | Cifras con origen y una evidencia que no sea opinión |
| **Saber qué hacer** | Ask y cierre | Una petición concreta y la promesa repetida |

**Presupuesto de tiempo y de palabras.** Se habla a unas 130 palabras por minuto, así que 180 segundos son 390 palabras como tope absoluto. El guion apunta a 330 o 360 palabras: el resto es aire para pausas y énfasis. Sin aire, el pitch suena a lectura.

| Parte | Tiempo | Tope de palabras |
|-------|:------:|:----------------:|
| Impacto y problema | 35 s | 76 |
| Solución y por qué nosotros | 35 s | 76 |
| Mercado y modelo | 35 s | 76 |
| Tracción | 35 s | 76 |
| Equipo | 15 s | 32 |
| Ask y cierre | 25 s | 54 |
| **Total** | **180 s** | **390** |

**Reglas para que venda:**

1. **Abre con una persona y un costo.** Nunca con una definición ni con "somos una startup que".
2. **Habla en el idioma del usuario:** pesos, horas, riesgo evitado. Las especificaciones técnicas se quedan para la demostración.
3. **Una cifra por frase, y cada cifra con origen.** Si no se puede rastrear a un documento del semestre, no se dice.
4. **Contrasta con la alternativa de hoy.** El jurado necesita saber por qué ustedes y no lo que el usuario ya usa.
5. **Una sola confesión honesta.** Mostrar el dato que todavía no cierra da credibilidad; mostrar dos la resta.
6. **Anuncia la demostración, no la hagas.** "En la demostración lo verán" cabe en una frase.
7. **Cierra repitiendo la promesa** en una oración que el jurado pueda repetir al salir.
8. **Palabras prohibidas:** innovador, plataforma, solución integral, revolucionario.

**Ejemplo completo: el sensor agrícola.** Las cifras de entrevistas, pruebas y pre-registros, y la cita, son **ilustrativas del ejemplo, no datos reales**. El resto viene de las semanas 4, 7 y de la economía unitaria de hoy.

> **1. Impacto y problema.** *Don Aurelio cultiva jitomate en invernadero cerca de Tehuacán. Cada mañana camina entre las camas y toca la tierra para decidir si riega. Cuando la planta se ve seca, el daño ya está hecho: pierde entre 10 y 20 por ciento de cada ciclo, de 8 mil a 50 mil pesos que no recupera. Y un agrónomo cobra entre 2 mil y 5 mil pesos por visita.*
>
> **2. Solución y por qué nosotros.** *Nuestro sensor es una estaca de 22 centímetros. Se clava en la tierra y un anillo de luz le dice a Don Aurelio, sin abrir el teléfono, si hoy toca regar. Los sistemas industriales le dan gráficas que no usa; el nuestro le da una decisión. Si evita una sola pérdida, aun la más pequeña, ya pagó más de tres años de suscripción. En la demostración lo verán reaccionar en vivo.*
>
> **3. Mercado y modelo.** *En México hay 285 mil productores con este problema y disposición de pago; 115 mil están donde podemos operar. Entregamos el sensor sin enganche: asumimos sus 532 pesos de costo y los recuperamos con una suscripción de 199 pesos al mes. Después de nube, inteligencia artificial y soporte, cada cliente nos deja 169 pesos mensuales. Con 2 mil clientes en dos años son 4.8 millones de pesos al año.*
>
> **4. Tracción.** *Entrevistamos a 9 productores y probamos el sistema completo con 7. Cinco lo instalaron solos en menos de 5 minutos y cuatro dejaron nombre y teléfono para el piloto. Uno nos dijo: "por fin dejo de adivinar". Nuestra economía por cliente hoy es de 1.3 contra una meta de 3, y sabemos qué la mueve: referidos entre productores y menos deserción.*
>
> **5. Equipo.** *Somos cuatro ingenieros mecatrónicos: hardware y firmware, aplicación y negocio. Construimos, probamos y calculamos todo esto, y seguimos después del curso.*
>
> **6. Ask y cierre.** *Pedimos acceso a tres agrotiendas de Tehuacán para un piloto de 20 clientes durante un ciclo. En 90 días medimos lo único que nos falta saber: cuánto cuesta conseguir un cliente y cuántos se quedan. Don Aurelio no necesita más datos. Necesita saber cuándo regar.*

| Parte | Palabras | Segundos hablados | Presupuesto |
|-------|:--------:|:-----------------:|:-----------:|
| 1. Impacto y problema | 67 | 30.9 | 35 s |
| 2. Solución y por qué nosotros | 71 | 32.8 | 35 s |
| 3. Mercado y modelo | 69 | 31.8 | 35 s |
| 4. Tracción | 61 | 28.2 | 35 s |
| 5. Equipo | 21 | 9.7 | 15 s |
| 6. Ask y cierre | 45 | 20.8 | 25 s |
| **Total** | **334** | **154.2 (2:34)** | **180 s** |

Quedan 26 segundos de aire para pausas, que es donde ocurre el efecto.

**Qué hace que este pitch venda:**
- **Impacto:** abre con una persona y una pérdida en pesos, y cierra con la misma persona.
- **Contraste:** "gráficas que no usa" frente a "una decisión" responde por qué ellos y no el sistema industrial.
- **Retorno para el cliente:** la cuenta de más de tres años de suscripción por una sola pérdida evitada (8,000 ÷ 2,388 = 3.35) hace que el precio parezca barato.
- **Honestidad que da credibilidad:** admite que la economía por cliente hoy es de 1.3 contra 3 y nombra qué la mueve.
- **Ask medible:** no pide "apoyo", pide tres agrotiendas y dice qué va a medir en 90 días.

### 1:28 – 1:32 · Prompt 5 en clase

### Prompt 5 — Claude: guion de pitch de 3 minutos (se ejecuta en clase)

```
Actúa como coach de pitch para fundadores técnicos, con
experiencia en jurados de aceleradoras de hardware. Tu objetivo
es que el pitch venda: que el jurado sienta el problema, quiera
el producto, crea los números y sepa qué se le pide. Cada
afirmación tiene evidencia detrás; sin evidencia no hay
afirmación, hay un pendiente. Prefieres una persona o una cifra a
un adjetivo.

Nuestro material:
Propuesta de valor (semana 4): [Versión 3]
Usuario y evidencia de entrevistas (semanas 3 y 4): [resumen y
  2 citas textuales]
Mercado TAM, SAM, SOM (semana 4): [cifras con fuente]
Modelo, precio y economía unitaria (semanas 7 y 9): [precio,
  costo, LTV ÷ inversión, payback]
Evidencia de pruebas y pre-registros (semanas 8 y 9): [cifras
  reales o "ninguna todavía"]
Equipo: [quién hace qué]
Ask: [qué piden, a quién y qué medirán con eso]

Escribe el guion de 3 minutos hablados con este presupuesto:
impacto y problema (35 s), solución y por qué nosotros (35 s),
mercado y modelo (35 s), tracción (35 s), equipo (15 s), ask y
cierre (25 s). A 130 palabras por minuto, los topes son 76, 76,
76, 76, 32 y 54 palabras; el total debe quedar entre 330 y 360.
Reglas: la primera frase es una persona concreta y lo que le
cuesta en pesos, horas o riesgo; contrasta con lo que el usuario
usa hoy; anuncia la demostración sin describirla (tiene sus
propios 7 minutos); termina repitiendo la promesa en una frase
que el jurado pueda repetir; no uses innovador, plataforma,
solución integral ni revolucionario.
Después del guion entrega: (a) las afirmaciones que no tienen
evidencia en mi material, marcadas como PENDIENTE, y (b) las 5
preguntas más difíciles que haría un jurado y de qué parte de
nuestro material saldría la respuesta.
```

### 1:32 – 1:40 · Práctica en parejas

Cada equipo se junta con otro. Cada uno dice en voz alta las partes 1, 2 y 6 de su guion, unos 90 segundos, y el otro responde dos cosas: *"¿Qué entendí?"* y *"¿Qué no te creí?"*. Luego se invierten. Dos rondas de 4 minutos.

**Las preguntas difíciles de inversionista que el equipo debe poder responder** (cada una apunta a un documento que ya existe):

| Pregunta | Dónde está la respuesta |
|----------|-------------------------|
| ¿Cuánto cuesta fabricar una unidad y cómo lo sabes? | BOM y revisión DFM (semanas 7 y 8) |
| ¿Por qué no lo hace [competidor]? | Mapa competitivo y lienzo Blue Ocean (semana 4) |
| ¿Qué pasa si sube el precio de la API de IA? | Costo de IA y decisión edge/cloud (semanas 5 y 7) |
| ¿Cuántos clientes necesitas para no perder dinero? | Punto de equilibrio (semana 7) |
| ¿Qué necesitas para vender legalmente? | Checklist regulatorio (esta semana) |
| ¿Qué hace que un cliente no cancele? | Churn y palancas (esta semana) |

!!! note "El video propio es el mejor profesor"
    Cada equipo graba su pitch en video durante las semanas de trabajo y lo ve. Nadie más le va a decir que habla demasiado rápido, que mira al piso o que se pierde en la parte de mercado.

---

## Bloque 6 — La demo de 7 minutos
**Duración: 10 min · Min 1:40 – 1:50**

### 1:40 – 1:44 · Para qué sirve y qué mira el jurado

La demo no es un recorrido por funciones. Es la prueba de que la promesa del pitch es verdad: el pitch dijo "hoy toca regar" y la demo muestra al sistema decidiéndolo con datos reales, sin que el equipo toque nada.

> *"El pitch es lo que dicen. La demo es lo que pasa. Si lo que pasa contradice lo que dicen, el jurado le cree a lo que pasa."*

El jurado mira tres cosas, que son los criterios de la rúbrica del curso:

| Componente | Lo que el jurado se pregunta | Peso en la rúbrica |
|------------|------------------------------|:------------------:|
| **Producto físico** | ¿Funciona? ¿Es robusto? ¿El uso de IA tiene un propósito real? | 30% |
| **App conectada** | ¿Conecta con el hardware? ¿Un externo la entiende sin explicación? | 25% |
| **Landing** | ¿Comunica la propuesta de valor? ¿Tiene CTA? ¿Está publicada? | 15% |

Los tres componentes caben en 7 minutos si la demo recorre **un solo camino**: la historia del usuario desde que instala el producto hasta que decide comprarlo.

### Estructura de los 7 minutos

| Tiempo | Tramo | Qué se ve | Qué prueba |
|--------|-------|-----------|------------|
| 0:00 – 0:45 | **Contexto** | El producto en la mano; una frase de quién lo usa y dónde | Que el jurado sabe qué va a ver |
| 0:45 – 3:15 | **Camino principal** | Instalación, primer dato, recomendación del sistema | Que el producto funciona sin que el equipo intervenga |
| 3:15 – 4:45 | **Provocar el evento** | Se cambia una condición real y el sistema reacciona | Que los datos son reales y la IA decide con ellos |
| 4:45 – 5:45 | **Fallo manejado** | Se corta la conexión; el sistema avisa y se recupera | Que el producto es robusto |
| 5:45 – 6:30 | **La compra** | El jurado abre la landing en su teléfono y ve el precio y el CTA | Que el producto se puede comprar |
| 6:30 – 7:00 | **Cierre** | Lo que funciona hoy, lo que falta y el siguiente paso | Que el equipo conoce sus límites |

### 1:44 – 1:48 · En qué deben centrarse

1. **Muestren el valor, no las funciones.** Narren desde el usuario ("Don Aurelio ve el anillo y sabe que toca regar"), no desde el producto ("el microcontrolador publica por MQTT"). La arquitectura se explica solo si el jurado pregunta.
2. **Provoquen el evento en vivo.** Un sistema que muestra datos grabados no prueba nada. Cambien una condición real delante del jurado (mojar la tierra, tapar el sensor, cambiar la temperatura) y que se vea causa y efecto en menos de un minuto.
3. **Hagan visible que la IA tiene un propósito.** Muestren la entrada (el dato del sensor), la decisión (la recomendación) y qué cambia en la decisión cuando cambia el dato. Si la recomendación sería la misma sin IA, el jurado lo nota.
4. **Muestren un fallo manejado.** Corten el WiFi 20 segundos o simulen la caída de la API de IA. Un sistema que degrada con un mensaje claro y se recupera solo impresiona más que uno que nunca falla, porque demuestra que se probó.
5. **Cierren con la compra.** Que el jurado escanee un QR, vea el precio y deje su pre-registro. Así la demo recorre los tres componentes y termina en la venta.
6. **Declaren cada atajo.** Si en campo el sensor mide cada 15 minutos y en la demo cada 5 segundos, se dice en voz alta. Lo simulado que se declara no resta; lo simulado que se descubre sí.

### Ejemplo: la demo del sensor agrícola

| Tiempo | Quién opera | Qué se hace y se dice | Plan B |
|--------|-------------|-----------------------|--------|
| 0:00 – 0:45 | Narrador | Sostiene la estaca. "Don Aurelio decide con la mano. Esto le dice cuándo regar. Les voy a mostrar el camino completo: instalar, medir, decidir y comprarlo." | Foto del producto instalado en campo |
| 0:45 – 3:15 | Operador | Clava la estaca en una maceta con tierra seca. El anillo se enciende. La app, proyectada, muestra la primera lectura en menos de 10 segundos y la recomendación: "hoy toca regar". Narrador: "en campo mide cada 15 minutos; hoy lo pusimos en 5 segundos para que lo vean". | Video de respaldo de este tramo, 90 segundos |
| 3:15 – 4:45 | Operador | Riega la maceta con un vaso de agua. En menos de 60 segundos (el requerimiento del PDS) la gráfica sube y el anillo cambia de "regar" a "no regar". Narrador explica por qué cambió la recomendación. | Datos de respaldo precargados y video |
| 4:45 – 5:45 | Operador | Apaga el hotspot 20 segundos. La app muestra "sin conexión, último dato hace 20 s" y no presenta el dato viejo como actual. Reactiva el hotspot: el sistema se recupera solo y no pierde lecturas. | Video de la prueba T3 |
| 5:45 – 6:30 | Narrador | Muestra un QR. El jurado abre la landing en su teléfono: headline, precio de 199 pesos al mes y CTA. Un integrante hace un pre-registro y se ve entrar a la hoja de cálculo. | Captura de la landing y de la hoja de registros |
| 6:30 – 7:00 | Narrador | "Hoy funciona esto. Falta esto: [limitación conocida]. Siguiente paso: el piloto de 20 productores." | Ninguno: es solo voz |

**Cómo se ensaya:**
- **Tres ensayos completos con cronómetro**, en el espacio de la evaluación o uno equivalente. El tercero, sin ayuda del instructor y sin detenerse si algo falla.
- **Dos roles:** un narrador que habla y un operador que manipula. Una sola persona no puede hacer las dos cosas bien.
- **Un plan B por cada tramo**, grabado un día antes: video de respaldo del camino principal, hotspot propio del teléfono y datos precargados. El salón puede no tener internet.

**Lista de verificación 15 minutos antes:**
1. Baterías cargadas y cable de respaldo.
2. Firmware congelado, con la versión anotada.
3. Datos de prueba limpios.
4. Hotspot del teléfono probado.
5. App instalada, con la sesión iniciada.
6. Landing abierta en una pestaña y QR impreso.
7. Videos de respaldo en el teléfono y en la laptop.
8. Entorno de prueba preparado (maceta con tierra seca, vaso de agua).
9. Proyección probada y cronómetro visible.

**Lo que no se hace:** depender del WiFi del salón, configurar en vivo, cambiar firmware el día de la evaluación, abrir código sin que lo pidan, pedir disculpas por lo que no se ve o llenar tiempo con funciones secundarias.

### 1:48 – 1:50 · Cada equipo anota el guion de su demo

Los equipos copian la tabla del ejemplo y la llenan con su producto: qué evento van a provocar, qué fallo van a mostrar, quién opera y cuál es el plan B de cada tramo. El guion de demo es un entregable de esta clase.

---

## Bloque 7 — Ruta de cierre
**Duración: 10 min · Min 1:50 – 2:00**

### La evaluación final y el plan hacia atrás

La clase de evaluación dura **15 minutos por equipo**: 3 de pitch, 7 de demostración del sistema en vivo (sensor, app y pantalla, sin falla) y 5 de retroalimentación del panel. Todo lo que el equipo haga en las dos semanas de trabajo apunta a esos 15 minutos y a la **página de proyecto final**, la memoria que respalda con evidencia lo que el panel ve.

```
SEMANA DE TRABAJO A: construir y conectar
  · App funcionando y conectada al dispositivo (Prompt 6)
  · Landing publicada en internet (Prompt 6)
  · Pruebas T1 a T3 aprobadas (Prompt 1)
  · Checklist regulatorio entregado (Prompt 4)
  · Secciones 1 a 16 de la página de proyecto final al día
  Punto de control: el dato fluye del sensor a la pantalla sin intervención

SEMANA DE TRABAJO B: probar, corregir y contar
  · Cinco pruebas de usuario, dos de ellas cruzadas entre equipos (Prompt 2)
  · Pruebas T4 a T6 y correcciones críticas
  · Pitch grabado en video, visto y reescrito (Prompt 5)
  · Demo ensayada tres veces con cronómetro y video de respaldo grabado
  · Documentación final: README, diagrama de arquitectura actualizado,
    manual de usuario básico
  · Secciones 17 a 22 de la página de proyecto final, resumen ejecutivo
    y anexos
  Congelamiento: a partir del último ensayo solo se corrigen bugs críticos
```

**Reglas del trabajo:**
- El repositorio de GitHub lleva un README y al menos un commit por sesión de trabajo. Evidencia el proceso iterativo y previene el "todo lo hice la noche anterior".
- Los pares de revisión cruzada los asigna el instructor, de modo que equipos con temáticas similares se prueben entre sí.
- Los equipos que se atoren en una frontera la documentan y piden asesoría con el registro en la mano, no con "no funciona".
- La página de proyecto final se publica en el sitio del equipo. Su índice, lo que se revisa en cada sección y cómo se conecta con la rúbrica están en la guía del proyecto final.

### Prompt 6 — Claude: genera los prompts para construir la app y la landing (se ejecuta en casa)

El equipo ya sabe programar; lo que cambia es dirigir a un modelo de código para que construya por ellos. Claude no escribe la app: escribe los prompts que hacen que v0, Cursor o Framer la construyan bien.

```
Actúa como arquitecto de software que guía a un equipo en
vibe coding. Tu trabajo no es escribir la app, es escribir los
prompts que hacen que un LLM de código (v0, Cursor) la
construya bien. Un buen prompt de construcción define: objetivo
de la pantalla o módulo, datos reales con su formato, estados
(cargando, normal, alerta, sin conexión, error), restricciones
técnicas y qué NO debe hacer. Prefieres iteraciones pequeñas,
cada una verificable antes de la siguiente.

Nuestro producto: [nombre y qué hace]
Arquitectura (semana 5): [protocolo y backend elegidos]
Formato real del dato que manda el dispositivo: [un ejemplo de
  JSON o de mensaje MQTT]
Wireframe de la app y concepto de landing (semana 6): [pantalla
  principal, estado de alerta, flujo de instalación; headline,
  visual y CTA de la landing]
Lo que el equipo domina: [lenguajes y herramientas]
Propuesta de valor y precio: [Versión 3 y precio]

Entrega:
A) APP: una secuencia de 5 a 7 prompts de construcción en el
   orden en que deben ejecutarse. El primero produce la pantalla
   principal con datos simulados; el último conecta con el
   dispositivo real. Cada prompt trae el criterio para saber que
   quedó bien antes de pasar al siguiente.
B) LANDING: un prompt para v0 o Framer con las secciones en
   orden, el texto de cada sección (usa nuestra propuesta de
   valor, no la reescribas), el CTA único y los metadatos (title,
   description, Open Graph).
C) Los 5 errores más comunes al hacer vibe coding de una app que
   habla con hardware y cómo evitarlos en nuestro caso.
```

---

## Entregables de esta clase y de las semanas de trabajo

**Al cierre de la clase (en digital):**

| Entregable | Se produce con |
|------------|----------------|
| Economía unitaria con los números propios | Prompt 3 |
| Esqueleto del pitch de 3 minutos con pendientes marcados | Prompt 5 |
| Guion de la demo de 7 minutos con plan B por tramo | Bloque 6 |
| Ruta de las dos semanas con responsables | Bloque 7 |

**Antes de la evaluación final:**

| Entregable | Referencia |
|------------|-----------|
| Sistema integrado funcionando: sensor, app y pantalla, sin falla | Bloque 1, pruebas T1 a T6 |
| Reporte de pruebas de usuario con cinco sesiones | Bloque 2, Prompt 2 |
| Landing publicada y accesible en internet | Bloque 3, Prompt 6 |
| Checklist regulatorio con estatus VERIFICADO o POR VERIFICAR | Bloque 4, Prompt 4 |
| Pitch de 3 minutos ensayado y grabado en video | Bloque 5, Prompt 5 |
| Demo de 7 minutos ensayada tres veces, con video de respaldo | Bloque 6 |
| Página de proyecto final publicada en el sitio del equipo | Guía del proyecto final |
| Repositorio con README y commits por sesión de trabajo | Bloque 7 |
| Documentación técnica: diagrama de arquitectura actualizado y manual de usuario básico | Bloque 1 |

---

## Bibliografía y recursos de la semana

### Lecturas obligatorias

Ulrich, K. T., Eppinger, S. D., & Yang, M. C. (2026). *Product Design and Development* (7.ª ed.). McGraw-Hill.
→ Capítulos de pruebas de producto y de economía del desarrollo. Complementa la lógica de pruebas y de decisión económica que se usa en esta clase.

IDEO U. *Business Design*. IDEO.
→ Secciones de canales y de modelo de ingresos y precio del Business Blueprint. Base del Bloque 3.

Cámara de Diputados del H. Congreso de la Unión. (2025). *Ley Federal de Protección de Datos Personales en Posesión de los Particulares*. Diario Oficial de la Federación, 20 de marzo de 2025.
→ Texto vigente, en vigor desde el 21 de marzo de 2025. Leer el apartado del aviso de privacidad antes de redactar el de la app.

### Lecturas recomendadas

Ries, E. (2011). *The Lean Startup*. Crown Business.
→ Producto mínimo viable, aprendizaje validado y pivote. Marco de fondo de todo el semestre.

Moore, G. (1991). *Crossing the Chasm*. HarperBusiness.
→ El origen del concepto de early adopters y por qué el lanzamiento empieza con un grupo pequeño.

Fitzpatrick, R. (2013). *The Mom Test*. CreateSpace.
→ Cómo hacer preguntas que producen evidencia y no cortesía. Directamente aplicable al protocolo de pruebas de usuario.

Krug, S. (2010). *Rocket Surgery Made Easy*. New Riders.
→ Guía práctica para hacer pruebas de usabilidad sin laboratorio y sin presupuesto.

Nielsen, J. (2000). Why You Only Need to Test with 5 Users. Nielsen Norman Group.
→ La base de la regla de cinco usuarios. Artículo corto, disponible en línea.

Skok, D. SaaS Metrics 2.0. For Entrepreneurs.
→ CAC, LTV, churn y payback explicados con la lógica de suscripción. Útil para entender la regla práctica de 3 a 1.

Kawasaki, G. (2015). *The Art of the Start 2.0*. Portfolio.
→ Estructura y disciplina del pitch.

### Herramientas de la semana

| Herramienta | Uso | Acceso |
|-------------|-----|--------|
| **v0 (Vercel)** | Generar la interfaz de la app y la landing desde un prompt | v0.dev |
| **Cursor** | Construir la lógica de la app y la conexión con el dispositivo | cursor.com |
| **Framer** | Alternativa para construir la landing | framer.com |
| **GitHub Pages, Netlify o Vercel** | Publicar la landing en internet | github.com, netlify.com, vercel.com |
| **Google Forms o Tally** | Formulario de pre-registro de la landing | forms.google.com, tally.so |
| **Cámara del teléfono** | Grabar las sesiones de prueba (con consentimiento) y el pitch | |

---

## Lo que el equipo debe poder responder al salir

- [ ] ¿En cuál de las cuatro fronteras de su sistema es más probable que falle, y qué registro pondrán ahí?
- [ ] ¿Cuál es su CAC, su LTV y su relación LTV ÷ inversión, y qué palanca mueve más el resultado?
- [ ] ¿Cuál de los temas regulatorios puede impedirles vender a un tercero y qué fuente oficial lo confirma?
- [ ] ¿Qué evidencia tienen para cada una de las seis partes de su pitch y cuáles son pendientes?
- [ ] ¿Cuál es el camino principal de su demo de 7 minutos, qué evento provocan en vivo y cuál es su plan B?


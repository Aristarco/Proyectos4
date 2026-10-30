# Semana 9 — Integración, go-to-market y pitch

!!! abstract "Blueprint IDEO: Entrega y captura de valor · DVF: 🟢 Factible · 🟡 Viable · 🔴 Deseable"
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
**Duración: 20 min · Min 0:00 – 0:20**

### 0:00 – 0:05 · Las fallas viven en las fronteras


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

### 0:12 – 0:20 · Pruebas mínimas y definición de listo

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
**Duración: 15 min · Min 0:20 – 0:35**

### 0:20 – 0:25 · Qué se prueba y con quién

En la semana 8 el equipo probó un supuesto con un prototipo. Ahora prueba **el sistema completo** con alguien que nunca lo ha visto. La diferencia importa: ya no se pregunta si una idea tiene sentido, se pregunta si el producto funciona en manos de otra persona.

**Con quién:** cinco personas. Con cinco usuarios aparece la mayoría de los problemas de usabilidad (regla de Nielsen); más usuarios repiten lo mismo. De esas cinco, tres deben ser del segmento objetivo. Las otras dos pueden ser integrantes de otro equipo: **cada equipo es el usuario externo de otro**. Eso cumple la función de revisión entre pares sin gastar una clase.

### 0:25 – 0:32 · El protocolo de 30 minutos

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

### 0:32 – 0:35 · Severidad y síntesis

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
**Duración: 35 min · Min 0:35 – 1:10**

### 0:35 – 0:40 · Early adopters: los primeros 20

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


### 1:20 – 1:30 · Estructura y de dónde sale cada parte

El pitch no explica el producto: convence a un desconocido de que el problema es real, de que la solución funciona y de que este equipo puede llevarla al mercado. Seis partes en 180 segundos, y cada una se sostiene con evidencia que el equipo ya construyó:

| Parte | Tiempo | Qué debe lograr | De dónde sale la evidencia |
|-------|:------:|-----------------|----------------------------|
| **Problema** | 35 s | Que el jurado sienta el problema con una persona concreta | Entrevistas y perfil del segmento (semanas 3 y 4) |
| **Solución** | 40 s | Que vea el producto funcionando | Prototipo y concepto (semanas 6 y 8), demo en vivo |
| **Mercado y modelo** | 35 s | Que el negocio sea lo bastante grande y tenga sentido | TAM, SAM, SOM (semana 4), precio y costos (semana 7) |
| **Tracción** | 35 s | Que haya evidencia de que alguien lo quiere | Pruebas de usuario y pre-registros (esta semana) |
| **Equipo** | 15 s | Que sean quienes pueden hacerlo | Quién hace qué |
| **Ask** | 20 s | Que el jurado sepa qué se les pide | La necesidad más urgente del plan |

**Reglas del pitch:**
- La primera frase del problema es una persona o una cifra, nunca una definición.
- La demo se cuenta como una acción visible ("clava la estaca, se enciende el anillo"), no como lista de funciones.
- Una cifra verificable vale más que un adjetivo.
- Si algo no tiene evidencia, no se afirma: se dice que es lo que van a medir.
- Palabras prohibidas: innovador, plataforma, solución integral, revolucionario.

**Ejemplo completo: el sensor agrícola.** El guion tiene 311 palabras, unos 2 minutos 24 segundos hablados a 130 palabras por minuto. Los 36 segundos restantes son la demo visible y las pausas. Las cifras de entrevistas, pruebas y pre-registros son **ilustrativas del ejemplo, no datos reales**; el resto viene de las semanas 4, 7 y de la economía unitaria de hoy.

> **Problema.** *Don Aurelio tiene 2 hectáreas de jitomate en invernadero cerca de Tehuacán. Cada mañana camina entre las camas y mete la mano a la tierra para decidir si riega. Cuando la planta ya se ve seca, el daño está hecho: un mal manejo del riego le cuesta entre 10 y 20 por ciento del ciclo, de 8 mil a 50 mil pesos. Y un agrónomo cobra entre 2 mil y 5 mil pesos por visita.*
>
> **Solución.** *Nuestro sensor es una estaca de 22 centímetros que se clava en la tierra. Un anillo de luz le dice a Don Aurelio, sin abrir el teléfono, si hoy toca regar. Si quiere saber cuánto y por qué, la app se lo explica en lenguaje de campo, con base en el cultivo y la etapa del ciclo.*
>
> **Mercado y modelo.** *En México hay unos 285 mil productores con este problema y disposición de pago; 115 mil están en estados donde podemos operar con nuestro modelo. Entregamos el sensor sin enganche y cobramos 199 pesos al mes. Después de nube, inteligencia artificial y soporte, cada cliente deja 169 pesos mensuales. Con 2 mil clientes en dos años son 4.8 millones de pesos al año.*
>
> **Tracción.** *Entrevistamos a 9 productores y probamos el sistema completo con 7. Cinco lo instalaron solos en menos de 5 minutos y cuatro se registraron para el piloto con nombre y teléfono. Un dato honesto: hoy nuestra economía por cliente es de 1.3 a 1; con referidos entre productores y menos deserción llega a 3.*
>
> **Equipo.** *Somos cuatro ingenieros mecatrónicos: dos de hardware y firmware, uno de aplicación y uno de negocio. Construimos, probamos y calculamos todo lo que acaban de ver.*
>
> **Ask.** *Pedimos acceso a tres agrotiendas de Tehuacán para un piloto de 20 clientes durante un ciclo. Con eso medimos lo único que nos falta saber: el costo real de adquirir un cliente y cuántos se quedan.*

**Qué hace bien este pitch:** nombra a una persona, usa cifras que se pueden rastrear a un documento, muestra la economía unitaria sin esconder que todavía no cierra, y su ask nace de lo que falta medir, no de un deseo vago.

### Prompt 5 en clase

### Prompt 5 — Claude: guion de pitch (se ejecuta en clase)

```
Actúa como coach de pitch para fundadores técnicos, con
experiencia en jurados de aceleradoras de hardware. Tu estándar:
cada afirmación tiene una evidencia detrás; sin evidencia no hay
afirmación, hay un pendiente. Prefieres una cifra verificable a un
adjetivo. El pitch dura 180 segundos y se habla a unas 130
palabras por minuto.

Nuestro material:
Propuesta de valor (semana 4): [Versión 3]
Segmento y evidencia de entrevistas (semanas 3 y 4): [resumen y
  2 citas textuales]
Mercado TAM, SAM, SOM (semana 4): [cifras con fuente]
Modelo, precio y economía unitaria (semanas 7 y 9): [precio,
  costo, LTV ÷ inversión, payback]
Evidencia de pruebas (semanas 8 y 9): [tasa de éxito, tiempos,
  SEQ, citas]
Señal de mercado (pre-registros, pilotos): [cifras reales o
  "ninguna todavía"]
Equipo: [quién hace qué]
Ask: [qué piden y a quién]

Escribe el guion con esta estructura y presupuesto de tiempo:
problema (35 s), solución con demo (40 s), mercado y modelo
(35 s), tracción (35 s), equipo (15 s) y ask (20 s).
Reglas: máximo 390 palabras en total; la primera frase del
problema es una persona concreta o una cifra, no una definición;
la demo se describe como acción visible; no uses innovador,
plataforma, solución integral ni revolucionario.
Después del guion entrega: (a) las afirmaciones que no tienen
evidencia en mi material, marcadas como PENDIENTE, y (b) las 5
preguntas más difíciles que haría un jurado y de qué parte de
nuestro material saldría la respuesta.
```

### 1:35 – 1:45 · Práctica en parejas

Cada equipo se junta con otro. Cada uno dice su **versión de 90 segundos** (problema, solución y ask) y el otro responde una sola cosa: *"¿Qué entendí y qué no te creí?"*. Luego se invierten. Dos rondas de 5 minutos.

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

## Bloque 6 — Ruta de cierre
**Duración: 15 min · Min 1:45 – 2:00**

### La evaluación final y el plan hacia atrás

La clase de evaluación dura **13 minutos por equipo**: 5 de demostración del sistema en vivo (sensor, app, pantalla, sin falla), 3 de pitch y 5 de preguntas del panel. Todo lo que el equipo haga en las dos semanas de trabajo apunta a esos 13 minutos.

```
SEMANA DE TRABAJO A: construir y conectar
  · App funcionando y conectada al dispositivo (Prompt 6)
  · Landing publicada en internet (Prompt 6)
  · Pruebas T1 a T3 aprobadas (Prompt 1)
  · Checklist regulatorio entregado (Prompt 4)
  Punto de control: el dato fluye del sensor a la pantalla sin intervención

SEMANA DE TRABAJO B: probar, corregir y contar
  · Cinco pruebas de usuario, dos de ellas cruzadas entre equipos (Prompt 2)
  · Pruebas T4 a T6 y correcciones críticas
  · Pitch grabado en video, visto y reescrito (Prompt 5)
  · Documentación final: README, diagrama de arquitectura actualizado,
    manual de usuario básico
  Congelamiento: a partir del último ensayo solo se corrigen bugs críticos
```

**Reglas del trabajo:**
- El repositorio de GitHub lleva un README y al menos un commit por sesión de trabajo. Evidencia el proceso iterativo y previene el "todo lo hice la noche anterior".
- Los pares de revisión cruzada los asigna el instructor, de modo que equipos con temáticas similares se prueben entre sí.
- Los equipos que se atoren en una frontera la documentan y piden asesoría con el registro en la mano, no con "no funciona".

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
| Esqueleto del pitch con pendientes marcados | Prompt 5 |
| Ruta de las dos semanas con responsables | Bloque 6 |

**Antes de la evaluación final:**

| Entregable | Referencia |
|------------|-----------|
| Sistema integrado funcionando: sensor, app y pantalla, sin falla | Bloque 1, pruebas T1 a T6 |
| Reporte de pruebas de usuario con cinco sesiones | Bloque 2, Prompt 2 |
| Landing publicada y accesible en internet | Bloque 3, Prompt 6 |
| Checklist regulatorio con estatus VERIFICADO o POR VERIFICAR | Bloque 4, Prompt 4 |
| Pitch de 3 minutos ensayado y grabado en video | Bloque 5, Prompt 5 |
| Repositorio con README y commits por sesión de trabajo | Bloque 6 |
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


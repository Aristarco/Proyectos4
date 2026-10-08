# Semana 8 — Prototipado y diseño para manufactura

!!! abstract "Blueprint IDEO: Creación de valor · DVF: 🔴 Deseable · 🟢 Factible"
    El prototipo no es el producto — es la pregunta más barata que el equipo puede hacerle al mundo real. Esta semana el equipo aprende a formular esa pregunta con precisión, a construir el mínimo necesario para responderla, y a usar lo que aprende para rediseñar el producto de forma que sea reproducible, más barato de fabricar, y listo para las primeras tiradas. El prototipado y el DFM no son temas separados: son dos mitades del mismo ciclo de aprendizaje.

---

## Distribución de tiempo presencial

| # | Bloque | Contenido | Tiempo |
|---|--------|-----------|:------:|
| 1 | Por qué prototipar | El prototipo como herramienta de aprendizaje, no de demostración | 15 min |
| 2 | Tipos de prototipo | Baja y alta resolución · Los cuatro tipos para productos mecatrónicos | 15 min |
| 3 | El proceso de tres pasos | Pregunta → Prototipa → Evidencia | 20 min |
| 4 | DFM | Del primer prototipo al diseño reproducible | 20 min |
| 5 | Economía Circular | La Ley General y su impacto en el diseño de producto | 15 min |
| 6 | Taller | El equipo define su plan de prototipado y aplica DFM al concepto | 25 min |
| 7 | Cierre | Defensa del plan — 3 minutos por equipo | 10 min |
| | **Total** | | **120 min** |

!!! tip "El hilo conductor"
    Prototipado y DFM son el mismo ciclo: el prototipo genera aprendizaje, el DFM convierte ese aprendizaje en decisiones de rediseño. Un equipo que prototipa sin aplicar DFM produce iteraciones que no convergen. Un equipo que aplica DFM sin haber prototipado optimiza algo que todavía no sabe si funciona.

---

## Bloque 1 — Por qué prototipar
**Duración: 15 min · Min 0:00 – 0:15**

### El error más costoso del semestre

El instructor abre sin diapositivas:

> *"¿Cuántos de ustedes han tenido la experiencia de trabajar semanas en algo, entregarlo, y escuchar de un usuario 'ah, pero yo necesitaba que hiciera otra cosa'? Eso no es un fallo del usuario — es un fallo del proceso. El prototipo existe para evitar ese momento. No para eliminarlo — para adelantarlo a cuando todavía es barato corregirlo."*

El prototipo no es una versión temprana del producto final. Es una herramienta de aprendizaje: algo construido deliberadamente para responder una pregunta específica sobre el producto, el usuario, o el negocio — antes de invertir recursos en construir algo que podría estar equivocado.

**Las tres razones para prototipar, en orden de importancia:**

**1. Resuelve preguntas pronto.** Cada semana que pasa sin validar una hipótesis es una semana de desarrollo construida sobre un supuesto. El prototipo convierte supuestos en evidencia.

**2. Aumenta la confianza.** Un equipo que ha visto a usuarios reales interactuar con algo tangible tiene más certeza sobre sus decisiones de diseño que un equipo que solo ha discutido en una sala.

**3. Reduce riesgo.** El error en papel cuesta minutos. El error en prototipo cuesta días. El error en producto terminado cuesta meses y dinero que no se recupera.

### La distinción que define el semestre

```
PROTOTIPO DE EXPLORACIÓN    FIRST-ITERATION PRODUCT
(lo que hacen AHORA)        (lo que entregan al final)
────────────────────────    ────────────────────────────
Responde preguntas          Es el producto mínimo que
específicas sobre el        un usuario real puede usar
diseño o el usuario         sin que el equipo esté presente

Puede ser feo, inestable,   Debe funcionar de forma
parcialmente funcional      autónoma y confiable

Lo usa el equipo para       Lo usa el usuario final
aprender                    para resolver su problema

Éxito = aprendizaje         Éxito = el usuario puede
                            instalarlo y usarlo solo
```

> *"En estas semanas construyen prototipos de exploración. Las semanas finales del curso son para el first-iteration product. Confundir los dos lleva a equipos que llegan a semana 14 con un prototipo pulido que nunca fue probado con usuarios — y que tiene problemas que se pudieron haber descubierto en semana 8."*

### El Business Blueprint como mapa de qué prototipar

El instructor proyecta el Business Blueprint de IDEO — que el grupo ya conoce — y hace la pregunta:

> *"Este blueprint tiene seis bloques: Clientes, Oferta, Modelo de ingresos y precio, Canales, Propuesta de valor, Costos, Socios, Equipo y recursos. Se puede prototipar cualquiera de ellos — no solo el artefacto físico. ¿Cuál tiene más incertidumbre en su proyecto ahora mismo?"*

Esa pregunta orienta el taller. El equipo que no sabe si el usuario pagará por la suscripción prototipa el modelo de ingresos (una landing page con precio real y un botón de pre-orden). El equipo que no sabe si la carcasa es instalable prototipa la forma física. El equipo que no sabe si la app es usable prototipa la pantalla principal.

---

## Bloque 2 — Tipos de prototipo
**Duración: 15 min · Min 0:15 – 0:30**

### Baja resolución vs. alta resolución

Los prototipos no son todos iguales. La resolución correcta depende de la pregunta que el equipo necesita responder — no de cuánto tiempo tiene o de qué tan bien quiere quedar.

**Baja resolución:**
- Proveen dirección en ideas tempranas
- Son rápidos de hacer — horas, no semanas
- El usuario puede ignorar imperfecciones y enfocarse en la pregunta que se está probando
- Pensar en: boceto, storyboard, maqueta en papel, alterar levemente un producto existente

**Alta resolución:**
- Ayudan a escoger entre opciones concretas o afinar lo que ofrece el producto
- Necesitan recursos — tiempo, materiales, software
- El nivel de detalle permite que el usuario reaccione a la experiencia real
- Pensar en: pop-up, demo funcional, maqueta del sitio, prototipo electrónico funcionando

**La regla:** usar la resolución mínima que responde la pregunta. Invertir en alta resolución antes de validar con baja resolución es uno de los errores más frecuentes en equipos de ingeniería — hacen algo funcional y perfecto antes de saber si están resolviendo el problema correcto.

### Los cinco formatos de prototipo — y cuándo usar cada uno

El instructor muestra los ejemplos reales del curso y de proyectos anteriores:

| Formato | Cuándo usarlo | Pregunta que responde |
|---------|--------------|----------------------|
| **Boceto o storyboard** | Al inicio, para explorar formas y flujos | ¿Esta dirección de diseño tiene sentido? |
| **Producto en papel o maqueta en pantalla** | Para probar interfaces y flujos de usuario | ¿El usuario entiende cómo usarlo? |
| **Historia en video** | Para validar la propuesta de valor antes de construir | ¿El usuario querría esto? ¿Lo compraría? |
| **Empaque o anuncio** | Para validar el mensaje y el precio | ¿El precio es correcto? ¿El mensaje resuena? |
| **Tienda pop-up o juego de rol** | Para validar el canal de venta y la experiencia de compra | ¿El usuario compra cuando lo tiene enfrente? |

### Los cuatro tipos de prototipo para productos mecatrónicos

Para el tipo de producto que desarrolla este grupo — artefacto + app + web — hay cuatro tipos de prototipo con propósitos distintos:

```
PROTOTIPO DE FORMA
Prueba la geometría, el tamaño, los materiales y la experiencia
física sin necesidad de electrónica funcional.
→ ¿El usuario puede instalarlo sin ayuda?
→ ¿Cabe en el espacio donde va?
→ ¿El material comunica confianza?
Herramienta: impresión 3D, cartón, arcilla, foam

PROTOTIPO DE FUNCIÓN
Prueba si el sistema electrónico y el software funcionan
sin necesidad de carcasa final.
→ ¿El sensor mide correctamente?
→ ¿El modelo de IA produce la respuesta esperada?
→ ¿La latencia entre sensor y app es aceptable?
Herramienta: protoboard, cables volando, ESP32 en la mano

PROTOTIPO DE EXPERIENCIA
Combina forma y función suficientemente para que un usuario
real pueda interactuar con el sistema completo.
→ ¿El usuario entiende qué hace el producto?
→ ¿La app tiene sentido sin instrucciones?
→ ¿La confirmación (LED, notificación) es clara?
Herramienta: carcasa impresa + electrónica funcional + app básica

PROTOTIPO DE NEGOCIO
Prueba si alguien pagaría por el producto antes de construirlo.
→ ¿El precio es aceptable?
→ ¿El canal de venta funciona?
→ ¿La propuesta de valor resuena?
Herramienta: landing page con precio real + botón de pre-orden
```

!!! tip "El prototipo de negocio es el más subestimado"
    Muchos equipos construyen el prototipo de función y forma antes de saber si alguien pagaría por el producto. Una landing page con un precio real y un botón de pre-orden — aunque el producto no exista todavía — responde la pregunta más importante del negocio en una semana. Bird Buddy recaudó €4.19 millones en Kickstarter antes de tener su versión final de producción.

---

## Bloque 3 — El proceso de tres pasos
**Duración: 20 min · Min 0:30 – 0:50**

### El proceso IDEO: Pregunta → Prototipa → Evidencia

El prototipado no es construir algo y ver qué pasa. Es un proceso disciplinado de tres pasos donde cada uno alimenta al siguiente.

```
    PREGUNTA          PROTOTIPA         EVIDENCIA
  ────────────      ────────────      ────────────
  ¿Qué quiero       Construye lo      Diseña cómo
  aprender?         mínimo para       vas a capturar
                    responderla       lo que aprendes
```

### Paso 1 — Hacer la pregunta correcta

La calidad del prototipo depende completamente de la calidad de la pregunta. Una pregunta vaga produce un prototipo que no dice nada. Una pregunta precisa produce un prototipo que revela exactamente lo que necesita saberse.

**Para decidir qué prototipar primero, buscar los supuestos con:**

- **Mayor riesgo:** ¿qué supuesto, si resulta falso, destruye el modelo de negocio? Ese es el primero en prototipar.
- **Mayor indefinición:** ¿qué parte del sistema el equipo nunca ha construido ni visto construir? Ahí está la mayor incertidumbre técnica.
- **Mayor controversia:** ¿en qué decisión el equipo sigue sin ponerse de acuerdo? El prototipo resuelve las discusiones que el debate no puede.

**Ejemplos de preguntas bien formuladas vs. mal formuladas:**

| Pregunta mal formulada | Pregunta bien formulada |
|------------------------|------------------------|
| "¿Funciona el sensor?" | "¿Puede el agricultor instalar el sensor en menos de 5 minutos sin instrucciones?" |
| "¿Está bien el diseño?" | "¿El usuario sabe que el dispositivo está funcionando sin abrir la app?" |
| "¿Es viable el negocio?" | "¿Pagaría el agricultor $119 MXN/mes si viera los datos de humedad en tiempo real?" |

### Paso 2 — Construir el prototipo correcto

Una vez que la pregunta está definida, el equipo elige el formato y la resolución mínima para responderla.

**Las cuatro reglas del buen prototipo:**

**1. Hazlo en un día o menos.** Si tarda más, está sobre-diseñado para la pregunta que responde. Reducir alcance o bajar la resolución.

**2. Se vale falsificar — que se sienta real, aunque no lo sea.** Un video que simula la app funcionando, una carcasa de cartón con el peso correcto, una landing page con precio real. El usuario no necesita que sea real — necesita que sea suficientemente real para reaccionar honestamente.

**3. Provee variaciones.** Cuando es posible, crear dos o tres versiones del mismo prototipo para que el usuario tenga puntos de comparación. Eso produce información mucho más útil que una sola opción.

**4. Construye para que el usuario actúe, no solo opine.** La pregunta "¿te gustaría usar esto?" produce respuestas de cortesía. La pregunta implícita de "¿puedes instalarlo?" produce comportamiento real. Diseñar el prototipo para capturar comportamiento, no opiniones.

### Paso 3 — Colectar evidencia

La evidencia no es "los usuarios dijeron que les gustó". Es la documentación de comportamiento real y reacciones específicas que permiten tomar decisiones de diseño con criterio.

**Diseñar el método de captura antes de prototipar:**
- ¿Cuántos usuarios necesitan para que la evidencia sea significativa? (mínimo 3, idealmente 5 del segmento objetivo)
- ¿Qué comportamientos específicos van a observar?
- ¿Cómo van a registrar lo que pasa? (video, notas, grabación de pantalla)
- ¿Qué pregunta de seguimiento van a hacer si el usuario se atasca?

**La evidencia más valiosa no es lo que dicen los usuarios — es lo que hacen.** Un usuario que dice "está muy claro" y luego pasa 3 minutos buscando el botón de encendido está diciéndote que no está claro. Observar supera a preguntar.

---

## Bloque 4 — Diseño para manufactura: del prototipo al producto reproducible
**Duración: 25 min · Min 0:50 – 1:15**

### El problema que el DFM resuelve

> *"El primer prototipo del semestre es una escultura. Tarda 40 horas de trabajo manual, usa componentes comprados de uno en uno en tiendas distintas, y solo la persona que lo hizo sabe cómo ensamblarlo. Cuando el instructor pide hacer tres más para la prueba de mercado, el equipo descubre que no puede. Eso no es un producto — es un experimento de laboratorio muy costoso."*

El Diseño para Manufactura (DFM) es el conjunto de metodologías para reducir los costos de fabricación sin comprometer la calidad ni la funcionalidad del producto. Empieza durante la fase de concepto — cuando las decisiones de diseño todavía son baratas de cambiar — y sigue iterando con cada prototipo.

> *"Las necesidades del cliente y las especificaciones del PDS son útiles para guiar el concepto, pero durante las últimas etapas de desarrollo es frecuente que los equipos tengan dificultad para enlazar esas especificaciones con el diseño particular al que se enfrentan. El DFM es el puente."*

**El costo de manufactura es el factor más determinante del éxito económico.** El margen de beneficio es la diferencia entre el precio de venta y el costo de fabricación. Si el DFM no se practica desde el diseño, el equipo llega a producción y descubre que el margen no existe.

### DFX — el ecosistema del que viene el DFM

El DFM es el más común de una familia de metodologías llamadas Diseño para X (DFX), donde X puede ser cualquier criterio de calidad: ensamble, servicio, medio ambiente, confiabilidad, costo, reutilización, seguridad. El instructor muestra el diagrama del ecosistema DFX sin entrar en detalle — la semana trabaja principalmente DFM y DFA (diseño para ensamble), que son los más relevantes para el nivel de producción del curso.

### El proceso DFM en 5 pasos

El proceso viene directamente de Ulrich & Eppinger (2026) — el estándar académico y de la industria:

```
DISEÑO PROPUESTO
        ↓
1. ESTIMAR costos de manufactura
        ↓
   ┌────────────────────────────────────┐
2. REDUCIR     3. DISMINUIR     4. REDUCIR
   costos de      costos de       costos de
   componentes    ensamble        soporte
   ↓              ↓               ↓
   └────────────────────────────────────┘
        ↓
5. CONSIDERAR el impacto en otros factores
        ↓
   ¿Suficientemente bien?
   NO → volver al inicio
   SÍ → DISEÑO ACEPTABLE
```

### Paso 1 — Estimar los costos de manufactura

El costo de manufactura es la suma de todos los gastos de los insumos del sistema más la eliminación de los residuos producidos. Se compone de tres categorías:

```
COSTO DE MANUFACTURA
├── Componentes
│   ├── Estándar (disponibles en catálogo)
│   └── Personalizados
│       ├── Materia prima
│       ├── Procesamiento
│       └── Maquinado
├── Ensamble
│   ├── Mano de obra
│   └── Equipo y herramientas
└── Gastos indirectos
    ├── Apoyo
    └── Asignación indirecta
```

Para medirlo: el Costo Unitario de Manufactura se calcula dividiendo los costos totales de fabricación de un período por el número de unidades producidas. Eso conecta directamente con el BOM y el modelo económico de semana 7 — no son ejercicios separados, son el mismo número visto desde perspectivas distintas.

### Paso 2 — Reducir los costos de componentes

El costo de componentes comprados es el elemento más importante del costo de manufactura en casi todos los productos electrónicos discretos. Tres estrategias:

**Entender las restricciones del proceso y sus impulsores de costo:**

Algunas partes son costosas simplemente porque los diseñadores no entendieron las capacidades y restricciones del proceso de producción. Un diseñador puede especificar un radio interno muy pequeño en una esquina de una pieza maquinada sin darse cuenta de que eso requiere electroerosión (EDM) — un proceso mucho más costoso que el maquinado estándar. O puede especificar tolerancias excesivamente estrictas sin entender la dificultad de alcanzarlas en producción.

> *"A veces estas características costosas ni siquiera son necesarias para la función del componente — surgen de la falta de conocimiento del proceso. Con frecuencia es posible rediseñar la pieza para obtener el mismo funcionamiento evitando los pasos costosos."*

**Aplicado a impresión 3D y PCB — los procesos de este curso:**

| Proceso | Restricción que aumenta el costo | Cómo evitarla |
|---------|----------------------------------|---------------|
| Impresión 3D FDM | Soportes en voladizos > 45° | Rediseñar la geometría para evitar voladizos o orientar la pieza |
| Impresión 3D FDM | Paredes < 1.2mm | Aumentar grosor mínimo de pared |
| PCB en JLCPCB | Componentes fuera de su librería estándar | Seleccionar componentes de la librería JLCPCB Basic |
| PCB en JLCPCB | Pitch < 0.8mm en SMD | Usar componentes con pitch ≥ 0.8mm |
| PCB en JLCPCB | Más de 2 capas | Rediseñar el ruteo para 2 capas |

**Rediseñar componentes para eliminar pasos de procesamiento:**

La reducción del número de pasos en el proceso de fabricación de una pieza resulta casi siempre en reducción de costos. La fabricación de "forma neta" — producir una pieza con la geometría final en un solo paso — es la estrategia más efectiva. Para productos de este curso: una carcasa impresa en 3D que no requiere post-procesado es mejor que una que necesita lijado, pintura y ensamble de múltiples partes.

**Seleccionar la escala económica apropiada:**

El costo de manufactura baja a medida que aumenta el volumen — esto es economía de escala. Para este curso:

```
1–3 unidades:    Impresión 3D en laboratorio + soldadura manual
                 Costo fijo bajo, costo variable alto
                 Proceso correcto: laboratorio

5–20 unidades:   JLCPCB + PCBA (ensamble incluido)
                 Costo fijo medio (setup), costo variable bajo
                 Proceso correcto: manufactura externa básica

20–100 unidades: JLCPCB PCBA + molde de inyección para carcasa
                 Costo fijo alto (molde), costo variable muy bajo
                 Proceso correcto: producción semi-industrial
```

Los componentes **estándar** — disponibles en catálogo y comunes a múltiples productos — siempre son preferibles a los personalizados en etapa early. Son más baratos, tienen mejor disponibilidad, y tienen cadenas de suministro establecidas. Usar un ESP32 estándar en lugar de diseñar un microcontrolador propio no es una limitación — es una decisión de DFM inteligente.

### Paso 3 — Disminuir los costos de ensamble (DFA)

El Diseño para Ensamble (DFA) es el subconjunto más importante del DFM para productos mecatrónicos universitarios. Aunque el ensamble representa una fracción pequeña del costo total, concentrarse en él produce beneficios indirectos enormes: reduce el número total de piezas, simplifica la manufactura, y baja los costos de soporte.

**Dos productos con el mismo número de piezas pueden diferir 2–3× en tiempo de ensamble** según la geometría y la trayectoria de inserción. Los principios que reducen ese tiempo:

- La pieza se inserta desde arriba — no requiere voltear el ensamble
- La pieza tiene alineamiento propio — no puede insertarse en la posición incorrecta
- No es necesario orientar la pieza antes de insertarla
- La pieza requiere solo una mano para ensamblarse
- La pieza no requiere herramientas especiales
- La pieza se ensambla en un solo movimiento lineal
- La pieza se asegura inmediatamente al insertarla (snap fit, presión, rosca)

**Aplicado a carcasas de productos mecatrónicos:**

```
❌ DIFÍCIL DE ENSAMBLAR:
  Carcasa en 4 partes con 8 tornillos M2
  → Requiere destornillador, alineación manual,
    tiempo de ensamble: ~20 minutos por unidad

✅ FÁCIL DE ENSAMBLAR:
  Carcasa en 2 partes con cierre snap-fit
  → No requiere herramientas, inserción desde arriba,
    tiempo de ensamble: ~2 minutos por unidad
```

### Paso 4 — Reducir costos de soporte de producción

Los costos de soporte de producción son todos los costos indirectos que no están en el BOM ni en el tiempo de ensamble directo, pero que son necesarios para que el sistema de manufactura funcione. No se ven en la primera cotización — aparecen cuando el producto empieza a fabricarse en volumen.

**Los principales costos de soporte para productos mecatrónicos:**

**Control de calidad:** inspección de componentes al recibirlos, pruebas de funcionamiento de cada unidad ensamblada, manejo de unidades defectuosas y reprocesos. Si el diseño tiene muchos componentes o tolerancias ajustadas, el costo de inspección sube proporcionalmente.

**Gestión de inventario:** mantener stock de cada componente del BOM tiene un costo. Un producto con 40 referencias distintas necesita gestionar 40 líneas de inventario — seguimiento de fechas de caducidad (baterías), mínimos de reorden, proveedores alternativos. Cada referencia que se elimina del BOM reduce este costo.

**Documentación técnica:** instrucciones de ensamble, diagramas de prueba, procedimientos de calibración. Si el ensamble es complejo y requiere conocimiento implícito del equipo, escalar a un tercero que lo fabrique se vuelve muy difícil sin documentación detallada.

**Mantenimiento de herramientas y equipos:** si el diseño requiere herramientas especiales o jigs de ensamble, alguien tiene que mantenerlos. Un diseño que funciona con herramientas estándar elimina ese costo.

**Curva de aprendizaje:** las primeras unidades siempre tardan más de ensamblar que las unidades 50 o 100. Un diseño más simple acorta esa curva — el ensamblador llega a velocidad óptima más rápido.

La relación con los pasos anteriores es directa: **cada componente eliminado en el Paso 2 y cada paso de ensamble simplificado en el Paso 3 reduce automáticamente los costos de soporte del Paso 4.** Por eso el DFM es iterativo — las mejoras se acumulan.

**Para los proyectos de este curso:** en volúmenes de 5–20 unidades los costos de soporte son principalmente tiempo del equipo. El riesgo real es llegar a semana 13 con un diseño que el equipo tarda 3 horas en ensamblar por unidad porque nunca se aplicó DFA — eso convierte las últimas semanas en una línea de ensamble en lugar de una prueba de mercado.

### Paso 5 — Considerar el efecto en otros factores

Reducir costos de manufactura no es el único objetivo. El éxito económico del producto también depende de su calidad, del tiempo al mercado, y del costo de desarrollo. Algunas decisiones de DFM reducen el costo de manufactura pero aumentan el tiempo de desarrollo o reducen la calidad percibida. Esos trade-offs deben evaluarse explícitamente, no ignorarse.

---

## Bloque 5 — Economía Circular y la Ley General: diseñar para el futuro que ya llegó
**Duración: 15 min · Min 1:10 – 1:25**

### Por qué este bloque en este curso

> *"Lo que van a diseñar en este semestre lo van a estar fabricando y vendiendo en los próximos años. Para ese momento, las organizaciones donde trabajen ya estarán inmersas en el cumplimiento de la Ley General de Economía Circular — publicada en el Diario Oficial de la Federación el 19 de enero de 2026. No es una tendencia. Es ley vigente en México."*

El instructor no presenta esto como un tema adicional — lo presenta como el contexto regulatorio en el que el DFM que acaban de aprender opera. Diseñar para manufactura sin diseñar para circularidad es diseñar para cumplimiento parcial.

### Qué es la Economía Circular — la definición de la Ley

La Ley la define con precisión en su Artículo 3:

> *"Modelo económico de Producción y Consumo sostenible que incluye soluciones sistémicas para el desarrollo económico, que disminuyen el impacto ambiental mediante ciclos técnicos y biológicos que permiten la permanencia y reintegración sustentable de los materiales de los productos a la economía, el cual tiene como principios rectores la eliminación de residuos y la contaminación, mantener productos y materiales en uso, así como regenerar los sistemas naturales."*

En términos simples: el modelo lineal tradicional es **extraer → fabricar → usar → tirar**. El modelo circular es **diseñar → fabricar → usar → recuperar → volver a fabricar**. El producto no termina en el basurero — sus materiales regresan al ciclo productivo.

### Los principios de la Ley más relevantes para el desarrollo de producto

El Artículo 4 establece los principios rectores. El instructor selecciona los cuatro que más impactan directamente las decisiones de diseño del curso:

**Diseño Circular (Artículo 3, fracción VII):**
El producto debe incorporar principios y mecanismos de circularidad en su Ciclo de Vida desde la fase de diseño. No es un ajuste posterior — es una decisión de diseño desde el boceto técnico.

**Modular (Artículo 4, principio VIII):**
Los productos deben ser separables en componentes o módulos que puedan ser reparados, actualizados o reutilizados de manera independiente. Esto tiene consecuencia directa en la decisión de carcasa — un producto cuyos componentes electrónicos no son accesibles sin destruirla viola este principio.

**Reparabilidad (Artículo 4, principio X):**
La Ley garantiza que los productos sean concebidos y fabricados con disponibilidad de refacciones, herramientas y lugares donde puedan repararse. Para un equipo que diseña hardware con IA: ¿puede el usuario final cambiar la batería? ¿Puede reemplazar el sensor si falla? ¿El firmware puede actualizarse sin que el dispositivo regrese al fabricante?

**Atemporal (Artículo 4, principio I):**
Los productos deben trascender en el tiempo mediante el uso de materiales adecuados, manufactura de calidad y modelos de diseño que eviten promover su reemplazo periódico o prematuro. El instructor señala directamente: diseñar obsolescencia programada no solo es mala práctica — bajo esta ley, es algo que el Estado busca evitar activamente.

### La Responsabilidad Extendida del Productor (REP)

Este es el mecanismo de cumplimiento más importante de la Ley para fabricantes de producto:

La REP (Artículo 3, fracción XXXI) establece que **el productor o importador es responsable ambientalmente de su producto en todo su Ciclo de Vida** — no solo hasta que el cliente lo compra, sino hasta que los materiales se recuperan o disponen finalmente.

En términos prácticos para un fabricante de hardware:

```
Sin REP (modelo lineal):
  Diseño → Fabrico → Vendo → Mi responsabilidad termina

Con REP (modelo circular — Ley vigente):
  Diseño → Fabrico → Vendo → Uso → Fin de vida
                                    ↑
                              Mi responsabilidad
                              no termina aquí
```

La Ley establece que la SEMARNAT publicará **acuerdos generales de implementación de la REP** por sector productivo. Los productos electrónicos e IoT están entre los primeros en la mira — son de los que generan más residuos de difícil gestión (RAEE: Residuos de Aparatos Eléctricos y Electrónicos).

### El Distintivo Nacional de Economía Circular

La Ley crea un Distintivo Nacional de Economía Circular (Artículo 17, fracción VI) — un sello que las empresas pueden obtener cuando sus productos y procesos cumplen con los criterios de circularidad establecidos. En los próximos años será un diferenciador de mercado, similar a lo que fue la certificación ISO 9001 en los 90.

### La conexión con el DFM — por qué importa desde hoy

El instructor cierra el bloque con la pregunta directa que conecta ambos temas:

> *"Revisen el boceto técnico de su producto con este lente. ¿La carcasa se puede abrir sin destruirla? ¿El PCB es modular — pueden reemplazar el sensor sin cambiar todo? ¿Los materiales que eligieron son reciclables o recuperables? ¿El firmware se puede actualizar remotamente? Si no pueden responder sí a estas preguntas, no están diseñando solo para manufacturar — están diseñando para tirar."*

**Las cuatro preguntas de circularidad que el equipo se hace sobre su diseño:**

| Pregunta | Principio de la Ley | Implicación de diseño |
|----------|--------------------|-----------------------|
| ¿Los componentes son accesibles para reparación? | Reparabilidad | Carcasa con acceso sin destrucción — snap-fit o tornillos accesibles |
| ¿Los módulos pueden reemplazarse de forma independiente? | Modular | PCB con conectores, no componentes soldados directamente a la carcasa |
| ¿Los materiales son identificables para reciclaje? | Ciclo de Vida | Marcar el material en las piezas de plástico (código de reciclaje) |
| ¿El producto puede actualizarse sin reemplazarse? | Atemporal | OTA updates para firmware — la mejora no requiere hardware nuevo |

!!! note "¿A partir de cuándo se aplica la REP a tu sector?"
    La Ley establece implementación gradual por acuerdos sectoriales. Los reglamentos específicos por sector productivo se emitirán en los próximos años — los equipos que diseñen con principios de circularidad desde hoy no tendrán que rediseñar cuando llegue el acuerdo que les aplique. Los que no lo hagan, sí.

---

## Bloque 6 — Taller
**Duración: 25 min · Min 1:25 – 1:50**

### Dos ejercicios en paralelo

El taller tiene dos partes que los equipos hacen simultáneamente:

**Parte A (15 min) — Plan de prototipado:** el equipo define qué va a prototipar primero y cómo.

**Parte B (20 min) — Revisión DFM del concepto:** el equipo aplica el proceso DFM a su diseño actual con ayuda de Claude.

---

### Parte A — Plan de prototipado

**Instrucción al grupo:**

> *"Tienen 15 minutos para definir su plan de prototipado. Tres decisiones: qué supuesto tienen que validar primero, qué tipo de prototipo van a construir para validarlo, y cómo van a saber si el prototipo respondió la pregunta."*

**Plantilla del plan de prototipado:**

```
PLAN DE PROTOTIPADO
Equipo: _________ Concepto: _________

SUPUESTO A VALIDAR:
[El supuesto más riesgoso o más incierto del proyecto ahora mismo]

PREGUNTA PRECISA:
[Formulada como: ¿puede [usuario específico] [acción específica]
sin [condición que se quiere eliminar]?]

TIPO DE PROTOTIPO:
[ ] Forma  [ ] Función  [ ] Experiencia  [ ] Negocio
Resolución: [ ] Baja  [ ] Alta
Por qué esta resolución: ___________

QUÉ VAN A CONSTRUIR:
[Descripción concreta — materiales, herramientas, tiempo estimado]

CÓMO VAN A CAPTURAR EVIDENCIA:
[Comportamiento a observar / Métrica a medir / Umbral de éxito]

UMBRAL DE ÉXITO:
[Si [X usuarios de Y] pueden [hacer Z] en menos de [tiempo],
el supuesto queda validado]
```

---

### Parte B — Revisión DFM del concepto con IA

### Prompt — Claude: revisión DFM del concepto

```
Actúa como un ingeniero de manufactura con experiencia en
diseño para manufactura (DFM) y diseño para ensamble (DFA)
aplicados a productos electrónicos de consumo y productos
IoT en etapa de prototipo temprano. Tu metodología sigue el
proceso de Ulrich & Eppinger: estimar costos, reducir
componentes, disminuir ensamble, reducir soporte, y evaluar
efectos en otros factores. Tu sesgo es hacia soluciones
que funcionen con los recursos de un laboratorio universitario
y manufactura externa básica (JLCPCB PCBA, impresión 3D FDM).
Cuando un aspecto del diseño viola principios de DFM, lo
señalas directamente y propones la alternativa específica.
No eres genérico — tus observaciones son sobre el diseño
particular que se te describe.

Somos un equipo de ingeniería en México. Tenemos el concepto
de diseño seleccionado en semana 6 y el BOM preliminar de
semana 5. Necesitamos aplicar DFM antes de entrar a la
siguiente fase de prototipado.

NUESTRO CONCEPTO DE DISEÑO:
Nombre: [nombre del concepto]
Descripción del artefacto: [qué hace, dimensiones aproximadas,
  materiales indicados en el boceto técnico]
Método de instalación: [cómo el usuario lo instala]
Carcasa: [número de partes, método de cierre, material]
Componentes principales del BOM:
  [listar los 5–8 componentes más importantes con su
   especificación — microcontrolador, sensores, módulos
   de comunicación, fuente de energía]

PROCESO DE MANUFACTURA PLANEADO:
Carcasa: [ ] Impresión 3D FDM  [ ] Mecanizado  [ ] Otro
PCB: [ ] JLCPCB solo PCB  [ ] JLCPCB + PCBA  [ ] Laboratorio
Ensamble: [ ] Manual en laboratorio  [ ] Externo

VOLUMEN OBJETIVO: [N unidades para prueba de mercado]

Aplica el proceso DFM en 5 pasos y entrega:

PASO 1 — ESTIMACIÓN DE COSTOS:
Con el BOM proporcionado, estima el costo unitario de
manufactura a [N] unidades. Desglosa:
· Componentes electrónicos (BOM)
· PCB fabricación + ensamble (JLCPCB PCBA estimado)
· Carcasa (impresión 3D o proceso indicado)
· Ensamble manual (horas × costo/hora estimado)
· Gastos indirectos (15%)
· Costo unitario total

PASO 2 — REDUCIR COSTOS DE COMPONENTES:
Identifica los 3 componentes de mayor costo del BOM.
Para cada uno:
· ¿Hay alternativa estándar más económica con
  especificaciones equivalentes?
· ¿Está disponible en la librería Basic de JLCPCB para PCBA?
· ¿Alguna decisión de diseño lo hace más caro de lo necesario?

PASO 3 — DISMINUIR COSTOS DE ENSAMBLE:
Evalúa la carcasa y el ensamble del producto:
· ¿Cuántas partes tiene la carcasa? ¿Se puede reducir?
· ¿El método de cierre requiere herramientas?
· ¿Hay piezas que requieren orientación manual?
· ¿Se pueden reemplazar tornillos por snap-fits o press-fits?
· Tiempo estimado de ensamble por unidad con el diseño actual
· Tiempo estimado con las mejoras propuestas

PASO 4 — REDUCIR SOPORTE DE PRODUCCIÓN:
¿Hay componentes no estándar que complican el inventario?
¿Hay pasos de ensamble que requieren habilidades especializadas?
¿El diseño facilita el control de calidad?

PASO 5 — EFECTOS EN OTROS FACTORES:
¿Alguna de las mejoras propuestas afecta negativamente
la calidad percibida, el tiempo al mercado, o la propuesta
de valor? Si sí, señalarlo explícitamente para que el
equipo evalúe el trade-off.

FORMATO DE SALIDA:

════════════════════════════════════════════════════════
REVISIÓN DFM
Concepto: [nombre] · Volumen: [N] unidades
════════════════════════════════════════════════════════

COSTO UNITARIO ESTIMADO (actual):
· BOM electrónico:          $[MXN]
· PCB + PCBA:               $[MXN]
· Carcasa:                  $[MXN]
· Ensamble manual:          $[MXN]
· Gastos indirectos (15%):  $[MXN]
Total actual:               $[MXN]/unidad

────────────────────────────────────────────────────────
OPORTUNIDADES DE REDUCCIÓN:

Componente 1 — [nombre actual]:
Problema: [por qué es caro o problemático]
Alternativa: [componente específico + precio + fuente]
Ahorro estimado: $[MXN]/unidad

Componente 2 — [nombre]
[mismo formato]

Componente 3 — [nombre]
[mismo formato]

────────────────────────────────────────────────────────
ENSAMBLE:
Diseño actual: [N] partes · Tiempo: ~[X] min/unidad
Propuesta: [N] partes · Tiempo: ~[X] min/unidad
Cambios recomendados: [cuáles específicamente]

────────────────────────────────────────────────────────
COSTO UNITARIO ESTIMADO (con mejoras DFM):
Total con mejoras: $[MXN]/unidad
Reducción: $[MXN] ([%]% de ahorro)

────────────────────────────────────────────────────────
TRADE-OFFS A EVALUAR:
[Si alguna mejora DFM afecta calidad, tiempo o propuesta
de valor — señalarlo con el trade-off específico]

COMPATIBILIDAD CON JLCPCB PCBA: ✅/⚠️/❌
[Componentes que no están en librería Basic y qué hacer]
════════════════════════════════════════════════════════
```

---

## Bloque 7 — Defensa del plan
**Duración: 10 min · Min 1:50 – 2:00**

El instructor selecciona 2 equipos con planes de prototipado distintos — uno con prototipo de forma, uno con prototipo de negocio o experiencia. Cada equipo tiene 4 minutos:

**Formato:**

```
Minuto 1: El supuesto más riesgoso
"El supuesto que necesitamos validar primero es [cuál].
Si ese supuesto resulta falso, [consecuencia para el negocio]."

Minuto 2: El prototipo
"Vamos a construir [qué], de [resolución], usando [cómo].
La pregunta que responde es: ¿puede [usuario] hacer [qué]?"

Minuto 3: La evidencia
"Sabremos que funcionó cuando [N] usuarios puedan [acción]
en menos de [tiempo / sin [condición]]."

Minuto 4: DFM — el cambio más importante
"La revisión DFM nos dice que el componente de mayor costo
es [cuál]. Si lo reemplazamos por [alternativa], el costo
unitario baja de $[X] a $[Y] MXN."
```

**La pregunta del instructor — una por equipo:**
- *"¿Por qué ese supuesto y no [otro supuesto más fundamental del negocio]?"*
- *"Si el usuario no puede hacer [acción], ¿qué cambian — el diseño, el material, o el proceso de instalación?"*
- *"¿El prototipo que planean es de baja resolución porque la pregunta lo permite, o porque no tienen tiempo para hacerlo bien?"*

---

## Tarea en casa (4 horas)

| Tarea | Tiempo | Entregable |
|-------|:------:|-----------| 
| Construir el primer prototipo según el plan definido en clase | 2h | Foto/video del prototipo + descripción de cómo se construyó |
| Probar el prototipo con mínimo 3 usuarios del segmento objetivo | 1h | Notas de observación con el formato del Paso 3 (evidencia) |
| Aplicar las mejoras DFM más importantes al diseño — actualizar el BOM | 1h | BOM actualizado con componentes revisados + costo unitario nuevo |

### Formato de reporte del prototipo

```
REPORTE DE PROTOTIPO — Semana 8
Equipo: _________ Concepto: _________

TIPO DE PROTOTIPO: [Forma / Función / Experiencia / Negocio]
RESOLUCIÓN: [Baja / Alta]
MATERIALES Y TIEMPO: [qué usaron y cuánto tardaron]

PREGUNTA QUE RESPONDÍA:
[La pregunta precisa del plan de prototipado]

EVIDENCIA RECOLECTADA:
Usuario 1: [qué observaron — comportamiento, no opinión]
Usuario 2: [qué observaron]
Usuario 3: [qué observaron]

¿SE VALIDÓ EL SUPUESTO? Sí / No / Parcialmente
Por qué: [qué evidencia lo soporta]

APRENDIZAJE CLAVE:
[La cosa más importante que aprendieron que no sabían antes]

CAMBIO AL DISEÑO:
[Qué cambia en el diseño como resultado de este prototipo]

SIGUIENTE HIPÓTESIS A PROTOTIPAR:
[El siguiente supuesto más riesgoso después de este]
```

---

## Bibliografía y recursos de la semana

### Lecturas obligatorias

Ulrich, K. T., Eppinger, S. D., & Yang, M. C. (2026). *Product Design and Development* (7.ª ed.). McGraw-Hill.
→ Capítulo 13: Diseño para manufactura. El proceso DFM de 5 pasos, costos unitarios, reducción de componentes y ensamble. Fuente directa del contenido de esta semana.

IDEO U. *Business Design*. IDEO.
→ Sección de prototipado: el proceso de tres pasos y los tipos de prototipo. Base del Bloque 3 de esta semana.

Cámara de Diputados del H. Congreso de la Unión. (2026). *Ley General de Economía Circular*. Diario Oficial de la Federación, 19 de enero de 2026.
→ Texto vigente. Artículos 1–4: objeto, objetivos, definiciones y principios de Economía Circular. Especial atención a las definiciones de Diseño Circular, Ciclo de Vida, Huella Ambiental y Responsabilidad Extendida del Productor (REP). Disponible en dof.gob.mx.

### Lecturas recomendadas

Kelley, T., & Kelley, D. (2013). *Creative Confidence: Unleashing the Creative Potential Within Us All*. Crown Business.
→ Capítulo 3: De la crítica a la curiosidad — el mindset del prototipado rápido. Accesible y muy aplicable al trabajo en equipo.

Ries, E. (2011). *The Lean Startup*. Crown Business.
→ Capítulo 6: Pivotar o perseverar — el ciclo construir-medir-aprender. La conexión entre prototipado y validación de negocio que se trabaja en esta semana.

Blank, S., & Dorf, B. (2012). *The Startup Owner's Manual*. K&S Ranch.
→ El concepto de Customer Development y por qué el prototipo de negocio (landing page, pre-orden) es tan poderoso como el prototipo físico.

Brown, T. (2009). *Change by Design*. HarperCollins.
→ Capítulo 4: Construir para pensar — la filosofía de IDEO sobre prototipado. Fácil de leer, muy motivador antes de las semanas de construcción.

Boothroyd, G., Dewhurst, P., & Knight, W. A. (2010). *Product Design for Manufacture and Assembly* (3.ª ed.). CRC Press.
→ El texto de referencia del DFA (Design for Assembly). Para quien quiera profundizar en los principios cuantitativos de reducción de tiempo de ensamble.

### Herramientas de la semana

| Herramienta | Uso | Acceso |
|-------------|-----|--------|
| **JLCPCB** | Cotización de PCB + PCBA con la librería de componentes | jlcpcb.com |
| **JLCPCB Parts Library** | Verificar disponibilidad de componentes para PCBA | jlcpcb.com/parts |
| **Bambu Lab / Prusa Slicer** | Verificar ángulos de voladizo antes de imprimir | bambulab.com / prusa3d.com |
| **Figma** | Prototipo de app de baja/alta resolución | figma.com |
| **Notion / Miro** | Storyboard y documentación del plan de prototipado | notion.so / miro.com |

---

## Lo que el equipo debe poder responder al salir

- [ ] ¿Cuál es el supuesto más riesgoso de su proyecto y qué prototipo van a construir para validarlo?
- [ ] ¿Qué evidencia específica — no opiniones, sino comportamiento — van a capturar con el prototipo?
- [ ] ¿Cuál es el componente de mayor costo de su BOM y cuál es la alternativa DFM que lo reduce?
- [ ] ¿Cuántas partes tiene su carcasa actual y cómo pueden reducirlas con snap-fit o rediseño?


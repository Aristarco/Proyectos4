# Semana 6 — Generación y selección de concepto de diseño

!!! abstract "Blueprint IDEO: Creación de valor · DVF: 🔴 Deseable · 🟢 Factible"
    El equipo ya sabe qué construir (propuesta de valor, semana 4) y cómo se conectan sus componentes (arquitectura, semana 5). Esta semana decide cómo se ve, cómo se toca y cómo se usa. El concepto de diseño no es decoración — es la primera decisión que el usuario va a juzgar antes de entender cómo funciona el producto.

---

## Distribución de tiempo presencial

| # | Bloque | Contenido | Tiempo |
|---|--------|-----------|:------:|
| 1 | Contexto | Del PDS al concepto de diseño — qué se decide aquí | 5 min |
| 2 | Principios | 7 principios de diseño que evitan la caja negra en PLA | 20 min |
| 3 | Técnicas | Morfología + analogías tecnológicas + renders con IA | 15 min |
| 4 | Taller A | Generación de conceptos de diseño — mínimo 3 por equipo | 30 min |
| 5 | Matriz de Pugh | Criterios de selección y evaluación comparativa | 20 min |
| 6 | Taller B | Primer boceto técnico del concepto elegido | 20 min |
| 7 | Cierre | Defensa de concepto — 3 minutos por equipo | 10 min |
| | **Total** | | **120 min** |

!!! tip "La distinción que define la semana"
    Concepto de **producto** = qué problema resuelve y para quién (semanas 2–4, ya hecho).
    Concepto de **diseño** = cómo se ve, cómo se toca, cómo se usa (semana 6, esto).
    Un equipo que confunde las dos llega a semana 13 con un producto que funciona pero que nadie quiere agarrar.

---

## Bloque 1 — Del PDS al concepto de diseño
**Duración: 5 min · Min 0:00 – 0:05**

### Qué se decide en semana 6 — y qué ya está decidido


> *Esta semana es para determinar exactamente cómo se ve su producto, qué tan grande es, de qué material es la carcasa, cómo el usuario lo instala, cómo sabe si está funcionando, y cómo se ve la primera pantalla de la app cuando la abre por primera vez.*

Pocas manos. Esa brecha es lo que cierra esta semana.

El PDS de semana 5 describe **qué debe hacer** el sistema. El concepto de diseño describe **cómo se experimenta**. Son documentos distintos con decisiones distintas — y las decisiones de diseño tienen consecuencias técnicas que retroalimentan al PDS.

```
PDS (semana 5)          CONCEPTO DE DISEÑO (semana 6)
────────────────        ──────────────────────────────
Qué funciones tiene     Cómo se ve la carcasa
Qué precisión tiene     Qué tan grande es y cómo se instala
Cuánta batería dura     Dónde está el LED de estado
Qué protocolos usa      Cómo sabe el usuario que funcionó
Qué resistencia IP      De qué material es y por qué
                        Cómo se ve la pantalla principal
                        Qué hace el usuario en los primeros 30 segundos
```

> *"El concepto de diseño es la primera cosa que el usuario va a juzgar. Antes de saber si el sensor funciona bien, el agricultor va a decidir si le da confianza clavarlo en su tierra. Esa decisión es de diseño, no de firmware."*

### Por qué generar varios conceptos antes de elegir uno

El error más frecuente en equipos de ingeniería: elegir el primer concepto de diseño que se les ocurre y refinarlo indefinidamente. El resultado es un diseño que no ha competido contra nada — sin saber si hay una alternativa mejor que hubiera tomado la mitad del tiempo de manufactura, o que el usuario hubiera preferido.

La generación de múltiples conceptos no es un ejercicio académico — es el proceso que hace que la decisión final sea defendible. La Matriz de Pugh solo funciona si hay conceptos reales que comparar.

**La regla de esta semana:** mínimo 3 conceptos de diseño por equipo, evaluados con criterios explícitos, antes de comprometerse con uno. El concepto elegido al final de la sesión es el que entra a CAD la semana siguiente.

---

## Bloque 2 — 7 principios de diseño que evitan la caja negra en PLA
**Duración: 20 min**

### Por qué este bloque antes de generar conceptos

> *"Si generamos conceptos ahora sin hablar primero de principios de diseño, el 80% de los equipos va a llegar al taller con una caja rectangular impresa en filamento negro. Eso no es un concepto de diseño — es la ausencia de uno. Veinte minutos antes del taller valen más que veinte semanas puliendo una caja."*

Los 7 principios que siguen no son un curso de diseño industrial — son el mínimo para que las decisiones de forma tengan intención.

---

### 1. Affordances — la forma dice cómo se usa

Término acuñado por Don Norman en *The Design of Everyday Things*. Un affordance es la propiedad de un objeto que comunica cómo debe ser usado — sin instrucciones, sin etiquetas, sin manual.

Una manija pide ser jalada. Un botón convexo pide ser presionado. Una ranura pide ser insertada. Una superficie rugosa en el costado de un dispositivo dice "agárrame aquí".

**La pregunta de diseño:** ¿qué le dice la forma de tu artefacto al usuario sobre cómo instalarlo y cómo interactuar con él, antes de que lea cualquier instrucción?

**El error más frecuente en productos de ingeniería:** un cuerpo perfectamente simétrico que no da ninguna pista sobre orientación, instalación, ni uso. El usuario lo agarra al azar y lo instala al revés. No porque sea tonto — porque el objeto no le dijo nada.

**Sobre materialidad:** el material también tiene affordances. El metal comunica rigidez y permanencia. El plástico blando comunica que puede apretarse. El ABS negro mate comunica instrumento técnico serio. Elegir el material correcto es parte del affordance — no solo decoración.

([Puedes ver algunos ejemplos de Affordances aquí](https://wordpress.kpu.ca/depd3530/2023/10/01/analysis-of-design-affordances-fiona-yu/))
---

### 2. Contour bias — las curvas generan confianza, los ángulos generan tensión

Investigación en neurociencia cognitiva muestra que los objetos con esquinas agudas activan respuestas de alerta en el cerebro. Los objetos con curvas las suprimen. No es estética — es fisiología.

Esto explica por qué el iPhone no tiene esquinas rectas aunque técnicamente sería más fácil de fabricar. Por qué los dispositivos médicos tienen radios generosos en todas las aristas. Por qué las herramientas de campo que el usuario va a usar muchas veces tienen bordes redondeados aunque añadan costo de manufactura.

**La pregunta de diseño:** ¿tu artefacto va a vivir en las manos de alguien, en una superficie que alguien toca, o en un lugar donde alguien lo ve todos los días? Si la respuesta es sí a cualquiera, las curvas no son un lujo — son parte de la propuesta de valor.

**Aplicado a impresión 3D:** un radio de 3mm en todas las aristas exteriores cuesta cero tiempo de diseño adicional en CAD y cambia completamente la percepción del objeto. No es la diferencia entre amateur y profesional en manufactura — es la diferencia en cómo el usuario lo percibe.

---

### 3. Consistencia — un lenguaje formal en todo el objeto

Un producto tiene lenguaje formal: el conjunto de decisiones de forma que se repiten de manera coherente en todo el objeto. El radio de esquinas. El tipo de transición entre superficies. La proporción entre partes. El tratamiento de las aristas.

Cuando ese lenguaje es consistente el producto *parece diseñado*. Cuando no lo es — una esquina con radio 2mm, otra con 8mm, una tercera recta — el objeto parece ensamblado por accidente aunque funcione perfectamente.

**La pregunta de diseño:** ¿las decisiones de forma que tomaron para una parte del objeto se replican en las demás? ¿El radio que usaron en la carcasa aparece también en los botones, en las ranuras de ventilación, en los detalles de montaje?

**Sobre proporción:** la consistencia también aplica a escala. Un componente que visualmente domina el objeto cuando debería ser secundario rompe la jerarquía visual. La proporción correcta no es la que cabe el circuito — es la que le comunica al usuario qué es importante y qué es secundario.

---

### 4. Constraints — el diseño previene el error

Un constraint es una restricción física o visual que hace que el error sea difícil o imposible. No depende de que el usuario lea las instrucciones — depende de que el objeto simplemente no permita el error.

El ejemplo más limpio: la tarjeta SIM solo entra en una posición porque una esquina está cortada a 45°. No hay forma de insertarla al revés. Eso es un constraint. Si la tarjeta fuera un rectángulo perfecto, el 30% de los usuarios la insertaría al revés y culparía al fabricante.

**La pregunta de diseño:** ¿cuáles son los errores de instalación o uso más probables en tu artefacto? ¿Puedes hacer que esos errores sean físicamente imposibles con el diseño?

Ejemplos aplicables a productos mecatrónicos:
- Conector que solo entra en una orientación (asimetría física)
- Cable de carga que sale solo por la base (no por los lados donde la humedad entraría)
- Tapa de batería que no cierra si la batería está al revés
- Botón de reset recesado para que no se presione accidentalmente

---

### 5. Confirmación — el sistema le dice al usuario que algo pasó

Cada vez que el usuario hace algo con el producto — lo enciende, lo configura, detecta un evento, envía un dato — necesita saber que pasó. Sin confirmación, el usuario repite la acción, la repite de nuevo, y eventualmente asume que el producto no funciona.

La confirmación puede ser visual (LED, cambio en pantalla), auditiva (beep, click), háptica (vibración), o en la app (notificación, cambio de estado). Lo importante es que sea inmediata, inequívoca, y proporcional a la importancia del evento.

**Los tres niveles de confirmación en un producto mecatrónico con app:**

```
Nivel 1 — Evento menor (lectura periódica normal):
Sin confirmación en el dispositivo. Dato actualizado en app.

Nivel 2 — Evento importante (umbral alcanzado):
LED cambia de color + notificación push en app.
El usuario necesita saber sin abrir la app.

Nivel 3 — Evento crítico (falla de sensor, batería baja):
LED parpadeante + vibración si aplica + alerta prominente
en app + notificación urgente. No puede ignorarse.
```

**La pregunta de diseño:** ¿para cada cosa que puede pasarle al sistema, el usuario sabe que pasó? ¿Sabrá que la batería está baja sin tener que abrir la app?

---

### 6. Costo-beneficio — cada decisión de diseño tiene un precio real

Cada feature que se agrega al diseño — una curva más, un material mejor, un LED adicional, una ranura de ventilación, una tapa con cierre a presión — tiene un costo real en manufactura, en tiempo de diseño, en complejidad de ensamble, en precio de componentes.

Eso no significa que no deba hacerse. Significa que la decisión debe ser consciente: *"Sabemos que añadir este radio cuesta X más en tiempo de CAD y X más en manufactura. Lo añadimos porque en nuestra Matriz de Pugh el contour bias tiene un peso de 15% y sin él perdemos puntos en deseabilidad."*

El error es en ambas direcciones:

- **Añadir features de diseño sin costo consciente:** el objeto se vuelve imposible de fabricar en el presupuesto
- **Eliminar todo lo que tenga costo:** el objeto parece una caja negra en PLA y nadie lo quiere comprar

**La pregunta de diseño:** para cada decisión de forma, ¿el valor que agrega al usuario justifica el costo que agrega al proceso?

---

### 7. Ciclo de desarrollo — este boceto no es el último

El diseño no se resuelve de una sola vez. Lo que el equipo produce hoy es la versión 1.0 del concepto — suficientemente buena para entrar a CAD, no suficientemente buena para ser el diseño final.

El ciclo es: boceto → CAD → prototipo impreso → feedback de usuario → ajuste → siguiente iteración. Cada vuelta del espiral reduce la incertidumbre y acerca el diseño al producto real.

> *"No se enamoren del boceto de hoy. Defiendan las decisiones que tomaron con criterios claros, pero estén dispuestos a cambiarlas cuando el prototipo físico les diga algo que el boceto no les pudo decir."*

Lo que sí debe sobrevivir a todas las iteraciones: los principios. El affordance puede cambiar de forma pero no puede desaparecer. La consistencia formal puede evolucionar pero no puede romperse. El ciclo de desarrollo no es permiso para tirar los principios — es el proceso para aplicarlos mejor.

---

### Los 7 en una hoja 

| Principio | Pregunta de diseño |
|-----------|-------------------|
| **Affordances** | ¿La forma dice cómo se usa antes de que el usuario lea nada? |
| **Contour bias** | ¿Las aristas y radios generan confianza o tensión? |
| **Consistencia** | ¿Hay un lenguaje formal coherente en todo el objeto? |
| **Constraints** | ¿El diseño hace que los errores sean difíciles o imposibles? |
| **Confirmación** | ¿El usuario sabe que algo pasó cada vez que algo pasa? |
| **Costo-beneficio** | ¿El valor que agrega cada feature justifica su costo real? |
| **Ciclo de desarrollo** | ¿Están comprometidos con los principios, no con el boceto? |

> *"Cuando estén generando sus conceptos en el taller, cada vez que tomen una decisión de forma pregúntense cuál de estos siete principios la justifica. Si ninguno la justifica, la decisión es arbitraria — y las decisiones arbitrarias de diseño son las que producen cajas negras en PLA."*

---

## Bloque 3 — Técnicas de generación de concepto de diseño con IA
**Duración: 15 min**

### Morfología — descomponer para recombinar

La morfología es la técnica de generación más sistemática para diseño de producto físico. El principio es simple: descomponer el diseño en sus parámetros independientes y generar variantes de cada uno. Luego recombinar variantes de distintos parámetros para obtener conceptos de diseño completos que no habrían aparecido pensando en el producto como un todo.

Es indispensable construir más de un concepto de diseño

Tabla morfológica para el sensor agrícola:

| Parámetro | Variante A | Variante B | Variante C |
|-----------|------------|------------|------------|
| **Forma de la carcasa** | Cilíndrica (como una estaca) | Rectangular plana | Esfera aplastada |
| **Método de instalación** | Clavado directo en tierra | Pinza en manguera de goteo | Superficie montada en pared de invernadero |
| **Indicador de estado** | LED visible en la parte superior | Vibración háptica | Sin indicador — solo en app |
| **Material exterior** | ABS negro mate | Aluminio anodizado | PP verde (camuflaje en campo) |
| **Interfaz de configuración** | Botón único + LED parpadeante | NFC con teléfono | Todo desde la app, sin botón físico |
| **Fuente de energía** | Batería LiPo reemplazable | Solar + batería buffer | Cable de alimentación a 12V (riego) |

**Cómo se genera un concepto desde la tabla:**
Tomar una variante de cada fila forma un concepto completo. Concepto A1B2C1: cilíndrico, instalado con pinza en manguera, LED, aluminio, NFC, solar. Concepto A2B1C3: rectangular, clavado directo, sin botón, PP verde, todo desde app, batería. Son productos distintos aunque resuelven el mismo problema.

> *"La morfología no garantiza que todos los conceptos sean buenos — garantiza que el espacio de diseño fue explorado de forma sistemática antes de elegir. Un equipo que usó morfología puede defender su elección diciendo '¿Por qué cilíndrico y no rectangular? Porque con los 6 conceptos que generamos, cilíndrico tuvo mejor puntuación en instalación y en costo de manufactura.' Eso es una decisión defendible."*

---

### Analogías tecnológicas — importar soluciones de otros sectores

Una de las fuentes más ricas de ideas de diseño es buscar cómo otros sectores han resuelto el mismo problema de experiencia de usuario — no de funcionamiento técnico, sino de experiencia.

Ejemplos:

**Problema de experiencia:** "el usuario no sabe si el dispositivo está funcionando sin mirar la app"

- ¿Cómo lo resuelve un router WiFi? → LED de estado con código de colores
- ¿Cómo lo resuelve un marcapasos? → No lo resuelve en el dispositivo — resuelve la ansiedad con datos en la app médica y visitas periódicas
- ¿Cómo lo resuelve un termostato inteligente? → Pantalla siempre encendida con temperatura actual visible

**Problema de experiencia:** "el dispositivo debe instalarse en un entorno hostil sin herramientas especializadas"

- ¿Cómo lo resuelve una cámara de seguridad exterior? → Bracket magnético + tornillo único de anclaje
- ¿Cómo lo resuelve un sensor de lluvia de coche? → Ventosa reutilizable en el parabrisas
- ¿Cómo lo resuelve una trampa para ratones? → Mecanismo de un solo movimiento que no requiere instrucciones

> *"La pregunta no es '¿qué haría otro producto de IoT agrícola?' — esa pregunta produce imitación. La pregunta es '¿qué sector ha resuelto brillantemente este problema de experiencia de usuario específico?' Esa pregunta produce innovación de diseño."*

---

### Renders con IA — ver antes de construir

El render conceptual con IA tiene un propósito específico en este punto del proceso: hacer visible una dirección de diseño antes de invertir tiempo en CAD. No es el diseño final — es suficientemente específico para evaluar si la dirección tiene sentido y para comunicarlo al resto del equipo.

Flujo de diseño:

```
Morfología + analogías     → Concepto en palabras + boceto en papel
Boceto en papel            → Prompt de render con IA (Midjourney / DALL-E / Ideogram)
Render conceptual          → Evaluación visual rápida
                           → ¿Vale la pena llevar a CAD?
                           → Sí: entra a Pugh + CAD
                           → No: descartado en 10 minutos, no en 10 horas
```

**La trampa del render prematuro:** generar renders con IA antes de tener criterios de diseño produce imágenes bonitas sin función. El render es para visualizar un concepto que ya existe en palabras — no para generar el concepto desde la imagen.

---

## Bloque 4 — Taller A: generación de conceptos de diseño
**Duración: 30 min · Min 0:40 – 1:10**

El taller sigue un flujo de tres prompts en secuencia. Entre cada prompt hay una pausa de reflexión — el equipo lee, anota, y decide qué llevar al siguiente. Claude no genera el concepto final: genera el espacio de posibilidades. El equipo elige.

```
Prompt 1 — Tabla morfológica     → el equipo estructura el espacio de diseño
           ↓ pausa: enriquecer la tabla con las analogías
Prompt 2 — Analogías tecnológicas → el equipo importa soluciones de otros sectores
           ↓ pausa: el equipo agrega variantes a la tabla con lo que encontró
Prompt 3 — Conceptos de diseño   → el equipo combina variantes en 3 conceptos completos
                                    (objeto + app + landing page)
```

### Instrucción al grupo

> *"Tres prompts en secuencia. Después de cada uno tienen 3 minutos para leer, anotar lo que les sirve y descartar lo que no. No pasen al siguiente prompt sin hacer esa pausa — **ahí es donde está el pensamiento,** no en el output de Claude."*

**La restricción que hace el ejercicio más rico:** los 3 conceptos finales deben ser genuinamente distintos — diferentes en al menos 3 parámetros de la tabla morfológica. Si los 3 tienen la misma forma, el mismo material y el mismo método de instalación, no son 3 conceptos — son un concepto con detalles cambiados.

---

### Prompt 1 — Claude: tabla morfológica

```
Actúa como diseñador industrial especializado en productos
de hardware conectado para mercados latinoamericanos. Tu sesgo
es hacia opciones construibles con medios universitarios —
nada que no pueda salir de un laboratorio con impresora 3D,
CNC básica y acceso a componentes en México. Cuando una variante
es técnicamente inviable para el equipo, no la incluyes.

Somos un equipo de ingeniería en México. Nuestro producto:

Nombre: [nombre del concepto]
Qué hace y para quién: [descripción en 2–3 oraciones]
Usuario y contexto de uso: [quién es, dónde instala el
  producto, cómo lo usa en su rutina diaria]
Restricciones del PDS relevantes para el diseño:
  · Resistencia ambiental: [IP, temperatura, humedad]
  · Presupuesto de manufactura por unidad: [MXN]
  · Instalación: [cómo el usuario lo instala sin ayuda]
  · Dimensiones máximas si las hay: [medidas]

Genera una tabla morfológica con 6–7 parámetros de diseño.
Para cada parámetro: 3 variantes genuinamente distintas.
Cada variante debe ser fabricable con los medios del equipo.

Parámetros obligatorios — ajusta los nombres según el producto:
· Forma general de la carcasa
· Método de instalación / montaje
· Indicador de estado sin necesidad de abrir la app
· Material y acabado exterior
· Interfaz física con el usuario (botones, touchpoints)
· Fuente de energía
· [Un séptimo parámetro específico de este producto]

Para cada variante indica entre paréntesis la implicación
de manufactura más importante: (impresión 3D / mecanizado /
molde de inyección / doblado de lámina / otro).

FORMATO DE SALIDA — solo la tabla, sin texto adicional:

════════════════════════════════════════════════════════
TABLA MORFOLÓGICA — [nombre del producto]
════════════════════════════════════════════════════════

| Parámetro | Variante A | Variante B | Variante C |
|-----------|------------|------------|------------|
| Forma de carcasa | [variante] (manufactura) | [variante] (manufactura) | [variante] (manufactura) |
[completar para los 6–7 parámetros]
════════════════════════════════════════════════════════
```

!!! tip "Pausa de reflexión — 3 minutos"
    El equipo lee la tabla completa. Para cada fila, responde: ¿hay alguna variante que Claude no consideró y que conocen de su investigación de campo o de sus entrevistas? Si la hay, la agregan a mano. La tabla es el punto de partida, no el límite del espacio de diseño.

---

### Prompt 2 — Claude: analogías tecnológicas

Este prompt va **después** de revisar la tabla morfológica — no antes. El equipo ya sabe en qué parámetros tiene opciones pobres o convencionales. Las analogías sirven para enriquecer esos parámetros específicos con soluciones que otros sectores ya validaron.

```
Actúa como consultor de innovación de diseño con experiencia
en transferencia de soluciones entre sectores. Tu metodología
es la analogía tecnológica: identificar problemas de experiencia
de usuario que ya fueron resueltos brillantemente en otros
sectores — no en el sector del producto que se diseña — y
extraer la lógica de solución que podría trasplantarse.
No buscas inspiración estética. Buscas mecanismos de interacción,
formas de instalación, sistemas de feedback y lógicas de uso
que ya funcionaron con usuarios reales en otro contexto.

Nuestro producto: [nombre + descripción en 2 oraciones]
Usuario: [perfil accionable — quién es y en qué contexto usa el producto]

Tenemos esta tabla morfológica preliminar:
[pegar la tabla del Prompt 1, con las variantes que el equipo
  ya enriqueció en la pausa de reflexión]

Los parámetros donde nuestras variantes son más convencionales
o donde no estamos satisfechos con las opciones:
[listar 2–3 parámetros específicos de la tabla donde
  quieren más inspiración]

Para cada parámetro señalado, encuentra 2–3 productos de
sectores completamente distintos al nuestro que hayan
resuelto el mismo problema de experiencia de forma brillante.

Para cada analogía:
· El producto y el sector de origen
· El problema de experiencia que resuelve
· La lógica de solución — cómo lo resuelve exactamente
· Cómo podría trasplantarse al parámetro de nuestro diseño

FORMATO DE SALIDA:

════════════════════════════════════════════════════════
ANALOGÍAS TECNOLÓGICAS — [nombre del producto]
════════════════════════════════════════════════════════

PARÁMETRO: [nombre del parámetro de la tabla]
Problema de experiencia: [qué necesita resolver este parámetro
  para el usuario específico]

Analogía 1: [producto] · Sector: [sector]
Problema que resuelve: [1 oración]
Lógica de solución: [cómo lo resuelve — el mecanismo, no la estética]
Trasplante posible: [cómo aplicar esa lógica a nuestro parámetro]

Analogía 2: [producto] · Sector: [sector]
[mismo formato]

────────────────────────────────────────────────────────
PARÁMETRO: [siguiente parámetro]
[mismo formato]

────────────────────────────────────────────────────────
VARIANTE SUGERIDA PARA AGREGAR A LA TABLA:
Parámetro: [cuál]
Variante nueva: [descripción] (manufactura: [proceso])
Viene de: [analogía que la inspiró]
════════════════════════════════════════════════════════
```

!!! tip "Pausa de reflexión — 3 minutos"
    El equipo revisa las analogías. Para cada una: ¿la lógica de solución tiene sentido para su usuario y su contexto? ¿Hay alguna variante nueva que agregar a la tabla antes de generar los conceptos? Agregar a mano en la tabla del Prompt 1 las variantes que emerjan. Con eso, la tabla está lista para el Prompt 3.

---

### Prompt 3 — Claude: los 3 conceptos de diseño

Este prompt recibe como input la tabla morfológica ya enriquecida con las variantes del equipo y las analogías. El equipo indica qué variantes prefieren en cada parámetro — Claude combina y describe los conceptos completos para los tres componentes del producto.

```
Actúa como diseñador industrial y UX designer con experiencia
en productos de hardware + software para mercados emergentes.
Tu especialidad es articular conceptos de diseño completos —
no solo el objeto físico, sino el sistema de tres componentes:
artefacto, app y página de lanzamiento — de forma que cada
componente refuerce la misma propuesta de valor y el mismo
lenguaje de diseño.

Nuestro producto: [nombre]
Propuesta de valor: [Versión 3 del prompt de semana 4]
Usuario y contexto: [perfil accionable + cómo usa el producto]

Esta es nuestra tabla morfológica final — con variantes propias
y variantes venidas de analogías tecnológicas:
[pegar la tabla enriquecida]

Estas son las combinaciones de variantes que queremos explorar
como conceptos. Para cada concepto indicamos qué variante
elegimos en cada parámetro:

CONCEPTO 1 — [nombre que le damos]
· Forma de carcasa: [variante elegida]
· Instalación: [variante elegida]
· Indicador de estado: [variante elegida]
· Material: [variante elegida]
· Interfaz física: [variante elegida]
· Energía: [variante elegida]
· [Parámetro 7]: [variante elegida]

CONCEPTO 2 — [nombre]
[mismo formato con variantes distintas]

CONCEPTO 3 — [nombre]
[mismo formato con variantes distintas]

Para cada concepto, desarrolla los tres componentes del producto:

ARTEFACTO FÍSICO:
· Experiencia de instalación: qué hace el usuario paso a paso
  para instalarlo desde la caja — máximo 5 pasos en lenguaje
  del usuario, no del ingeniero
· Experiencia de uso cotidiano: qué ve y hace el usuario en
  una interacción típica con el producto ya instalado
· Principios de diseño activos: cuáles de los 7 principios
  (Affordances, Contour bias, Consistencia, Constraints,
  Confirmación, Costo-beneficio) están presentes en este
  concepto y cómo se manifiestan

APP — pantalla principal:
· Estado normal: qué muestra cuando todo funciona bien
· Estado de alerta: qué cambia visualmente
· Acción principal: qué hace el usuario desde esa pantalla
· Qué NO muestra: información que se omite deliberadamente
  y por qué esa omisión es una decisión de diseño

LANDING PAGE — primer pantallazo:
· Headline: la primera frase que ve el visitante
· La imagen o visual principal que acompaña el headline
· El único call-to-action de la página

FORMATO DE SALIDA:

════════════════════════════════════════════════════════
CONCEPTO 1 — [nombre]
Combinación morfológica: [parámetro → variante para cada uno]
════════════════════════════════════════════════════════

ARTEFACTO
Instalación: [pasos numerados]
Uso cotidiano: [3 oraciones máximo]
Principios activos: [cuáles y cómo]

APP
Normal: · Alerta: · Acción principal:
Omisión deliberada: [qué y por qué]

LANDING PAGE
Headline: "[texto]"
Visual principal: [descripción]
CTA: "[texto del botón]"

────────────────────────────────────────────────────────
CONCEPTO 2 — [nombre]
[mismo formato]

────────────────────────────────────────────────────────
CONCEPTO 3 — [nombre]
[mismo formato]
════════════════════════════════════════════════════════
```

!!! tip "Pausa de reflexión — 3 minutos antes de la Matriz de Pugh"
    El equipo lee los 3 conceptos completos. ¿Cuál les genera más preguntas? ¿Cuál les preocupa más desde manufactura? ¿Cuál creen que su usuario preferiría? No decidir todavía — esas intuiciones son los criterios que van a poner en la Matriz de Pugh.



### Prompt 4 — Claude: genera los prompts de render para Midjourney e Imagen 3

Claude tiene todo el contexto acumulado de la sesión y de las semanas anteriores. En lugar de que el equipo construya el prompt de render desde cero — con el riesgo de dejar fuera información crítica — Claude toma todo lo que ya se trabajó y produce dos prompts optimizados: uno para Midjourney y uno para Imagen 3 de Google.

```
Actúa como un director de arte con experiencia en crear prompts
de render para herramientas de IA generativa de imagen aplicadas
al diseño industrial de producto. Conoces en profundidad la
sintaxis y las fortalezas de Midjourney v6 y de Imagen 3 de
Google — son herramientas distintas que responden a estilos de
prompt distintos:

Midjourney: responde mejor a descriptores en cadena separados
por comas, con parámetros técnicos al final (--ar, --style,
--v). Es espectacular visualmente pero tiende a interpretar
creativamente lo que no está explícito — necesita restricciones
claras para mantenerse fiel al concepto.

Imagen 3 (Google): responde mejor a lenguaje descriptivo fluido
en párrafos cortos con intención clara. Más fiel al texto cuando
el objeto es industrial y específico — menos tendencia a
"embellecer" con formas no pedidas. Ideal para evaluar si el
concepto comunica lo que debe comunicar.

Tu trabajo es tomar toda la información del equipo y producir
dos prompts listos para copiar y pegar — uno para cada
herramienta. El objetivo del render no es espectáculo visual:
es hacer visible la dirección de diseño para poder evaluarla
antes de invertir horas en CAD.

INFORMACIÓN DEL EQUIPO:

Del perfil de segmento y contexto de uso (semana 4):
Usuario: [perfil accionable — quién es, edad aproximada, dónde
  usa el producto, en qué condiciones ambientales]
Entorno físico de uso: [descripción del espacio real donde vive
  el producto — campo, taller, cocina, consultorio, etc.]
Nivel de sofisticación tecnológica del usuario: [alto / medio / bajo
  — esto define si el producto debe verse como herramienta
  de campo o como electrónica de consumo]

De la tabla morfológica y el concepto elegido (Prompts 1, 2 y 3):
Nombre del concepto: [nombre evocador]
Forma de la carcasa: [variante elegida — con dimensiones aproximadas]
Material y acabado: [variante elegida]
Método de instalación: [cómo se instala — define la posición en el render]
Indicador de estado: [tipo, posición y color]
Interfaz física: [botones, textura, touchpoints visibles]
Analogía tecnológica que inspiró el diseño: [de qué sector vino
  la inspiración — define el lenguaje visual de referencia]

De los principios de diseño (Bloque 2 de semana 6):
Contour bias aplicado: [nivel de curvatura — muy redondeado /
  moderado / apenas suavizado en aristas]
Affordances principales: [qué comunica la forma antes de que
  el usuario la toque — qué se clava, qué se agarra, qué se presiona]
Confirmación visible: [cómo se ve en el render que el dispositivo
  tiene un indicador de estado activo]

De la arquitectura del sistema (semana 5):
Tamaño relativo al hardware interno: [qué tan compacto debe ser
  el objeto dado el microcontrolador y sensores que contiene]
Restricciones de IP o resistencia ambiental del PDS: [qué
  condiciones ambientales debe comunicar visualmente el producto]

Ángulo de render preferido: [frontal / tres cuartos / en contexto
  de uso / explotar vista — si no están seguros, tres cuartos]

Con toda esta información genera exactamente dos outputs:

FORMATO DE SALIDA:

════════════════════════════════════════════════════════
PROMPT PARA MIDJOURNEY v6
════════════════════════════════════════════════════════
[El prompt completo listo para copiar y pegar en Midjourney.
Estructura: descriptores visuales en cadena, del objeto al
contexto, de la forma a la iluminación, restricciones al final.
Terminar con parámetros técnicos: --ar 4:3 --style raw --v 6]

Por qué funciona este prompt en Midjourney:
[2 líneas — qué restricciones específicas se pusieron para
evitar que Midjourney interprete creativamente lo que
debe mantenerse fiel al concepto]

════════════════════════════════════════════════════════
PROMPT PARA IMAGEN 3 (Google AI Studio / Vertex AI)
════════════════════════════════════════════════════════
[El prompt completo listo para copiar y pegar en Imagen 3.
Estructura: párrafos cortos descriptivos, del objeto al entorno,
de los materiales a la iluminación. Lenguaje fluido, no lista
de atributos.]

Por qué funciona este prompt en Imagen 3:
[2 líneas — en qué aspectos Imagen 3 va a ser más fiel que
Midjourney para este concepto específico]

════════════════════════════════════════════════════════
QUÉ EVALUAR EN EL RENDER
════════════════════════════════════════════════════════
[3 preguntas concretas que el equipo debe hacerse al ver
el resultado — no "¿les gusta?" sino preguntas sobre si
el render comunica los principios de diseño correctos:
affordances, contour bias, confirmación]
════════════════════════════════════════════════════════
```

!!! tip "El render como filtro rápido, no como decisión final"
    Si al ver el render el equipo dice "no es esto" — el concepto necesita revisarse antes de entrar a Pugh, no después. Cambiar una variante morfológica ahora cuesta cero. Cambiarla después del CAD cuesta días.

!!! note "Midjourney vs. Imagen 3"
    Imagen 3 tiende a ser más fiel cuando el objeto es industrial y específico. Midjourney produce renders más espectaculares pero a veces agrega lo que no pediste. Generar en ambas y comparar toma 5 minutos — vale la pena antes de comprometerse con una dirección.

---

## Bloque 5 — Matriz de Pugh: selección del concepto de diseño
**Duración: 20 min · Min 1:10 – 1:30**

### Por qué la Matriz de Pugh y no solo "el que más nos gusta"

La Matriz de Pugh es una herramienta de selección de concepto desarrollada por Stuart Pugh en los años 80 y todavía estándar en diseño de producto industrial. Su principio: comparar múltiples conceptos contra los mismos criterios ponderados, usando un concepto de referencia como datum.

Por qué no alcanza con "el que más nos gusta":
- La preferencia del equipo raramente coincide con la preferencia del usuario
- Los equipos de ingeniería tienden a favorecer el concepto técnicamente más sofisticado — que no siempre es el más usable
- Sin criterios explícitos, las discusiones de diseño se resuelven por quién habla más fuerte
- La Matriz de Pugh obliga a nombrar los criterios antes de evaluar — eliminando el sesgo de acomodar los criterios al concepto favorito

### Los criterios de evaluación — la decisión más importante de la matriz

Los criterios deben incluir **obligatoriamente** los dos tipos:

**Criterios de deseabilidad (¿el usuario lo preferirá?):**
- Facilidad de instalación sin instrucciones
- Legibilidad del estado del dispositivo sin abrir la app
- Confianza que inspira el material y el acabado
- Tamaño apropiado para el contexto de uso
- Facilidad de limpieza y mantenimiento

**Criterios de factibilidad (¿podemos construirlo?):**
- Costo de manufactura por unidad a 10 unidades
- Complejidad del proceso de ensamble
- Disponibilidad de materiales en México
- Compatibilidad con el proceso de manufactura disponible (lab / JLCPCB)
- Tiempo de fabricación del prototipo

!!! warning "Lo no negociable"
    La Matriz de Pugh no puede estar dominada por criterios técnicos. Un concepto perfectamente factible que el usuario no va a adoptar no crea valor. Si la matriz tiene 5 criterios de factibilidad y 1 de deseabilidad, el resultado va a favorecer el concepto más fácil de construir — que no es necesariamente el correcto.

    **La regla:** mínimo 2 criterios de deseabilidad y 2 de factibilidad, con peso explícito asignado a cada uno. Los criterios de deseabilidad deben sumar al menos el 40% del peso total.

### Cómo funciona la Matriz de Pugh

1. Se elige un concepto de referencia (datum) — generalmente el más convencional o el que el equipo consideraría "la opción obvia"
2. Cada concepto alternativo se evalúa contra el datum criterio por criterio:
   - **+** = mejor que el datum en este criterio
   - **–** = peor que el datum
   - **S** = igual al datum (same)
3. Los **+** y **–** se suman ponderados por el peso del criterio
4. El concepto con mayor puntuación ponderada es el candidato — no la decisión final, sino el punto de partida para la discusión

### Prompt 5 — Claude: construcción de la Matriz de Pugh

```
Actúa como un ingeniero de producto con experiencia en
selección de concepto usando la Matriz de Pugh para productos
de hardware + software en etapa de prototipo temprano. Tu
metodología asegura que los criterios de evaluación representen
tanto la perspectiva del usuario (deseabilidad) como la del
equipo de desarrollo (factibilidad), con peso explícito para
cada uno. No permites que la matriz esté dominada por criterios
técnicos cuando el producto va dirigido a un usuario no técnico.

Somos un equipo de ingeniería en México. Tenemos 3 conceptos
de diseño para evaluar:

CONCEPTO 1 — [nombre]: [descripción en 2 oraciones]
CONCEPTO 2 — [nombre]: [descripción en 2 oraciones]
CONCEPTO 3 — [nombre]: [descripción en 2 oraciones — este es el datum]

Nuestro usuario: [perfil accionable — quién es, cómo usa el
  producto, qué le importa en el momento de instalación y uso]

Nuestras restricciones de manufactura:
· Proceso disponible: [laboratorio / JLCPCB+PCBA / otro]
· Presupuesto por unidad: [MXN]
· Volumen objetivo: [N unidades para prueba de mercado]

Construye la Matriz de Pugh con estas especificaciones:

1. CRITERIOS: define 8–10 criterios de evaluación que incluyan
   obligatoriamente:
   · Mínimo 3 criterios de DESEABILIDAD (perspectiva del usuario)
   · Mínimo 3 criterios de FACTIBILIDAD (perspectiva del equipo)
   Para cada criterio: nombre, descripción de 1 línea, y peso
   (los pesos de todos los criterios deben sumar 100).
   Los criterios de deseabilidad deben sumar mínimo 40% del peso.

2. EVALUACIÓN: compara el Concepto 1 y 2 contra el Concepto 3
   (datum) en cada criterio. Usa: + (mejor), – (peor), S (igual).
   Justifica brevemente cada evaluación no obvia.

3. PUNTUACIÓN: calcula el puntaje ponderado de cada concepto
   (+ = +peso, – = –peso, S = 0). Suma total ponderada.

4. ANÁLISIS: ¿qué dice la puntuación? ¿Hay criterios donde
   todos los conceptos empatan que podrían ajustarse en el
   concepto ganador? ¿Hay un criterio de alto peso donde el
   concepto ganador es débil — riesgo a mitigar?

FORMATO DE SALIDA:

════════════════════════════════════════════════════════
MATRIZ DE PUGH
Datum: [nombre del Concepto 3]
════════════════════════════════════════════════════════

CRITERIOS Y PESOS:

DESEABILIDAD (peso total: [X]%)
· [criterio] ([peso]%): [descripción]
· [criterio] ([peso]%): [descripción]
· [criterio] ([peso]%): [descripción]

FACTIBILIDAD (peso total: [Y]%)
· [criterio] ([peso]%): [descripción]
· [criterio] ([peso]%): [descripción]
· [criterio] ([peso]%): [descripción]

[otros criterios si aplica]

────────────────────────────────────────────────────────
MATRIZ DE EVALUACIÓN:

| Criterio (peso) | C1 — [nombre] | C2 — [nombre] | C3 — datum |
|-----------------|:-------------:|:-------------:|:----------:|
| [criterio] ([%]) | + / – / S | + / – / S | datum |
[completar para todos los criterios]

Puntuación ponderada:
C1: [suma] · C2: [suma] · C3 (datum): 0

────────────────────────────────────────────────────────
CONCEPTO GANADOR: [cuál]
Por qué ganó: [2 oraciones — qué combinación de criterios lo llevó]

RIESGO PRINCIPAL: [el criterio de mayor peso donde el concepto
  ganador es débil o empata con los demás — cómo mitigarlo]

ITERACIÓN RECOMENDADA: [si hay atributos del Concepto X que
  podrían adoptarse en el ganador para mejorar su puntuación]
════════════════════════════════════════════════════════
```

---

## Bloque 6 — Taller B: primer boceto técnico del concepto elegido
**Duración: 20 min · Min 1:30 – 1:50**

### Del concepto elegido al compromiso de diseño

La Matriz de Pugh produjo un ganador. Ahora comienza algo diferente: el equipo se compromete con ese concepto al nivel de detalle suficiente para entrar a CAD la semana siguiente. No es el modelo final — es el boceto técnico que define las decisiones de diseño que el CAD va a materializar.

> *"Un boceto técnico no es un dibujo artístico — es un conjunto de decisiones. Cada línea que dibujan dice: 'elegimos esto en lugar de aquello'. El modelo CAD de la semana siguiente es la consecuencia de este boceto, no el lugar donde se toman las decisiones de diseño."*

**La diferencia entre boceto conceptual y boceto técnico:**

```
BOCETO CONCEPTUAL           BOCETO TÉCNICO
(lo que hicieron antes)     (lo que hacen ahora)
────────────────────        ──────────────────────────────
"Forma cilíndrica"          Cilindro de ∅28mm × 220mm
"Material robusto"          ABS 3mm de espesor, radio int. 11mm
"LED de estado"             LED RGB Ø5mm en la cara superior,
                            accesible desde el exterior
"Se instala en tierra"      Punta cónica a 45°, longitud 80mm,
                            con aros de retención cada 20mm
"Conector de carga"         USB-C centrado en la base,
                            protegido con tapa de goma IP67
```

### Lo que el boceto técnico debe definir

**Para el artefacto físico:**
- Dimensiones principales con cotas (no exactas — aproximadas con intención)
- Vistas necesarias: al menos frontal, lateral y una sección transversal si hay componentes internos
- Materiales y procesos de cada parte
- Puntos de ensamble y cómo se abren para mantenimiento o recarga
- Dónde están los conectores, LEDs, botones — y por qué ahí
- Cómo se relaciona con el entorno de uso (suelo, pared, manguera, mesa)

**Para la interfaz de la app (wireframe de baja fidelidad):**
- La pantalla principal: qué muestra y qué no
- El flujo de instalación: los pasos que el usuario sigue la primera vez
- La pantalla de alerta: cómo se ve cuando hay un problema

### Prompt 6 — Claude: crítica técnica del boceto

El equipo hace el boceto en papel primero. Luego lo describe a Claude para obtener crítica técnica antes de comprometerse:

```
Actúa como un ingeniero de diseño industrial con experiencia
en revisar bocetos técnicos de productos de hardware en etapa
de pre-CAD. Tu especialidad es identificar decisiones de diseño
que van a generar problemas en manufactura, en uso real, o en
el ensamble — antes de que aparezcan en el modelo 3D. Eres
directo: señalas el problema y propones la solución específica.
No corriges todo — priorizas los 3 problemas más importantes.

Somos un equipo de ingeniería en México. Elegimos el siguiente
concepto de diseño con la Matriz de Pugh y hemos hecho el
primer boceto técnico. Necesitamos crítica antes de entrar a CAD.

Concepto elegido: [nombre]
Descripción: [2 oraciones de qué es y cómo se usa]
Usuario y contexto de uso: [quién, dónde, cómo]

Descripción del boceto técnico del artefacto:
[describir en texto lo que muestra el boceto:
  - forma general y dimensiones aproximadas
  - materiales indicados para cada parte
  - dónde están los componentes electrónicos principales
  - método de instalación y fijación
  - puntos de acceso para mantenimiento o recarga
  - indicadores visuales o físicos para el usuario]

Descripción del wireframe de la app:
[describir la pantalla principal y el flujo de instalación]

Analiza el boceto y entrega:

1. PROBLEMAS CRÍTICOS (máximo 3):
Los problemas que, si no se corrigen antes de entrar a CAD,
van a causar retrabajo significativo o van a hacer el producto
inutilizable o imposible de fabricar.

Para cada problema:
· Qué es el problema exactamente
· Por qué es crítico (consecuencia si no se corrige)
· Solución específica (no genérica)

2. PREGUNTAS SIN RESOLVER:
Las decisiones de diseño que el boceto no define y que el CAD
va a necesitar. El equipo debe resolverlas antes de modelar.

3. UNA FORTALEZA DEL DISEÑO:
Lo que el boceto hace bien — para que el equipo sepa qué no
cambiar cuando empiece a iterar.

FORMATO DE SALIDA:

════════════════════════════════════════════════════════
CRÍTICA DE BOCETO TÉCNICO
Concepto: [nombre]
════════════════════════════════════════════════════════

PROBLEMA 1 — [nombre del problema]
Qué es: [descripción específica]
Por qué es crítico: [consecuencia]
Solución: [qué cambiar exactamente]

PROBLEMA 2 — [nombre del problema]
[mismo formato]

PROBLEMA 3 — [nombre del problema]
[mismo formato]

────────────────────────────────────────────────────────
PREGUNTAS SIN RESOLVER:
· [pregunta 1 — decisión que el boceto no define]
· [pregunta 2]
· [pregunta 3]

FORTALEZA DEL DISEÑO:
[Qué hace bien el boceto — 2 oraciones]

LISTO PARA CAD: sí / con ajustes menores / necesita revisión
════════════════════════════════════════════════════════
```

---

## Bloque 7 — Defensa de concepto
**Duración: 10 min**

### Formato — 3 minutos por equipo


**Estructura de los 3 minutos:**

```
Minuto 1: El concepto elegido
"Elegimos [nombre del concepto]. Es [forma] hecho de [material],
se instala [método]. El usuario sabe que funciona porque [indicador]."

Minuto 2: Por qué este y no los otros
"Lo elegimos sobre los otros dos conceptos porque en la Matriz
de Pugh ganó en [criterio de deseabilidad más importante] y en
[criterio de factibilidad más importante]. El Concepto X tenía
[ventaja] pero perdió en [criterio]."

Minuto 3: El riesgo que asumen
"El riesgo principal de este concepto es [problema identificado
en la crítica del boceto]. Lo vamos a mitigar haciendo [qué]."
```

**Ya te preguntaste:**

- *"¿Por qué ese material y no [alternativa obvia]? ¿Ya verificaron el precio y disponibilidad?"*
- *"¿El usuario de 50 años que describieron en su segmento puede instalar esto sin instrucciones? ¿Lo probaron?"*
- *"¿La pantalla principal que describieron cabe en un teléfono Android de 5 pulgadas? ¿Ya hicieron el wireframe a escala?"*
- *"¿El concepto ganador en Pugh mejoró con algún atributo de los otros dos? Si no, ¿por qué no?"*

**Criterios de aprobación del concepto:**

✅ **Aprobado** — El equipo puede describir el concepto en 1 oración sin mencionar cómo funciona técnicamente. La Matriz de Pugh tiene criterios de deseabilidad y factibilidad con peso explícito. El boceto define dimensiones aproximadas y materiales.

⚠️ **Aprobado con ajuste** — El concepto está claro pero la Matriz tiene menos de 2 criterios de deseabilidad, o el boceto no define materiales, o el equipo no puede justificar la decisión de diseño principal.

❌ **Regresado** — No hay 3 conceptos evaluados (solo uno con variaciones menores), o la Matriz está dominada por criterios técnicos, o el "boceto técnico" es una descripción verbal sin dimensiones ni materiales.

---

## Tarea en casa (4 horas)

| Tarea | Tiempo | Entregable |
|-------|:------:|-----------| 
| Generar conceptos adicionales si el resultado en clase fue insuficiente — mínimo 3 en total con Prompt 1 | 1h | Tabla morfológica + 3 conceptos descritos |
| Matriz de Pugh completa con criterios ponderados, evaluación justificada y concepto ganador | 1h | Matriz en la plantilla del formato de salida del Prompt 3 |
| Boceto técnico del concepto elegido con cotas aproximadas, materiales indicados y sección transversal | 1h | Foto del boceto en papel o boceto digital (Procreate / papel milimétrico / draw.io) |
| Wireframe de baja fidelidad de la pantalla principal de la app y el flujo de instalación | 1h | Wireframe en papel o Figma / draw.io (no diseño final — baja fidelidad) |

### Entregable de la semana

```
ENTREGABLE SEMANA 6
Equipo: ________ Concepto: ________

1. TABLA MORFOLÓGICA
   [6–7 parámetros × 3 variantes]

2. LOS 3 CONCEPTOS DE DISEÑO
   Para cada uno: nombre evocador, combinación morfológica,
   experiencia de instalación, experiencia de uso cotidiano,
   analogía tecnológica, implicación de manufactura principal

3. MATRIZ DE PUGH
   Criterios con peso explícito (mín. 2 deseabilidad + 2
   factibilidad, deseabilidad ≥ 40% del peso total)
   Evaluación: +/–/S con justificación para cada celda
   Puntuación ponderada y concepto ganador

4. BOCETO TÉCNICO DEL CONCEPTO ELEGIDO
   · Vistas: frontal, lateral, sección transversal
   · Dimensiones aproximadas con cotas
   · Materiales indicados por parte
   · Ubicación de componentes principales

5. WIREFRAME DE LA APP
   · Pantalla principal (estado normal + estado de alerta)
   · Flujo de instalación (primeros 3 pasos)
```

---

## Bibliografía y recursos de la semana

### Lecturas obligatorias

**Principios de diseño**

Norman, D. A. (2013). *The Design of Everyday Things* (edición revisada y ampliada). Basic Books.
→ Capítulos 1 y 2: affordances, feedback, constraints y mappings. El libro de referencia de la semana — los principios que se trabajaron en el Bloque 2 vienen directamente de aquí.

Bar, M., & Neta, M. (2006). Humans prefer curved visual objects. *Psychological Science*, 17(8), 645–648.
→ El paper original detrás del principio de Contour bias. Dos páginas. Vale leerlo para entender que no es opinión estética sino evidencia experimental.

**Selección de concepto**

Pugh, S. (1991). *Total Design: Integrated Methods for Successful Product Engineering*. Addison-Wesley.
→ Capítulo 6: la Matriz de Pugh en su formulación original. El método que se aplica en el Bloque 5.

Ulrich, K. T., & Eppinger, S. D. (2015). *Product Design and Development* (6.ª ed.). McGraw-Hill.
→ Capítulo 7: concept generation y concept selection. El estándar académico del proceso que se sigue en esta semana. Disponible en biblioteca universitaria.

**Morfología y generación de conceptos**

Cross, N. (2011). *Design Thinking: Understanding How Designers Think and Work*. Berg Publishers.
→ Capítulo 4: systematic methods for concept generation — morfología y sus variantes. Acceso libre en muchas bibliotecas digitales universitarias.

---

### Lecturas recomendadas

Kim, W. C., & Mauborgne, R. (2015). *Blue Ocean Strategy* (edición ampliada). Harvard Business Review Press.
→ Capítulo 3: el lienzo estratégico y las cuatro acciones. Referencia del análisis competitivo de semana 4 que sigue siendo relevante cuando el concepto de diseño se posiciona frente a competidores.

IDEO. (2015). *The Field Guide to Human-Centered Design*. IDEO.org.
→ Disponible en descarga gratuita en: [ideo.com/post/field-guide-to-human-centered-design](https://www.ideo.com/post/field-guide-to-human-centered-design)
→ Sección "Ideation": técnicas de generación de concepto que complementan la morfología.

---

### Herramientas de la semana

| Herramienta | Uso en esta semana | Acceso |
|-------------|-------------------|--------|
| **Claude** (Anthropic) | Prompts 1, 2, 3, 4, 5 y 6 | claude.ai |
| **Midjourney** | Render conceptual del concepto elegido | midjourney.com (requiere suscripción) |
| **Imagen 3** (Google) | Render conceptual — alternativa a Midjourney | aistudio.google.com (gratuito con cuenta Google) |
| **draw.io / diagrams.net** | Boceto técnico digital y wireframe de app | app.diagrams.net (gratuito, sin instalación) |
| **Figma** | Wireframe de la app si se prefiere sobre draw.io | figma.com (plan gratuito disponible) |

---

### Para ir más lejos — opcional

Lidwell, W., Holden, K., & Butler, J. (2010). *Universal Principles of Design* (2.ª ed.). Rockport Publishers.
→ Los 7 principios de la sesión están aquí con más profundidad, más contexto histórico y más ejemplos de aplicación en producto. Un libro de referencia que vale tener cerca durante todo el semestre de diseño.

Kolko, J. (2011). *Exposing the Magic of Design: A Practitioner's Guide to the Methods and Theory of Synthesis*. Oxford University Press.
→ Para equipos que quieren entender por qué la síntesis de información de usuario (lo que hicieron en semanas 2–4) conecta con las decisiones de diseño de esta semana.

---

## Lo que el equipo debe poder responder al salir

- [ ] ¿Pueden describir el concepto elegido en una oración sin mencionar cómo funciona técnicamente?
- [ ] ¿Por qué ese concepto y no los otros dos? — con referencia a criterios específicos de la Matriz de Pugh
- [ ] ¿Cuál es el parámetro de diseño más crítico de su concepto y qué pasa si ese parámetro cambia?
- [ ] ¿Cuál es el criterio de deseabilidad con mayor peso en su matriz y cómo saben que su concepto lo cumple?


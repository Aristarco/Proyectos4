# Búsqueda de Oportunidades

## Objetivo de la semana

*Que el equipo identifique una oportunidad de producto concreta, arraigada en un problema observable en mercados latinoamericanos, usando IA como acelerador de búsqueda y síntesis — y elija la oportunidad que desarrollará durante el semestre.*

## Blueprint: **Creación de valor** · DVF: 🔴 Deseable

Esta semana el equipo responde la pregunta más importante del semestre antes de escribir una sola línea de código o hacer un solo modelo 3D: 

!!! tip "¿Existe un problema real que vale la pena resolver?"
    Todo lo que se construya después depende de la calidad de la respuesta que encuentren hoy.

## Cómo leer este documento

Cada paso tiene dos modos de instrucción que corren en paralelo:

🔍 **Modo Explorador** — equipos que buscan oportunidad desde cero

🔬 **Modo Estresor** — equipos que ya tienen una idea y necesitan cuestionarla

# Vista rápida de los 7 pasos

| **#** | **Paso** | **Tiempo** | **IA** |
| --- | --- | --- | --- |
| 1 | Búsqueda de oportunidades en LATAM con IA | 20 min | Perplexity + Claude / otra |
| 2 | Síntesis de insights con IA | 25 min | Claude / otra → Perplexity |
| 3 | Pain-Gain Map | 25 min | Claude / otra |
| 4 | SCAMPER + Remix de ideas | 20 min | Claude / otra |
| 5 | Validación preliminar de deseabilidad | 15 min | otra → Perplexity |
| 6 | Criterios de selección de oportunidad | 10 min | Sin IA |
| 7 | Elección y defensa de la oportunidad | 5 min / Tarea | Opcional |

## Paso 1 — Búsqueda de oportunidades en LATAM con IA 

Los alumnos que no tienen aún una idea de negocio entran en el Modo Explorador, buscaremos una serie de problemas **REALES** antes de elegir nada.

Para aquellos que ya tienen un proyecto que quieren desarrollar diremos que están en Modo Estresor, esto es necesitan ver su idea desde afuera: ¿qué tan saturado está ese espacio? ¿qué problemas adyacentes existen que no habían visto? ¿hay ángulos de negocio que su idea ya tiene pero que aún no explotan?

Usamos dos IAs en paralelo porque cada una tiene un perfil distinto y se compensan:


|   | **Perplexity** | **Claude** |
| --- | --- | --- |
| **Fortaleza** | Datos reales, fuentes verificables, cifras de mercado actualizadas | Síntesis creativa, conexiones no obvias, reencuadre de problemas |
| **Debilidad** | Tiende a lo obvio, repite el consenso del mercado | Sin datos propios — necesita que le des contexto |
| **Uso en este paso** | Anclar en realidad: ¿el problema existe, qué tan grande es, quién ya lo ataca? | Romper el consenso: ¿qué nadie está viendo, qué ángulo es contraintuitivo? |

Perplexity te dice qué existe. Claude te dice qué podría existir. Los necesitas a los dos para no quedarte ni con datos sin imaginación ni con imaginación sin datos.

!!! Warning "Instrucción general al grupo"
    "Vamos a buscar oportunidades con dos IAs en paralelo — no son intercambiables, cada una tiene un trabajo diferente. Perplexity para anclar en datos reales; Claude para romper el pensamiento obvio. Lean su tarjeta de modo y arranquen. Tienen 12 minutos de trabajo, luego compartimos hallazgos."

## **PROMPTS:** 

# 🔍 Modo Explorador

Ronda 1 — **Perplexity:** anclar en realidad (6 min)


Actúa como un analista senior de oportunidades de negocio con
experiencia en mercados emergentes de América Latina, especializado
en identificar problemas donde una solución digital-física integrada 
puede generar tracción comercial real. Tu metodología combina
análisis de brechas de mercado, detección de comportamientos
no atendidos y evaluación de disposición a pagar en contextos
de recursos limitados.

Somos un equipo de emprendedores en México desarrollando un
negocio basado en producto digital-físico. Nuestro stack incluye:
desarrollo de aplicaciones móviles y web con IA integrada,
hardware conectado (ESP32, Raspberry Pi, sensores, actuadores,
comunicaciones BLE/MQTT/WiFi), diseño y manufactura de producto
físico (CAD, impresión 3D, PCB), e integración de modelos de IA
tanto en dispositivo como en la nube. El resultado que buscamos
es un negocio con tres componentes articulados: una aplicación
con IA, un artefacto físico inteligente y una página web de
venta con propuesta de valor clara. Tenemos seis meses para
llegar a un MVP comercializable y validado.

Identifica 4 oportunidades de negocio no resueltas o mal resueltas
en el sector de *[ELIGE el área que hayas pensado o bien uno de estos que te atraiga: salud comunitaria / manufactura artesanal / logística urbana / agua y medio ambiente / seguridad física / educación técnica]* en México y América Latina que cumplan estas
condiciones:

- El problema ocurre de forma frecuente (semanal o diaria) y
  tiene un costo observable para el usuario

- Existe evidencia de que la gente ya paga por soluciones
  imperfectas o pierde tiempo y dinero por no tenerlas

- La oportunidad se puede atacar con una solución que combine
  inteligencia artificial, interfaz digital y componente físico

- El mercado potencial en LATAM supera las 50,000 personas o 
  negocios con disposición real a pagar

Para cada oportunidad entrega:

1. El problema concreto: quién lo tiene, cuándo ocurre, cuánto 
   le cuesta no resolverlo

2. La solución actual más usada y por qué sigue siendo insuficiente

3. Por qué una solución que combine app con IA + artefacto físico
   inteligente es el enfoque correcto para este problema

4. Estimado del tamaño de mercado en LATAM con fuente 

No propongas soluciones tecnológicas todavía. Solo problemas

con contexto de mercado suficiente para evaluar su potencial.

--------------------------------------------------------------------------------

**Ronda 2 — Claude / otra:** romper el consenso (6 min)


Una vez que Perplexity te devuelve las 4 oportunidades, llevas los resultados a Claude:


Actúa como un innovador con experiencia en detectar oportunidades de negocio que el mercado ignora porque parecen demasiado nicho,
demasiado obvias o demasiado difíciles. Tu enfoque es el pensamiento lateral aplicado a mercados emergentes: buscas lo que todos ven pero nadie está atacando, y lo que nadie ve porque está demasiado cerca. Tienes especial habilidad para imaginar negocios donde la combinación de inteligencia artificial, interfaces digitales y objetos físicos inteligentes crea una propuesta de valor que ninguno de los tres componentes podría crear por separado.

Estamos construyendo un negocio en México con tres componentes

articulados: una aplicación con IA, un artefacto físico inteligente y una página web de venta. Nuestras capacidades abarcan tanto el desarrollo de software e IA como el diseño y manufactura de hardware conectado. Tenemos seis meses para llegar a MVP comercializable.

Estas son las 4 oportunidades que identificamos a través de análisis de mercado:

*[PEGA AQUÍ los resultados de Perplexity]*

Necesito que hagas 3 cosas:

1. ROMPE EL CONSENSO: ¿Cuál de las 4 oportunidades está siendo 
   atacada de la forma más predecible? ¿Qué ángulo contraintuitivo
   nadie está viendo porque todos asumen lo mismo sobre ese
   problema? ¿Cómo cambiaría la propuesta de valor si el artefacto
   físico, la app y la web de venta se articularan de una forma
   no convencional?

2. ENCUENTRA EL PROBLEMA OCULTO: Debajo de estas 4 oportunidades
   superficiales, ¿cuál es el problema raíz que, si se resolviera
   con una solución digital-física integrada, haría innecesarios
   2 o más de estos problemas al mismo tiempo? ¿Qué negocio
   emerge de resolver ese problema raíz?

3. EL SEGMENTO IGNORADO: ¿Hay algún grupo de usuarios que tiene
   estos problemas con el doble de intensidad pero que no aparece
   en los análisis de mercado convencionales porque no tiene voz
   digital — no escribe en foros, no da entrevistas, no aparece
   en reportes — pero que claramente existe en la realidad
   mexicana y tiene disposición real a pagar?

No me repitas lo que Perplexity ya encontró. Dame lo que el análisis de mercado convencional no puede ver.

### Qué anotar al final de los 12 minutos

De Perplexity: las 2 oportunidades con más evidencia de mercado (datos, tamaño, costo observable del problema).

De Claude: el ángulo no obvio más prometedor — puede ser una nueva lectura de una oportunidad ya identificada, el problema raíz oculto, o el segmento ignorado.

Llevas estos 3 insumos al Paso 2.

----------------------------------------------------------------------------------------------------------------------------------

# 🔬 Modo Estresor

Ronda 1 — **Perplexity:** auditoría de ecosistema (6 min)

Actúa como un analista de inteligencia competitiva especializado en negocios de producto digital-físico en América Latina, con experiencia en evaluar si una idea tiene espacio real en el mercado o si está entrando a un ecosistema ya saturado o con barreras no obvias. Tu metodología incluye análisis de actores existentes, detección de brechas no cubiertas, identificación de mercados adyacentes y evaluación de timing de mercado.

Somos un equipo de emprendedores en México construyendo un negocio basado en tres componentes articulados: una aplicación con IA, un artefacto físico inteligente y una página web de venta. Nuestras capacidades abarcan desarrollo de software e IA, hardware conectado (ESP32, Raspberry Pi, sensores, PCB) y manufactura de producto físico. Tenemos seis meses para llegar a MVP comercializable.

Nuestra idea actual es:

*[DESCRIBE TU IDEA EN 3–4 ORACIONES: qué hace, para quién, cómo se articulan los tres componentes — app, artefacto y página de venta — y qué problema cree el equipo que resuelve]*

Responde con datos verificables y fuentes:

1. SATURACIÓN DEL ESPACIO: ¿Quién más está atacando este problema
   en LATAM o en el mundo con soluciones que combinen software, 
   IA y hardware? Menciona al menos 3 actores reales con su nivel 
   de tracción actual.

2. BRECHAS NO CUBIERTAS: En el mismo espacio donde opera nuestra 
   idea, ¿qué subproblemas o segmentos de usuario están siendo 
   ignorados por los actores actuales? Dame 3 brechas concretas 
   con evidencia de que son reales y de que representan disposición 
   a pagar.

3. MERCADOS ADYACENTES: ¿Hay sectores o tipos de usuario donde 
   una solución como la nuestra — app con IA + artefacto físico 
   + canal de venta digital — podría aplicarse con adaptaciones 
   menores y donde el problema sea igual o más intenso?

4. TIMING: ¿Hay señales de que este mercado está listo para una 
   solución integrada digital-física ahora? ¿Qué tendencia 
   reciente lo indica o lo contradice?


Ronda 2 — **Claude / Otra:** estrés profundo de la idea (6 min)

Actúa como un inversionista con experiencia en negocios de producto digital-físico en mercados emergentes, conocido por hacer las preguntas que los equipos no quieren escuchar pero necesitan responder antes de comprometer seis meses en una idea.

No eres destructivo — eres brutalmente honesto porque te importa que el negocio llegue a algo real y comercializable.

Somos emprendedores en México. Nuestra idea es:

*[DESCRIBE TU IDEA EN 3–4 ORACIONES]*

Nuestro modelo de negocio tiene tres componentes: una aplicación con IA, un artefacto físico inteligente y una página web de venta. 

Nuestras capacidades: desarrollo de software e IA, hardware conectado, manufactura de producto físico. Tenemos seis meses para llegar a MVP comercializable.

Este es el análisis de ecosistema que encontramos:

*[PEGA AQUÍ los resultados de Perplexity]*

Hazme el estrés que más necesito — no el más cómodo:

1. EL SUPUESTO MÁS PELIGROSO: ¿Cuál es el supuesto sobre el 
   usuario o el mercado que estamos dando por hecho y que, si 
   resulta falso, hace que toda la idea pierda sentido? ¿Cómo 
   lo probaríamos o refutaríamos en menos de una semana sin 
   construir nada?

2. LA ARISTA QUE NO VIMOS: Basándote en las brechas del análisis 
   de ecosistema, ¿hay una versión de nuestro negocio — 
   manteniendo los tres componentes pero cambiando el usuario 
   objetivo, el problema atacado o cómo se articulan app, 
   artefacto y canal de venta — que tenga un mercado más claro 
   o una propuesta de valor más fuerte? Descríbela como pitch 
   de 3 oraciones.

3. EL PIVOTE MÍNIMO: Si tuvieras que cambiar UNA sola cosa de 
   nuestra idea para hacerla significativamente más fuerte — 
   el usuario objetivo, el problema central, la forma en que 
   los tres componentes se relacionan entre sí, o el modelo 
   de ingresos — ¿qué cambiarías y por qué?

Sé específico. No me des frameworks — dame decisiones accionables.


**Qué anotar al final de los 12 minutos**

De Perplexity: las 2 brechas más concretas que los actores actuales no están cubriendo.

De Claude: el supuesto más peligroso que el equipo necesita probar, y la arista alternativa más prometedora.

Llevas estos 3 insumos al Paso 2.



## Paso 2 — Síntesis de insights con IA


El Paso 1 produjo datos: oportunidades con cifras de mercado, brechas identificadas, ángulos no obvios. El problema es que los datos dispersos no toman decisiones — los insights sí.

!!! tip "Insight 
    Un insight de negocio no es un dato recopilado ni una observación general. Es una afirmación específica que revela por qué un problema persiste, quién lo sufre más, qué lo hace difícil de resolver, y qué tan caro le resulta al usuario seguir sin solución. Un buen insight señala exactamente dónde existe la oportunidad de negocio — y hace que sea difícil ignorarla.

En este paso usamos dos IAs con roles distintos:

|   | Claude | Perplexity |
| --- | --- | --- |
| Trabajo | Sintetizar y estructurar los hallazgos del Paso 1 en insights accionables | Verificar y anclar los insights con datos reales cuando Claude los genera sin fuente |
| Cuándo usarlo | | Primero — para construir el insight | Segundo — para validar que el costo del problema y el tamaño de mercado del insight son reales |


### La diferencia entre dato e insight no es de forma — es de utilidad para tomar decisiones. El instructor muestra estos dos ejemplos en pantalla sin comentario adicional. Los equipos los leen y el instructor pregunta: "¿Cuál de los dos les dice qué hacer?"

| Esto es un dato | Esto es un insight |
| --- | --- |
| "Hay problemas de riego en agricultura de pequeña escala en México" | "Los agricultores de 1–5 hectáreas en Sonora toman decisiones de riego basadas en experiencia táctil — aprietan un puñado de tierra. Eso les genera pérdidas de 15–30% de cosecha por ciclo. Los sensores de humedad profesionales cuestan entre $200 y $2,000 USD — más de lo que ganan en un ciclo de cultivo de tomate. El problema no es falta de tecnología: es que la tecnología existente cuesta más de lo que el problema cuesta. Ahí está el espacio." |
| "Las tiendas pequeñas tienen problemas de seguridad" | "Las tiendas de abarrotes en zonas periurbanas de CDMX y GDL sufren robo hormiga por parte de empleados y clientes — no robo a mano armada. Las pérdidas representan entre $3,000 y $8,000 MXN mensuales según registros del INEGI. Los sistemas de CCTV profesionales cuestan $15,000–40,000 MXN de instalación. La solución actual es 'revisar la cámara cuando ya pasó algo' — reactiva, no preventiva. Nadie está usando visión por computadora + alerta en tiempo real a ese precio." |


### El insight nombra al usuario específico, cuantifica el costo del problema, explica por qué las soluciones actuales no bastan, y señala exactamente dónde está el espacio de negocio.


### 🔍 Modo Explorador

Ronda 1 — Claude: construir el insight (12 min)

Tomas los 3 insumos del Paso 1 (2 oportunidades con datos + 1 ángulo no obvio) y los llevas a Claude:

PROMPT

Actúa como un estratega de innovación con experiencia en traducir hallazgos de mercado en insights de negocio accionables para emprendedores que construyen productos digitales-físicos. Tu especialidad es encontrar la formulación exacta que revela por qué un problema persiste y dónde está el espacio real de negocio — no el espacio teórico.

Somos un equipo de emprendedores en México desarrollando un negocio con tres componentes articulados: una aplicación con IA, un artefacto físico inteligente y una página web de venta. Nuestras capacidades abarcan desarrollo de software e IA, hardware conectado (ESP32, Raspberry Pi, sensores, PCB) y manufactura de producto físico. Tenemos seis meses para llegar a un MVP comercializable. Estamos en la etapa de selección de oportunidad — aún no hemos elegido en qué problema trabajar.

Estos son los hallazgos de nuestra búsqueda de mercado:

[PEGA AQUÍ los 3 insumos del Paso 1:

 - Las 2 oportunidades con datos de Perplexity

 - El ángulo no obvio de Claude]

Necesito que hagas lo siguiente:

1. SINTETIZA EN INSIGHTS: Convierte cada oportunidad en un 
   insight estructurado con este formato exacto: 

   - Quién específico tiene el problema (segmento concreto, 
     no "los usuarios" ni "las empresas")

   - Qué les cuesta no resolverlo (tiempo, dinero, calidad, 
     riesgo — con cifra o estimado)

   - Por qué las soluciones actuales no bastan (no "son caras" 
     en abstracto — cuál es la razón específica por la que 
     fallan para este usuario)

   - Dónde está exactamente el espacio: la brecha entre lo que 
     existe y lo que se necesita

2. ELIGE Y JUSTIFICA: De los insights generados, ¿cuál tiene 
   el espacio de negocio más claro para una solución que combine
   app con IA + artefacto físico + canal de venta digital?

   Justifica en función del usuario, el costo del problema y 
   la viabilidad de los tres componentes juntos.

3. FORMULA EL INSIGHT GANADOR: Redacta el insight elegido en 
   3–4 oraciones que cualquier persona pudiera leer y entender 
   por qué es una oportunidad real. Sin jerga. Sin abstracciones.


Ronda 2 — Perplexity: verificar los números (8 min)

Claude construyó el insight — pero sus cifras son estimaciones, no datos verificables. Antes de comprometer seis meses con una oportunidad, necesitas saber si los números son reales.

Tomas el insight ganador y lo llevas a Perplexity:

Actúa como un analista de inteligencia de mercado especializado en validación de oportunidades de negocio en América Latina, con acceso a fuentes primarias y secundarias confiables: INEGI, BID, CEPAL, reportes sectoriales, bases de datos de startups y registros de comportamiento de mercado. Tu trabajo es separar los supuestos de los hechos verificables — no para destruir ideas, sino para que los emprendedores sepan exactamente en qué parte de su oportunidad están parados sobre roca y en qué parte están parados sobre arena.

Somos emprendedores en México construyendo un negocio con tres componentes: una aplicación con IA, un artefacto físico inteligente y una página web de venta. Identificamos una oportunidad de negocio a través de análisis de mercado y necesitamos verificar si sus afirmaciones clave tienen respaldo en datos reales antes de comprometer seis meses de desarrollo.

Este es el insight que necesitamos verificar:

[PEGA AQUÍ el insight ganador que generó Claude]

Verifica cada una de estas afirmaciones con fuentes citables:

1. SEGMENTO: ¿El usuario descrito existe con ese perfil y ese
   problema en México o LATAM? ¿Cuántos son aproximadamente?
   Busca en INEGI, reportes de organismos multilaterales (BID,
   CEPAL, FAO, OPS según el sector), o estudios sectoriales
   recientes. Si el dato exacto no existe, dame el proxy más
   cercano con su fuente.

2. COSTO DEL PROBLEMA: ¿La cifra de pérdida o costo que 
   menciona el insight tiene respaldo en datos reales?

   Si no hay dato exacto, ¿cuál es el rango documentado más
   cercano? ¿Hay comportamiento observable que lo confirme

   — pagos actuales a soluciones imperfectas, pérdidas
   documentadas, seguros contratados, workarounds que tienen 
   costo?

3. SOLUCIONES ACTUALES: ¿Las alternativas que el insight 
   describe como insuficientes existen realmente y tienen las 
   características y precios que se mencionan? Dame al menos 
   2 ejemplos concretos con precio real y limitación verificable.

4. DISPOSICIÓN A PAGAR: ¿Hay evidencia de que este mercado 
   en LATAM está dispuesto a pagar por una solución mejor? 
   Busca señales de comportamiento: ¿ya pagan por algo similar 
   aunque sea peor? ¿hay búsquedas activas documentadas? 
   ¿comunidades online donde buscan soluciones? ¿intentos 
   de crowdfunding o mercados informales activos?

Al terminar, dame un veredicto por afirmación:

✅ Verificada con fuente

⚠️ Plausible pero sin dato directo — proxy usado

❌ No encontré respaldo — el equipo necesita validar esto
   con usuarios reales antes de continuar

Sé directo. Un insight mal fundamentado descubierto hoy vale más que uno descubierto en seis meses.


Al final del Paso 2 se obtiene un insight verificado con esta estructura:

INSIGHT DE OPORTUNIDAD — [Nombre del equipo]

QUIÉN: [Segmento específico con tamaño estimado verificado]

EL PROBLEMA: [Qué les ocurre, cuándo, con qué frecuencia]

LO QUE LES CUESTA: [Cifra o rango verificado — tiempo, dinero o riesgo]

POR QUÉ NO ESTÁ RESUELTO: [Razón específica por la que las soluciones actuales fallan para este usuario]

EL ESPACIO: [La brecha exacta entre lo que existe y lo que se necesita — donde vive el negocio]

FUENTES: [Las 2–3 fuentes que verificó Perplexity]

VEREDICTO DE VERIFICACIÓN: [✅ / ⚠️ / ❌ por afirmación]


### 🔬 Modo Estresor

**Ronda 1** — Claude: auditoría del insight implícito 

Toda idea de negocio tiene un insight implícito — una afirmación sobre el usuario y el problema que el equipo da por cierta sin haberla formulado explícitamente. El objetivo de esta ronda es hacerlo visible para poder cuestionarlo.

**Prompt**

Actúa como un estratega de producto con experiencia en identificar los supuestos ocultos detrás de ideas de negocio — los insights implícitos que los equipos dan por ciertos sin haberlos formulado ni verificado. Tu especialidad es hacer visible lo que se asume como obvio, porque ahí es donde más frecuentemente fallan los negocios de hardware + software en mercados emergentes.

Somos un equipo de emprendedores en México con una idea de negocio que combina tres componentes: una aplicación con IA, un artefacto físico inteligente y una página web de venta. Nuestras capacidades: desarrollo de software e IA, hardware conectado, manufactura de producto físico. Tenemos seis meses para MVP comercializable.

Nuestra idea es:

*[DESCRIBE LA IDEA EN 3–4 ORACIONES]*

Del análisis de ecosistema del Paso 1 obtuvimos esto:

*[PEGA LOS 3 INSUMOS DEL PASO 1: brechas de Perplexity + supuesto peligroso y arista alternativa de Claude]*

Necesito que hagas tres cosas:

1. FORMULA EL INSIGHT IMPLÍCITO: ¿Cuál es el insight sobre el 
   usuario y el problema que nuestro equipo está dando por
   cierto sin haberlo verificado? Exprésalo en el mismo formato
   que usarías para un insight sólido: quién, qué les cuesta,
   por qué no está resuelto, dónde está el espacio.
   Sé preciso — no parafrasees nuestra idea, formula el
   supuesto que la sostiene.

2. AUDITA EL INSIGHT: Una vez formulado, dime:

   - ¿Qué parte del insight tiene más probabilidad de ser
     falsa o más débil de lo que asumimos?

   - ¿Qué evidencia necesitaríamos para saber si es verdadera?

   - ¿Hay una versión alternativa del insight — mismo problema,
     diferente usuario, o mismo usuario, diferente problema —
     que podría ser más sólida?

3. FORMULA EL INSIGHT DE LA ARISTA NUEVA: Usando la arista
   alternativa que encontramos en el Paso 1, formula un segundo 
   insight con el mismo formato. ¿Para quién es, qué les cuesta,
   por qué no está resuelto, dónde está el espacio?
   ¿Cómo se articularían los tres componentes del negocio
   — app, artefacto y canal de venta — alrededor de esta
   arista?


**Ronda 2** — Perplexity: verificar y comparar ambos insights 

Tienes dos insights: el de tu idea original y el de la arista nueva. Necesitas datos reales para los dos antes de decidir cuál defender en el Paso 7. No es una comparación de opiniones — es una comparación de evidencia.

**Prompt**

Actúa como un analista de inteligencia competitiva con experiencia en evaluar la solidez de oportunidades de negocio digital-físico en mercados emergentes latinoamericanos. Tu metodología consiste en contrastar las afirmaciones de una oportunidad con datos verificables de fuentes primarias y secundarias — INEGI, BID, CEPAL, reportes de industria, bases de datos de comportamiento de mercado — para determinar qué tan firme es el suelo sobre el que un emprendedor está parado antes de comprometer recursos.

Somos emprendedores en México desarrollando un negocio que combina tres componentes: una aplicación con IA, un artefacto físico inteligente y una página web de venta. Tenemos dos direcciones posibles de negocio y necesitamos datos reales para elegir la más sólida, no la más atractiva en papel.

INSIGHT A — nuestra idea original:

*[PEGA EL INSIGHT IMPLÍCITO FORMULADO POR CLAUDE]*

INSIGHT B — arista alternativa identificada:

*[PEGA EL INSIGHT DE LA ARISTA NUEVA]*

Para cada insight, verifica con fuentes citables:

1. EXISTENCIA Y TAMAÑO DEL SEGMENTO: ¿El usuario descrito 
   existe con ese perfil y ese problema en México o LATAM?
   ¿Cuántos son? Dame la fuente más específica disponible
   — si no hay dato exacto, el proxy más cercano con origen.

2. COSTO REAL DEL PROBLEMA: ¿Hay datos documentados — 
   pérdidas reportadas, pagos observables a soluciones
   imperfectas, costos de workarounds — que respalden el 
   costo que cada insight describe? ¿O es una estimación 
   sin respaldo directo?

3. COMPETENCIA ESPECÍFICA: ¿Hay actores en el mercado 
   atacando exactamente esta combinación de usuario + 
   problema + solución digital-física para cada insight?
   No el problema genérico — esta combinación específica.
   Menciona actores reales con tracción observable.

4. SEÑAL DE MERCADO MÁS FUERTE: ¿Cuál de los dos insights 
   tiene más evidencia de que el mercado está listo — pagos 
   actuales, búsquedas documentadas, comunidades activas, 
   intentos previos de solución con tracción?

Al terminar entrega una tabla comparativa:

| Criterio          | Insight A | Insight B |

|-------------------|-----------|-----------|

| Segmento verificado | ✅/⚠️/❌ | ✅/⚠️/❌ |

| Costo documentado   | ✅/⚠️/❌ | ✅/⚠️/❌ |

| Competencia mapeada | ✅/⚠️/❌ | ✅/⚠️/❌ |

| Señal de mercado    | ✅/⚠️/❌ | ✅/⚠️/❌ |

No me digas cuál elegir — dame los datos y deja que la evidencia hable por sí sola.


Qué tienen al final del Paso 2

Dos insights comparados con evidencia verificada:

INSIGHT A — Idea original

[Formato completo: quién, costo, por qué no resuelto, espacio]

Tabla de verificación: [✅ / ⚠️ / ❌ por criterio]

Fuentes: [las que encontró Perplexity]

INSIGHT B — Arista nueva

[Formato completo: quién, costo, por qué no resuelto, espacio]

Tabla de verificación: [✅ / ⚠️ / ❌ por criterio]

Fuentes: [las que encontró Perplexity]

DECISIÓN PROVISIONAL: ¿Cuál llevan al Paso 3?

(pueden llevar los dos si ambos tienen evidencia sólida — el Paso 3 los ayudará a decidir con el Pain-Gain Map)


----------------------------------------------------------------------------------

## Paso 3 — Pain-Gain Map

El Paso 2 produjo un insight verificado: sabemos quién tiene el problema, qué les cuesta y por qué no está resuelto. El Paso 3 convierte ese insight en una radiografía del usuario — un mapa que descompone exactamente qué lo frustra (dolores) y qué resultado desea obtener (ganancias).

!!! warning 
    La oportunidad de negocio vive en el cruce entre el dolor más intenso y la ganancia más deseada que ninguna solución actual entrega. El Pain-Gain Map hace ese cruce visible y específico.

    Este paso es principalmente analógico — papel, marcadores, conversación de equipo. La IA entra al final, no al principio, para ampliar lo que el equipo construyó con su propio criterio.

En este paso usamos dos IAs con roles distintos:



|   | Claude | Perplexity |
| --- | --- | --- |
| **Trabajo** | Ampliar y cuestionar el mapa construido por el equipo — encontrar dolores que no vieron, ganancias que subestimaron, y entregar el mapa completo en formato listo para usar | Verificar que los dolores identificados son reales y frecuentes con datos de comportamiento de usuarios en LATAM |
| **Cuándo usarlo** | Después de que el equipo construyó su mapa en papel — no antes | Solo si algún dolor del mapa necesita verificación de frecuencia o intensidad real |



"El Pain-Gain Map es una radiografía del usuario — no de su producto ni de su idea. Dos columnas: qué le duele y qué quiere ganar. La oportunidad está donde el dolor es más intenso y la ganancia más deseada todavía no la da nadie bien. Tienen 10 minutos para construirlo en papel antes de tocar cualquier IA."

Regla crítica que el instructor comunica antes de arrancar:

"La columna de dolores se llena con lo que el usuario experimenta hoy — no con lo que su producto resuelve. Si están escribiendo en los dolores lo que su solución hace, están llenando el mapa al revés."


Plantilla — la misma para ambos modos
Se entrega impresa o en Google Slides compartido. Cada equipo llena una.

╔═════════════════════════════════════════════════════════════╗

║  PAIN-GAIN MAP                        Equipo: ___________   ║

║  Usuario / segmento específico: __________________________   ║

╠══════════════════════════════╦══════════════════════════════╣

║     DOLORES (Pains)          ║      GANANCIAS (Gains)        ║

║                              ║                               ║

║  ¿Qué les frustra hoy?       ║  ¿Qué resultado esperan?      ║

║  ¿Qué les falta?             ║  ¿Cómo sería su situación     ║

║  ¿Qué proceso es torpe,      ║  mejor si el problema         ║

║  lento, caro o riesgoso?     ║  desapareciera?               ║

║  ¿Qué workaround usan        ║  ¿Qué métrica mejoraría?      ║

║  aunque les incomode?        ║  ¿Qué dejarían de perder?     ║

╠══════════════════════════════╬══════════════════════════════╣

║                              ║                               ║

║  D1.                         ║  G1.                          ║

║                              ║                               ║

║  D2.                         ║  G2.                          ║

║                              ║                               ║

║  D3.                         ║  G3.                          ║

║                              ║                               ║

╠══════════════════════════════╩══════════════════════════════╣

║  EL ESPACIO SIN CUBRIR:                                      ║

║  El dolor más intenso: ___  La ganancia más deseada: ___     ║

║                                                              ║

║  "Existe una oportunidad para [quién] que necesita           ║

║   [qué resultado] porque hoy [por qué no lo tiene]"          ║

╚═════════════════════════════════════════════════════════════╝


🔍 Modo Explorador
Ronda 1 — Construcción en papel (10 min)
Antes de abrir cualquier IA, el equipo llena el mapa con su propio criterio a partir del insight del Paso 2.

Para llenar los dolores — tres preguntas guía:

¿Qué hace el usuario HOY para resolver este problema, aunque sea de forma mala, costosa o incómoda? Ese workaround contiene los dolores más reales.
¿Qué parte de ese workaround le sigue fallando o frustrando?
¿Qué pierde en tiempo, dinero, calidad o tranquilidad por no tener una solución mejor?

Para llenar las ganancias — tres preguntas guía:

Si el problema desapareciera mañana, ¿qué cambiaría concretamente en su día o en su negocio?
¿Qué métrica específica mejoraría? (menos horas, menos costo, menos errores, más ventas, menos riesgo)
¿Qué podría hacer que hoy no puede hacer porque el problema se lo impide?

Al terminar el mapa en papel, identificar:

El dolor más intenso: el que le cuesta más no resolver (en dinero, tiempo o riesgo)
La ganancia más deseada: el resultado que más quiere obtener
¿Hay alguna solución actual que cubra exactamente ese cruce? Si no, ahí está el espacio.


Ronda 2 — Claude: ampliar, cuestionar y entregar el mapa final (10 min)
El equipo transcribe su mapa y lo lleva a Claude. El prompt incluye instrucciones de formato de salida para que Claude entregue directamente el mapa completo listo para usar:

Actúa como un investigador de experiencia de usuario con

especialización en comportamiento de consumidores y pequeños

empresarios en mercados latinoamericanos. Tu metodología combina

análisis de fricción de producto, mapeo de deseos no articulados

y detección de dolores que los usuarios normalizan — los que no

mencionan en una primera conversación porque asumen que no tienen

solución. Tienes especial habilidad para encontrar lo que un

equipo de producto no ve porque está demasiado enfocado en

su propia solución.

Somos un equipo de emprendedores en México desarrollando un

negocio con tres componentes articulados: una aplicación con IA,

un artefacto físico inteligente y una página web de venta.

Construimos este Pain-Gain Map sobre nuestro usuario objetivo

a partir de un insight de mercado verificado. Ahora necesitamos

que lo amplíes y lo cuestiones — no que lo valides.

Nuestro usuario / segmento: [DESCRIBE EL SEGMENTO DEL INSIGHT]

Nuestro insight verificado: [PEGA EL INSIGHT DEL PASO 2]

Nuestro Pain-Gain Map construido hasta ahora:

DOLORES que identificamos:

- D1: [pega]

- D2: [pega]

- D3: [pega]

GANANCIAS que identificamos:

- G1: [pega]

- G2: [pega]

- G3: [pega]

Necesito que hagas tres cosas y que entregues el resultado

en el formato exacto que te indico al final:

1. DOLORES QUE NO VIMOS: ¿Qué dolores reales tiene este

   usuario que nuestro mapa no capturó? Enfócate en:

   - Dolores que los usuarios normalizan y rara vez mencionan

     porque creen que no tienen solución

   - Dolores emocionales o de estatus (vergüenza, frustración,

     sensación de pérdida de control) que acompañan al dolor

     funcional que ya identificamos

   - Dolores que aparecen ANTES o DESPUÉS del momento

     principal del problema — el contexto que rodea la fricción

   Agrega mínimo 2 dolores adicionales específicos para este

   usuario en contexto LATAM.

2. GANANCIAS QUE SUBESTIMAMOS: ¿Qué resultados deseados

   tiene este usuario que nuestro mapa minimiza o ignora?

   Enfócate en ganancias de segundo orden — lo que cambia

   en su vida o negocio como consecuencia de resolver el

   problema principal, no solo el resultado directo.

   Agrega mínimo 2 ganancias adicionales con ese enfoque.

3. EL CRUCE MÁS PODEROSO: Con el mapa ampliado, identifica

   la combinación de dolor más intenso + ganancia más deseada

   que representa el espacio de negocio más claro para una

   solución que combine app con IA + artefacto físico +

   canal de venta digital. Explica en 2 oraciones por qué

   ese cruce específico y no otro.

FORMATO DE SALIDA — entrega exactamente esto, sin agregar

texto antes ni después:

═══════════════════════════════════════════════════════

PAIN-GAIN MAP COMPLETO

Usuario / segmento: [el segmento específico]

═══════════════════════════════════════════════════════

DOLORES (ordenados de mayor a menor intensidad):

⭐ D1: [el más intenso — original o nuevo]

   D2: [segundo más intenso]

   D3: [tercer más intenso]

   D4: [agregado — dolor normalizado que no vieron]

   D5: [agregado — dolor emocional o de contexto]

GANANCIAS (ordenadas de mayor a menor deseo):

⭐ G1: [la más deseada — original o nueva]

   G2: [segunda más deseada]

   G3: [tercera más deseada]

   G4: [agregada — ganancia de segundo orden]

   G5: [agregada — ganancia de segundo orden]

EL CRUCE MÁS PODEROSO:

Dolor ⭐ [nombre] × Ganancia ⭐ [nombre]

[2 oraciones explicando por qué este cruce y no otro]

LA OPORTUNIDAD EN UNA ORACIÓN:

"Existe una oportunidad para [quién] que necesita [qué resultado]

porque hoy [por qué no lo tiene]."

═══════════════════════════════════════════════════════


Ronda 3 — Perplexity: verificar frecuencia e intensidad (5 min)
Solo si el equipo tiene dudas sobre qué tan frecuente o intenso es el dolor ⭐ del mapa. No es obligatoria si el insight del Paso 2 ya verificó esto.

Actúa como un analista de comportamiento de mercado con

experiencia en documentar cómo usuarios en América Latina

experimentan y expresan sus problemas — en foros, redes sociales,

comunidades de práctica, reseñas de productos y reportes

sectoriales. Tu especialidad es encontrar evidencia de primera

mano de que un problema específico duele de forma frecuente e

intensa, no solo de que existe en abstracto.

Somos emprendedores en México que identificamos el siguiente

dolor como el más intenso de nuestro usuario y queremos

verificar si esa intensidad y frecuencia tienen respaldo en

comportamiento real antes de construir un negocio alrededor

de él.

USUARIO / SEGMENTO: [del Pain-Gain Map]

DOLOR PRINCIPAL A VERIFICAR: [el dolor ⭐ del mapa]

Verifica con evidencia de comportamiento real — no estadísticas

generales — y entrega tu respuesta en este formato exacto:

FRECUENCIA

¿Con qué regularidad experimenta este usuario este dolor?

Evidencia encontrada: [dónde y cómo lo expresan — comunidades,

foros, grupos, canales — con ejemplos concretos y links si

están disponibles]

Veredicto: diario / semanal / mensual / ocasional

INTENSIDAD

¿Qué tan caro o incómodo es en términos observables?

Evidencia encontrada: [pagos actuales, workarounds con costo,

pérdidas documentadas atribuibles a este dolor específico]

Veredicto: alto / medio / bajo

MOMENTO

¿Cuándo ocurre exactamente en el flujo de trabajo o vida

del usuario?

[descripción del momento preciso donde intervenir]

Tipo: continuo / periódico / situacional

CONCLUSIÓN PARA EL EQUIPO:

[Una oración directa: el dolor ⭐ está bien fundamentado /

necesita ajuste / es menos intenso de lo que asumieron]


🔬 Modo Estresor
El Estresor no construye el mapa desde cero — lo usa como herramienta de auditoría en tres rondas progresivas. El objetivo no es llenar un mapa bonito, sino descubrir si la idea ataca los dolores correctos y si hay aristas de negocio que el equipo no ha visto.
Ronda 1 — Construcción honesta en papel (8 min)
El equipo llena el mapa desde la perspectiva del usuario, no desde la perspectiva de su idea.

Instrucción específica: llenar los dolores con lo que el usuario experimenta hoy, antes de que la idea del equipo exista. No lo que la idea resuelve — lo que el usuario vive.

Al terminar, marcar cada dolor con uno de tres símbolos:

✅ Nuestra idea lo resuelve bien
⚠️ Nuestra idea lo atenúa parcialmente
❌ Nuestra idea no lo toca

La pregunta incómoda antes de abrir Claude: ¿el dolor marcado con ❌ o ⚠️ es más intenso que el que nuestra idea resuelve con ✅? Si la respuesta es sí, el equipo está atacando el dolor equivocado — y el Paso 4 (SCAMPER) puede generar la dirección correcta.


Ronda 2 — Claude: auditoría del mapa, detección de aristas y entregable (12 min)
Actúa como un consultor de estrategia de producto con experiencia

en identificar desalineaciones entre lo que un equipo cree que

resuelve y lo que el usuario realmente necesita. Tu especialidad

es el análisis de Pain-Gain Maps para detectar si una solución

está atacando los dolores correctos o si existe una oportunidad

de negocio más poderosa en los dolores que la solución actual

ignora. Trabajas principalmente con negocios de hardware y

software en mercados emergentes de América Latina.

Somos emprendedores en México con una idea de negocio que combina

tres componentes: una aplicación con IA, un artefacto físico

inteligente y una página web de venta. Construimos un Pain-Gain

Map de nuestro usuario y auditamos qué dolores resuelve nuestra

idea. Necesitamos que lo analices sin piedad y que entregues

el resultado en el formato que te indicamos al final.

Nuestra idea: [DESCRIBE EN 3–4 ORACIONES]

Nuestro Pain-Gain Map con auditoría:

DOLORES del usuario (con símbolo de cobertura):

- D1: [dolor] → ✅ / ⚠️ / ❌

- D2: [dolor] → ✅ / ⚠️ / ❌

- D3: [dolor] → ✅ / ⚠️ / ❌

GANANCIAS que desea el usuario:

- G1: [ganancia]

- G2: [ganancia]

- G3: [ganancia]

Realiza estos tres análisis y entrega el resultado en el

formato exacto que se indica al final:

1. DESALINEACIÓN CRÍTICA: ¿Hay algún dolor ❌ o ⚠️ que sea

   más intenso o frecuente que el que nuestra idea resuelve

   con ✅? Si es así, ¿qué implica para la propuesta de valor?

   ¿Estamos atacando el dolor correcto o el más conveniente

   para nuestra solución actual?

2. ARISTA DE NEGOCIO NO VISTA: Usando los dolores ❌ o ⚠️,

   describe una versión alternativa o complementaria del

   negocio que los atacara directamente. ¿Cómo cambiarían

   los tres componentes — app con IA, artefacto físico y

   canal de venta — para resolver esos dolores?

   Formula la arista como oportunidad en una oración.

3. GANANCIAS NO ENTREGADAS: ¿Cuál de las ganancias deseadas

   entrega peor nuestra solución actual? ¿Cómo podría

   rediseñarse uno de los tres componentes para entregarla

   mejor sin abandonar lo que ya resuelve bien?

FORMATO DE SALIDA — entrega exactamente esto:

═══════════════════════════════════════════════════════

PAIN-GAIN MAP AUDITADO

Usuario / segmento: [el segmento específico]

═══════════════════════════════════════════════════════

DOLORES CON AUDITORÍA (ordenados de mayor a menor intensidad):

⭐ D1: [el más intenso] → ✅/⚠️/❌

   D2: [segundo]        → ✅/⚠️/❌

   D3: [tercero]        → ✅/⚠️/❌

GANANCIAS (ordenadas de mayor a menor deseo):

⭐ G1: [la más deseada] → entregada: bien / parcial / no

   G2: [segunda]        → entregada: bien / parcial / no

   G3: [tercera]        → entregada: bien / parcial / no

DESALINEACIÓN CRÍTICA:

[¿La idea ataca el dolor correcto? Sí / No / Parcialmente]

[1–2 oraciones explicando la desalineación si existe]

ARISTA DE NEGOCIO IDENTIFICADA:

"Existe una oportunidad adicional para [quién] que necesita

[qué resultado] porque hoy [por qué no lo tiene] — y nuestra

solución actual no la cubre."

Cómo cambiarían los tres componentes: [1 oración por componente]

GANANCIA NO ENTREGADA:

[Cuál es y cómo rediseñar uno de los tres componentes para

entregarla mejor — 2 oraciones]

DECISIÓN RECOMENDADA:

[ ] Continuar con la idea original — la desalineación es menor

[ ] Explorar la arista en paralelo — ambas tienen potencial

[ ] Considerar pivote — la arista es más sólida que la idea original

Justificación: [1 oración]

═══════════════════════════════════════════════════════


Ronda 3 — Perplexity: verificar el mercado de la arista (5 min)
Si Claude identificó una arista de negocio relevante en la Ronda 2, verificar si tiene mercado real antes de llevarla al Paso 4.

Actúa como un analista de mercado con experiencia en evaluar

el potencial comercial de oportunidades de negocio específicas

en sectores de América Latina. Tu metodología combina búsqueda

de evidencia de comportamiento de usuarios, análisis de

soluciones existentes y estimación de disposición a pagar

en mercados emergentes. Tu trabajo no es vender la idea —

es decirle al emprendedor si el dolor tiene mercado suficiente

para justificar construir alrededor de él.

Somos emprendedores en México con una idea de negocio que

combina una aplicación con IA, un artefacto físico inteligente

y una página web de venta. Durante el análisis de nuestro

Pain-Gain Map identificamos una arista de negocio que nuestra

solución actual no cubre. Necesitamos saber si tiene mercado

real antes de comprometer recursos en explorarla.

NUESTRA IDEA ACTUAL resuelve: [dolor ✅ principal]

PARA EL USUARIO: [segmento]

LA ARISTA QUE EVALUAMOS ataca: [dolor ❌ o ⚠️ identificado]

OPORTUNIDAD FORMULADA: [la oración de oportunidad de la arista]

Verifica con datos reales y entrega tu respuesta en este

formato exacto:

TAMAÑO DEL SEGMENTO

¿Cuántos usuarios en México o LATAM tienen este problema

con frecuencia semanal o mayor?

Dato encontrado: [cifra o rango con fuente]

Fuente: [nombre del reporte u organismo]

Confiabilidad: alta / media / estimada

EVIDENCIA DE DISPOSICIÓN A PAGAR

¿Hay señales observables de que este segmento busca o paga

por resolver este dolor específico?

Evidencia: [pagos actuales, búsquedas, comunidades, intentos

previos — con ejemplos concretos]

Veredicto: clara / parcial / no encontrada

COMPETENCIA EN ESTE ESPACIO ESPECÍFICO

¿Alguien ya ataca exactamente esta combinación de usuario

+ dolor + solución digital-física?

Actores encontrados: [nombres reales con tracción observable,

o "no encontrados"]

Brecha confirmada: sí / no / parcial

CONCLUSIÓN PARA EL EQUIPO:

[Una oración directa sobre si la arista tiene mercado

suficiente para justificar explorarla: sí, con condiciones,

o no — y por qué]




























[Introducción)](./recursos/archivos/1_Desarrollo%20Productos.pdf)

<iframe src="../recursos/archivos/1_Desarrollo%20Productos.pdf" width="800" height="440"></iframe>


Tarea: 
* Hacer la revisión de la tarea en el documento y pl
* Plantear la problemática que está resolviendo mi proyecto
* Preparar un prototipo (método experimental) que te permita asegurar que tu proyecto está resolviendo un problema real
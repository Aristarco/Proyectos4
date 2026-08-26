# Búsqueda de Oportunidades

## Objetivo de la semana

*Que el equipo identifique una oportunidad de producto concreta, arraigada en un problema observable en mercados latinoamericanos, usando IA como acelerador de búsqueda y síntesis — y elija la oportunidad que desarrollará durante el semestre.*

# Blueprint IDEO: **Creación de valor** · DVF: 🔴 Deseable

Esta semana el equipo responde la pregunta más importante del semestre antes de escribir una sola línea de código o hacer un solo modelo 3D: 

!!! Tip ¿Existe un problema real que vale la pena resolver?

    Todo lo que se construya después depende de la calidad de la respuesta que encuentren hoy.

# Cómo leer este documento

Cada paso tiene dos modos de instrucción que corren en paralelo:

🔍 **Modo Explorador** — equipos que buscan oportunidad desde cero

🔬 **Modo Estresor** — equipos que ya tienen una idea y necesitan cuestionarla

# Vista rápida de los 7 pasos

| --- | --- | --- | --- |
| **#** | **Paso** | **Tiempo** | **IA** |
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

| --- | --- | --- |
| " " | **Perplexity** | **Claude** |
| **Fortaleza** | Datos reales, fuentes verificables, cifras de mercado actualizadas | Síntesis creativa, conexiones no obvias, reencuadre de problemas |
| **Debilidad** | Tiende a lo obvio, repite el consenso del mercado | Sin datos propios — necesita que le des contexto |
| **Uso en este paso** | Anclar en realidad: ¿el problema existe, qué tan grande es, quién ya lo ataca? | Romper el consenso: ¿qué nadie está viendo, qué ángulo es contraintuitivo? |

Perplexity te dice qué existe. Claude te dice qué podría existir. Los necesitas a los dos para no quedarte ni con datos sin imaginación ni con imaginación sin datos.

!!! Warning Instrucción general al grupo
    "Vamos a buscar oportunidades con dos IAs en paralelo — no son intercambiables, cada una tiene un trabajo diferente. Perplexity para anclar en datos reales; Claude para romper el pensamiento obvio. Lean su tarjeta de modo y arranquen. Tienen 12 minutos de trabajo, luego compartimos hallazgos."

## **PROMPTS:** 

# 🔍 Modo Explorador

Ronda 1 — Perplexity: anclar en realidad (6 min)
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
en el sector de [ELIGE el área que hayas pensado o bien uno de estos que te atraiga: salud comunitaria / manufactura artesanal /
logística urbana / agua y medio ambiente / seguridad física / educación técnica] en México y América Latina que cumplan estas
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

Ronda 2 — Claude / otra: romper el consenso (6 min)

Una vez que Perplexity te devuelve las 4 oportunidades, llevas los resultados a Claude:

Actúa como un innovador con experiencia en detectar oportunidades

de negocio que el mercado ignora porque parecen demasiado nicho,

demasiado obvias o demasiado difíciles. Tu enfoque es el

pensamiento lateral aplicado a mercados emergentes: buscas lo que

todos ven pero nadie está atacando, y lo que nadie ve porque está

demasiado cerca. Tienes especial habilidad para imaginar negocios

donde la combinación de inteligencia artificial, interfaces

digitales y objetos físicos inteligentes crea una propuesta de

valor que ninguno de los tres componentes podría crear por

separado.

Estamos construyendo un negocio en México con tres componentes

articulados: una aplicación con IA, un artefacto físico

inteligente y una página web de venta. Nuestras capacidades

abarcan tanto el desarrollo de software e IA como el diseño y

manufactura de hardware conectado. Tenemos seis meses para

llegar a MVP comercializable.

Estas son las 4 oportunidades que identificamos a través de

análisis de mercado:

[PEGA AQUÍ los resultados de Perplexity]

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

No me repitas lo que Perplexity ya encontró. Dame lo que el

análisis de mercado convencional no puede ver.

























[Introducción)](./recursos/archivos/1_Desarrollo%20Productos.pdf)

<iframe src="../recursos/archivos/1_Desarrollo%20Productos.pdf" width="800" height="440"></iframe>


Tarea: 
* Hacer la revisión de la tarea en el documento y pl
* Plantear la problemática que está resolviendo mi proyecto
* Preparar un prototipo (método experimental) que te permita asegurar que tu proyecto está resolviendo un problema real
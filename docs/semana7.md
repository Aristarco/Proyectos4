# Semana 7 — Viabilidad técnica y económica

!!! abstract "Blueprint: Captura de valor · DVF: 🟡 Viable · 🟢 Factible"
    No basta con que el producto sea deseable y construible. Esta semana responde la pregunta que más equipos evitan: ¿el negocio cierra? Si el costo de fabricar el producto supera lo que el usuario está dispuesto a pagar, no hay captura de valor posible — sin importar cuán elegante sea el diseño o cuán sólida sea la arquitectura.

!!! warning "Esta semana puede extenderse a dos sesiones"
    El contenido es denso por diseño: es la única clase de matemáticas financieras del semestre para este grupo. El hilo conductor está diseñado para cortarse en cualquier punto y retomarse sin perder coherencia. 

---

## Distribución de tiempo presencial

| # | Bloque | Contenido | Tiempo |
|---|--------|-----------|:------:|
| 1 | Marco conceptual | Viabilidad, factibilidad y pertinencia | 15 min |
| 2 | Modelos de ingresos | Los 5 modelos IDEO + hardware con suscripción a fondo | 25 min |
| 3 | Costos | BOM real + costos de desarrollo + costo de la IA | 30 min |
| 4 | Matemáticas financieras | Flujo de caja, VP, VPN, TIR — con ejercicios en clase | 40 min |
| 5 | Taller | El equipo construye su modelo económico | 10 min arranque |
| | **Total sesión 1** | | **120 min** |

!!! tip "El hilo conductor"
    Cada bloque alimenta al siguiente en una sola dirección: primero entienden **para qué** capturar valor (marco), luego **cómo** (modelos de ingresos), luego **cuánto cuesta** crearlo (costos), luego **si la matemática cierra** (finanzas), y finalmente **si su negocio específico funciona** (taller).

---

## Bloque 1 — Viabilidad, factibilidad y pertinencia
**Duración: 15 min · Min 0:00 – 0:15**

### Tres preguntas distintas que los equipos confunden


> *"Tres preguntas. Las tres son necesarias. Ninguna reemplaza a las otras. Y la mayoría de los proyectos que fracasan fallaron en responder al menos una de ellas con honestidad."*

```
PERTINENCIA     →  ¿Vale la pena hacerlo?
                   ¿El proyecto responde a una necesidad real
                   y es relevante para el contexto donde opera?
                   (Respondida en semanas 2–4: Pain-Gain Map,
                   entrevistas, propuesta de valor)

FACTIBILIDAD    →  ¿Cómo se puede hacer?
                   ¿El equipo tiene los recursos técnicos,
                   humanos y operativos para ejecutarlo?
                   (Respondida en semanas 5–6: arquitectura,
                   PDS, concepto de diseño)

VIABILIDAD      →  ¿Se puede hacer y es sostenible?
                   ¿El modelo económico cierra?
                   ¿El negocio puede mantenerse en el tiempo?
                   (Semana 7: esto)
```

**La secuencia importa.** No tiene sentido calcular la viabilidad económica de un producto que nadie necesita (pertinencia) o que el equipo no puede construir (factibilidad). Por eso llega en semana 7 y no en semana 2.

### Las tres dimensiones de la viabilidad

La viabilidad no es solo financiera.

**Viabilidad económica y financiera:**
¿El modelo de ingresos genera más de lo que cuesta operar? ¿La inversión inicial se recupera en un plazo razonable? ¿Los indicadores financieros (VPN, TIR) justifican el riesgo? Esta es la dimensión que ocupa la mayor parte de la sesión.

**Viabilidad operativa:**
¿El equipo puede fabricar, entregar y dar soporte al producto con sus recursos actuales? Un producto que funciona en el laboratorio pero que requiere 40 horas de ensamble manual por unidad no es operativamente viable a escala. Esto conecta directamente con las decisiones de manufactura de semana 5.

**Viabilidad legal:**
¿El producto cumple con las regulaciones aplicables? Para productos con hardware electrónico en México: certificación NOM para emisiones electromagnéticas, consideraciones de datos personales si la app recolecta información del usuario, restricciones de la banda de frecuencia usada para comunicación. No es un curso de derecho — es saber qué preguntas hacer antes de lanzar.

> *"Un equipo que llega a semana 13 con un prototipo funcional pero sin haber respondido estas tres preguntas no tiene un producto — tiene un experimento de laboratorio muy costoso."*

---

## Bloque 2 — Modelos de ingresos: cómo captura valor el negocio
**Duración: 25 min**

### Por qué el modelo de ingresos es una decisión de diseño

Un modelo de ingresos no es solo "cómo cobras" — es una decisión que define la relación entre el negocio y el usuario, el ciclo de vida del producto, la estructura de costos, y el tipo de empresa que el equipo está construyendo. Elegir mal el modelo puede destruir un producto excelente.

> *"Un modelo de ingresos es cómo la gente está dispuesta a pagar por tu oferta. No cómo tú quieres que paguen — cómo ellos están dispuestos a hacerlo. Esa distinción es la diferencia entre un modelo que funciona y uno que fuerza al usuario a comportarse de una forma en que no quiere."*

### Los 5 modelos fundamentales — framework de IDEO

La columna más importante para los equipos no es la de beneficios — es la de **desafío de diseño**: qué problema tienen que resolver para que el modelo funcione.

| Modelo | Ejemplo | Beneficio para el cliente | Beneficio para el negocio | Desafío de diseño |
|--------|---------|--------------------------|--------------------------|-------------------|
| **Pago por evento** | Starbucks | Simple, rápido, finito | Simple, rápido, finito | Puede ser difícil lograr la repetición de compra |
| **Suscripción** | Netflix | Paga y olvida · Poco tiempo en la transacción | Flujo de ingresos continuo | Más difícil lograr el compromiso inicial · puede tener costos de adquisición más altos |
| **Publicidad** | Instagram | Baja barrera de uso · sin cargo al usuario | Más fácil aumentar el número de usuarios | Requiere base grande y sostenida + proceso de venta de anuncios |
| **Freemium** | New York Times | Período de prueba o características gratuitas | "Enganchar" clientes · más fácil aumentar usuarios | Hay que diseñar el momento para cobrar · riesgo de muchos usuarios sin ingresos |
| **Pago por uso** | Uber | No pagas por lo que no usas | Apela a usuarios con tasas variables de uso | Necesidad de diseñar un sistema para rastrear el uso |



*Pago por evento:* el más simple. Para productos de hardware es la venta directa — compras el sensor y es tuyo. El problema es que el negocio no tiene ingresos recurrentes después de la venta: si el usuario no necesita comprar otro, la relación termina ahí.

*Suscripción:* el modelo más atractivo para hardware + software porque genera ingresos recurrentes predecibles. El desafío es que el usuario tiene que ver valor continuo — si el sensor funciona bien y la app hace lo mismo todos los meses, ¿por qué seguir pagando? Hay que diseñar valor que se acumule: historial, alertas cada vez más inteligentes, benchmarking con otros usuarios.

*Publicidad:* prácticamente inviable para el tipo de productos de este curso. Requiere millones de usuarios activos y un equipo de ventas de publicidad. Lo incluimos para que el equipo entienda por qué no aplica.

*Freemium:* relevante para la app. Hardware gratis o subsidiado + funcionalidades básicas gratis + funcionalidades premium de pago. El desafío es diseñar el "muro" correcto — el momento donde el usuario decide si paga o no. Si el muro está demasiado pronto, nadie llega. Si está demasiado tarde, nadie paga.

*Pago por uso:* interesante para ciertos casos — un sensor que cobra por cada recomendación generada, o por cada alerta enviada. Requiere infraestructura de medición y facturación más compleja. Viable si el uso del producto varía mucho entre usuarios.

---

---

### Ejercicio — Benchmarking de modelos de ingresos

Antes de decidir el modelo propio, el equipo investiga cómo otras empresas con ofertas similares están cobrando. El objetivo no es copiarlo — es entender el espacio de posibilidades real y los momentos de fricción que ya existen en el mercado.

> *"Para comenzar a pensar en el modelo de ingresos y precio, mira en el mundo para entender cómo otras compañías están cobrando por productos o servicios similares al tuyo. No tienen que ser competidores directos — pueden ser productos que resuelven el mismo tipo de problema en otro sector o mercado."*

**Instrucción:** el equipo investiga 3 empresas con oferta similar a la suya. Para cada una: qué venden, cómo cobran (quién paga, cuándo, bajo qué condición), el rango de precio visible, y las notas sobre fricción en el proceso de pago y otros actores que podrían aportar ingresos al modelo.

```
BENCHMARKING DE MODELOS DE INGRESOS
Producto: ___________________________

┌──────────────────────┬──────────────────────────┬──────────────────┬────────────────────────────────────────┐
│ Producto o servicio  │ Modelo de ingresos       │ Rango de precio  │ Notas                                  │
│ similar              │ (quién paga, cuándo)     │                  │ ¿Momentos de fricción en el pago?      │
│                      │                          │                  │ ¿Otros stakeholders que podrían pagar? │
├──────────────────────┼──────────────────────────┼──────────────────┼────────────────────────────────────────┤
│                      │                          │                  │                                        │
│                      │                          │                  │                                        │
├──────────────────────┼──────────────────────────┼──────────────────┼────────────────────────────────────────┤
│                      │                          │                  │                                        │
│                      │                          │                  │                                        │
├──────────────────────┼──────────────────────────┼──────────────────┼────────────────────────────────────────┤
│                      │                          │                  │                                        │
│                      │                          │                  │                                        │
└──────────────────────┴──────────────────────────┴──────────────────┴────────────────────────────────────────┘
```

**Las dos preguntas que el equipo responde al terminar la tabla:**

1. *¿Qué modelo están usando mayoritariamente los competidores y por qué creen que eligieron ese?*
2. *¿Hay algún stakeholder que los competidores no están cobrando y que podría ser una fuente de ingresos para su negocio?* (ejemplo: en un sensor agrícola, ¿podrían pagar también las aseguradoras agrícolas, los distribuidores de insumos, o el gobierno a través de programas de tecnificación?)

**Prompt — Perplexity: benchmarking de modelos de ingresos**

```
Actúa como analista de inteligencia competitiva especializado
en modelos de negocio para productos de hardware + software
en mercados latinoamericanos y globales. Tu metodología consiste
en identificar cómo empresas con ofertas similares están
capturando valor — no solo su precio de lista, sino el modelo
completo: quién paga, cuándo, bajo qué condición, y qué
fricción existe en ese proceso de pago.

Somos emprendedores en México con el siguiente producto:
[nombre + descripción en 2–3 oraciones]
Propuesta de valor: [Versión 3 del prompt de semana 4]
Segmento objetivo: [perfil accionable]

Investiga 3 empresas o productos con oferta similar a la nuestra
— pueden ser competidores directos, indirectos, o productos
que resuelven el mismo tipo de problema en otro sector o mercado.

Para cada empresa entrega:

EMPRESA: [nombre]
Qué ofrece: [descripción en 1 oración]
Modelo de ingresos: [cómo cobra — quién paga, cuándo, bajo qué condición]
Rango de precio: [precios documentados o estimados con fuente]
Momentos de fricción: [dónde el usuario típicamente duda o abandona
  el proceso de pago — prueba gratuita que no convierte, precio
  oculto hasta el final, contrato anual que genera resistencia]
Otros stakeholders: [¿hay alguien más que paga o podría pagar
  además del usuario final? distribuidores, instituciones,
  gobiernos, seguros, marcas que patrocinan]

Al terminar las 3 empresas, responde:
¿Qué modelo de ingresos predomina en este espacio y por qué
crees que es el elegido por la mayoría?
¿Hay algún stakeholder que nadie está cobrando actualmente
y que podría ser una oportunidad de ingresos para un nuevo entrante?
```

!!! tip "La columna de stakeholders alternativos es la más valiosa"
    La mayoría de los equipos asume que el único que paga es el usuario final. En muchos mercados esa es la fuente de ingresos más difícil — baja disposición a pagar, ciclo de ventas largo, mucha fricción. Preguntar quién más tiene interés en que el problema esté resuelto frecuentemente revela fuentes de ingresos más accesibles: instituciones, distribuidores, fabricantes de insumos, programas gubernamentales.

---

### El modelo específico para este curso: hardware + suscripción

La mayoría de los productos del curso tienen tres componentes: artefacto físico, app y página web. Eso habilita un modelo de ingresos en dos capas que es el más común en productos IoT exitosos:

```
CAPA 1 — HARDWARE (venta única o subsidiada)
El artefacto físico se vende una vez.
Opciones:
· Precio completo: el usuario paga el costo real + margen
· Subsidiado: el hardware se vende al costo o por debajo
  (el negocio recupera con la suscripción)
· "Enganche": el hardware es barato pero la app y los
  consumibles son donde está el margen real

CAPA 2 — SOFTWARE / SERVICIO (suscripción mensual o anual)
La app, el acceso a datos históricos, las alertas inteligentes,
las recomendaciones del modelo de IA.
· Plan básico: datos en tiempo real + alertas básicas
· Plan premium: historial completo + recomendaciones de IA
  + soporte técnico + integraciones
```

**Por qué este modelo funciona para productos con IA:**

El modelo de IA tiene un costo operativo continuo — cada llamada a la API cuesta dinero, la infraestructura cloud tiene costo mensual, las actualizaciones del modelo requieren inversión. La suscripción es la única forma de cubrir esos costos operativos sin que el precio del hardware suba a un nivel que el segmento no puede pagar.

> *"Si su producto hace 500 consultas al modelo de IA por día y cada llamada a la API cuesta $0.002 USD, eso es $1 USD al día por usuario activo — $30 USD al mes solo en inferencia. Sin suscripción, ese costo lo absorbe el negocio indefinidamente. La suscripción debe cubrir todos los costos de operación."*

**El desafío de diseño de este modelo:**

¿Cómo se ve el momento donde el usuario decide si suscribirse o no? Si el hardware ya está instalado y funcionando, el usuario tiene incentivo a no pagar y seguir con las funcionalidades gratuitas. El producto tiene que estar diseñado para que el valor de la suscripción sea visible y urgente en el momento correcto — no después de 3 meses de uso gratuito.

---

## Bloque 3 — Costos: qué cuesta crear el valor
**Duración: 30 min**

### El inventario de costos — dos actividades, dos listas

Antes de calcular nada, hacer el inventario completo de costos por actividad de negocio.

> *"Una forma de comenzar a mirar los costos es por actividad: qué necesito para crear mi oferta, y qué más necesito para hacerla llegar a mis clientes. Primero piensen en todos los costos que se les ocurran sin filtrar. Luego reflexionen: ¿cuáles son absolutamente necesarios para satisfacer la propuesta de valor?"*

**Para CREAR el producto — el equipo piensa en:**
- Componentes electrónicos, sensores, actuadores (BOM del hardware)
- PCB: fabricación y ensamble (JLCPCB, laboratorio propio)
- Carcasa: impresión 3D, inyección, mecanizado
- Mano de obra de ensamble y prueba por unidad
- Infraestructura cloud: servidor, base de datos, almacenamiento
- **Costo de la IA:** APIs de modelos × volumen de llamadas esperado
- Licencias de software de desarrollo

**Para DISTRIBUIR el producto — el equipo piensa en:**
- Empaque y envío
- Canal de venta: tienda en línea, distribuidores, venta directa
- Soporte técnico post-venta
- Actualizaciones de firmware OTA

### El BOM real — la base de todo

El Bill of Materials es el documento que convierte la arquitectura de semana 5 en números reales. No estimaciones — precios cotizados en fuentes reales.

**Las cuatro columnas que el BOM necesita:**

| Componente | Especificación | Precio unitario | Proveedor / Tiempo de entrega |
|------------|---------------|-----------------|-------------------------------|
| ESP32-S3 | 8MB Flash, 8MB PSRAM | $85 MXN | LCSC / 3 semanas |
| Sensor humedad suelo | Capacitivo, rango 0–100% VWC | $120 MXN | MercadoLibre / 3 días |
| [resto de componentes] | | | |

**Algunas fuentes de cotización reales:**
- [lcsc.com](https://www.lcsc.com) — componentes electrónicos, precios de volumen
- [jlcpcb.com](https://www.jlcpcb.com) — PCB + ensamble (PCBA)
- [digikey.com.mx](https://www.digikey.com.mx) — componentes con disponibilidad en México
- [mercadolibre.com.mx](https://www.mercadolibre.com.mx) — componentes locales, envío rápido
- [mouser.mx](https://www.mouser.mx) — componentes técnicos especializados

### El costo que nadie calcula: la IA

Este es el punto que más sorprende a los equipos cada semestre. Trabaja con números reales:

> *"Si su producto usa un modelo de IA en la nube — Claude, GPT, Gemini — **cada llamada tiene un costo. No es gratuito.** Y a escala, ese costo puede destruir el margen del negocio si no se calculó desde el inicio."*

**Cómo calcular el costo de la IA — el método correcto:**

La fórmula es simple. Lo que no es simple es el número de tokens — y ese número no se estima, se mide.

```
Costo mensual por usuario =
  Número de llamadas al modelo / día
  × (tokens input + tokens output) por llamada
  × Precio por token del modelo elegido
  × 30 días
```

**Paso 1 — Medir los tokens reales, no estimarlos**

La forma más directa: **preguntarle a Claude directamente**.

El equipo construye el prompt real que su producto enviaría al modelo — el que el sistema mandaría en una interacción típica con el usuario — y se lo pasa a Claude en el chat con esta instrucción:

```
Cuenta los tokens de este prompt y dime cuántos son de input.
Después, si la respuesta típica que generarías para esta petición
tiene aproximadamente X palabras, ¿cuántos tokens de output serían?

[pegar el prompt real del producto aquí]
```

Claude devuelve el conteo de input y estima el output. Es suficientemente preciso para el ejercicio de estimación de costos.

!!! note "Para producción real — usar el endpoint oficial"
    En un producto en producción, la forma precisa es llamar al endpoint `count_tokens` de la API de Anthropic antes de cada mensaje, o leer el campo `usage.input_tokens` / `usage.output_tokens` que viene en cada respuesta de la API. Para el ejercicio real, preguntarle a Claude en el chat es suficiente.

!!! warning "Atención con los modelos más recientes"
    Los modelos Claude 4.7 en adelante usan un tokenizador más nuevo — el mismo texto produce aproximadamente 30% más tokens que en modelos anteriores. Al comparar costos entre modelos distintos, el número de tokens no es el mismo aunque el prompt sí lo sea.

**Regla empírica si no tienen el prompt listo aún:**
En español, aproximadamente 1 token ≈ 3–4 caracteres. El español es menos eficiente que el inglés en tokens — la misma oración en español puede costar 20–30% más tokens. Un prompt de 300 palabras en español son típicamente 500–700 tokens.

**Paso 2 — Verificar el precio actual del modelo**

Los precios de los modelos cambian con frecuencia. Siempre consultar la fuente oficial antes de calcular:

- Anthropic: [anthropic.com/pricing](https://anthropic.com/pricing)
- OpenAI: [openai.com/pricing](https://openai.com/pricing)
- Google: [ai.google.dev/pricing](https://ai.google.dev/pricing)

**Paso 3 — Calcular con los números reales**

```
Ejemplo con números hipotéticos — el equipo los sustituye con los suyos:

Producto: sensor agrícola con recomendación de riego
Modelo elegido: Claude Haiku (verificar precio actual en anthropic.com/pricing)
Prompt medido en consola: 650 tokens input
Respuesta típica medida: 180 tokens output
Llamadas por día: 2 (mañana y tarde)

Costo/día = (650 × precio_input/1K + 180 × precio_output/1K) × 2
Costo/mes = Costo/día × 30

→ Sustituir precio_input y precio_output con los valores actuales
  de la página de precios de Anthropic al momento del cálculo.
```

!!! warning "Los precios de las APIs cambian — nunca uses precios de un documento"
    Los precios de Claude, GPT y Gemini se han reducido significativamente en los últimos dos años y pueden seguir cambiando. El número que aparecía en esta página la semana pasada puede estar desactualizado hoy. Siempre ir a la fuente oficial antes de calcular el modelo económico del producto.

**La decisión que el costo de la IA retroalimenta:**

Si el costo mensual de la API por usuario resulta ser $30 MXN y la suscripción planeada es $150 MXN/mes, el 20% del ingreso se va en inferencia antes de pagar nada más. Si ese número sube a $80 MXN, el modelo empieza a no cerrar.

Eso retroalimenta directamente la decisión de arquitectura de semana 5: **edge vs. cloud no es solo una decisión técnica — es una decisión económica.** Un modelo pequeño corriendo en el ESP32 tiene costo de inferencia prácticamente cero. Un modelo grande en la nube tiene costo variable que escala con cada usuario activo.

### Los costos de desarrollo — ciclos de aprendizaje

La presentación introduce un concepto crítico para proyectos de innovación: el costo de desarrollo no es lineal ni predecible. Se estructura en **ciclos de aprendizaje** — cada ciclo es un loop completo de diseño → construcción → prueba → aprender.

```
COSTO TOTAL DE DESARROLLO =
  Costo Fijo Directo        (salarios, licencias, espacio)
+ Costo Variable Directo    (materiales, prototipado, pruebas)
+ Costo Indirecto           (overhead: 10–20% de los directos)
+ Reserva para Contingencias (25–40% en proyectos de innovación)
```

**La reserva para contingencias en innovación es significativamente mayor** que en proyectos tradicionales (que usan 10–15%) porque en innovación no se conoce de antemano cuántas iteraciones se necesitarán.

**Estimación de ciclos de aprendizaje:**

El primer paso para estimar el costo de desarrollo es separar el producto final en sus componentes fundamentales. Después caracterizar cada una de las partes de esos componentes y asignar el costo unitario. Finalmente estimar el número de ciclos que necesitaremos para tener un producto funcional. 


| Escenario | Número de ciclos | Cuándo aplica |
|-----------|-----------------|---------------|
| Mínimo | 3 ciclos | El primer concepto funciona bien |
| Promedio | 5 - 7 ciclos | Punto de partida realista para estimación |
| Máximo | 8+ ciclos | Fallas técnicas importantes o rechazo del mercado |

```
Rango de costo de prototipado =
  Costo unitario del ciclo × (ciclos mínimos a máximos)
```

**Ejemplo resuelto — sensor agrícola:**

El equipo estima el costo de un ciclo de aprendizaje completo (diseño → construcción → prueba → aprender):

COSTO DE UN CICLO DE APRENDIZAJE

Costos fijos directos (por ciclo):
  Horas de ingeniería: 80h × $80 MXN/h          = $6,400 MXN
  Licencias de software (CAD, IDE, prorrateado)  = $500 MXN
  Subtotal fijos directos                        = $6,900 MXN

Costos variables directos (materiales de un prototipo):

| Componente | Componentes | Ciclos | Costo U | Costo Total |
| --- | --- | --- | --- | --- |
| Carcasa | Diseño, desarrollo, impresión | 4 | $180 | $720 |
| Electrónica | BOM electrónico (ESP32 + sensores + módulos), Consumibles | 6 | $970 | $5,820 |
| App | Desarrollo | 5 | $5,000 | $25,000 |
| Página | Desarrollo web | 5 | $5,000 | $25,000 |


  Subtotal variables directos por ciclo  = $1,350 MXN
  Costo variable directo total = $56,540

Costos indirectos (15% de los directos):
  ($6,900 + $1,350) × 0.15                       = $1,238 MXN

Costo base por ciclo = $56,540 + $1,350 + $1,238  = $59,128 MXN

Reserva para contingencias (30%):
  $59,128 × 0.30                                  = $17,338 MXN

COSTO TOTAL                                       = $76,865 MXN
```

Puede variar el número de ciclos dependiendo del expertisse del diseñador, sin embargo siempre se tiene que planear para el peor escenario, especialmente si la incertidumbre es alta. También conviene hacer una estimación del costo mínimo si todo sale bien y el costo máximo de los ciclos de aprendizaje si hubiera alguna contingencia con el fin de estresar los números y nunca quedar por debajo del costo final del proyecto

Presupuesto de desarrollo recomendado a presentar:
→ Usar el escenario promedio como base: ~$76,800 MXN
→ No presentar el mínimo — si algo sale mal, el proyecto
  corre el riesgo de quedar sin recursos antes de llegar a un producto funcional


*"¿Ven que la mayor parte del costo no es el BOM? Son las horas de ingeniería. En un proyecto de innovación, el tiempo del equipo es el recurso más caro — y el más difícil de estimar. Por eso la reserva para contingencias existe: no para gastarla, sino para tener margen cuando el ciclo toma el doble de lo planeado."*

**Lo que el ejercicio revela para su propio producto:**

El equipo hace este mismo cálculo con sus números reales — sus horas estimadas por ciclo, su BOM cotizado en semana 5, su proceso de manufactura elegido. El resultado no tiene que ser exacto: tiene que ser honesto sobre el orden de magnitud de la inversión que requiere llegar a un producto funcional.



### Diferenciación de costos — D, F, S

La tabla de costos de IDEO tiene una columna que la mayoría de las hojas de costeo no tienen: la clasificación D / F / S. No es burocracia — es la columna que le dice al equipo dónde tiene poder de decisión y dónde no, y qué costos está asumiendo porque realmente crean valor para el usuario versus los que asume porque no tiene alternativa.

**Las tres categorías:**

**(D) Costos de DIFERENCIACIÓN**
Son los costos que dan vida directamente a la propuesta de valor — los que hacen que el producto sea mejor o distinto para el usuario específico. Recortarlos destruye el diferencial.

En el food truck del ejemplo: la proteína orgánica ($240/kg) es D porque eso es exactamente lo que distingue al negocio de un food truck convencional. Sin proteína orgánica, la propuesta de valor desaparece. El food runner que hace entregas a domicilio también es D — nadie más en el espacio lo tiene.

En la app de storytelling: las licencias de historias ($100,000/app) son D — sin ese contenido licenciado la app no existe. El equipo de desarrollo también es D porque sin ellos no hay app.

**(F) Costos FLEXIBLES**
Importantes pero no esenciales — se pueden intercambiar, reducir, diferir, o encontrar alternativas mientras el equipo aprende qué valora realmente el usuario. No son opcionales para siempre, pero sí son negociables en etapa early.

En el food truck: la compra del camión y aparcamiento es F — al inicio se puede rentar un camión en lugar de comprarlo. En la app: el espacio de oficina es F — en etapa temprana se puede trabajar desde casa. Las computadoras son F — las que ya tiene el equipo sirven para empezar.

**(S) Costos ESTABLECIDOS**
Fuera del control del equipo — tarifas estándar, comisiones de plataformas, costos regulatorios, precios de proveedores sin margen de negociación. No se pueden eliminar ni reducir significativamente.

En el food truck: licencias municipales, gasolina, recogida de basura — hay que pagarlos sin importar el volumen. En la app: la comisión de la App Store (30% sobre cada venta) es S — Apple y Google no negocian con startups.

---

**El insight más importante de esta clasificación:**

> *"Si tienes demasiados costos en la columna D, o no puedes decidir cómo clasificarlos, es una señal para hacer una pausa y reflexionar en tu propuesta de valor. ¿Qué es realmente lo más importante para tus clientes? Los costos D deberían ser pocos, específicos, y directamente conectados con lo que el usuario valoraría perder si no estuvieran."*

La clasificación también revela dónde actuar cuando el modelo no cierra:
- Los costos **S** no se pueden recortar — hay que vivir con ellos o cambiar el modelo
- Los costos **F** son los primeros candidatos a reducir o diferir sin destruir el producto
- Los costos **D** son los últimos en tocar — si hay que recortarlos, hay un problema más profundo de propuesta de valor

---

**La tabla de costos:**

La plantilla ([el archivo Excel compartido](https://docs.google.com/spreadsheets/d/1JuSEMTup0SboFw5DALgj-5uJdznsZv_j/edit?usp=sharing&ouid=118419766353546707509&rtpof=true&sd=true)). Tiene dos secciones — CREAR y DISTRIBUIR —  con la columna D/F/S integrada.

```
CREAR la oferta
(recursos y gente necesarios para construir el producto ya en producción)
Pensar en:
· Componentes electrónicos, sensores, actuadores (BOM)
· PCB: fabricación y ensamble
· Carcasa: impresión 3D, mecanizado, molde
· Personal para ensamblar y probar
· Infraestructura cloud y APIs (incluida la IA)
· Licencias de software de desarrollo

DISTRIBUIR la oferta a los clientes
(recursos necesarios para que el producto llegue al usuario)
Pensar en:
· Empaque y logística de envío
· Canal de venta: plataforma e-commerce, distribuidores
· Soporte técnico y garantía
· Marketing digital y adquisición de usuarios
· Actualizaciones de firmware OTA
```

Cada fila tiene: nombre del costo → clasificación D/F/S → costo estimado → unidad de medida → cuántas unidades produce ese costo → **costo unitario** (calculado automáticamente).

El costo unitario total al final es el input directo para calcular el precio de venta y el punto de equilibrio.

**Ejemplo aplicado al sensor agrícola — clasificación D/F/S:**

| Costo | D/F/S | Por qué |
|-------|:-----:|---------|
| Sensor de humedad capacitivo de alta precisión | D | Define la calidad del dato — si se reemplaza por uno más barato, la recomendación de riego pierde precisión |
| Modelo de IA para recomendación agronómica | D | Es la diferenciación central — sin IA el producto es solo un sensor genérico |
| ESP32-S3 | F | Podría sustituirse por otro microcontrolador compatible — la elección es conveniente, no irreemplazable |
| Carcasa IP67 | F | Podría empezar con IP54 en el prototipo y escalar a IP67 en producción |
| PCB fabricado en JLCPCB | S | Precio estándar de mercado sin margen de negociación significativo |
| Comisión de la App Store (30%) | S | No negociable con Apple o Google |
| Infraestructura AWS IoT Core | S | Precio estándar por mensaje — sin alternativa equivalente a ese precio |



---

## Bloque 4 — Matemáticas financieras: ¿la aritmética del negocio cierra?
**Duración: 40 min · Min 1:10 – 1:50**

### Por qué este bloque en este curso

> *"Esta es la única clase de matemáticas financieras que van a ver en el contexto de sus proyectos como ingenieros mecatrónicos. No es un curso de finanzas — es el mínimo que necesitan para saber si un negocio tiene sentido antes de comprometer tres años de su vida construyéndolo."*

### Flujo de caja — la radiografía del negocio

El flujo de caja es el movimiento real de dinero que entra y sale del negocio en un período. No es lo mismo que las ganancias — un negocio puede ser "rentable en papel" y quedarse sin efectivo para operar.

```
Flujo de caja operativo = Entradas de efectivo − Salidas de efectivo

Entradas:    Ventas de hardware + suscripciones activas
Salidas:     BOM + manufactura + cloud + APIs + personal + overhead
```

**La pregunta que el flujo de caja responde:** ¿en qué mes el negocio deja de perder dinero y empieza a generar efectivo? Ese es el **punto de equilibrio** — el número de unidades vendidas donde los ingresos cubren exactamente los costos fijos y variables.

```
Punto de equilibrio (unidades) =
  Costos fijos totales / (Precio de venta − Costo variable por unidad)
```
```

Margen de contribución = Precio de venta - costos variables

El margen de contribución es una metrica de gran importancia. Nos dice cuanto aporta cada producto vendido a cubrir los costos fijos. Aumentar el margen de contribución disminuira el numero de productos que hay que vender para alcanzar el punto e equilibrio.   
```
---

### Precio de venta — dos métodos

El producto tiene dos componentes de precio con lógicas distintas. El hardware se vende una vez — su precio mínimo se puede calcular desde el costo. La suscripción se cobra mensualmente — su precio mínimo integra tanto los costos operativos recurrentes como la recuperación del hardware en un año.

**Método 1 — Cost-plus (costo más margen):**

```
PASO 1 — COSTO UNITARIO DEL HARDWARE
BOM + manufactura:              $380 MXN
Overhead (15%):                 $57 MXN
Contingencias (25% del BOM):    $95 MXN
──────────────────────────────────────
Costo unitario del hardware:    $532 MXN
```

```
PASO 2 — PRECIO MÍNIMO DE LA SUSCRIPCIÓN MENSUAL

El precio mínimo de la suscripción debe cubrir dos cosas:
los costos operativos mensuales por usuario activo,
y la recuperación del costo del hardware en 12 meses
con un costo financiero del 20% anual.

A) Recuperación del hardware en 12 meses (con costo financiero):
   Costo del hardware:                          $532 MXN
   Costo financiero (20% anual):                $106 MXN
   Total a recuperar en 12 meses:               $638 MXN
   Cuota mensual de recuperación:               $638 ÷ 12 = $53 MXN/mes

B) Costos operativos mensuales por usuario:
   Cloud + base de datos (prorrateado):         $18 MXN/mes
   Costo de la IA — Claude Haiku:
     · 2 llamadas/día × (650 tokens input
       + 180 tokens output) = 1,660 tokens/día
     · Precio referencia: ~$0.0003 USD / 1K tokens
     · Costo/día: 1,660 × $0.0003 / 1,000 = $0.00050 USD
     · Costo/mes: $0.00050 × 30 = $0.015 USD ≈ $0.27 MXN/mes
   Soporte técnico (estimado):                  $12 MXN/mes
   ──────────────────────────────────────────────────────
   Subtotal operativo:                          $30.27 MXN/mes

Costo total mensual por usuario:
   $53.00 (recuperación hardware)
 + $30.27 (operativos)
 = $83.27 MXN/mes

Con margen del 40%:
   $83.27 × 1.40 = $116.58 MXN/mes → redondeado: $119 MXN/mes
```

Este es el **precio mínimo de suscripción** — el piso por debajo del cual el negocio pierde dinero. El siguiente paso es compararlo con lo que el mercado está pagando (obtenido en el ejercicio de benchmarking de modelos de ingresos).

```
Si precio mínimo calculado < precio de mercado → hay margen de maniobra
Si precio mínimo calculado > precio de mercado → hay un problema:
   el equipo necesita reducir costos, subsidiir el hardware,
   o replantear el modelo de ingresos
```

**Método 2 — Value-based pricing (precio por valor entregado):**

El precio no se calcula desde el costo — se calcula desde el valor que el usuario recibe. Este método fija el techo, no el piso.

```
Ejemplo — sensor agrícola:
Pérdida evitada por estrés hídrico por ciclo:  $15,000 MXN
Valor capturado por el producto (10%):          $1,500 MXN/ciclo
Ciclos al año:                                  3
Valor anual para el usuario:                    $4,500 MXN
Precio anual que el usuario justificaría:       hasta $4,500 MXN
Precio mensual equivalente (techo):             hasta $375 MXN/mes
```

> *"El método 1 te da el piso: $119 MXN/mes mínimo para no perder dinero con este ejemplo. El método 2 te da el techo: $375 MXN/mes es lo que el usuario puede justificar. El precio real vive entre esos dos números. Cuanto más cerca del techo, mayor el margen — pero mayor también la fricción de ventas. Cuanto más cerca del piso, más fácil vender — pero menos margen para operar y crecer."*





---

### Valor del dinero en el tiempo

Un peso hoy vale más que un peso en el futuro por tres razones: puede invertirse y generar rendimientos, la inflación reduce su poder de compra, y hay riesgo de no recibirlo.

**Fórmula del Valor Presente (VP):**
```
VP = VF / (1 + i)^n

Donde:
VP = Valor Presente (lo que buscamos)
VF = Valor Futuro (la suma a recibir)
i  = Tasa de descuento (costo de oportunidad del capital)
n  = Número de períodos
```

**Ejercicio 1 — Valor Futuro con capitalización no anual:**

> Una empresa deposita $45,000 USD en una cuenta que paga 7.5% anual capitalizable trimestralmente. ¿Cuánto acumula en 5 años y 6 meses?
<!-- 
```
i trimestral = 7.5% / 4 = 1.875% = 0.01875
n trimestres = 5.5 años × 4 = 22 trimestres
VF = 45,000 × (1 + 0.01875)^22
VF = 45,000 × 1.5063 = $67,785 USD
```
-->
**Ejercicio 2 — Valor Presente de obligación futura:**

> Debe pagar $125,000 MXN en 48 meses. La tasa de descuento es 12% anual compuesto mensualmente. ¿Cuánto debe invertir hoy?
<!-- 
```
i mensual = 12% / 12 = 1% = 0.01
n = 48 meses
VP = 125,000 / (1 + 0.01)^48
VP = 125,000 / 1.6122 = $77,531 MXN
```
-->
**Ejercicio 3 — Flujos mixtos irregulares:**

> Flujos esperados: Año 1: $10,000; Año 3: $15,000; Año 5: $8,000. Tasa de descuento: 9%.
<!-- 
```
VP = 10,000/(1.09)^1 + 15,000/(1.09)^3 + 8,000/(1.09)^5
VP = 9,174 + 11,589 + 5,201
VP = $25,964
```
-->
---

### Valor Presente Neto (VPN)

El VPN calcula si un proyecto genera más valor del que cuesta, incorporando el valor del dinero en el tiempo. Un VPN positivo indica que el proyecto es rentable. El proyecto con mayor VPN es el más rentable al comparar alternativas.

```
VPN = −A + Σ (Ft / (1 + r)^t)

Donde:
A  = Inversión inicial
Ft = Flujo de caja neto en el período t
r  = Tasa de descuento = Tasa libre de riesgo + premio al riesgo
t  = Período
```

**Ejercicio 4 — Proyecto con flujos constantes (anualidad):**

> InnovaTech invierte $250,000 USD. Genera $60,000 USD anuales por 6 años. Tasa de descuento: 11%. ¿Es viable?
<!-- 
```
VPN = −250,000 + 60,000 × [1 − (1.11)^−6] / 0.11
VPN = −250,000 + 60,000 × 4.2305
VPN = −250,000 + 253,830
VPN = +$3,830 USD → Proyecto aceptado (VPN > 0, por poco)
```
-->
**Ejercicio 5 — VPN con flujos variables:**

> Inversión inicial: $50,000 USD. Flujos: Año 1: $7,500; Año 2: $12,000; Año 3: $20,000; Año 4: $25,000. Tasa: 4%.

<!-- 
```
VPN = −50,000 + 7,500/1.04 + 12,000/1.04² + 20,000/1.04³ + 25,000/1.04⁴
VPN = −50,000 + 7,212 + 11,094 + 17,790 + 21,370
VPN = +$7,466 USD → Viable
```
-->
**Ejercicio 6 — Con valor residual:**

> Maquinaria: inversión $1,000,000 USD. Flujos: Año 1: $300K; Año 2: $350K; Año 3: $375K; Año 4: $300K + valor salvamento $150K. Tasa: 10%.
<!-- 
```
VPN = −1,000,000 + 300,000/1.1 + 350,000/1.1² + 375,000/1.1³ + 450,000/1.1⁴
VPN = −1,000,000 + 272,727 + 289,256 + 281,794 + 307,228
VPN = +$151,005 USD → Viable
```
-->
**Ejercicio 7 — Comparación de proyectos:**

> Proyecto X vs. Y. Inversión inicial: $50,000 ambos. Tasa: 8%.

| Año | Proyecto X | Proyecto Y |
|-----|:----------:|:----------:|
| 1 | $25,000 | $10,000 |
| 2 | $25,000 | $20,000 |
| 3 | $25,000 | $45,000 |

Que proyecto es mas rentable?
<!-- 
```
VPN X = −50,000 + 25,000/1.08 + 25,000/1.08² + 25,000/1.08³
VPN X = −50,000 + 23,148 + 21,433 + 19,845 = +$14,426

VPN Y = −50,000 + 10,000/1.08 + 20,000/1.08² + 45,000/1.08³
VPN Y = −50,000 + 9,259 + 17,147 + 35,721 = +$12,127

Proyecto X tiene mayor VPN → se prefiere X
```
-->

**Ejercicio 8 — Análisis de sensibilidad:**

> Proyecto X (inversión $50,000, flujos $25,000 × 3 años). ¿Cómo cambia la decisión según la tasa de descuento? haz el ejercicio para 8%, 15%, 20% y 25%
haz una tabla:
 
| Tasa | VPN | Decisión |
|------|:---:|:--------:|
<!-- 
| 8% | +$14,426 | ✅ Aceptar |
| 15% | +$4,996 | ✅ Aceptar |
| 20% | −$726 | ❌ Rechazar |
| 25% | −$5,600 | ❌ Rechazar |
-->

> *"Esto es análisis de sensibilidad: la misma inversión puede ser buena o mala dependiendo del costo de oportunidad de su capital. Un emprendedor en México con acceso a crédito al 20% anual tiene que exigirle más a sus proyectos que uno con acceso al 8%."*

---

### Tasa Interna de Retorno (TIR)

La TIR es la tasa de descuento que hace que el VPN sea exactamente cero. Es la rentabilidad intrínseca del proyecto — independiente de las tasas del mercado.

**Regla de decisión:** si TIR > costo de capital del equipo → proyecto viable.

```
VPN = −A + Σ (Ft / (1 + TIR)^t) = 0

Se calcula por interpolación lineal:
TIR = r₁ + (r₂ − r₁) × VPN₁ / (VPN₁ − VPN₂)
```

**Ejercicio 9 — TIR por interpolación lineal:**

> Global Solutions: inversión $500,000 USD. Flujos: Año 1: $180K; Año 2: $200K; Año 3: $190K; Año 4: $170K. Costo de capital: 14%.

```
Probar r₁ = 14%:
VPN₁ = −500,000 + 180,000/1.14 + 200,000/1.14² + 190,000/1.14³ + 170,000/1.14⁴
VPN₁ = −500,000 + 157,895 + 153,893 + 128,384 + 100,560 = +$40,732

Probar r₂ = 22%:
VPN₂ = −500,000 + 180,000/1.22 + 200,000/1.22² + 190,000/1.22³ + 170,000/1.22⁴
VPN₂ = −500,000 + 147,541 + 134,394 + 104,679 + 76,826 = −$36,560

TIR = 14% + (22% − 14%) × 40,732 / (40,732 + 36,560)
TIR = 14% + 8% × 0.527 = 14% + 4.2% ≈ 18.2%

TIR (18.2%) > Costo de capital (14%) → Proyecto viable ✅
```

---

## Bloque 5 — Taller: el modelo económico del producto
**Duración: 10 min arranque en clase · continúa en casa**

### Instrucción al grupo

> *"Tienen 10 minutos para arrancar su modelo económico. No tiene que estar completo — tiene que estar empezado. Un BOM con los 5 componentes más caros de su arquitectura ya es un comienzo real. Lo que no hagan hoy lo hacen en casa."*

El equipo hace en clase:
1. Listar los 10 componentes de mayor costo de su BOM
2. Identificar su modelo de ingresos — ¿cuál de los 5 aplica a su producto?
3. Clasificar sus costos: ¿cuáles son D, cuáles F, cuáles S?

El resto va a casa.

---

## Tarea en casa (4 horas)

| Tarea | Tiempo | Entregable |
|-------|:------:|-----------|
| BOM completo con precios reales cotizados en LCSC, JLCPCB, DigiKey o MercadoLibre | 1.5h | Hoja de cálculo con componente, especificación, precio unitario, proveedor, tiempo de entrega |
| Modelo financiero: costo unitario, precio de venta (cost-plus y value-based), punto de equilibrio, proyección de flujo de caja a 12 meses | 1.5h | Hoja de cálculo con las fórmulas visibles — no solo resultados |
| Calcular el costo mensual de la IA para su producto con su arquitectura real | 30 min | Tabla: llamadas/día × tokens × precio × usuarios objetivo |
| Ejercicios 4–9 de la presentación que no se resolvieron en clase | 30 min | Resolución paso a paso |

### Prompt — Claude: modelo económico del producto

```
Actúa como un analista financiero con especialización en
modelos de negocio para startups de hardware + software en
mercados emergentes latinoamericanos. Tu metodología combina
el análisis de costos reales con proyecciones financieras
conservadoras — siempre que hay incertidumbre, usas el escenario
menos favorable para no generar falsas expectativas. Cuando
los números no cierran, lo dices directamente y propones
qué palancas puede mover el equipo: reducir costos, ajustar
precio, cambiar modelo de ingresos, o reducir el alcance.

Somos un equipo de emprendedores en México con un producto
de hardware + software. Necesitamos construir nuestro modelo
económico antes de comprometer recursos en manufactura.

NUESTRO PRODUCTO:
Nombre: [nombre]
Descripción: [qué hace y para quién]
Propuesta de valor: [Versión 3 del prompt de semana 4]

MODELO DE INGRESOS ELEGIDO:
[pegar el modelo elegido con su justificación]
Precio de hardware: $[MXN] (venta única / subsidiado)
Precio de suscripción: $[MXN]/mes (si aplica)

NUESTRO BOM (componentes principales):
[pegar el BOM con precios reales cotizados]
Costo de PCB + ensamble (JLCPCB PCBA): $[MXN]
Costo de carcasa (impresión 3D / otro): $[MXN]
Mano de obra de ensamble y prueba: $[MXN]

COSTO DE LA IA:
Modelo usado: [Claude / GPT / Gemini / modelo propio]
Llamadas por día por usuario: [número]
Tokens promedio por llamada: [número]
Precio por token: [$USD]
Costo calculado: $[MXN]/mes por usuario

INFRAESTRUCTURA CLOUD:
Servicio: [AWS / GCP / Firebase / otro]
Costo estimado: $[MXN]/mes para [N] usuarios activos

VOLUMEN OBJETIVO:
Prueba de mercado (año 1): [N] unidades
Crecimiento año 2: [N] unidades

Con esta información, construye el modelo económico completo:

PASO 1 — COSTO UNITARIO REAL:
Desglose completo del costo por unidad a volumen de 10
(prueba de mercado) y a volumen de 100 (escala inicial).
Incluir: BOM + manufactura + porción de cloud + porción de IA
+ overhead (15%) + contingencias (25%).

PASO 2 — PRECIO DE VENTA:
Cost-plus con margen del 40%: ¿cuánto sería?
Value-based: dado el valor que entrega al usuario, ¿cuánto
podría cobrar? ¿El segmento pagaría ese precio?
Precio recomendado y por qué.

PASO 3 — PUNTO DE EQUILIBRIO:
Con el precio recomendado, ¿cuántas unidades necesitan vender
para cubrir los costos fijos del primer año?
¿Es ese número alcanzable con los recursos del equipo?

PASO 4 — FLUJO DE CAJA A 12 MESES:
Proyección mes a mes asumiendo:
· Ventas de hardware según el plan de volumen
· Suscripciones acumuladas (usuarios activos × precio mensual)
· Costos fijos mensuales (cloud, IA, overhead)
· Inversión inicial en el mes 0

¿En qué mes se alcanza flujo de caja positivo?

PASO 5 — VPN DEL PROYECTO (simplificado):
Con los flujos del paso 4 y una tasa de descuento del 15%
(costo de oportunidad razonable para emprendedor en México),
¿el VPN es positivo? ¿El proyecto crea valor en 12 meses?

FORMATO DE SALIDA:

════════════════════════════════════════════════════════
MODELO ECONÓMICO
Producto: [nombre] · Modelo de ingresos: [cuál]
════════════════════════════════════════════════════════

COSTO UNITARIO
A 10 unidades: $[MXN] · A 100 unidades: $[MXN]
Componente de mayor costo: [cuál y qué porcentaje del total]
El costo de la IA representa: [%] del costo unitario

PRECIO DE VENTA
Cost-plus (40%): $[MXN] hardware + $[MXN]/mes suscripción
Value-based: hasta $[MXN] hardware + $[MXN]/mes suscripción
Precio recomendado: $[MXN] + $[MXN]/mes — por qué: [razón]

PUNTO DE EQUILIBRIO
Unidades necesarias año 1: [N]
¿Alcanzable? ✅/⚠️/❌ — [justificación]

FLUJO DE CAJA (resumen)
Mes de flujo positivo: mes [N]
Inversión acumulada antes de break-even: $[MXN]

VPN A 12 MESES (tasa 15%)
VPN = $[MXN] → Proyecto [viable / marginalmente viable / inviable]

────────────────────────────────────────────────────────
ALERTAS:
[Si hay algo que no cierra o que requiere decisión del equipo —
  directo y específico. Si el costo de la IA destruye el margen,
  decirlo. Si el precio que el mercado pagaría es menor que el
  cost-plus, decirlo.]

PALANCAS DISPONIBLES:
[Las 2–3 decisiones que el equipo puede tomar para mejorar
  la viabilidad: cambiar el modelo de IA a edge, subir el precio
  de suscripción, reducir el BOM cambiando un componente,
  aumentar el volumen objetivo]
════════════════════════════════════════════════════════
```

---

## Bibliografía y recursos de la semana

### Lecturas de referencia

Brealey, R. A., Myers, S. C., & Allen, F. (2020). *Principles of Corporate Finance* (13.ª ed.). McGraw-Hill.
→ Capítulos 2–3: valor presente y criterios de inversión. El texto estándar de finanzas corporativas — para quien quiera ir más a fondo en VPN y TIR.

Smith, P. G., & Merritt, G. M. (2002). *Proactive Risk Management: Controlling Uncertainty in Product Development*. Productivity Press.
→ Base de la metodología de ciclos de aprendizaje y reservas de contingencia para proyectos de innovación.

IDEO. (2015). *The Field Guide to Human-Centered Design*. IDEO.org.
→ Sección "Revenue Models": el origen de la tabla de modelos de ingresos usada en el Bloque 2. Descarga gratuita en ideo.com.

### Herramientas de la semana

| Herramienta | Uso | Acceso |
|-------------|-----|--------|
| **LCSC** | Cotización de componentes electrónicos | lcsc.com |
| **JLCPCB** | PCB + ensamble (PCBA) con cotización en línea | jlcpcb.com |
| **DigiKey MX** | Componentes con disponibilidad en México | digikey.com.mx |
| **Google Sheets** | Modelo financiero: BOM, flujo de caja, VPN | sheets.google.com |
| **Anthropic Pricing** | Costo real de la API de Claude por token | anthropic.com/pricing |
| **OpenAI Pricing** | Costo real de GPT por token | openai.com/pricing |

---

## Lo que el equipo debe poder responder al salir

- [ ] ¿Cuál es el costo unitario real de su producto a 10 unidades?
- [ ] ¿Qué modelo de ingresos eligieron y cuál es el desafío de diseño que tienen que resolver para que funcione?
- [ ] ¿Cuánto cuesta mensualmente la IA en su producto por usuario activo?
- [ ] ¿El VPN de su proyecto a 12 meses es positivo con los números reales del BOM?


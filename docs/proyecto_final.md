# Proyecto final: la página de memoria del proyecto

!!! abstract "Una sola página, tres usos"
    Dentro de la página web de su equipo van a construir una sección llamada **Proyecto final**. Esa sección cumple tres funciones al mismo tiempo. Es su **guía**: se llena semana a semana con lo que ya producen en clase. Es su **plan de negocio**: alguien que no conoce el curso la lee y entiende qué construyeron, para quién y por qué es un negocio. Y es la **memoria de calificación**: el evaluador verifica en ella, con evidencia, cada criterio de la rúbrica.

!!! warning "No es una colección de respuestas de IA"
    Cada sección muestra una **decisión del equipo** y la evidencia que la sostiene. El resultado de un prompt es insumo, no contenido. Una página que pega salidas de Claude sin decisión, sin evidencia y sin lo que el equipo corrigió se lee como una página que nadie pensó.

---

## Cómo se escribe cada sección

Todas las secciones usan la misma plantilla de cuatro líneas. Es la manera de que el proyecto cuente su ciclo de aprendizaje: lo que decidieron, con qué evidencia, qué cambió y qué sigue abierto.

```
Versión y fecha: [por ejemplo, "Versión 2, semana 7"]
Decisión:   lo que el equipo decidió, en una oración
Evidencia:  el dato, la prueba o el documento que la sostiene (con enlace)
Qué cambió: respecto a la versión anterior, y por qué
Qué falta:  lo que sigue siendo hipótesis o está pendiente
```

**Siete reglas de la página:**

1. **Cada afirmación lleva su evidencia.** Sin evidencia se marca como **HIPÓTESIS**. Un equipo que sabe qué no sabe está mejor parado que uno que lo asume todo.
2. **Cada número tiene fuente o se marca como supuesto.** Un número sin origen no se publica.
3. **Las fallas se documentan y se diagnostican.** Un equipo que explica en qué frontera falló su sistema y cómo lo encontró suma. Uno que lo esconde resta.
4. **Una pantalla por sección.** El detalle va a los anexos con enlace; la sección muestra la decisión, no el expediente.
5. **Todos los enlaces funcionan sin iniciar sesión** (repositorio, landing, videos, hojas de cálculo).
6. **La página se actualiza semana a semana.** La fecha de versión de cada sección demuestra el proceso iterativo.
7. **El resumen ejecutivo se escribe al final**, cuando ya se sabe qué es lo importante.

---

## Cómo se conecta con la rúbrica

La evaluación final dura 15 minutos por equipo: 3 de pitch, 7 de demo y 5 de retroalimentación. Lo que el panel ve ahí se respalda en la página, y lo que el panel no alcanza a ver se califica directamente en ella.

| Criterio de la rúbrica | Peso | Se ve en la evaluación | Se respalda en las secciones |
|------------------------|:----:|------------------------|------------------------------|
| Producto físico funcionando con IA | 30% | Demo de 7 min | 7, 8, 9, 10, 11, 17, 21 |
| Aplicación conectada al producto | 25% | Demo de 7 min | 8, 12, 17, 18 |
| Landing page de lanzamiento | 15% | Demo (tramo de la compra) | 19 |
| Pitch | 15% | Pitch de 3 min y retroalimentación | 0, 2, 5, 13, 15, 20 |
| Documentación técnica y BOM | 10% | Solo en la página | 3, 4, 6, 7, 8, 11, 13, 14, 15, 16, 18 |
| Entregables semanales y proceso | 5% | Solo en la página y el repositorio | 1, 10, 21, 22, Anexo B |

---

## Índice de la página

### Portada

| # | Sección | Qué debe contener | Viene de | Rúbrica |
|---|---------|-------------------|----------|---------|
| 0 | **Resumen ejecutivo** | Nombre y logotipo; la propuesta de valor en 25 palabras o menos; foto o render del producto; tres cifras clave (mercado alcanzable, precio, economía unitaria); enlaces al repositorio, la landing, el video del pitch y el video de respaldo de la demo; el estado del proyecto en una oración honesta. Una pantalla. | Semanas 4, 6, 7, 9 | Pitch |

### Parte I. Oportunidad y mercado

| # | Sección | Qué debe contener | Viene de | Rúbrica |
|---|---------|-------------------|----------|---------|
| 1 | **Equipo** | Perfil del equipo (nombres, roles, área de interés), acuerdo de colaboración y quién hizo qué. | Semana 1 | Proceso |
| 2 | **Problema y oportunidad** | Pain-Gain Map con el dolor y la ganancia principales; la oportunidad en una oración; los criterios con los que se eligió y las alternativas descartadas; evidencia de deseabilidad y la defensa de la oportunidad. | Semana 2 | Pitch |
| 3 | **Usuario y evidencia de campo** | Síntesis de al menos 3 entrevistas (hipótesis confirmada, ajustada o refutada, con citas textuales); segmento accionable en sus cuatro capas, cada dato marcado VERIFICADO o HIPÓTESIS; hipótesis críticas pendientes. | Semanas 3 y 4 | Documentación |
| 4 | **Mercado y competencia** | TAM, SAM y SOM con la cadena de filtros y la fuente de cada número; competidores directos, indirectos y sustitutos, y el más peligroso; mapa de posicionamiento; lienzo estratégico con las cuatro acciones (eliminar, reducir, incrementar, crear). | Semana 4 | Documentación |
| 5 | **Propuesta de valor y oferta** | La propuesta de valor (25 palabras o menos) junto a la oferta técnica; el nivel en la pirámide de Bain; la evaluación Insightful, Unique, Targeted; el error que cometía la primera versión. | Semana 4 | Pitch |
| 6 | **Propiedad intelectual, marca y vigilancia** | Nombre elegido y resultado de la búsqueda fonética en el IMPI; FTO (alta, media o baja) con la vigilancia tecnológica que lo sustenta (bases consultadas y patentes relevantes); el ajuste hecho si el resultado fue medio o bajo; estrategia de protección. | Semana 3 | Documentación |

### Parte II. Producto

| # | Sección | Qué debe contener | Viene de | Rúbrica |
|---|---------|-------------------|----------|---------|
| 7 | **Especificación del producto (PDS)** | Las cuatro categorías de requerimientos (funcionales, desempeño, interfaz, restricción), mínimo 4 en cada una, cada requerimiento con su criterio de verificación; una columna de estado (cumple, no cumple, pendiente) con enlace a la prueba que lo comprueba; la definición del first-iteration product. | Semanas 5 y 9 | Producto, Documentación |
| 8 | **Arquitectura del sistema** | Diagrama de bloques anotado (hardware, software, IA, protocolos, flujo de datos); la decisión edge, cloud o híbrido con sus tres puntos de justificación y su consecuencia; por qué cada protocolo y no otro; la versión final tras la integración y qué cambió respecto a la de la semana 5. | Semanas 5 y 9 | Producto, App, Documentación |
| 9 | **Diseño del producto** | Principios de diseño aplicados (cuáles de los siete y dónde se ven en el objeto); tabla morfológica; tres conceptos; matriz de Pugh con criterios y pesos (deseabilidad con al menos 40%); concepto elegido con render y boceto técnico con cotas; cómo evolucionó el diseño del boceto al producto final. | Semana 6 | Producto |
| 10 | **Prototipos y evidencia** | Por cada prototipo: la pregunta, el tipo y la resolución, qué se construyó, la evidencia recolectada, el aprendizaje y el cambio al diseño; una línea de tiempo del ciclo de aprendizaje con fotos. | Semana 8 | Producto, Proceso |
| 11 | **Manufactura, DFM y circularidad** | BOM final con componente, especificación, precio unitario, proveedor y tiempo de entrega; volumen objetivo y el proceso de manufactura que le corresponde; la revisión DFM con el costo unitario antes y después; respuestas a las cuatro preguntas de circularidad y lo que se cambió por ellas; cómo reproducir una unidad. | Semanas 5, 7 y 8 | Documentación, Producto |
| 12 | **Aplicación conectada** | Wireframes y flujo de usuario; los estados de la app (cargando, normal, alerta, sin conexión, error); cómo se conecta con el dispositivo (protocolo y formato del dato); capturas; cómo ejecutarla (APK o URL); enlace al repositorio con README y commits por sesión de trabajo; limitaciones conocidas. | Semanas 6 y 9 | App |

### Parte III. Negocio

| # | Sección | Qué debe contener | Viene de | Rúbrica |
|---|---------|-------------------|----------|---------|
| 13 | **Modelo de negocio (Business Blueprint)** | El Business Blueprint de una página con sus ocho cajas (clientes, oferta, modelo de ingresos y precio, canales, propuesta de valor, costos, socios, equipo y recursos), cada una con enlace a la sección que la sustenta; el benchmarking de tres empresas con oferta similar; el modelo de ingresos elegido y su desafío de diseño. Es el plan de negocio en una sola vista. | Semanas 4 y 7 | Pitch, Documentación |
| 14 | **Costos, precio y viabilidad financiera** | Tabla de costos CREAR y DISTRIBUIR con clasificación D, F, S y costo unitario; costo de la IA medido (tokens medidos, no estimados); costo de desarrollo por ciclos de aprendizaje (mínimo, promedio, máximo); precio con cost-plus y value-based y el rango entre piso y techo; punto de equilibrio; flujo de caja a 12 meses; VPN con la tasa usada y su justificación. | Semana 7 | Documentación |
| 15 | **Go-to-market y economía unitaria** | Perfil del cliente número 1; canales elegidos y por qué; plan de preventa o de piloto; CAC, LTV, churn, LTV ÷ inversión y payback, con cada supuesto marcado como medido o supuesto; sensibilidad y palancas con su efecto numérico. | Semana 9 | Pitch, Documentación |
| 16 | **Regulación y aspectos legales** | Checklist por tema (radio y homologación, datos personales, seguridad y etiquetado, baterías, licencias de software y del modelo de IA, términos de venta, economía circular, exportación si aplica) con estatus VERIFICADO o POR VERIFICAR y fuente oficial; aviso de privacidad y términos básicos de la app si recolecta datos; qué debe resolverse antes de vender a un tercero. | Semanas 8 y 9 | Documentación |

### Parte IV. Validación y lanzamiento

| # | Sección | Qué debe contener | Viene de | Rúbrica |
|---|---------|-------------------|----------|---------|
| 17 | **Integración y pruebas del sistema** | Las cuatro fronteras del sistema; resultados de las pruebas T1 a T6 con su evidencia (registros, mediciones, fotos); bugs encontrados, en qué frontera y cómo se diagnosticaron; lo que no funciona todavía y por qué; el checklist de listo (hardware sin laptop, app desplegada, landing publicada, flujo sin intervención). | Semana 9 | Producto, App |
| 18 | **Pruebas con usuarios** | El protocolo de 30 minutos usado; cinco sesiones (tres del segmento, dos de otros equipos); tabla por tarea con éxito sin ayuda, tiempo y SEQ; hallazgos por severidad con citas; cambios hechos; señal de negocio separando compromisos reales de opiniones. | Semana 9 | Documentación, App |
| 19 | **Landing page** | URL publicada; headline, visual, beneficios, precio visible y un solo CTA; evidencia en la página; metadatos y Open Graph; métricas (visitas, clics en el CTA, pre-registros); el prompt con el que se construyó. | Semana 9 | Landing |
| 20 | **Pitch y demo** | Video del pitch de 3 minutos con su guion y la evidencia de cada afirmación; guion de la demo de 7 minutos con plan B por tramo; video de respaldo de la demo; las preguntas difíciles de inversionista con su respuesta y enlace a la sección que la sostiene. | Semana 9 | Pitch |

### Parte V. Cierre

| # | Sección | Qué debe contener | Viene de | Rúbrica |
|---|---------|-------------------|----------|---------|
| 21 | **Uso de IA en el proyecto** | *En el proceso:* los cinco prompts que más cambiaron el proyecto, qué se pidió, qué respondió la IA, qué corrigió el equipo y por qué (incluye un caso donde la IA se equivocó). *En el producto:* qué hace el modelo, dónde corre, qué recibe y qué devuelve, su costo medido por usuario, qué pasa si falla y por qué el producto sería peor sin IA. | Semanas 1 a 9 | Producto, Proceso |
| 22 | **Reflexión y siguientes pasos** | El aprendizaje más importante del semestre (un párrafo por integrante, firmado); qué harían distinto; las hipótesis críticas que siguen sin verificar y cómo las verificarán; el plan de 90 días (piloto, financiamiento o primer cliente); los riesgos principales. | Cierre del curso | Proceso |

### Anexos

| Anexo | Contenido |
|-------|-----------|
| **A** | BOM completo con cotizaciones y enlaces a los proveedores |
| **B** | Repositorio, README, bitácora de commits y bitácora de entregables semanales |
| **C** | Archivos de diseño: CAD, PCB, esquemáticos y firmware |
| **D** | Datos crudos: notas de entrevistas y de pruebas de usuario (con consentimiento) |
| **E** | Hojas de cálculo del modelo financiero, con las fórmulas visibles |
| **F** | Bibliografía y fuentes de datos del proyecto |

---

## Esqueleto de la página

Para empezar, el equipo copia esta estructura en su sitio y la va llenando semana a semana:

```
# Proyecto final: [nombre del producto]

## 0. Resumen ejecutivo

## Parte I. Oportunidad y mercado
## 1. Equipo
## 2. Problema y oportunidad
## 3. Usuario y evidencia de campo
## 4. Mercado y competencia
## 5. Propuesta de valor y oferta
## 6. Propiedad intelectual, marca y vigilancia

## Parte II. Producto
## 7. Especificación del producto (PDS)
## 8. Arquitectura del sistema
## 9. Diseño del producto
## 10. Prototipos y evidencia
## 11. Manufactura, DFM y circularidad
## 12. Aplicación conectada

## Parte III. Negocio
## 13. Modelo de negocio (Business Blueprint)
## 14. Costos, precio y viabilidad financiera
## 15. Go-to-market y economía unitaria
## 16. Regulación y aspectos legales

## Parte IV. Validación y lanzamiento
## 17. Integración y pruebas del sistema
## 18. Pruebas con usuarios
## 19. Landing page
## 20. Pitch y demo

## Parte V. Cierre
## 21. Uso de IA en el proyecto
## 22. Reflexión y siguientes pasos

## Anexos A a F
```

---

## Cuándo se llena cada sección

La página crece con los entregables semanales. Esta tabla dice qué sección cierra cada semana:

| Semana | Entregable de la semana | Secciones que se llenan |
|:------:|-------------------------|-------------------------|
| 1 | Perfil del equipo | 1 |
| 2 | Reporte de oportunidad | 2 |
| 3 | Vigilancia tecnológica, marca y entrevistas | 3 (entrevistas), 6 |
| 4 | Canvas de mercado y propuesta de valor | 3 (segmento), 4, 5 |
| 5 | PDS y arquitectura | 7, 8, 11 (BOM preliminar) |
| 6 | Concepto de diseño, Pugh y boceto | 9, 12 (wireframes) |
| 7 | Viabilidad técnica y económica | 13, 14, 11 (BOM cotizado) |
| 8 | Prototipado, DFM y economía circular | 10, 11 (DFM y circularidad) |
| 9 | Integración, go-to-market y pitch | 15, 16, 17, 18, 19, 20 |
| Trabajo final | Sistema, página y videos terminados | 0, 12 (app construida), 21, 22, anexos |

---

## Ruta de lectura de 10 minutos para el evaluador

Un evaluador con poco tiempo verifica el proyecto en este orden:

| Minutos | Sección | Qué verifica |
|:-------:|---------|--------------|
| 1 | 0. Resumen ejecutivo | Qué es el proyecto y en qué estado está |
| 1 | 5. Propuesta de valor | Si la propuesta nombra al usuario, el resultado y por qué ellos |
| 2 | 13. Business Blueprint | Si el negocio tiene sentido en una sola vista |
| 2 | 17. Integración y pruebas | Si el sistema funciona y si el equipo sabe diagnosticarlo |
| 2 | 18. Pruebas con usuarios | Si hay evidencia de que alguien externo lo usó |
| 1 | 21. Uso de IA | Si la IA tiene un propósito real |
| 1 | 20. Pitch y demo | Los videos y el guion |

---

## Si un inversionista busca un plan de negocio

La misma página se lee como plan de negocio. Esta es la correspondencia:

| Lo que el lector busca | Dónde está |
|------------------------|------------|
| Resumen ejecutivo | 0 |
| Problema | 2, 3 |
| Solución y propuesta de valor | 5, 9 |
| Mercado y competencia | 4 |
| Modelo de negocio | 13 |
| Operaciones y manufactura | 11 |
| Finanzas y economía unitaria | 14, 15 |
| Aspectos legales | 16 |
| Tracción y validación | 18, 19 |
| Equipo | 1 |
| Riesgos y siguientes pasos | 22 |


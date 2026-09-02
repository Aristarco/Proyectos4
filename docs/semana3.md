# Semana 3 — Propiedad intelectual, marca y vigilancia tecnológica

!!! abstract "Blueprint IDEO: Creación de valor · DVF: 🟢 Factible"
    La semana anterior el equipo identificó una oportunidad deseable. Esta semana responde si puede apropiársela: ¿alguien ya protegió lo que quieren construir? ¿pueden registrar su marca? ¿qué tan libre es el espacio tecnológico donde van a operar? Y por fin — con la oportunidad clara y verificada — entrevistan usuarios reales.

---

## Distribución de tiempo presencial

| Paso | Contenido | Tiempo | Modo |
|------|-----------|:------:|------|
| 1 | Defensas semana 2 | 15 min | Presentación por equipos |
| 2 | Propiedad intelectual: panorama completo | 40 min | Exposición del instructor |
| 3 | Cómo elegir y validar un nombre de marca con IA | 20 min | Taller |
| 4 | Búsqueda fonética de marcas — demo IMPI | 10 min | Demo en vivo |
| 5 | Vigilancia tecnológica: qué hay protegido de su idea | 20 min | Taller |
| 6 | Mini-taller de entrevistas: protocolo y ensayo | 15 min | Práctica en pares |
| **Total** | | **120 min** | |

!!! tip "Lo que se mueve a semana 4"
    Búsqueda fonética individual, vigilancia tecnológica profunda y síntesis de entrevistas. Semana 4 abre con 30 min de cierre de estos tres hilos.

---

## Paso 1 — Defensas semana 2

**Duración: 15 min**

=== "Equipos aprobados"
    90 segundos. Solo la oportunidad en una oración + la hipótesis más importante para esta semana.

=== "Equipos regresados"
    2 minutos. Qué cambió, por qué cambió, y la oportunidad revisada.

!!! note "Nota del instructor"
    No dejar que las defensas se extiendan. El valor es el cierre psicológico, no la profundidad.

---

## Paso 2 — Propiedad intelectual: panorama completo

**Duración: 40 min · Exposición del instructor**

### Por qué le importa la PI a un emprendedor

!!! danger "Lanzas sin revisar y te demandan"
    Una empresa con patente vigente te envía una carta de cese. Tienes que retirar el producto después de meses de desarrollo.

!!! danger "No registras y alguien más lo hace"
    Tu startup lleva 18 meses operando sin registrar su marca. Un competidor la registra primero. Legalmente, el nombre es de ellos.

!!! danger "Usas una librería sin leer la licencia"
    Tu firmware usa una librería GPL. Eso obliga a publicar todo tu código fuente — el secreto industrial desaparece por una línea de `#include`.

### Los cinco instrumentos de PI

=== "Marca registrada"
    - **Protege:** el nombre, logo o signo que distingue el producto
    - **Duración:** 10 años renovables indefinidamente
    - **Costo aprox:** $3,000–6,000 MXN por clase en IMPI
    - **Clases relevantes:** Clase 9 (electrónica/software), Clase 42 (servicios tecnológicos)
    - **Cuándo:** antes de lanzar públicamente

=== "Patente de invención"
    - **Protege:** solución técnica nueva y no obvia
    - **Duración:** 20 años no renovables
    - **Costo aprox:** $15,000–80,000 MXN + años de tramitación
    - **Para startups early-stage:** casi nunca al inicio. La velocidad protege mejor.

=== "Modelo de utilidad"
    - **Protege:** mejoras a objetos o dispositivos existentes
    - **Duración:** 10 años no renovables
    - **Tramitación:** más rápida (1–2 años)
    - **Para este grupo:** más relevante que la patente en la mayoría de casos

=== "Diseño industrial"
    - **Protege:** apariencia ornamental (forma, líneas, colores)
    - **Duración:** 15 años
    - **Aplica cuando:** el diferencial es cómo se ve, no cómo funciona

=== "Derechos de autor"
    - **Protege:** código fuente, documentación, diseños gráficos
    - **Duración:** vida del autor + 100 años
    - **Costo:** prácticamente cero — nace automáticamente al crear

=== "Secreto industrial"
    - **Protege:** algoritmos, fórmulas, datos de entrenamiento de IA
    - **Duración:** indefinida mientras se mantenga en secreto
    - **Ventaja:** no requiere revelar el funcionamiento

### PI de software y modelos de IA

!!! warning "Licencias open source — regla práctica"
    - **MIT / Apache 2.0** ✅ — uso comercial libre
    - **LGPL** ✅ — permite enlazar sin contaminar el código propio
    - **GPL v2/v3** ⚠️ — si la incluyes, todo el código debe publicarse bajo GPL

### Estrategia pragmática

| Prioridad | Acción | Por qué |
|-----------|--------|----------|
| **1 — Siempre** | Registro de marca | Barato, rápido, el más doloroso de no tener |
| **2 — Con tracción** | Modelo de utilidad / diseño industrial | Cuando hay capital y diferencial real |
| **3 — Estrategia** | Velocidad de ejecución | Llegar antes protege más que una patente en trámite |
| **Siempre** | NDA con colaboradores | Protege el secreto industrial desde el día 1 |

---

## Paso 3 — Cómo elegir y validar un nombre de marca con IA

**Duración: 20 min · Taller**

### Criterios de un buen nombre

| Criterio | La trampa más común |
|----------|----------------------|
| **Pronunciable** ES/EN | Nombres que un angloparlante no lee pierden alcance |
| **Corto** — 2–3 sílabas | Los de 4+ sílabas se acortan solos |
| **Sin significado negativo** | Hay marcas famosas que significan palabras obscenas en otro idioma |
| **Registrable** | El IMPI rechaza nombres genéricos como "Sensor Agua" |
| **Dominio disponible** | .com o .mx tomado obliga a variantes torpes |
| **Coherente con la emoción** | No qué hace — cómo se siente usarlo |

### Prompt 1 — Generación de nombres (Claude)

```
Actúa como un estratega de naming con 15 años de experiencia
creando marcas para productos de tecnología en mercados
latinoamericanos. Tu metodología combina lingüística aplicada,
posicionamiento y criterios de registrabilidad del IMPI.

Somos emprendedores en México con: app con IA + artefacto
físico inteligente + página web de venta.

Propuesta de valor: [oportunidad en una oración de semana 2]
Usuario: [segmento del Pain-Gain Map]
Concepto: [Concepto Recomendado en 2–3 oraciones]
Emoción buscada: [cómo se siente el usuario al usarlo]

Genera 12 nombres (máx 3 sílabas, pronunciable en ES):

A — EVOCADORES (3): evocan emoción sin describir el producto
B — COMPUESTOS (3): dos raíces fusionadas en una palabra nueva
C — INVENTADOS (3): sin significado previo, pronunciables en ES
D — DISRUPTIVOS (3): rompen la convención de la categoría

Por cada nombre: pronunciación ES/EN, qué evoca, riesgo de antecedente.
```

!!! tip "Pausa (2 min)"
    Elige las **3 que más resuenan** — no las más seguras, las que generan algo.

### Prompt 2 — Evaluación de los 3 finalistas (Claude)

```
Actúa como consultor senior de marca para startups de hardware
en mercados emergentes. Señala los problemas que los equipos
no quieren ver.

Producto: [descripción en 2 oraciones]
Usuario: [segmento]
Finalistas: 1. [A]  2. [B]  3. [C]

Evalúa en 7 dimensiones:
1. Memorabilidad (prueba del bar)
2. Pronunciabilidad ES/EN
3. Registrabilidad IMPI
4. Coherencia emocional
5. Riesgo semántico (otros idiomas + jerga)
6. Escalabilidad LATAM
7. Diferenciación en categoría IoT/hardware

Puntaje ✅/⚠️/❌ por dimensión + veredicto.
Cierra con: nombre recomendado al IMPI y alternativa si tiene antecedente.
```

### Prompt 3 — Verificación digital (Perplexity)

```
Actúa como investigador de inteligencia de marca digital
para startups latinoamericanas.

CANDIDATO 1: [nombre]  CANDIDATO 2: [nombre]

Verifica para cada uno:
1. Dominio .com — ¿tomado? ¿por quién?
2. Dominio .mx
3. Redes sociales (Instagram, X, LinkedIn, TikTok)
4. App Store / Google Play
5. Uso comercial en México o LATAM
6. Primeros resultados Google

Semáforo por candidato: 🟢 libre / 🟡 parcial / 🔴 riesgo
Comparativa final: ¿cuál llevar al IMPI?
```

---

## Paso 4 — Búsqueda fonética en IMPI: demo en vivo

**Duración: 10 min · Demo del instructor**

La búsqueda fonética determina si un nombre está registrado o en trámite — incluyendo nombres que **suenan similar**.

**Sitio:** [marcanet.impi.gob.mx](https://marcanet.impi.gob.mx)

El instructor muestra: búsqueda por clase de Niza, lectura del estado (vigente/trámite/caducado), y qué hacer si hay antecedente.

!!! note "Backup si IMPI está caído"
    [tmdn.org](https://www.tmdn.org) · [tmsearch.uspto.gov](https://tmsearch.uspto.gov)

---

## Paso 5 — Vigilancia tecnológica

**Duración: 20 min · Taller**

### Mapa de bases de datos: México → LATAM → Global

| Capa | Base | URL |
|------|------|-----|
| **México** | IMPI/SIGA | [siga.impi.gob.mx](https://siga.impi.gob.mx) |
| **LATAM** | LATIPAT (18 países) | [latipat.epo.org](https://latipat.epo.org) |
| **LATAM** | INPI Brasil | [busca.inpi.gov.br](https://busca.inpi.gov.br) |
| **Global** | Lens.org | [lens.org](https://www.lens.org) |
| **Global** | Google Patents | [patents.google.com](https://patents.google.com) |
| **Global** | Espacenet | [worldwide.espacenet.com](https://worldwide.espacenet.com) |

### Los 7 pasos de búsqueda

!!! info "Paso 1 — Preparación con Claude"
    Antes de abrir cualquier base. Claude construye términos técnicos, sinónimos y códigos IPC en ES/EN.

!!! success "Paso 2 — México (IMPI/SIGA)"
    | Estado | Significado | Acción |
    |--------|-------------|--------|
    | **Vigente** | Protección activa | ⚠️ Revisar reclamos |
    | **Caducada** | Venció | ✅ Espacio libre |
    | **En trámite** | No concedida aún | ⚠️ Riesgo potencial |
    | **Sin resultados** | Libre en México | ✅ Documentar |

!!! info "Paso 3 — LATAM (LATIPAT)"
    18 países simultáneos: MX, BR, CO, AR, CL y más.

!!! info "Paso 4 — Global con filtro MX (Lens.org)"
    Filtros: `Legal Status → Active` · `Jurisdiction → MX` · `[código IPC]`

!!! info "Paso 5 — Familias y referencias cruzadas"
    Para las 2–3 patentes de mayor riesgo: backward/forward citations + patent family en Espacenet.

!!! warning "Paso 6 — Interpretar reclamos con Claude"
    El título describe. Los reclamos protegen. Usar Prompt 2 del taller.

!!! success "Paso 7 — Conclusión FTO"
    | Nivel | Situación | Acción |
    |-------|-----------|--------|
    | 🟢 **Alta** | Sin patentes vigentes | Continuar y documentar |
    | 🟡 **Media** | Reclamos no cubren exactamente | Ajustar concepto |
    | 🔴 **Baja** | Patente vigente que cubre el mecanismo | Asesoría legal |

### Prompts del taller

#### Prompt 1 — Términos de búsqueda (Claude)

```
Actúa como especialista en vigilancia tecnológica para startups
de hardware + software en mercados emergentes.

Concepto: [nombre + descripción]
Mecanismo técnico: [sensores, procesamiento, comunicación]
Componente de IA: [qué hace y dónde corre]

Entrega:
- Términos en ES y EN (principales + sinónimos + combinaciones AND)
- Códigos IPC relevantes (3–5 con descripción)
- Secuencia: IMPI → LATIPAT → Lens.org
```

#### Prompt 2 — Interpretar reclamos (Claude)

```
Actúa como analista de PI para equipos de ingeniería sin formación legal.

Concepto: [descripción técnica]
Patente: Título / Número / Titular / Estado en MX / Año
Reclamos: [pega reivindicaciones 1–5]

Responde:
1. Qué protege (sin jerga legal)
2. Qué NO protege
3. ¿Nuestro concepto cae dentro o fuera?
   Veredicto: dentro ⚠️ / fuera ✅ / zona gris ❌
4. Recomendación: ignorar / ajustar / asesoría legal / usar como guía
```

#### Prompt 3 — Actores tecnológicos en LATAM (Perplexity)

```
Actúa como analista de inteligencia tecnológica en LATAM.
Busca primero en MX y LATAM, luego global.

Concepto: [descripción + sector]

Entrega:
- Actores en México: nombre, tipo, qué hace, nivel de actividad
- Actores en LATAM (BR, CO, AR, CL, PE)
- Actores globales con presencia en LATAM
- 2–3 papers relevantes últimos 3 años
- Conclusión: densidad MX/LATAM + implicación para el equipo
```

---

## Paso 6 — Mini-taller de entrevistas

**Duración: 15 min**

Ahora el equipo tiene hipótesis específicas y concepto definido tras la vigilancia. El momento correcto para aprender a entrevistar es justo antes de hacerlo.

=== "❌ NO es"
    - Preguntar si les gustaría el producto
    - Presentar el concepto para ver la reacción
    - Convencer al usuario de la idea

=== "✅ SÍ es"
    - Escuchar la **experiencia actual** del usuario
    - Hablar menos del 20% del tiempo
    - Preguntar **comportamiento pasado**, no intención futura

!!! danger "La trampa más común"
    ❌ *"¿Comprarías un sensor que te diga cuándo regar?"* — siempre dicen sí

    ✅ *"¿Qué hiciste la última vez que no sabías si tenías que regar?"*

### Protocolo de 20 minutos

```
APERTURA (2 min)
"Estamos investigando cómo [usuario] maneja [problema].
No tenemos nada que vender — queremos entender su experiencia."

EXPLORACIÓN (12 min)
· ¿Cuándo fue la última vez que resolviste [el problema]? ¿Qué hiciste?
· ¿Con qué frecuencia ocurre?
· ¿Qué es lo más frustrante de cómo lo resuelves hoy?
· ¿Has probado alternativas? ¿Qué pasó?
· ¿Cuánto te cuesta no tener una mejor solución?

HIPÓTESIS (4 min) — solo si la conversación lo permite
"Exploramos la idea de [descripción vaga]. ¿Resonaría?"
→ Escuchar. Si dicen no, preguntar por qué.

CIERRE (2 min)
· ¿Hay alguien más que debería hablar con nosotros?
· ¿Puedo contactarte para seguimiento?

NO HACER:
✗ Mostrar prototipo o app
✗ Preguntar "¿pagarías X?"
✗ Defender la idea
✗ Hablar más del 20%
```

### Ensayo en clase (10 min)

Pares dentro del equipo: 5 min de entrevista + 2 min de retroalimentación interna.

El instructor señala solo: (1) habla más del 20%, (2) pregunta intención futura en vez de comportamiento pasado.

---

## Tarea en casa

| Tarea | Tiempo | Entregable |
|-------|:------:|-----------| 
| Búsqueda fonética en IMPI | 1h | Captura + decisión de nombre |
| Vigilancia tecnológica profunda | 1h | 3–5 patentes analizadas + FTO |
| 3 entrevistas reales | 1.5h | Notas con citas textuales |
| Síntesis de entrevistas con Claude | 0.5h | Insight validado o ajuste al concepto |

### Prompt síntesis de entrevistas

```
Actúa como investigador de usuario experto en sintetizar
entrevistas de validación para equipos early-stage.

ENTREVISTA 1 — Usuario: [perfil] — Notas: [lo que dijeron]
ENTREVISTA 2 — Usuario: [perfil] — Notas: [lo que dijeron]
ENTREVISTA 3 — Usuario: [perfil] — Notas: [lo que dijeron]

Hipótesis: H1 / H2 / H3 [del Paso 5 de semana 2]

Entrega:
- Verificación de cada hipótesis: ✅ confirmada / ⚠️ parcial / ❌ refutada + evidencia
- Insight emergente: el patrón no anticipado que apareció consistentemente
- Cita más importante + por qué
- Impacto en el concepto: confirma / ajusta / pivota
- Próxima hipótesis urgente
```

---

## Lo que cierra en semana 4

Primeros 30 min de semana 4:

1. **PI (10 min):** cada equipo comparte FTO y nombre elegido
2. **Entrevistas (15 min):** dos equipos comparten síntesis y ajuste
3. **Transición (5 min):** conectar PI + entrevistas con análisis de mercado

---

## Checklist de salida

- [ ] ¿Qué tipo de PI proteger primero en tu proyecto?
- [ ] ¿Tienes 2 nombres candidatos evaluados?
- [ ] ¿Sabes aplicar el protocolo de entrevista? (80/20 + comportamiento pasado)
- [ ] ¿Tienes 3 personas identificadas para entrevistar esta semana?

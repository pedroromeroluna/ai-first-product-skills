# AI First PM — Skills

Colección de **skills** (agentes especialistas) del curso **AI First PM** de [Product HUB](https://www.producthub.com.ar/).

Cada skill es un experto en un tema de producto, listo para sumar a tu Sistema Operativo de PM.

## Skills disponibles

| Skill | Qué hace |
|---|---|
| [`product-strategy`](product-strategy/SKILL.md) | CPO de bolsillo: te entrevista para framear el problema real, la métrica a mover y las hipótesis a investigar, antes de saltar a la solución. |
| [`market-research`](market-research/SKILL.md) | Analista de mercado: investiga competidores, tamaño de oportunidad y segmentos en la web (research secundario). Token-aware. |
| [`ux-research`](ux-research/SKILL.md) | UX Researcher: define objetivo, segmento, método (entrevista/encuesta/shadowing…) y el guión de preguntas con **Jobs To Be Done** para investigar con usuarios reales. |
| [`usuarios-sinteticos`](usuarios-sinteticos/SKILL.md) | Genera usuarios sintéticos de tu segmento y pre-testea tu guión (entrevista/panel/pre-mortem) para afilar las preguntas antes de salir a campo. No valida nada, solo mejora tu guión. |
| [`motor-de-insight`](motor-de-insight/SKILL.md) | Motor de convergencia: procesa las respuestas de tu research (+ contexto de negocio) y extrae insights con evidencia, **JTBD funcionales/emocionales/sociales**, el Perfil del Cliente del **Value Proposition Canvas** y oportunidades priorizadas contra el outcome (las ramas del **Opportunity Solution Tree**). |
| [`motor-de-ideacion`](motor-de-ideacion/SKILL.md) | Motor de ideación en dos tiempos. **Diverge**: prepara tu workshop con stakeholders (How Might We trazables, ideas semilla de la IA en zona sellada, agenda y tablero en FigJam/Slides/HTML). **Converge**: lee los resultados y sintetiza el **Mapa del Valor** + el brief de prototipo. Trabaja en dupla con el subagente [`ui-designer`](ui-designer/README.md). |
| [`ui-designer`](ui-designer/README.md) | **Subagente ejecutor** (no es un skill): el dueño del Figma MCP de tu sistema. Construye tableros FigJam hoy — design systems y screens en próximas clases. Los skills piensan el QUÉ; él ejecuta el CÓMO. |
| [`product-metric-coach`](product-metric-coach/SKILL.md) | Te guía para definir la North Star Metric de un producto y construir su Key Metric Tree (Reach, Activation, Engagement, Retention, Business-specific). |
| [`cpo-prd-coach`](cpo-prd-coach/SKILL.md) | CPO que te entrevista para co-crear el PRD de tu producto sección por sección (problema, usuario, solución, MVP con landing y captura de leads, métricas). Delega la arquitectura técnica en tu skill de CTO. |

## La cadena de Discovery

Estos skills están diseñados para **trabajar en conjunto**: cada uno termina su trabajo sugiriendo el siguiente. Así pasás de una idea difusa a un plan de investigación accionable.

```
 idea difusa
     │
     ▼
 product-strategy ──► problema · métrica · hipótesis
     │
     ├──► market-research ─ ¿la oportunidad es grande? competidores + tamaño   (research secundario · web)
     │
     └──► ux-research ───── ¿el problema es real para la gente? método + guión JTBD  (research primario · usuarios)
              │
              └──► usuarios-sinteticos ─ pre-testeá el guión antes de campo (afila las preguntas, NO valida)
                       │
                       ▼ (salís a campo: entrevistas / encuestas con usuarios reales)
                       │
              motor-de-insight ── convergencia: respuestas + datos de negocio → insights con evidencia
                                  → JTBD (funcional/emocional/social) → Perfil del Cliente (VPC)
                                  → oportunidades priorizadas (ramas del Opportunity Solution Tree)
                       │
                       ▼
              motor-de-ideacion ─ workshop de ideación con stakeholders ──► Mapa del Valor + brief de prototipo
```

> El handoff entre skills es lo que convierte tu sistema en un **squad**: no es una herramienta suelta, es un equipo de especialistas que se pasan la posta.

## Cómo usar un skill (2 modos)

### Modo 1 — Sumalo a tu Second Brain (Claude Code)
1. Descargá el archivo `SKILL.md` del skill que quieras.
2. Ponelo en tu proyecto, dentro de `.claude/skills/<nombre-del-skill>/SKILL.md`.
3. Invocalo escribiendo `/<nombre-del-skill>` (ej. `/product-metric-coach`).

### Modo 2 — Copy-paste (sin instalar nada)
1. Abrí el `SKILL.md` y tocá el botón **Raw** (o **Copy raw file**).
2. Copiá **todo** el contenido (incluido el encabezado entre `---`).
3. Pegalo como **primer mensaje** en Claude o ChatGPT y empezá a trabajar.

Los dos modos dan el mismo resultado. Elegí el que te quede más cómodo.

---

*Material educativo del curso AI First PM · Product HUB.*

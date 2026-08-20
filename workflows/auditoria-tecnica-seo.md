# Auditoría SEO completa de un sitio

Convierte el conocimiento de los 7 capítulos en un **entregable real**: un informe de auditoría de un dominio concreto, con hallazgos verificados sobre páginas reales (no teoría general) y priorizados por impacto real, no por severidad abstracta de una herramienta.

Usa este workflow cuando el usuario pida auditar un sitio, diagnosticar su SEO, o antes de recomendar cambios técnicos/de contenido sobre un dominio real.

## Herramienta base: `firecrawl-seo-audit`

Este workflow delega la recolección de datos (mapeo del sitio, scraping de páginas clave, extracción de metadata) a la skill `firecrawl-seo-audit`. Este workflow añade lo que esa skill, por sí sola, no tiene: los frameworks de `seo-digital` para interpretar y priorizar lo que Firecrawl encuentra.

Diferencia con invocar `firecrawl-seo-audit` directamente: esa skill sabe *qué recolectar*; este workflow sabe *qué significa cada hallazgo y cuánto importa*.

## FASE 0 — Alcance (2 min)

No preguntes más de lo necesario — infiere del contexto y confirma solo lo que falte:
- URL del sitio (obligatorio)
- Keywords objetivo, si las hay (si no, se infieren del contenido y del sector)
- ¿Hay competidores conocidos a comparar? (si no, se detectan por SERP durante la auditoría)
- ¿Auditoría completa o un área concreta? (técnica / on-page / off-page / contenido / IA generativa)

## FASE 1 — Recolección (delegada a `firecrawl-seo-audit`)

Ejecuta el "Firecrawl Collection Plan" de esa skill:
1. Mapear el sitio (estructura de URLs).
2. Scrapear páginas clave: home, producto/servicio, precios, blog, about, landings de alto valor.
3. Extraer title tags, meta descriptions, encabezados, enlazado interno, señales de canonical, alt text.
4. Si hay keywords objetivo, buscar y scrapear las páginas mejor posicionadas para comparar.

## FASE 2 — Interpretación con los frameworks de `seo-digital`

No te limites a listar lo que Firecrawl encontró — interprétalo con el conocimiento de los capítulos:

- **Crawling/indexación** → [ch01](../chapters/ch01-crawling-indexacion-arquitectura.md): ¿la arquitectura encontrada es flat o deep? ¿hay señales de crawl budget desperdiciado (duplicados, parámetros, páginas huérfanas)? ¿el robots.txt bloquea algo por error?
- **Core Web Vitals** → [ch02](../chapters/ch02-core-web-vitals-y-diagnostico.md): si hay datos de rendimiento disponibles (o se pueden estimar de la estructura de la página), compara contra los umbrales exactos (LCP ≤2.500ms, INP ≤200ms, CLS ≤0,1). Si el sitio reporta caída de tráfico, sigue el **proceso de diagnóstico de 6 pasos** del cheatsheet antes de asumir causa técnica.
- **On-page e intención** → [ch03](../chapters/ch03-onpage-keywords-e-intencion.md): para cada keyword objetivo, identifica la intención real mirando la SERP scrapeada (informacional/navegacional/comercial/transaccional) y compara si el formato de página del sitio coincide con lo que domina esa SERP.
- **Off-page y E-E-A-T** → [ch04](../chapters/ch04-offpage-autoridad-y-eeat.md): evalúa señales de autoridad visibles (menciones, autoría, transparencia) — no inventes datos de backlinks que Firecrawl no puede ver.
- **Contenido y topic clusters** → [ch05](../chapters/ch05-topic-clusters-y-estrategia-contenido.md): ¿el sitio tiene estructura de pillar + clusters, o son posts sueltos sin enlazado bidireccional? ¿hay señales de content decay (fechas antiguas, datos obsoletos)?
- **IA generativa** → [ch06](../chapters/ch06-seo-ia-generativa.md): ¿el contenido es extraíble (párrafos autoconclusivos)? ¿hay entidad clara? No prioricies llms.txt sin evidencia de impacto real.
- **Implementación técnica** → [ch07](../chapters/ch07-implementacion-tecnica-checklist.md): usa el checklist crítico/alto/medio/continuo como base de verificación página por página, y los snippets como referencia exacta de "cómo debería verse" cada fix.

## FASE 3 — Priorización (RICE adaptado, no severidad de herramienta)

Para cada hallazgo, puntúa con el framework del [cheatsheet](../cheatsheet.md#framework-de-priorización-técnica-adaptado-de-rice--revenue-at-risk):

**Alcance** (nº de URLs/sesiones afectadas) × **Impacto** (tráfico/ingreso en riesgo) × **Confianza** (probabilidad de que el fix recupere ese valor) ÷ **Esfuerzo** (horas de implementación)

Ordena el informe final por este score, no por la etiqueta "crítico/alto/medio" que asignaría una herramienta genérica — un problema "crítico" en una página irrelevante pesa menos que uno "medio" en la página de mayor valor comercial del sitio.

## FASE 4 — Entregable

Usa [`templates/informe-auditoria-seo.md`](../templates/informe-auditoria-seo.md) para estructurar el resultado final. Cada hallazgo debe citar: la página exacta, el capítulo/framework que lo respalda, y el score de priorización.

## FASE 5 — Verificación antes de entregar

Pasa el [`checklists/checklist-auditoria-rapida.md`](../checklists/checklist-auditoria-rapida.md) sobre las páginas auditadas antes de dar el informe por cerrado. Si algo del checklist no se pudo verificar con los datos recolectados (p. ej. Core Web Vitals reales, que requieren Search Console/PageSpeed), decláralo explícitamente como "no verificable con esta auditoría" en vez de omitirlo o asumirlo.

## Rerun

```
workflow: seo-digital/auditoria-tecnica-seo
site: [url]
keywords: [lista]
área: [completa | técnica | on-page | off-page | contenido | ia-generativa]
```

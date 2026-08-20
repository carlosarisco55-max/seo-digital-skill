---
name: seo-digital
description: "Skill de SEO accionable: conocimiento de fuentes primarias (Google Search Central, web.dev, Moz, Ahrefs, Backlinko, Search Engine Land/Journal, Lighthouse) MÁS workflows que producen entregables reales sobre un sitio concreto — auditoría SEO completa (vía firecrawl-seo-audit + priorización RICE) y diagnóstico de caída de tráfico (proceso de descarte de 6 pasos). Cubre SEO técnico (crawling, indexación, Core Web Vitals, arquitectura), on-page (title tags, encabezados, keyword research, intención), off-page (link building, E-E-A-T, autoridad), estrategia de contenido (topic clusters, mantenimiento), SEO en la era de la IA generativa (AI Overviews, AI Mode, GEO, llms.txt), snippets técnicos listos (robots.txt, sitemap, JSON-LD, meta tags) y checklists de auditoría/pre-publicación. Usa este skill al auditar un dominio real, diagnosticar una caída de tráfico, planificar contenido, evaluar visibilidad en motores de IA, o implementar meta tags/structured data."
---

<!-- argument-hint: [topic, framework name, or chapter number] -->

# SEO Digital
**Fuentes**: Google Search Central, web.dev, Google Search Quality Rater Guidelines, Moz, Ahrefs, Backlinko, HubSpot, Search Engine Land, Search Engine Journal, Semrush, Yoast, Lighthouse (ver notas de fuente por framework en cada capítulo) | **Capítulos**: 7 | **Generado**: 2026-08 (investigación web, sin documento de curso local) | **Ch07 fusionado 2026-08-18** desde la skill `seo` de `web-quality-skills` (instalada vía `autoskills`)

## Cómo usar este skill

- **Auditar un sitio real** — pide "audita el SEO de [dominio]"; ejecuto [`workflows/auditoria-tecnica-seo.md`](workflows/auditoria-tecnica-seo.md), que combina `firecrawl-seo-audit` (recolección) con los frameworks de esta skill (interpretación y priorización RICE) y produce un informe real, no una explicación teórica.
- **Diagnosticar una caída de tráfico** — pide "¿por qué bajó el tráfico de [sitio]?"; ejecuto [`workflows/diagnostico-caida-trafico.md`](workflows/diagnostico-caida-trafico.md), el proceso de descarte de 6 pasos de ch02, sin saltar orden.
- **Sin argumentos** — carga los frameworks core para referencia rápida
- **Con un tema** — pregunta por `crawling`, `Core Web Vitals`, `keyword research`, `link building`, `topic clusters`, `AI Overviews`; busco y leo el capítulo relevante
- **Con capítulo** — pide `ch04`; cargo ese capítulo específico
- **Explorar** — pregunta "qué capítulos tienes" para ver el índice completo

Cuando preguntes por un tema no cubierto en Core Frameworks, leeré el capítulo correspondiente antes de responder.

---

## Core Frameworks & Mental Models

**Crawling, indexación y arquitectura** (Ch 1): toda visibilidad pasa por 3 filtros secuenciales — **Crawling → Indexing → Serving**. El crawl budget solo importa en sitios grandes (1M+ páginas). La canonicalización sigue una jerarquía de señales (redirects > rel=canonical > sitemap); robots.txt controla rastreo, nunca indexación. La arquitectura (flat vs. deep, silos) debe reflejar el tamaño real del sitio, no el deseado.

**Core Web Vitals y diagnóstico** (Ch 2): umbrales exactos en percentil 75 de datos de campo — **LCP ≤2.500ms, INP ≤200ms, CLS ≤0,1**. Ante una caída de tráfico, sigue el proceso de descarte en orden fijo (confirmar → algorithm update → absorción por SERP features/IA → cambios técnicos → cambios de diseño → content decay) antes de actuar.

**On-page, keywords e intención** (Ch 3): identifica la **intención de búsqueda** (informacional/navegacional/comercial/transaccional) analizando la SERP real antes de escribir. Keyword research combina 4 fuentes: semillas, keywords propias ya posicionadas, keywords de competidores, y el gap entre ambos. Un H1 único, jerarquía de encabezados sin saltos.

**Off-page, link building y E-E-A-T** (Ch 4): **Trust** es el centro de E-E-A-T (Experience, Expertise, Authoritativeness, Trust) — un marco de autoevaluación humana, no un algoritmo. Comprar/vender enlaces es spam explícito según política de Google. En 2026, las menciones de marca sin enlace (co-citation) cuentan como autoridad real, no solo el backlink dofollow.

**Estrategia de contenido: topic clusters** (Ch 5): organiza contenido como **pillar page + cluster pages + enlazado interno bidireccional**, nunca como posts sueltos. El contenido decae solo con el tiempo (content decay) — audita y refresca de forma recurrente, diagnosticando primero si es decay real o consecuencia de un cambio propio antes de decidir la acción (actualizar/consolidar/podar).

**SEO en la era de la IA generativa** (Ch 6): AI Overviews y AI Mode se apoyan en los mismos sistemas de calidad de Google, usando **query fan-out** (subconsultas). GEO tiene 5 principios (fundamentos SEO, claridad de entidad, extraibilidad, presencia más allá del sitio propio, medición distinta). Cuidado con el hype: los datos reales muestran que llms.txt tiene adopción mínima por bots de retrieval de IA (~1% de peticiones) — verifica evidencia antes de priorizar tácticas nuevas.

---

## Chapter Index

| # | Título | Frameworks clave |
|---|-------|----------------|
| [ch01](chapters/ch01-crawling-indexacion-arquitectura.md) | Crawling, indexación y arquitectura del sitio | 3 etapas de Search, crawl budget, canonicalización, flat vs. deep, silos |
| [ch02](chapters/ch02-core-web-vitals-y-diagnostico.md) | Core Web Vitals, señales de página y diagnóstico de caídas | Umbrales LCP/INP/CLS, técnicas de mejora, proceso de diagnóstico de caída de tráfico, structured data |
| [ch03](chapters/ch03-onpage-keywords-e-intencion.md) | SEO on-page, keyword research e intención de búsqueda | 4 tipos de intención, proceso de keyword research, jerarquía de encabezados |
| [ch04](chapters/ch04-offpage-autoridad-y-eeat.md) | SEO off-page, link building y E-E-A-T | E-E-A-T, Who/How/Why, autoridad más allá del enlace, políticas de link spam |
| [ch05](chapters/ch05-topic-clusters-y-estrategia-contenido.md) | Estrategia de contenido: topic clusters y mantenimiento | Pillar + clusters, proceso de construcción de cluster, decisión de mantenimiento de contenido |
| [ch06](chapters/ch06-seo-ia-generativa.md) | SEO en la era de la búsqueda generativa | AI Overviews/AI Mode, query fan-out, GEO (5 principios), realidad de llms.txt, políticas de contenido con IA |
| [ch07](chapters/ch07-implementacion-tecnica-checklist.md) | Implementación técnica y checklist rápido | Snippets robots.txt/sitemap/JSON-LD, title/meta/heading, alt text, hreflang, checklist de auditoría crítico→continuo, tabla de herramientas |

## Topic Index

- **Acciones manuales** → ch02
- **Algorithm updates** → ch02
- **Anchor text** → ch04
- **Arquitectura de sitio (flat/deep/silos)** → ch01, ch05
- **AI crawlers (GPTBot, ClaudeBot, PerplexityBot)** → ch01, ch06
- **AI Overviews / AI Mode** → ch02, ch05, ch06
- **Canonicalización / rel=canonical** → ch01
- **Content decay / refresco de contenido** → ch02, ch05
- **Core Web Vitals (LCP/INP/CLS)** → ch02, ch07
- **Crawl budget** → ch01
- **Crawling e indexación (3 etapas)** → ch01
- **Datos estructurados / rich results / JSON-LD** → ch02, ch07
- **E-E-A-T** → ch04
- **Encabezados (H1-H6)** → ch03, ch07
- **Enlazado interno** → ch01, ch05, ch07
- **GEO (Generative Engine Optimization)** → ch06
- **hreflang / SEO internacional** → ch02, ch07
- **Intención de búsqueda** → ch03
- **JavaScript SEO / renderizado** → ch01, ch02
- **Keyword research** → ch03
- **Link building / backlinks** → ch04
- **Link spam / políticas de Google** → ch04
- **llms.txt** → ch06
- **Log file analysis** → ch01
- **Meta description / title tags — snippets listos** → ch03, ch07
- **Mobile-first indexing / viewport / tap targets** → ch02, ch07
- **Páginas huérfanas (orphan pages)** → ch01
- **Prioritización de fixes técnicos (RICE / revenue-at-risk)** → ch02, cheatsheet
- **Query fan-out** → ch05, ch06
- **Checklist de auditoría rápida (crítico/alto/medio/continuo)** → ch07
- **robots.txt — snippet listo** → ch01, ch07
- **Ranking drop / diagnóstico de caídas** → ch02
- **Sitemaps XML — snippet listo** → ch01, ch07
- **Spam policies / contenido generado con IA** → ch06
- **Title tags** → ch03, ch07
- **Topic clusters / pillar pages** → ch05
- **URL structure** → ch01, ch07
- **Herramientas (Search Console, PageSpeed, Screaming Frog...)** → ch07

## Workflows (accionable — generan un entregable real)

- [workflows/auditoria-tecnica-seo.md](workflows/auditoria-tecnica-seo.md) — auditoría completa de un dominio, usando `firecrawl-seo-audit` para recolección y los 7 capítulos para interpretación y priorización RICE
- [workflows/diagnostico-caida-trafico.md](workflows/diagnostico-caida-trafico.md) — proceso de descarte de 6 pasos ante una caída de tráfico orgánico

## Templates (entregables)

- [templates/informe-auditoria-seo.md](templates/informe-auditoria-seo.md) — estructura del informe de auditoría
- [templates/informe-diagnostico-trafico.md](templates/informe-diagnostico-trafico.md) — estructura del informe de diagnóstico de caída

## Checklists

- [checklists/checklist-auditoria-rapida.md](checklists/checklist-auditoria-rapida.md) — verificación crítico/alto/medio/continuo
- [checklists/checklist-pre-publicacion.md](checklists/checklist-pre-publicacion.md) — última verificación antes de publicar contenido nuevo

## Supporting Files

- [glossary.md](glossary.md) — todos los términos clave con definiciones
- [patterns.md](patterns.md) — todos los frameworks y procesos aplicables, con trade-offs
- [cheatsheet.md](cheatsheet.md) — tablas de decisión rápida, umbrales numéricos y checklists

---

## Scope & Limits

Este skill se construyó **enteramente a partir de investigación web** (vía `agent-reach`) en fuentes primarias y de práctica establecida del sector — no existe un documento de curso local para SEO, a diferencia de otros skills de esta familia.

**Dependencia de los workflows accionables**: `workflows/auditoria-tecnica-seo.md` y `workflows/diagnostico-caida-trafico.md` invocan la skill `firecrawl-seo-audit` para scraping/mapeo real de sitios, que requiere `FIRECRAWL_API_KEY` configurada (ver [[reference_firecrawl_setup]] en memoria — plan gratis, 1000 créditos/mes). Algunos datos (Core Web Vitals reales, histórico de Search Console) no son obtenibles vía scraping y deben declararse "no verificables con esta auditoría" en vez de asumirse. Investigación realizada y fuentes consultadas en **2026-08**; dado que SEO (y en particular la parte de IA generativa, Ch 6) cambia con frecuencia, revisa las fechas de fuente citadas en cada framework y contrasta con la documentación oficial vigente antes de decisiones de alto impacto.

**Skills hermanos de la misma familia** (algunos en construcción en paralelo): `conversion-a-leads` (funnel TOFU/MOFU/BOFU, CRO, formularios/CTAs/pop-ups, lead magnets — ya construido), `planificacion-estrategica`, `sem-ads`, `redes-sociales`. Este skill (`seo-digital`) trata específicamente de **cómo conseguir tráfico orgánico hacia el sitio** (rastreo, indexación, contenido, autoridad, IA generativa) — no duplica contenido de esos otros skills:
- La optimización de la propia landing page para convertir visitas en leads (CRO, formularios, pop-ups, lead magnets) pertenece a `conversion-a-leads`.
- Campañas de búsqueda pagada (Google Ads, Bing Ads) pertenecen a `sem-ads`, no a este skill — aunque ambas comparten el concepto de intención de búsqueda (Ch 3) y keyword research.
- Distribución orgánica en redes sociales pertenece a `redes-sociales`, aunque las menciones/co-citaciones sociales sí son relevantes aquí para GEO (Ch 4, Ch 6).
- Planificación de objetivos/roadmap de marketing a nivel más amplio pertenece a `planificacion-estrategica`.

**Honestidad sobre gaps de investigación**: la cobertura de SEO local (Google Business Profile, paquete local de 3), SEO para e-commerce a gran escala (feeds de producto, Merchant Center) y auditoría de accesibilidad como señal de SEO es intencionalmente ligera o ausente — no se investigaron en profundidad en esta pasada. Si necesitas alguno de estos temas en detalle, indícalo para investigación adicional dirigida en vez de asumir que este skill ya lo cubre con la misma profundidad que crawling/indexación, Core Web Vitals o topic clusters.

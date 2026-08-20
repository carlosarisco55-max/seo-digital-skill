## Las 3 etapas de Google Search (Crawling → Indexing → Serving)
**When to use**: como modelo mental por defecto para diagnosticar cualquier problema de visibilidad orgánica.
**How**: Crawling (Googlebot descubre y descarga) → Indexing (Google analiza, agrupa duplicados y elige canónica) → Serving (filtra el índice por relevancia ante una query real). Ubica el problema en la etapa correcta antes de actuar.
**Trade-offs**: rápido de aplicar como primer filtro, pero no sustituye el diagnóstico técnico detallado dentro de cada etapa.

## Presupuesto de rastreo (crawl budget)
**When to use**: solo en sitios grandes (1M+ páginas, cambios semanales) o con muchos cambios diarios (10K+ páginas); en sitios pequeños no hace falta gestionarlo activamente.
**How**: capacidad de rastreo (la fija Google según salud del servidor) × demanda de rastreo (inventario percibido + popularidad + staleness — el inventario percibido es el único que controlas directamente). Reduce URLs duplicadas/sin valor, usa 404/410 reales, mantén sitemap actualizado.
**Trade-offs**: gestionar crawl budget en un sitio pequeño es esfuerzo desperdiciado — confirma primero que tu sitio cumple los umbrales de tamaño/frecuencia antes de invertir tiempo aquí.

## Jerarquía de señales de canonicalización
**When to use**: cuando el mismo contenido es accesible por varias URLs.
**How**: redirects (señal fuerte) > rel="canonical" (fuerte) > sitemap (débil pero útil a escala). Nunca uses robots.txt para canonicalizar — bloquea rastreo, no fusiona duplicados.
**Trade-offs**: mandar señales contradictorias entre estas fuentes hace que Google decida por su cuenta, con resultado impredecible — mantén coherencia entre las tres.

## Core Web Vitals: umbrales y prioridad de arreglo
**When to use**: para auditar rendimiento técnico con datos de campo (no solo laboratorio).
**How**: LCP ≤2.500ms / INP ≤200ms / CLS ≤0,1 medidos en percentil 75 de datos reales. LCP: hacer el recurso descubierto en HTML fuente + fetchpriority alto + sin lazy-load. CLS: fijar width/height, evitar animar propiedades que inducen layout (usar transform en su lugar). Ambos: asegurar elegibilidad bfcache.
**Trade-offs**: optimizar solo con Lighthouse (laboratorio) sin confirmar en campo real puede dar falsa sensación de éxito.

## Proceso de diagnóstico de caída de tráfico orgánico
**When to use**: ante cualquier caída de tráfico o rankings, antes de reaccionar con cambios.
**How**: (1) confirmar en 2 fuentes + descartar acción manual → (2) revisar coincidencia con algorithm update → (3) revisar si el buscador absorbió el tráfico (AI Overviews, SERP features nuevas) → (4) revisar cambios técnicos → (5) revisar cambios de diseño → (6) revisar content decay.
**Trade-offs**: saltarse el orden lleva a "arreglar" el síntoma equivocado y desperdiciar semanas de trabajo técnico.

## Los 4 tipos de intención de búsqueda
**When to use**: antes de cualquier optimización on-page, para decidir qué formato de página crear.
**How**: informacional (aprender) → contenido educativo; navegacional (encontrar sitio/marca) → página de marca clara; comercial (comparar antes de decidir) → comparativas/reseñas; transaccional (actuar ya) → landing/producto sin fricción. Verifica siempre contra la SERP real, no asumas.
**Trade-offs**: escribir el formato equivocado para la intención dominante no se arregla con mejor copy de title/meta — hay que rehacer el formato.

## Proceso de keyword research (4 fuentes)
**When to use**: al planificar contenido nuevo o auditar cobertura existente.
**How**: semillas (brainstorming + tool) → keywords propias ya posicionadas sin saberlo → keywords de competidores reales → content gap entre ambos. Lee volumen y dificultad siempre juntos, en relación a tu autoridad actual.
**Trade-offs**: priorizar solo por volumen alto ignora dificultad y autoridad propia, llevando a perseguir keywords inalcanzables a corto plazo.

## Jerarquía de encabezados H1-H6
**When to use**: al estructurar cualquier página de contenido largo.
**How**: un H1 único (tema principal) → H2 por sección principal (debe funcionar como índice si se escanea solo) → H3 para subdividir H2 extensos. Nunca saltar niveles. Densidad de referencia: un encabezado cada 250-350 palabras.
**Trade-offs**: over-optimizar encabezados con keyword forzada reduce legibilidad y confianza sin aportar ranking real.

## E-E-A-T como autoevaluación (no como algoritmo)
**When to use**: al evaluar cualquier pieza de contenido, especialmente en temas YMYL.
**How**: Trust es el centro; Experience/Expertise/Authoritativeness lo alimentan sin ser todos obligatorios a la vez. Aplica el filtro "Who, How, Why": ¿es evidente quién escribió? ¿es transparente cómo se produjo (incluida IA)? ¿existe para servir a la audiencia o para atraer tráfico de buscadores?
**Trade-offs**: simular las señales superficiales (bylines genéricos, badges) sin sustancia real no engaña ni al marco de calidad ni, cada vez más, a los lectores.

## Autoridad más allá del enlace (co-citación y menciones de marca)
**When to use**: al diseñar estrategia de link building/PR también orientada a visibilidad en IA.
**How**: prospecta medios que ya cubren tu tema (búsqueda clásica + Google News + qué citan los propios LLMs), prioriza journalists que citan datos, produce contenido con datos originales pensado para ser citado. El enlace es un bonus, la mención/cita es el objetivo real.
**Trade-offs**: perseguir solo el enlace dofollow ignora que las menciones sin enlace y co-citaciones ya cuentan como señal de autoridad real en 2026, tanto para SEO como para GEO.

## Topic cluster (pillar + clusters + enlazado)
**When to use**: al organizar contenido de un sitio con más de un puñado de artículos sobre el mismo tema amplio.
**How**: elegir tema core → validar con keyword research + PAA/AI Overviews → escribir pillar (debe responder por sí solo) → construir cluster pages (una por subtema/long-tail) → enlazar: cada cluster→pillar, pillar→cada cluster, clusters entre sí solo si el solapamiento es real.
**Trade-offs**: un cluster de muchas páginas delgadas no genera la misma autoridad que uno de pocas páginas realmente profundas.

## Decisión de mantenimiento de contenido (actualizar/consolidar/redirigir/podar)
**When to use**: al auditar contenido con tráfico en declive.
**How**: primero diagnostica si es decay gradual sin cambios previos (→ refrescar) o caída tras un cambio propio (→ comparar y considerar revertir). Solo después decide entre actualizar, consolidar con 301, o podar (404/410).
**Trade-offs**: aplicar el arreglo equivocado (refrescar cuando debía revertirse) desperdicia esfuerzo y puede empeorar el problema.

## GEO: 5 principios de visibilidad en IA
**When to use**: al optimizar contenido/marca para ser citado por AI Overviews, ChatGPT, Perplexity.
**How**: (1) fundamentos SEO como base → (2) claridad de entidad (datos estructurados, consistencia de nombre) → (3) contenido extraíble (párrafos autoconclusivos, hechos concretos, idea principal al inicio) → (4) visibilidad más allá del sitio propio (YouTube, Reddit, reseñas, prensa) → (5) medición distinta (citación, share of voice, sentimiento — no solo clics).
**Trade-offs**: GEO sin fundamentos SEO sólidos (rastreo, indexación, E-E-A-T) no tiene base real sobre la que construir.

## llms.txt: chequeo de evidencia antes de invertir tiempo
**When to use**: antes de priorizar la creación/mantenimiento de un archivo llms.txt como táctica de GEO.
**How**: contrasta con datos reales de adopción (Ahrefs: 97% de archivos sin peticiones; solo ~1% de tráfico real de bots de retrieval de IA) antes de asumir impacto alto. Google confirma que es neutral para Google Search específicamente ("no ayuda ni perjudica").
**Trade-offs**: no es dañino mantenerlo, pero tratarlo como prioridad alta sin evidencia desvía tiempo de tácticas con impacto más demostrado (extraibilidad de contenido, presencia en plataformas de terceros).

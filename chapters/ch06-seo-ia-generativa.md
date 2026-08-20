# Capítulo 6: SEO en la era de la búsqueda generativa (AI Overviews, AI Mode y GEO)

## Core Idea
La búsqueda generativa (AI Overviews, AI Mode, y motores de IA como ChatGPT/Perplexity que responden con búsqueda) no sustituye al SEO clásico — se construye directamente encima de él, usando los mismos sistemas de rastreo, indexación y calidad. Pero cambia lo que se optimiza y cómo se mide el éxito: de "ranking y clics" a "ser citado y mencionado", y de "Search Console" a métricas de visibilidad de marca que aún están madurando como disciplina. Es también el área con más ruido y desinformación del sector ahora mismo — conviene distinguir con cuidado lo que Google confirma oficialmente de lo que son prácticas emergentes sin evidencia sólida todavía.

## Frameworks Introducidos

- **Cómo funcionan AI Overviews y AI Mode (versión oficial de Google)**
  - Cuándo usarlo: como base factual antes de aplicar cualquier táctica de "optimización para IA" — mucho contenido del sector especula sin partir de esta base.
  - Cómo: AI Overviews usa un modelo Gemini personalizado que trabaja **en conjunto** con los sistemas de calidad y ranking existentes de Google (no los sustituye) y con el Knowledge Graph. Está diseñado para mostrar solo información respaldada por resultados web de alta calidad, con enlaces a ese contenido de soporte — Google afirma explícitamente que por este diseño "generalmente no alucina" como sí puede hacerlo un chatbot LLM puro. Tanto AI Overviews como AI Mode pueden usar **query fan-out**: descomponen la consulta original en múltiples subconsultas relacionadas, cada una ejecutada como búsqueda propia, antes de sintetizar la respuesta — esto explica por qué a veces aparece un abanico más amplio y diverso de enlaces de soporte que en una búsqueda clásica. Para ser elegible como enlace de soporte no hay requisitos técnicos adicionales más allá de estar indexado y ser elegible para aparecer con snippet en Search normal.
  - Control técnico: como la IA está integrada en Search, robots.txt para Googlebot sigue siendo el control de acceso; para limitar qué se muestra (no el acceso en sí) se usan `nosnippet`, `data-nosnippet`, `max-snippet` o `noindex`.
  - (fuente: Google Search Central, "AI Features and Your Website", developers.google.com/search/docs/appearance/ai-features; y Google, "How AI Overviews in Search work", google.com/search/howsearchworks/google-about-AI-overviews.pdf, consultado 2026-08)

- **GEO (Generative Engine Optimization): 5 principios**
  - Cuándo usarlo: al diseñar contenido y presencia de marca con el objetivo explícito de ser citado/mencionado en respuestas de IA, no solo de rankear en el listado clásico.
  - Cómo, los 5 principios: (1) **Los fundamentos de SEO son la base** — GEO no sustituye SEO técnico y de contenido, se apoya en él. (2) **Claridad de entidad** — ayuda a los sistemas de IA a distinguir tu marca de nombres similares y a entender de qué categoría/tema eres una fuente creíble; se logra con información bien estructurada (datos estructurados, "about" claros, consistencia de nombre/entidad en toda la web). (3) **Contenido extraíble y reutilizable** — párrafos que tienen sentido completo leídos de forma aislada (sin depender de "como mencionamos arriba" o "por eso"), con hechos y cifras concretas, encabezados descriptivos y la idea principal al inicio del párrafo — esto aplica sobre todo a sistemas con recuperación en tiempo real (RAG), como Google AI Mode o Perplexity con grounding, o ChatGPT con navegación activada. (4) **La visibilidad en IA va más allá de tu propio sitio** — los sistemas de IA también recogen de YouTube, Reddit, reseñas, prensa del sector; las menciones ganadas en esos canales importan tanto como tu propio contenido. (5) **La medición cambia** — no hay clic que atribuir; las métricas propuestas son frecuencia de citación, share of voice frente a competidores, contexto (qué prompts disparan tu mención) y sentimiento (positivo/neutro/negativo).
  - (fuente: Search Engine Land, "Generative engine optimization (GEO): How to win AI mentions", searchengineland.com/what-is-generative-engine-optimization-geo-444418, 2026-02-11, consultado 2026-08)

- **llms.txt: qué dice realmente la evidencia (contraste con el hype)**
  - Cuándo usarlo: antes de invertir tiempo en generar/mantener un archivo llms.txt bajo la suposición de que mejora la visibilidad en IA.
  - Cómo — los datos: un análisis de Ahrefs sobre 137.000 dominios encontró que el 97% de los archivos llms.txt no recibieron ninguna petición. De los que sí tuvieron tráfico, el 96% vino de bots — pero mayoritariamente **no de IA**: herramientas de auditoría SEO (21%), bots no identificados (14%), crawlers como Googlebot (13%), herramientas de "tech profiling" (11%). Los bots de recuperación de IA vinculados a ChatGPT y Perplexity representaron solo el 1% de las peticiones. Un análisis previo de SE Ranking sobre 300.000 dominios no encontró conexión entre tener llms.txt y frecuencia de citación en IA. La postura pública de Google (John Mueller) es que llms.txt "no está pensado para búsqueda" y lo describe como "una muleta temporal, quizá para ahorrar tokens" útil sobre todo para herramientas de codificación con IA, no para SEO/GEO.
  - Matiz importante (actualización posterior de Google, misma semana): Google aclaró su guía para decir que mantener llms.txt "no hace daño ni ayuda" a tu visibilidad en Google Search — es neutral para Google específicamente, y sigue siendo tu decisión si quieres mantenerlo para otros sistemas que sí lo consulten. La recomendación práctica: no lo trates como una táctica de alto impacto por ahora — la evidencia de adopción real por los bots de retrieval de IA es mínima.
  - (fuente: Search Engine Journal, "97% Of llms.txt Files Got No Requests, Ahrefs Data Shows", searchenginejournal.com/97-of-llms-txt-files-got-no-requests-ahrefs-data-shows/579478, 2026-06-16; y "Google's Updated Guidance Now Says It's 'Fine' To Use LLMs.txt", searchenginejournal.com/googles-says-its-fine-to-use-llms-txt-for-ai-seo/579608, 2026-06-17, consultado 2026-08)

- **Contenido generado con IA: cuándo viola las políticas de spam**
  - Cuándo usarlo: al decidir si y cómo usar IA generativa para producir contenido a escala.
  - Cómo: la política de Google es consistente desde hace años y no distingue automatización clásica de IA generativa: usar automatización (incluida IA) **con el propósito principal de manipular el ranking** es una violación de las políticas de spam ("scaled content abuse"), independientemente de la herramienta usada para producirlo. No toda automatización es spam — Google reconoce usos legítimos desde hace tiempo (resultados deportivos, previsión meteorológica, transcripciones). La pregunta que Google plantea explícitamente para autoevaluarse: "¿ves la IA como una forma esencial de ayudarte a producir contenido útil y original, o como una forma barata y fácil de manipular el ranking?".
  - (fuente: Google Search Central, "Google Search's Guidance on Generative AI Content on Your Website", developers.google.com/search/docs/fundamentals/using-gen-ai-content, consultado 2026-08)

## Key Concepts

- **AI Overview**: resumen generado por IA que aparece integrado en la SERP clásica de Google, con enlaces de soporte a contenido web que respalda la respuesta.
- **AI Mode**: experiencia de búsqueda conversacional más profunda de Google, para preguntas que antes requerían varias búsquedas sucesivas (exploración, comparación, razonamiento).
- **Query fan-out**: técnica de descomposición de una consulta en múltiples subconsultas relacionadas antes de generar la respuesta — usada por AI Overviews y AI Mode.
- **GEO (Generative Engine Optimization)**: disciplina de posicionar marca y contenido para ser citado/recomendado por plataformas de IA (Google AI Overviews/AI Mode, ChatGPT, Perplexity).
- **RAG (Retrieval-Augmented Generation)**: arquitectura donde un sistema de IA recupera contenido en tiempo real (vía búsqueda/grounding) antes de generar una respuesta — determina qué tan crítica es la "extraibilidad" del contenido (principio 3 de GEO).
- **AI crawlers**: bots automatizados que recolectan contenido web para entrenar o alimentar modelos de IA — ejemplos con nombre propio: GPTBot (OpenAI/ChatGPT), anthropic-ai (Claude), Applebot (Apple Intelligence/Siri), PerplexityBot. Cada uno tiene su propio user-agent y puede gestionarse de forma independiente en robots.txt.
- **Scaled content abuse**: política de spam de Google contra la generación masiva de páginas (con o sin IA) cuyo propósito principal es manipular rankings sin aportar valor real a usuarios.

## Mental Models

- Trata GEO como una extensión del SEO, no como una disciplina paralela que reemplaza los fundamentos: los 5 principios de GEO empiezan explícitamente con "los fundamentos de SEO son la base" — invertir en GEO sin tener rastreo/indexación/E-E-A-T sólidos es construir sobre arena.
- Ante cualquier "táctica nueva de IA" que circula en el sector (como llms.txt), pregunta primero "¿hay datos de adopción real, o es una suposición razonable sin evidencia?" — la brecha entre el hype de llms.txt en 2025-2026 y los datos reales de tráfico de bots (1% de retrieval de IA real) es el ejemplo de referencia de por qué este chequeo importa en un campo que cambia tan rápido.
- Piensa la "extraibilidad" de contenido (principio 3 de GEO) como escribir para un lector que solo va a ver un párrafo sacado de contexto, no el artículo completo — si esa unidad de texto no tiene sentido aislada, tampoco es útil para un sistema RAG que la recupera de forma independiente.
- Ante la ausencia de clic atribuible en menciones de IA, no asumas que "no funcionó" — el marco de medición en 2026 todavía está madurando (share of voice, sentiment, frecuencia de citación son proxies, no conversión directa); no descartes el canal solo porque no encaja en el modelo de atribución clásico de "clic → sesión → conversión".

## Anti-patterns

- **Asumir que llms.txt es una táctica de alto impacto por defecto**: la evidencia de 2026 (97% sin peticiones, 1% de tráfico real de bots de retrieval de IA) contradice esa suposición — no es dañino tenerlo, pero tampoco es prioritario frente a fundamentos de SEO/E-E-A-T sin evidencia sólida que lo respalde.
- **Generar contenido en masa con IA con el propósito primario de rankear, sin revisión ni valor añadido**: cae directamente en la política de "scaled content abuse" de Google — el riesgo no es solo "contenido mediocre", es exclusión activa de resultados.
- **Escribir párrafos que dependen de contexto previo ("como dijimos antes", "por eso") en contenido que quieres ver citado por sistemas RAG**: esos fragmentos pierden sentido cuando se extraen de forma aislada — reduce directamente su probabilidad de ser recuperados con precisión.
- **Bloquear indiscriminadamente todos los crawlers de IA en robots.txt "por seguridad"**: puede eliminar sin darte cuenta la elegibilidad de citación en herramientas de investigación que tus propios compradores B2B usan a diario — la decisión de bloquear debe ser deliberada por bot, no un bloqueo general reflejo.
- **Medir el éxito de GEO con el mismo framework de atribución de clics que SEO clásico**: como no hay clic garantizado en una mención de IA, forzar ese modelo de medición concluye erróneamente que el canal "no funciona" cuando en realidad el journey de conversión simplemente no pasa por ese clic.

## Reference Tables

**SEO clásico vs. GEO — qué cambia**

| Aspecto | SEO clásico | GEO |
|---|---|---|
| Objetivo principal | Rankear en primeras posiciones | Ser citado/mencionado en respuestas de IA |
| Métrica de éxito | Rankings, clics, tráfico | Citaciones, menciones, share of voice |
| Cómo te encuentra el usuario | Clic a tu web | La IA incluye tu marca en la respuesta generada |
| Optimización de contenido | Title tags, keywords, velocidad, calidad | Párrafos autoconclusivos, hechos claros, datos estructurados |
| Construcción de credibilidad | Backlinks, autoría, reseñas, autoridad de dominio | Menciones positivas en plataformas de confianza |
| Plataformas clave | Google, Bing | Google AI Overviews/AI Mode, ChatGPT, Perplexity |

**Adopción real de llms.txt por tipo de bot (datos Ahrefs, 137.000 dominios, 2026-06)**

| Tipo de solicitante | % de peticiones a llms.txt |
|---|---|
| Herramientas de auditoría SEO | 21% |
| Bots no identificados | 14% |
| Crawlers clásicos (Googlebot, etc.) | 13% |
| Herramientas de tech profiling | 11% |
| Agentes de codificación (Claude Code, etc.) | 10% |
| Bots de entrenamiento de IA | 5% |
| Herramientas GEO/AEO (scanners, validadores) | 5% |
| Asistentes de IA | 2% |
| Bots de investigación | 2% |
| **Bots de retrieval de IA (ChatGPT, Perplexity)** | **~1%** |

## Worked Example

**Estrategia GEO + SEO para un sitio de comparativas de software B2B:**

1. Verificar que los fundamentos SEO clásicos están sólidos primero (crawling/indexación limpios, Core Web Vitals en verde, E-E-A-T claro con autoría real) — sin esto, invertir en GEO específicamente no tiene base sobre la que construir.
2. Auditar 3-5 páginas de comparativa clave y reescribir los párrafos de conclusión/definición para que sean autoconclusivos: cada afirmación de "X es mejor para Y" debe llevar el dato/razón en el mismo párrafo, sin depender de referencias cruzadas a otras secciones.
3. Añadir/verificar datos estructurados relevantes (`Product`, `Review`, `FAQPage` donde aplique) para reforzar claridad de entidad.
4. Mapear dónde más allá del propio sitio se menciona la marca (Reddit, reseñas en G2/Capterra, prensa del sector) y priorizar generar más presencia genuina ahí, no solo en el propio dominio.
5. No priorizar la creación de llms.txt como primera acción — dado los datos de adopción real, dedicar ese tiempo a extraibilidad de contenido y presencia en plataformas de terceros tiene evidencia más sólida de impacto en 2026.
6. Establecer una medición realista: en vez de solo tráfico orgánico, trackear menciones de marca en respuestas de IA para queries del sector (share of voice) como métrica complementaria, no sustitutiva, del tráfico clásico.

## Key Takeaways

1. AI Overviews y AI Mode se apoyan en los mismos sistemas de calidad/ranking de Google, no los sustituyen — no hay requisito técnico adicional para aparecer como enlace de soporte más allá de estar indexado y ser elegible en Search normal.
2. Query fan-out (descomposición de una consulta en subconsultas) explica por qué sitios con cobertura profunda por temas (topic clusters, Ch 5) tienen más superficie elegible de aparecer citados.
3. GEO tiene 5 principios accionables (fundamentos SEO, claridad de entidad, extraibilidad, presencia más allá del sitio propio, medición distinta) — no es una lista de trucos, es una extensión estructurada del SEO clásico.
4. La evidencia real sobre llms.txt en 2026 contradice buena parte del hype del sector: adopción de bots de retrieval de IA real es de apenas ~1% de las peticiones — no lo trates como prioridad alta sin evidencia que lo respalde para tu caso específico.
5. Usar IA para generar contenido no es en sí mismo una violación — lo es cuando el propósito primario es manipular ranking sin aportar valor; la pregunta de autoevaluación de Google ("¿ayuda esencial o atajo barato?") sigue siendo el filtro más simple y vigente.

## Connects To
- **Ch 1**: los AI crawlers (GPTBot, ClaudeBot, PerplexityBot) tienen gestión de acceso independiente en robots.txt de la de Googlebot — la arquitectura técnica del Ch 1 debe decidir esto por bot, no de forma genérica.
- **Ch 4**: las menciones de marca y co-citaciones del Ch 4 son el mecanismo exacto que alimenta la visibilidad en motores de IA — GEO y "autoridad más allá del enlace" son la misma disciplina vista desde ángulos distintos.
- **Ch 5**: el query fan-out premia a los sitios con topic clusters profundos — más páginas propias elegibles significa más probabilidad de aparecer citado en alguna de las subconsultas generadas.
- **Ch 2**: el paso 3 del proceso de diagnóstico de caída de tráfico (Ch 2) — "¿el buscador se está quedando el tráfico?" — es exactamente el fenómeno de absorción de clics por AI Overviews descrito aquí.

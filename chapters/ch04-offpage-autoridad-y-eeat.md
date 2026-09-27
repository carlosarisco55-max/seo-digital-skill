# Capítulo 4: SEO off-page, link building y E-E-A-T

## Core Idea
Los enlaces siguen siendo un factor de ranking real, pero desde 2026 la autoridad se construye en un plano más amplio: menciones de marca (con o sin enlace), co-citaciones junto a fuentes reconocidas, y cómo los sistemas de calidad de Google (E-E-A-T) evalúan quién hay detrás del contenido. Perseguir enlaces sin construir autoridad real de marca es cada vez más frágil, tanto para SEO clásico como para aparecer citado en respuestas de IA.

## Frameworks Introducidos

- **E-E-A-T: Experience, Expertise, Authoritativeness, Trust**
  - Cuándo usarlo: como marco de autoevaluación de cualquier pieza de contenido antes de publicarla, especialmente en temas YMYL (Your Money or Your Life: salud, finanzas, seguridad).
  - Cómo: **Trust** (confianza) es el elemento central de la familia — una página poco fiable tiene E-E-A-T bajo sin importar cuánta experiencia, expertise o autoridad aparente tenga (ejemplo textual de Google: un estafador financiero puede ser muy "experto" en estafar, pero eso no genera confianza). **Experience**: ¿el creador tiene experiencia real de primera mano con el tema? (una reseña de alguien que usó el producto vs. alguien que no). **Expertise**: ¿tiene el conocimiento/habilidad necesarios? (un electricista cualificado vs. un aficionado a casas antiguas hablando de instalaciones eléctricas). **Authoritativeness**: ¿es la fuente "de referencia" reconocida para ese tema? (la página oficial de un gobierno para renovar el pasaporte es la fuente autoritativa por definición). Estos tres elementos se solapan y contribuyen a Trust, pero no lo sustituyen — no hace falta que un contenido demuestre los tres para ser útil (puede ser válido solo por su experiencia genuina, por ejemplo).
  - Importante: E-E-A-T **no es un factor de ranking directo ni una puntuación que Google calcule y aplique** — es el marco que usan los quality raters humanos para evaluar si los sistemas automáticos de ranking están funcionando bien. Sirve como autoevaluación, no como algoritmo a "optimizar" literalmente.
  - (fuente: Google Search Quality Rater Guidelines, guidelines.raterhub.com/searchqualityevaluatorguidelines.pdf, actualizado 2025-09-11; y Google Search Central Blog, "E-A-T gets an extra E for Experience", 2022-12-01, consultado 2026-08)

- **"Who, How, Why" — autoevaluación de contenido people-first**
  - Cuándo usarlo: al auditar si el contenido de un sitio está alineado con lo que Google llama contenido "people-first" (creado para personas, no para manipular rankings).
  - Cómo: **Who** (quién) — ¿es evidente quién creó el contenido? ¿hay byline con información sobre el autor y su experiencia en el tema? **How** (cómo) — ¿es transparente cómo se produjo el contenido, incluyendo si hubo automatización o IA involucrada? **Why** (por qué) — ¿existe para servir a una audiencia real, o principalmente para atraer tráfico de buscadores? Señal de alerta explícita de Google: contenido creado principalmente para atraer visitas de buscadores, que resume superficialmente lo que ya dicen otras fuentes sin aportar valor propio.
  - (fuente: Google Search Central, "Creating Helpful, Reliable, People-First Content", developers.google.com/search/docs/fundamentals/creating-helpful-content, consultado 2026-08)

- **Autoridad más allá del enlace: menciones de marca y co-citación (2026)**
  - Cuándo usarlo: al diseñar una estrategia de link building/PR que también funcione para visibilidad en motores de IA, no solo en SERP clásico.
  - Cómo: los backlinks siguen siendo relevantes para ranking clásico, pero "hoy la autoridad se construye a través de visibilidad" en un sentido más amplio — buscadores y sistemas de IA analizan cómo aparece tu marca en publicaciones creíbles y con qué temas se te asocia consistentemente. Un **co-citation** (mención de tu marca junto a fuentes reconocidas del sector, con o sin enlace) refuerza autoridad igual que un enlace tradicional. Las menciones de marca sin enlace ("unlinked brand mentions") ya no son "desperdiciadas" — son señal de autoridad tanto para SEO clásico como para GEO (ver Ch 6).
  - (fuente: Backlinko, "Link Building for SEO: Proven Strategies That Still Work", backlinko.com/link-building, 2026-06-11, consultado 2026-08)

## Key Concepts

- **Dofollow / Nofollow**: un enlace estándar ("dofollow", término no oficial pero de uso universal) pasa "link equity"; un enlace con `rel="nofollow"` le dice al buscador que no lo cuente como voto de confianza para ranking — pero sigue aportando tráfico de referencia y visibilidad de marca.
- **Anchor text**: el texto visible/clicable de un enlace; ayuda a entender el contexto de la página enlazada — debe ser conciso, relevante y natural; el uso excesivo de keyword exacta en anchor text se considera sobre-optimización.
- **Enlaces editoriales**: los que consigues sin pedirlos (alguien te cita porque tu contenido es la mejor referencia) o los que sí pides pero a través de una relación editorial genuina (guest post en un medio con criterio editorial real).
- **YMYL (Your Money or Your Life)**: categoría de temas (salud, finanzas, seguridad, temas legales) donde Google exige un nivel más alto de E-E-A-T porque un error de información puede causar daño real.
- **Enlace patrocinado/publicitario**: enlace pagado por publicidad o patrocinio — Google acepta que existan, siempre que lleven `rel="nofollow"` o `rel="sponsored"`; no marcarlos así constituye link spam.

## Mental Models

- Antes de perseguir un enlace, pregúntate "¿esta mención construiría confianza de marca igual sin el enlace?" — si la respuesta es sí, has entendido por qué el co-citation y las menciones sin enlace ya no se descartan como "sin valor" en la disciplina de 2026.
- Usa E-E-A-T como una lista de preguntas de autodiagnóstico ("¿quién escribió esto y por qué debería confiar en su experiencia real?"), no como una casilla técnica que se marca añadiendo un badge o una frase — el marco existe para evaluar calidad real, no para simular sus señales superficiales.
- Trata "Who, How, Why" como un filtro secuencial: si el "Why" de una pieza de contenido es principalmente "necesitamos rankear para esta keyword", ningún nivel de pulido en el "How" (redacción, formato) compensará ese origen — Google diseñó el marco explícitamente para detectar ese patrón.
- Piensa en tu perfil de enlaces como un perfil de reputación pública, no como un inventario a optimizar en aislado — la pregunta relevante no es "¿cuántos enlaces tengo?" sino "¿qué tipo de sitios me mencionan y en qué contexto?".

## Anti-patterns

- **Comprar o intercambiar enlaces con fines de ranking** ("link a mí y yo te enlazo a ti" de forma sistemática, pagar por enlaces sin marcarlos nofollow/sponsored, programas automatizados de creación de enlaces): son ejemplos explícitos de link spam en las políticas de Google — el riesgo no es solo "no funciona", es una violación directa de las políticas de spam con consecuencias de penalización.
- **Guest posting masivo en sitios de baja calidad editorial** (sitios que existen para vender ubicaciones de guest post, con páginas tipo "escribe para nosotros" y bajos estándares editoriales): produce enlaces de bajo valor y expone a asociación con contenido de mala calidad — prioriza publicaciones establecidas con audiencia real que raramente aceptan guest posts, salvo por contenido genuinamente valioso.
- **Sobre-optimizar el anchor text con keyword exacta repetida**: el anchor text fue "abusado" históricamente para manipulación SEO, por lo que los buscadores ahora analizan también el texto circundante y el contexto — un perfil de enlaces con anchor text idéntico y forzado en la mayoría de enlaces es una señal de manipulación, no de relevancia.
- **Añadir un byline o "escrito por expertos" sin que exista experiencia real detrás**: simular las señales superficiales de E-E-A-T (badges, bylines genéricos) sin la sustancia real no engaña ni al marco de calidad ni, cada vez más, a los propios lectores.
- **Ignorar el link spam en widgets o footers**: enlaces keyword-ricos ocultos en widgets distribuidos en muchos sitios, o enlaces repetidos en footers/plantillas de múltiples dominios propios, son ejemplos explícitos de spam listados por Google — un patrón fácil de caer en él sin intención maliciosa consciente (ej. widgets de "creado con [herramienta]").

## Reference Tables

**Tipos de enlace y su función**

| Tipo | Pasa autoridad de ranking | Notas |
|---|---|---|
| Dofollow (estándar) | Sí | La mayoría de enlaces por defecto |
| Nofollow (`rel="nofollow"`) | No | Obligatorio en enlaces pagados/patrocinados |
| Sponsored (`rel="sponsored"`) | No | Específico para contenido pagado |
| Editorial no solicitado | Sí | El de mayor valor — nadie lo pidió, lo ganaste |
| Co-citation (mención sin enlace) | No directamente, sí de autoridad de marca | Cada vez más relevante también para GEO (Ch 6) |

**Ejemplos de link spam según política oficial de Google (no exhaustivo)**

| Práctica | Por qué es spam |
|---|---|
| Comprar/vender enlaces sin nofollow/sponsored | Manipula ranking directamente |
| Intercambio excesivo de enlaces ("link a mí, te enlazo") | Reciprocidad artificial sin valor editorial |
| Enlaces automatizados por programas/bots | No hay criterio editorial humano |
| Enlaces keyword-ricos ocultos en widgets distribuidos | Manipulación a escala, oculta al usuario |
| Enlaces repetidos en footers/plantillas de múltiples sitios propios | Autoridad artificial entre dominios afiliados |

## Worked Example

**Campaña de autoridad para una marca B2B SaaS que quiere reducir dependencia de link building tradicional:**

1. Auditar qué medios/blogs ya mencionan la marca (con o sin enlace) usando alertas y búsqueda de marca — identificar patrones de co-citación con competidores reconocidos.
2. Buscar la keyword del sector propio en Google (incluyendo AI Overviews/AI Mode) y en Google News para identificar qué publicaciones cubren el tema con regularidad — añadirlas a una lista de prospección junto a asociaciones del sector y publicaciones especializadas.
3. Repetir la misma búsqueda de fuentes citadas dentro de LLMs (qué fuentes aparecen consistentemente citadas en respuestas de ChatGPT/Perplexity para temas del sector) para unificar la lista de prospección de SEO clásico y GEO.
4. Priorizar journalists/bloggers que citan datos y estadísticas con regularidad como objetivo de outreach — son los más propensos a enlazar contenido con datos originales.
5. Producir una pieza de contenido con datos propios (encuesta, estudio interno) diseñada explícitamente para ser citable, y ofrecerla a esa lista de prospección — el objetivo es la mención/cita, el enlace es un bonus, no el único KPI de éxito de la campaña.

## Key Takeaways

1. E-E-A-T no es un factor de ranking que se calcule algorítmicamente — es el marco de evaluación humana de calidad; Trust es su elemento central, y Experience, Expertise y Authoritativeness lo alimentan sin ser obligatorios todos a la vez.
2. Aplica el filtro "Who, How, Why" a cualquier pieza de contenido antes de publicarla — si el "Why" es principalmente rankear, ningún pulido posterior lo arregla.
3. Comprar/vender enlaces, el intercambio excesivo y los enlaces automatizados son link spam según política explícita de Google — no son solo "poco efectivos", son una violación con riesgo real de penalización.
4. En 2026, las menciones de marca sin enlace y las co-citaciones junto a fuentes reconocidas del sector cuentan como autoridad real, tanto para SEO clásico como para visibilidad en motores de IA.
5. El anchor text debe ser natural y variado — el patrón de "misma keyword exacta repetida en la mayoría de enlaces" es hoy una señal de manipulación, no de relevancia temática.

## Connects To
- **Ch 3**: el contenido que genera enlaces editoriales y menciones orgánicas es, en la práctica, el mismo contenido bien estructurado y con intención correcta descrito en el capítulo de on-page.
- **Ch 5**: las páginas pillar con datos originales y profundidad temática son las que más naturalmente atraen enlaces y co-citaciones.
- **Ch 6**: la lógica de "co-citación y menciones de marca" de este capítulo es exactamente el mecanismo que alimenta la visibilidad en AI Overviews y otros motores generativos — GEO no es una disciplina aparte, es la extensión natural de esta autoridad.
- **Ch 9**: método de clase para el enlazado externo — criterios para elegir el medio (tráfico, temática, frescura, contenido sensible, DR/DA), cómo descubrirlo y comprobarlo, y el entregable mensual al cliente — contrastado con la política de spam de enlaces de este capítulo (publirreportaje ⇒ `sponsored`/`nofollow`).

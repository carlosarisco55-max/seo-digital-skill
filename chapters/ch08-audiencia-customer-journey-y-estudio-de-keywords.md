# Capítulo 8: Audiencia, customer journey y estudio de palabras clave

> **Procedencia (leer primero).** Este capítulo mezcla tres capas y las etiqueta:
> - **[CLASE]** — el método tal como se enseña en un curso de posgrado de marketing digital (2026-09). Si difiere de la fuente primaria, la tabla de verificación lo señala.
> - **[VERIFICADO]** — contrastado con fuente primaria el 2026-09-21 (enlaces al final).
> - **[EXPERTO]** — criterio propio de práctica SEO; es una recomendación, no un hecho citado.

## Core Idea
Antes de tocar una sola keyword hay que saber **para quién** se escribe y **por qué camino** llega esa persona a comprar. El método de clase encadena tres piezas — *searcher persona → customer journey → estudio de palabras clave* — y las usa juntas: la persona enfoca el journey, y el journey enfoca (y luego se corrige con) el estudio de keywords. El entregable no es una lista de keywords: es una **tabla keyword → intención → contenido/URL objetivo**, con cada decisión respaldada por evidencia (pantallazo de SERP o de herramienta).

## Frameworks Introducidos

- **El triángulo audiencia · customer journey · keywords [CLASE]**
  - Cuándo usarlo: al arrancar cualquier proyecto SEO, antes de diseñar la arquitectura web.
  - Cómo: (1) *Audiencia*: perfilar uno o varios públicos objetivo (la "foto"). (2) *Customer journey*: entender el viaje desde la primera idea, aunque sea remota, hasta la compra. (3) *Keywords*: detectar términos con más oportunidad de negocio **y** huecos que el journey no cubría. El objetivo (centro del triángulo) es la estrategia de contenidos.
  - Regla [EXPERTO]: el flujo es iterativo, no lineal — el estudio de keywords casi siempre revela pasos del journey que no habías imaginado; vuelve a actualizarlo.

- **Searcher persona [CLASE]**
  - Estructura: nombre + edad + frase-lema · **Perfil** · **Objetivos** · **Puntos de dolor**. Un proyecto suele tener **varios** (ejemplo de clase, viajes a la India: la aventurera del tigre, el gastrónomo, la interesada en antropología, la interesada en espiritualidad).
  - Cómo se construye en clase: tres fuentes → Claude → resultado pulido a mano. (a) Información propia del cliente (¿qué demandan más quienes compran? ¿por qué se cae la compra en el último momento?). (b) Estudios fiables (Google Académico, etc.) sobre el perfil real. (c) Estudio de palabras clave (volúmenes de una herramienta, con fuente y fecha).
  - [EXPERTO] Una persona generada por IA sin datos propios es una **hipótesis**, no un hallazgo. Márcala como tal y valídala con: Search Console/GA4 si hay sitio, ventas o soporte (objeciones reales), entrevistas, y la propia SERP (¿quién rankea? ¿para qué perfil está escrito?). *Searcher persona ≠ buyer persona*: la buyer persona describe quién compra; la searcher persona añade **cómo busca** (consultas, dispositivo, momento, preguntas). Parte de la buyer persona que ya tengas y enriquécela con comportamiento de búsqueda.

- **Customer journey por intención [CLASE]**
  - Cómo: pintar el viaje como una línea en zigzag de nodos (cada nodo = una búsqueda/pregunta real), con leyenda de colores arriba y flechas de PR, y colorearlos por intención: **informativa** (verde oscuro y amarillo: "¿cuál es el felino más grande?", "¿dónde se pueden ver tigres?", "mejor época…", "¿es seguro…?", "riesgos…") → **comercial** ("mejores rutas", "mejores agencias para ir a…") → **transaccional** ("opiniones de la agencia X", "contactar agencia X").
  - Oportunidad de **PR digital** [CLASE]: los nodos de "mejores agencias" y "opiniones" se resuelven con contenido de terceros (rankings, comparativas, reseñas). Ahí no basta con optimizar tu web: hay que **aparecer en las páginas de otros** (estrategia de relevancia y autoridad, ver Ch 4).
  - [EXPERTO] Matices: "contactar [marca]" es navegacional/de marca; "opiniones de [marca]" es reputación (comercial con intención de validar). Las listas de terceros ("mejores X") son también las fuentes que suelen citar los buscadores de IA (ver Ch 6): estar en ellas rinde doble.

- **Estudio de palabras clave en 4 fuentes [CLASE]**
  1. *Preguntar al cliente/director del área*: términos que creen que usan sus clientes y **exclusiones** (con qué no quieren trabajar).
  2. *Posicionamiento propio* (si existe): por qué términos ya posicionas.
  3. *Competencia*: por qué posicionan los principales competidores.
  4. *Nuevas oportunidades*: términos donde ni tú ni ellos posicionáis.
  - Coincide con el proceso de 4 pasos del Ch 3 (semillas → propias → competidores → gap). Diferencia: la clase añade el paso 1 (cliente y exclusiones) y lo ancla al journey.

- **Reglas de asignación keyword ↔ contenido [CLASE]**
  - Una keyword principal por contenido; puedes trabajar varias pero **focaliza una**.
  - Una keyword no es valiosa por su volumen: lo es porque es **relevante para tu contenido y además tiene volumen**.
  - En nichos sin volumen relevante, guíate por customer journey y searcher persona.
  - Una keyword informacional **jamás** es la keyword objetivo de una página de servicio.
  - [EXPERTO] Una página posiciona en la práctica por cientos de consultas; "una keyword" significa una **intención principal por URL**. Dos URLs para la misma intención = canibalización.

- **Detección de intención con la SERP [CLASE]**
  - En clase se trabajan 3 intenciones: informacional, comercial, transaccional. Método: sentido común primero; si hay duda, **busca en Google y mira qué tipo de contenido premia**. Ejemplos de clase: "mejor época para viajar a Tailandia" (informacional) vs "mejores seguros de hogar" (comercial: comparativas).
  - [EXPERTO] Añade la 4.ª, **navegacional** (búsqueda de una marca/sitio concreto), como en el Ch 3; el método enseñado trabaja con las 3 primeras.

## Key Concepts

- **SERP [CLASE]**: página de resultados. Elementos: orgánicos, patrocinados (SEM), fragmentos destacados, resultados locales (mapas), imágenes/vídeos/noticias/enriquecidos (recetas, libros, vuelos, hoteles), "Más preguntas" (People Also Ask), y **AI Overview** ("Vista creada con IA") y pestaña **Modo IA**.
- **AI Overview [CLASE + VERIFICADO]**: se enseña que llegó a España a finales de marzo de 2025 y que, además de mejorar CTR como otros resultados, provoca pérdida de tráfico sobre todo en consultas informativas. Fecha verificada: **26-mar-2025**. Sobre el efecto en tráfico ver la tabla de matices.
- **URL [CLASE]**: protocolo · subdominio · dominio · TLD · carpeta de idioma · slug · parámetros. Parámetros de pago: `utm_source`, `utm_medium`, `utm_campaign`. Parámetros típicos SEO: `?search=`, `?color=`, `?order=`.
- **Metadatos [CLASE]**: title (lo que aparece en la SERP), meta description, etiquetas de encabezado (H1…), meta robots.
- **Cómo funciona Google [CLASE]**: 1 Rastreo (bots siguen enlaces) → 2 Indexación (analiza y guarda en el índice) → 3 Clasificación (ordena lo indexado por relevancia/utilidad).
- **Tareas SEO [CLASE]**: optimización de contenido · "relaciones públicas digitales" (ganar enlaces externos a páginas estratégicas) · auditoría/optimización técnica · medición (dashboards).
- **Enlaces [CLASE]**: señales que "sugieren a Google" la temática de la página enlazada. *Anchor text* = texto del enlace; *link* = URL destino.

## Verificación de lo dicho en clase (contraste con fuentes primarias, 2026-09-21)

| Afirmación en clase | Qué dice la fuente | Cómo tratarla |
|---|---|---|
| Meta robots = "instrucciones sobre cómo **rastrear** e indexar" | Google: la etiqueta controla **indexación y visualización** en resultados, no el rastreo; solo se lee si la página es rastreable, y si robots.txt la bloquea, la etiqueta se ignora | Como se enseña: "rastrear e indexar". En práctica: robots.txt = rastreo; meta robots = indexación/snippets |
| Se pueden dejar sin indexar URLs con parámetros, sin valor SEO, logins "para optimizar el crawl budget" | Google: `noindex` **no ahorra** crawl budget (Google sigue pidiendo la página y luego la descarta); para reducir rastreo recomienda **robots.txt** (y 404/410 para páginas eliminadas) | Como se enseña: "no indexar para optimizar crawl budget". En práctica: noindex sirve para *no aparecer*; robots.txt para *no gastar rastreo* |
| Hay que vigilar el crawl budget, sobre todo en e-commerce que cambia a menudo | Google lo dirige a sitios de **1 M+ páginas** con cambios semanales, o **10 k+** con cambios diarios, o muchas URLs "Detectada: sin indexar" (estimaciones "aproximadas") | Un sitio pequeño no tiene problema de crawl budget; céntrate en calidad e indexación |
| URLs sin mayúsculas; separar con "-" no "_" | Google: las URLs distinguen mayúsculas (`/APPLE` ≠ `/apple`) y recomienda guiones sobre guiones bajos | Regla sólida y coherente con la clase |
| Sin ñ, acentos, símbolos | Google: los caracteres no ASCII deben ir codificados (percent-encoding) y recomienda usar palabras del idioma de la audiencia | Convención práctica válida (slugs limpios); no es una penalización, es mantenibilidad |
| Priorizar URLs estáticas sin parámetros | Google: "usa tan pocos parámetros como puedas" | Coherente |
| AI Overview "pierde tráfico, sobre todo en informativas" | Pew Research (jul-2025, 900 adultos de EE. UU., datos de marzo-2025): clic en un resultado tradicional en el **8 %** de las visitas con resumen de IA vs **15 %** sin él; clic en un enlace del propio resumen: **1 %**; abandonan la sesión tras la página de resultados el **26 %** vs **16 %**. Es **EE. UU., no España** | Dirección correcta y respaldada. Cifras de proveedores de SEO (p. ej. "-61 % de CTR") varían mucho por metodología: no las cites sin abrir la fuente |
| Semrush: prueba gratuita de 7 días | Fuentes 2026 coinciden en **7 días con tarjeta**; algunos afiliados anuncian 14 días, no es la oferta estándar | Pon recordatorio para cancelar antes del día 7 |

## Herramientas (según clase + datos verificados)

| Herramienta | Uso en clase | Dato verificado 2026-09-21 |
|---|---|---|
| Semrush | Keywords propias, de la competencia y oportunidades; volúmenes aproximados | Prueba 7 días con tarjeta |
| Google Trends | Tendencias y estacionalidad; **no da volúmenes** (índice relativo) | Gratuita |
| AnswerThePublic | Arrancar de cero: preguntas y temas alrededor de un término (incluye ahora pestañas de Modelos de IA y Redes) | Gratis: 3 búsquedas/día; exportar CSV es de pago |
| Sugerencias de Google y "Más preguntas" | Tirar del hilo gratis | Gratuitas |
| Screaming Frog | Auditoría técnica | Gratis hasta 500 URLs, sin límite de tiempo; licencia £199/año |
| Ahrefs · Sistrix · Search Console · GA4 · Sheets | Backlinks · índice de visibilidad · estado técnico y rendimiento · medición · trabajo diario | — |
| Web Developer (extensión Chrome) | Inspeccionar metadatos/encabezados | Gratuita |

## Mental Models

- **Audiencia → journey → keyword, y vuelta.** Cada capa corrige a la anterior. Si una keyword con volumen no encaja en ningún nodo del journey, o la persona está mal o esa keyword no es para ti.
- **El volumen es un dato, la relevancia es una decisión.** Ordena por relevancia para negocio, filtra por volumen, desempata por dificultad.
- **La SERP es el jefe.** Para elegir formato, mira qué premia Google *hoy* (comparativa, guía, ficha, local); no discutas con la SERP.
- **Si el método enseñado y la fuente primaria difieren, anota ambos; en la práctica manda la fuente primaria.**

## Anti-patterns

- Persona inventada sin datos ("Marta, 38 años") presentada como hecho.
- Keyword informacional como objetivo de una página de servicio.
- Elegir keywords por volumen sin comprobar la SERP (intención y formato).
- Dos páginas peleando por la misma intención (canibalización).
- Cifras de volumen copiadas de un ejemplo de clase y presentadas como datos del proyecto.
- Entregable sin pantallazos: cada decisión se justifica con evidencia enlazada.
- Usar `noindex` pensando que ahorra rastreo.

## Reference Tables

**Salida mínima de clase vs salida profesional del estudio de keywords**

| Columna | Clase | Profesional |
|---|---|---|
| Keyword | ✔ | ✔ |
| Volumen mensual | ✔ | ✔ (fuente y fecha) |
| Categoría/contenido | ✔ | URL objetivo + tipo de página |
| Intención | (implícita) | Informacional / comercial / transaccional / navegacional |
| Dificultad (KD) | — | ✔ |
| Posición actual y URL que rankea | — | ✔ (si hay sitio) |
| SERP features (AIO, PAA, local…) | — | ✔ |
| Prioridad / esfuerzo | — | ✔ |
| Evidencia | pantallazo | enlace al pantallazo en la carpeta de evidencias |

**Las 3 intenciones de clase**

| Intención | Qué busca | Ejemplo de clase | Contenido |
|---|---|---|---|
| Informacional | Saber algo | "¿Cómo empezar una estrategia SEO?" | Guía/artículo |
| Comercial | Comparar antes de decidir | "mejores agencias de marketing digital en Barcelona" | Comparativas/listas |
| Transaccional | Contratar/comprar | "agencia de marketing industrial" | Landing de servicio/producto |

## Worked Example (ilustrativo: viajes a la India)

1. **Personas**: Marta (tigre), gastrónomo, antropología, espiritualidad — cada una con perfil/objetivos/dolores.
2. **Journey de Marta**: "¿cuál es el felino más grande?" → "el tigre está en peligro de extinción" → "¿dónde se pueden ver tigres en libertad?" → "mejor época para ir a la India y ver tigres" → "¿es seguro ver tigres en la India?" → "riesgos de viajar a la India" → "consejos para viajar sin enfermedades gastrointestinales" → *comercial* "mejores rutas para ir a la India" → "mejores agencias para ir a la India" → *transaccional* "opiniones de [agencia]" → "contactar [agencia]".
3. **Keywords**: se cruzan con volúmenes de herramienta y se detectan huecos del journey.
4. **Mapa contenido**: informativos → blog; comerciales → comparativas/landing de rutas; transaccional → landing de servicio/contacto. Nodos de "mejores agencias"/"opiniones" → **estrategia de PR** (aparecer en páginas de terceros).
5. Cada decisión, con pantallazo de SERP/herramienta.

## Key Takeaways

1. Persona → journey → keywords, y iterar. El entregable es la tabla keyword → intención → URL, con evidencia.
2. Una intención principal por URL; jamás keyword informacional en página de servicio.
3. Valida siempre la intención mirando la SERP; el volumen no decide solo.
4. La persona sintética es hipótesis hasta validarla con datos propios.
5. Distingue lo enseñado de lo verificado: meta robots, noindex/crawl budget, AIO.
6. Los nodos comerciales/transaccionales dependen de terceros → plan de relevancia y autoridad.

## Connects To
- **Ch 3**: intención, 4 fuentes de keyword research, encabezados y metadatos.
- **Ch 5**: el mapa keyword→contenido es el insumo de los topic clusters.
- **Ch 4**: los nodos "mejores X/opiniones" alimentan el plan de link building y PR.
- **Ch 6**: AI Overviews/AI Mode: qué informativas están en riesgo y por qué importa ser citado.
- **Workflow**: [`workflows/estudio-audiencia-keywords.md`](../workflows/estudio-audiencia-keywords.md) · **Plantilla**: [`templates/estudio-audiencia-keywords.md`](../templates/estudio-audiencia-keywords.md)

## Fuentes verificadas (2026-09-21)
- Google Search Central — [Gestionar el crawl budget de sitios grandes](https://developers.google.com/search/docs/crawling-indexing/large-site-managing-crawl-budget)
- Google Search Central — [Estructura de URL](https://developers.google.com/search/docs/crawling-indexing/url-structure)
- Google Search Central — [Meta robots](https://developers.google.com/search/docs/crawling-indexing/robots-meta-tag)
- Pew Research Center, 22-jul-2025 — [Google users are less likely to click on links when an AI summary appears](https://www.pewresearch.org/short-reads/2025/07/22/google-users-are-less-likely-to-click-on-links-when-an-ai-summary-appears-in-the-results/)
- Search Engine Land — [Google rolls out AI Overviews in EU regions](https://searchengineland.com/google-rolls-out-ai-overviews-in-eu-regions-453595) (26-mar-2025)
- Google Blog ES — [El Modo IA llega a España](https://blog.google/intl/es-es/productos/la-busqueda-de-google-el-modo-ia-llega-a-espana/) (oct-2025)
- Screaming Frog — [SEO Spider](https://www.screamingfrog.co.uk/seo-spider/) y [precios](https://www.screamingfrog.co.uk/seo-spider/pricing/)
- AnswerThePublic — [versión gratuita](https://answerthepublic.zendesk.com/hc/en-us/articles/22617503900187-Is-There-a-Free-Version-of-AnswerThePublic)

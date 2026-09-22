# Capítulo 1: Crawling, indexación y arquitectura del sitio

## Core Idea
Antes de que una página pueda rankear tiene que sobrevivir tres filtros secuenciales: que Google la **rastree** (crawling), que decida **indexarla** (indexing) y que la considere **elegible para servir** en resultados (serving). Cada filtro tiene sus propios puntos de fallo, y la arquitectura del sitio (URLs, enlazado interno, jerarquía de carpetas) es la palanca que más influye en cuánto presupuesto de rastreo e "link equity" llega a cada página.

## Frameworks Introducidos

- **Las 3 etapas de Google Search: Crawling → Indexing → Serving**
  - Cuándo usarlo: como modelo mental por defecto para diagnosticar cualquier problema de visibilidad ("¿la página no aparece porque no se rastreó, no se indexó, o se indexó pero no se sirve para esa query?").
  - Cómo: (1) **Crawling** — Googlebot descubre URLs (por enlaces, sitemaps, o URLs ya conocidas) y descarga su contenido, ejecutando JavaScript con una versión reciente de Chromium. (2) **Indexing** — Google analiza el contenido, agrupa páginas duplicadas ("clustering") y elige una **URL canónica** por grupo; solo la canónica entra en el índice. La indexación no está garantizada aunque el rastreo sí ocurra. (3) **Serving** — cuando un usuario busca, Google filtra el índice por relevancia (cientos de factores: ubicación, idioma, dispositivo).
  - (fuente: Google Search Central, "In-depth guide to how Google Search works", developers.google.com/search/docs/fundamentals/how-search-works, consultado 2026-08)

- **Presupuesto de rastreo (crawl budget) = capacidad de rastreo × demanda de rastreo**
  - Cuándo usarlo: solo es relevante para sitios grandes (1M+ páginas con cambios semanales, o 10K+ páginas con cambios diarios) o sitios con muchas URLs marcadas "Detectada: actualmente sin indexar" en Search Console. Sitios pequeños no necesitan gestionarlo activamente.
  - Cómo: la **capacidad de rastreo** (crawl capacity limit / hostload) la fija Google según la salud del servidor — sube si las respuestas son rápidas y estables, baja si hay errores 5xx, rate-limiting (429) o latencia alta. La **demanda de rastreo** depende de tres factores que sí controlas: (1) **inventario percibido** — cuantas más URLs duplicadas o sin valor conozca Google, más rastreo desperdicia (el factor que más puedes controlar); (2) popularidad de las URLs; (3) "staleness" — cuánto tarda el contenido en quedar desactualizado.
  - Tácticas para maximizar eficiencia: consolidar contenido duplicado, devolver 404/410 (no redirects infinitos) para páginas eliminadas permanentemente, eliminar errores "soft 404", mantener el sitemap actualizado con `<lastmod>`, soportar HTTP 304 (Not Modified) para ahorrar ancho de banda del rastreo, y bloquear con robots.txt páginas de bajo valor (scroll infinito, filtros facetados, versiones con distinto orden) que no deben indexarse.
  - (fuente: Google Search Central, "Crawl Budget Management", developers.google.com/crawling/docs/crawl-budget, actualizado 2026-07-22, consultado 2026-08)

- **Canonicalización: cómo Google elige la URL representativa de un grupo de duplicados**
  - Cuándo usarlo: cuando el mismo contenido es accesible por varias URLs (parámetros, http/https, con/sin www, versión de impresión, paginación, variantes mobile/desktop).
  - Cómo: Google agrupa ("clustering") páginas con contenido similar y elige una canónica por señales, de más a menos fuertes: **redirects** (señal fuerte de que el destino debe ser canónico) > `rel="canonical"` (link o header HTTP) > **sitemap** (señal débil, pero ayuda). Importante: no uses robots.txt para canonicalización — Google puede seguir indexando una URL bloqueada en robots.txt sin poder leer su contenido, lo que es peor que dejarla rastreable con canonical apuntando a otra parte.
  - (fuente: Google Search Central, "How to Specify a Canonical", developers.google.com/search/docs/crawling-indexing/consolidate-duplicate-urls, consultado 2026-08)

- **Autoridad interna (PageRank) y cómo fluye por el enlazado [CLASE]**
  - Cuándo usarlo: al decidir cómo enlazar internamente o al razonar por qué una página posiciona mejor que otra del mismo sitio con contenido similar.
  - Cómo, el modelo enseñado: los enlaces son votos de confianza. Si A enlaza a B, A "vota" por B. No todos los votos valen igual — un enlace desde una página con mucha autoridad (home, una página con muchos enlaces externos) transmite más que muchos enlaces desde páginas irrelevantes. Si una página reparte su autoridad entre muchos enlaces salientes, el valor de cada uno se divide (ej.: home con autoridad 100 → 4 hijos directos reciben 25 cada uno → los hijos de esos reciben 12,5 cada uno).
  - **[CLASE + VERIFICADO] Corrección importante — el mito del 301**: en clase se enseña (con diagrama) que una redirección 301 hace perder la mitad de esa autoridad al pasar por ella (25 → 12,5 en vez de 25 → 25). Google desmintió esto oficialmente: en 2016 Gary Illyes confirmó que **no hay dilución de PageRank en redirecciones 301/302/30x**, y John Mueller lo ratificó después. Una 301 traspasa la señal completa a la URL de destino, igual que un enlace directo — lo único que sí pierde equidad es encadenar varias redirecciones seguidas (301→301→301), y por reconocimiento/tiempo, no por un descuento fijo por salto. En el examen responde como en clase; en la práctica, no evites redirigir por miedo a perder posicionamiento.
  - Enlazar a una página que devuelve 404 o 500 "tira" esa porción de autoridad: no hay contenido al otro lado al que pasarla — coherente con el anti-pattern de más abajo de no enlazar internamente a páginas rotas.
  - [EXPERTO] El reparto numérico limpio (100 → 25 → 12,5…) es una simplificación didáctica del PageRank original (Page y Brin, 1998). El algoritmo de ranking actual de Google usa cientos de señales adicionales; PageRank clásico es solo una de ellas, ya no la única ni la dominante.
  - (fuente: Search Engine Land, "Google: There is no PageRank dilution when using 301, 302, or 30x redirects anymore" (2016); confirmado por Gary Illyes y John Mueller, Google)

- **Arquitectura de sitio: flat vs. deep, y silos de contenido**
  - Cuándo usarlo: al diseñar o reestructurar la jerarquía de carpetas/URLs de un sitio nuevo o con crecimiento de contenido.
  - Cómo: **arquitectura plana** (flat) — la mayoría de páginas a pocos clics del home; funciona en sitios pequeños (portfolios, blogs), reparte mejor el link equity del home, pero no escala (se vuelve un cajón de sastre desorganizado). **Arquitectura profunda** (deep) — jerarquía estricta de categorías/subcategorías; escala en e-commerce y hubs de contenido grandes, pero arriesga enterrar páginas importantes demasiados clics de profundidad, diluyendo el PageRank interno. **Silos de contenido** — agrupar páginas relacionadas para señalar expertise temática a los buscadores: silo físico (vía estructura de URL, ej. `/zapatillas-running/trail/`) o silo virtual (solo vía enlazado interno, más flexible pero más fácil de romper con un enlace mal puesto). El enfoque recomendado es híbrido: directorios lógicos reforzados con enlazado interno disciplinado — enlaza mucho dentro del mismo silo, y cuando enlaces a otro silo, hazlo intencionalmente desde una página de nivel alto, no desde dentro del contenido profundo.
  - (fuente: Screaming Cat / Search Engine Land, "Site Architecture for SEO", consultado 2026-08)

## Key Concepts

- **URL Discovery**: el proceso por el que Google encuentra URLs nuevas — vía enlaces desde páginas conocidas, o vía sitemaps enviados. No hay un "registro central" de todo internet.
- **Googlebot**: el programa (crawler/robot/spider) que descarga páginas; usa un límite algorítmico de qué rastrear, con qué frecuencia y cuántas páginas por sitio, evitando sobrecargar el servidor (responde a señales como HTTP 500 = "más despacio").
- **Renderizado**: Googlebot ejecuta JavaScript con una versión reciente de Chrome antes de "ver" el contenido — sin esto, el contenido inyectado por JS puede no verse.
- **robots.txt**: archivo que le dice a los crawlers qué URLs pueden o no solicitar. No sirve para desindexar contenido (una URL bloqueada puede seguir indexada sin contenido visible), solo para ahorrar rastreo.
- **XML sitemap**: lista de URLs que le dices a Google que prefieres ver en resultados (las canónicas). Es el formato más versátil (soporta imágenes, vídeo, noticias, versiones localizadas); también existen sitemaps RSS/Atom y de texto plano. Se declara dentro de robots.txt con la línea `Sitemap: https://ejemplo.com/sitemap.xml`.
- **Orphan page (página huérfana)**: página sin ningún enlace interno entrante — prácticamente invisible para el rastreo, no se indexa ni rankea.
- **Crawl depth**: número de clics desde el home hasta una página. Como referencia práctica, cualquier página objetivo a más de 5 clics de profundidad merece revisión.
- **Soft 404**: página que devuelve HTTP 200 pero cuyo contenido indica "no encontrado" — Google la sigue rastreando y desperdicia presupuesto; hay que devolver un 404/410 real.
- **Códigos de respuesta HTTP y su lectura para SEO [CLASE]**: `200` todo correcto, es lo que debe devolver cada URL enlazada internamente; `301` redirección permanente, traspasa toda la señal a la URL destino (ver framework de PageRank arriba — no diluye); `302` redirección temporal, Google sigue tratando la URL original como la canónica, úsalo solo si el cambio no es definitivo; `404` la página no existe, no pasa autoridad a ningún sitio — evita enlazar internamente a una; `500` error de servidor, si es frecuente reduce la capacidad de rastreo que Google asigna al sitio (ver crawl budget arriba).

## Mental Models

- Piensa el rastreo como un recurso escaso y con coste, no infinito: cada URL de bajo valor que permites rastrear (parámetros, duplicados, facetas) le resta presupuesto a las páginas que sí quieres indexadas. La pregunta operativa no es "¿puedo permitir que esto se rastree?" sino "¿quiero que Google gaste tiempo aquí en vez de en mis páginas de valor?".
- Usa "inventario percibido" como tu primera palanca de crawl budget porque es la única de las tres (junto a popularidad y staleness) que controlas directamente — no puedes fabricar popularidad de la nada, pero sí puedes eliminar duplicados y URLs sin valor hoy mismo.
- Trata la canonicalización como jerarquía de señales, no como una sola regla: si mezclas señales contradictorias (ej. sitemap apunta a A, pero rel=canonical de la página apunta a B), Google decide por su cuenta cuál gana — evita mandar señales mixtas.
- Para arquitectura, pregunta primero "¿flat o deep?" en función del tamaño real del sitio (no del tamaño deseado a 3 años) — sobre-diseñar una jerarquía profunda para un blog de 40 posts diluye autoridad sin necesidad.

## Anti-patterns

- **Usar robots.txt para "desindexar" contenido**: robots.txt bloquea el *rastreo*, no la *indexación* — una URL bloqueada puede seguir apareciendo en resultados sin snippet. Para desindexar de verdad, usa `noindex` (meta robots o header X-Robots-Tag) y deja la URL rastreable para que Google pueda ver esa instrucción.
- **Redirigir en cadena en vez de devolver 404/410 en páginas eliminadas permanentemente**: Google no "olvida" una URL conocida — un 404/410 es la señal más fuerte de "no vuelvas a rastrear esto"; una URL bloqueada en cambio permanece en la cola de rastreo mucho más tiempo.
- **Confundir "más profundo = más importante" en el diseño de URLs**: enterrar páginas de conversión a 6+ clics del home, mientras páginas irrelevantes (ej. "Sobre nosotros") acumulan más enlaces internos que la página de producto principal — la distribución de enlaces internos debe reflejar prioridad de negocio, no antigüedad de creación.
- **Dejar que el renderizado JS oculte el contenido crítico**: si el HTML inicial no contiene el contenido principal y depende 100% de JavaScript del lado del cliente (CSR) sin fallback SSR, el contenido puede quedar en una cola de renderizado separada del rastreo, retrasando o arriesgando su indexación.
- **Silo virtual sin disciplina de enlazado**: depender solo de enlaces internos (sin URLs organizadas en subdirectorios) para crear un silo temático es frágil — un solo enlace mal puesto rompe la señal temática y "gotea" autoridad hacia fuera del silo.
- **Evitar redirigir por miedo a "perder PageRank"**: mito desmentido por Google desde 2016 (ver framework de PageRank arriba) — no rediseñar una URL o no consolidar contenido duplicado por esta razón es un coste de oportunidad innecesario; lo que sí diluye equidad es encadenar varias redirecciones seguidas.

## Reference Tables

**Diagnóstico rápido: ¿en qué etapa falla la página?**

| Síntoma en Search Console | Etapa que falla | Primera acción |
|---|---|---|
| "Detectada: actualmente sin indexar" en volumen alto | Crawling (demanda insuficiente) | Auditar inventario percibido: ¿hay duplicados/parámetros consumiendo presupuesto? |
| "Rastreada: actualmente sin indexar" | Indexing (Google la vio, no la quiso) | Revisar calidad/originalidad del contenido, señales de canonical |
| Indexada pero sin impresiones para queries objetivo | Serving (relevancia) | Revisar intención de búsqueda, competencia y calidad relativa del contenido |
| Errores 5xx o 429 en Crawl Stats | Capacidad de rastreo (servidor) | Revisar rendimiento del servidor / rate limiting |

**Técnicas de canonicalización (de más a menos versátil)**

| Método | Uso principal |
|---|---|
| `rel="canonical"` (link element) | Método estándar por página, más control |
| `rel="canonical"` (header HTTP) | Necesario para archivos no-HTML (PDF, etc.) |
| Sitemap | Señal débil pero útil a escala para sitios grandes |
| Redirects 301 | Señal fuerte — solo cuando la versión antigua debe desaparecer definitivamente |

## Worked Example

**Diagnóstico de un sitio de e-commerce con 200.000 URLs y "Detectada: actualmente sin indexar" en el 40% de sus páginas de producto:**

1. Revisar Crawl Stats en Search Console → si hay errores 5xx/429 recientes, el problema es capacidad de rastreo (servidor), no arquitectura.
2. Si el servidor está sano, revisar el reporte "Inventario percibido": ¿cuántas URLs son variantes de filtros/parámetros (`?color=azul&talla=M`) del mismo producto? Si son miles, ese es el cuello de botella — Google reparte su presupuesto entre variantes sin valor en vez de entre productos nuevos.
3. Acción: bloquear en robots.txt las combinaciones de parámetros de bajo valor, consolidar con `rel="canonical"` las variantes que sí quieres que existan (ej. por color) hacia la versión principal del producto, y asegurar que el sitemap solo liste las URLs canónicas reales.
4. Verificar que las páginas de producto de mayor margen no estén a más de 3-4 clics del home — si un producto rentable está enterrado en una categoría de 6 niveles, subirlo de nivel en la navegación o añadir enlaces cruzados desde páginas de alto tráfico.
5. Re-enviar el sitemap actualizado y monitorear semanalmente el % de páginas "Detectada: sin indexar" — debería bajar en 2-4 semanas si el diagnóstico fue correcto.

## Key Takeaways

1. Rastreo, indexación y "serving" son tres filtros distintos — un problema de visibilidad puede estar en cualquiera de los tres, y cada uno tiene un diagnóstico y arreglo diferente.
2. El presupuesto de rastreo solo importa de verdad en sitios grandes o con cambios muy frecuentes; en sitios pequeños, mantener el sitemap actualizado y revisar el reporte de indexación es suficiente.
3. Robots.txt controla el *rastreo*; noindex controla la *indexación* — usarlos al revés es el error técnico más común y más caro de diagnosticar después.
4. La arquitectura (flat vs. deep, silos) no tiene una respuesta universal correcta — depende del tamaño real del sitio, y debe revisarse con datos de crawl depth y páginas huérfanas, no por intuición.
5. Nunca mandes señales de canonicalización contradictorias entre sitemap, `rel=canonical` y redirects — Google decide por su cuenta cuando hay conflicto, y el resultado no siempre es el que querías.

## Connects To
- **Ch 2**: Core Web Vitals y renderizado JS afectan directamente si Googlebot logra "ver" el contenido a tiempo durante la etapa de rendering descrita aquí.
- **Ch 5**: los topic clusters y pillar pages son la aplicación de contenido de la misma lógica de silos y enlazado interno de este capítulo.
- **Ch 6**: los crawlers de IA (GPTBot, ClaudeBot, PerplexityBot) tienen su propia gestión de robots.txt y acceso, independiente de Googlebot — lo que bloqueas para uno no necesariamente afecta al otro.
- **Ch 7**: los snippets de códigos de respuesta y el checklist de auditoría técnica aplican directamente el modelo de autoridad interna y canonicalización de este capítulo.

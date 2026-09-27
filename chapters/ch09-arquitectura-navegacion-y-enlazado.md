# Capítulo 9: Arquitectura de la información, navegación y enlazado (interno y externo)

> **Procedencia (leer primero).** Este capítulo mezcla tres capas y las etiqueta, igual que el Ch 8:
> - **[CLASE]** — lo enseñado en un curso de posgrado de marketing digital (2026-09-23). Si difiere de la fuente primaria, se señala.
> - **[VERIFICADO]** — contrastado con fuente primaria el 2026-09-23 (enlaces al final).
> - **[EXPERTO]** — criterio propio de práctica SEO; es una recomendación, no un hecho citado.
>
> Por qué es un capítulo nuevo y no una ampliación (a diferencia del Día 2): reúne dos talleres completos (arquitectura web y enlazado externo) que no encajaban en Ch01 ni en Ch04 sin romper su hilo. Ch01 sigue siendo la referencia de PageRank, códigos HTTP y el mito del 301; aquí no se repite.

## Core Idea
La arquitectura decide **qué páginas existen y cómo se conectan**; el enlazado (interno y externo) decide **cuánta autoridad recibe cada una**. Son la misma idea a dos escalas: transferir autoridad desde las URLs que más tienen hacia las que más negocio generan. Dentro del sitio se controla del todo (menú, footer, contenido); fuera se gana, con medios de terceros que cumplan unos criterios.

## Frameworks Introducidos

- **Arquitectura web y despliegue de URLs [CLASE]**
  - Definición de clase: la arquitectura define qué páginas componen el sitio y cómo se relacionan; es la base sobre la que se diseña y desarrolla la web. Bien planteada: (1) organiza los contenidos, (2) facilita que Google los encuentre y los priorice frente a la competencia, (3) permite que los usuarios encuentren antes los contenidos que más negocio generan.
  - Se dibuja como un **árbol**: Home → categorías → subcategorías (ejemplo de clase, tienda de ropa: Home → Pantalones / Gorras / Camisas / Blog; Pantalones → Largos / Cortos; Camisas → De rayas / De cuadros / Lisas).
  - **Regla: "un servicio, una página"**. Cada servicio clave necesita su propia URL exclusiva, para trabajar contenidos orientados a un conjunto concreto de keywords e intención. Ejemplo de clase (una clínica de psicología): una única página de "áreas de trabajo" que aloja todas las terapias es lo que **no** hay que hacer.
  - [EXPERTO] "Una página por servicio" es "una intención principal por URL" (ver Ch 8). No significa una página por cada variante trivial: crea la URL cuando hay una intención de búsqueda distinta que atender, y valida en la SERP que Google premia páginas separadas. Profundidad: ver flat vs. deep en Ch 1 — el árbol de clase es de 3 niveles.

- **Sintaxis de una URL [CLASE + VERIFICADO]**
  - Partes (ejemplo de clase: `https://www.adidas.com/es/camisetas/manga-corta/camiseta-amarilla-edicion-2026`): **protocolo** (`https://`, cifra la comunicación) · **subdominio** (`www`, o `tienda.` en `tienda.ejemplo.com`: sección o sitio independiente sin comprar dominio nuevo) · **dominio** (nombre único del sitio) · **TLD** (la extensión tras el punto: `.com`, `.es`) · **carpeta de idioma/región** (`/es/`) · **carpetas y slug** (`/camisetas/manga-corta/` y la parte final que identifica la página).
  - Reglas de clase: URLs **estáticas** (sin parámetros) frente a **dinámicas** (con parámetros), más limpias y comprensibles; sin caracteres extraños (Ñ, acentos, puntos, comas, símbolos); **sin mayúsculas**; palabras separadas con **guion `-`, nunca guion bajo `_`**.
  - **[VERIFICADO]** Contraste con Google (Search Central, "URL structure best practices"): Google **recomienda guiones frente a guiones bajos** (coincide); **trata `/APPLE` y `/apple` como URLs distintas**, por eso conviene estandarizar en minúsculas (coincide, y el motivo es evitar duplicados); los caracteres no ASCII (acentos, ñ) **se admiten pero deben ir codificados en porcentaje** — evitarlos es criterio de limpieza, no una prohibición de Google; recomienda **recortar parámetros que no cambian el contenido**; **no da ninguna longitud recomendada** (el "<75 caracteres" de Ch 7 es convención).
  - **[VERIFICADO] Matiz sobre HTTPS**: la clase dice que Google impulsa https frente a http. Google lo recomienda y lo incluye en su lista de autoevaluación de *page experience*, pero su documentación actual no lo presenta como un factor de ranking fuerte: dice que no hay una señal única y que, salvo Core Web Vitals, el resto de aspectos de page experience no ayudan directamente a posicionar más alto. Úsalo por seguridad y confianza, no como palanca de ranking.

- **Qué URLs pesan más: jerarquía de importancia y link juice [CLASE]**
  - Idea de partida: los enlaces (internos y externos) son de lo más importante para Google; cantidad y calidad de los enlaces que recibe una página influyen en su visibilidad. Una página posiciona mejor cuantos más enlaces internos recibe y cuanto más importantes sean las URLs de las que vienen.
  - Orden de importancia de las URLs: (1) **la Home**, la de más autoridad; (2) **las enlazadas desde el menú principal y el footer**: se repiten en todas las páginas, así que reciben muchos enlaces y desde páginas importantes; (3) **las enlazadas desde el cuerpo de la Home**: no están en menú ni footer pero reciben un enlace directo de la URL más importante; (4) **las sin enlazar**, de menor autoridad porque no reciben ningún enlace interno.
  - **Idea clave**: cuanto más cerca de la Home esté una URL y más enlaces internos reciba, más autoridad tendrá y más opciones de posicionar.
  - Reparto numérico (100 → 25 → 12,5): ver Ch 1. **[CLASE] En la Clase 3 el diagrama ya no incluye el paso por una redirección 301 y la diapositiva de códigos dice que la 301 "es fundamental para no perder posicionamiento"**, coherente con Google (ver el mito del 301 en Ch 1).
  - **[VERIFICADO]** Google: "cada página que te importe debería tener un enlace desde al menos otra página de tu sitio" (una URL sin enlazar es una página huérfana, Ch 1), y los enlaces deben ser `<a>` con `href` para que Google los siga.

- **Dónde enlazar: menú, footer y contenido [CLASE]**

  | Ubicación | Qué se enlaza | Por qué |
  |---|---|---|
  | **Menú principal** | Lo más importante para el negocio: servicios/productos con alto volumen de búsqueda; los que, aun con poco volumen, generan mucho retorno; y contenidos informacionales estratégicos que empujan a comprar | Es la ubicación más importante: se replica en todas las páginas y reparte gran autoridad a lo enlazado |
  | **Footer** | Contenidos importantes pero no tanto como para el menú, que aun así se quieren enlazar desde todas las páginas: sobre todo páginas legales y algunas URLs con cierto peso en el negocio | Aparece en todas las páginas, con menos protagonismo que el menú |
  | **Contenido** (cuerpo de la página) | Páginas que **no** están enlazadas desde menú ni footer: contextuales, sin necesariamente gran potencial de búsqueda o negocio, pero relevantes para el nivel en el que estás | Para no "desperdiciar link juice" repartiéndolo entre muchas páginas ya enlazadas y de forma duplicada |

  - **Anchor text [CLASE + VERIFICADO]**: debe ser una palabra clave por la que se quiere posicionar la URL enlazada, y **no** genérica ("click aquí" o derivados). Google (Link best practices): "el buen anchor text es descriptivo, razonablemente conciso y relevante para la página en la que está y para la página a la que enlaza"; pone como malos ejemplos "Click here", "Read more" o "Website".
  - **[EXPERTO] Matiz sobre duplicar enlaces**: la lógica de clase (no repetir en el contenido lo que ya está en menú/footer) es un criterio de diseño para repartir mejor la autoridad y evitar menús interminables. No he encontrado documentación oficial de Google que diga que enlazar la misma URL desde el menú y desde el contenido "desperdicie" autoridad; declaraciones de John Mueller recogidas por prensa especializada (Search Engine Journal, Search Engine Roundtable) indican que ambos enlaces pueden contar y que los enlaces contextuales aportan más contexto que los del menú. En el examen responde como en clase; en la práctica, no dejes de enlazar contextualmente a una página importante solo porque ya esté en el menú.
  - [EXPERTO] Un menú que enlaza a todo diluye lo enlazado: prioriza. El menú es un ranking de prioridades del negocio, no un índice.

- **Enlazado externo: criterios del medio [CLASE]**
  - Objetivo: igual que en el enlazado interno, transferir autoridad desde páginas "con más autoridad" hacia las páginas de tu web con mayor capacidad de generar negocio. Aquí se **gana** un enlace desde contenidos publicados por medios con autoridad, apuntando a esas páginas (ejemplo de clase: para un máster de marketing digital, una revista de formación, un medio de marketing, un medio generalista como El País, un blog de tecnología).
  - Criterios de selección del medio:

  | Criterio | Regla de clase | ¿Quién lo dice? |
  |---|---|---|
  | Origen del tráfico | Principalmente del país en el que se quiere posicionar | [CLASE] |
  | Cantidad de tráfico | Considerable: mínimo **1.200 sesiones al mes** | [CLASE] (sin fuente) |
  | Temática | Afín a la página que se va a enlazar | [CLASE] |
  | Frescura | Que el medio cree contenido nuevo; evitar que meta el enlace en un artículo antiguo | [CLASE] |
  | Tipo de contenido | No debe ser un "publirreportaje": debe hablar de un tema, no de las bondades directas de tu web/servicio/producto | [CLASE]; coherente con la política de spam de Google (abajo) |
  | Métricas de terceros | **Domain Rating (Ahrefs) > 20** y **Domain Authority (Moz) > 24** | [CLASE]; son métricas de empresas de SEO, **no de Google** |
  | Contenido sensible | Si publica casinos u otro contenido sensible, evitar el sitio. En el taller se concreta: el último contenido de casinos debe ser de hace **más de 1 año** | [CLASE] (dos versiones de la regla, ver abajo) |
  | Actividad | Si lleva **más de 3 meses** sin publicar, no trabajar con ese medio | [CLASE] |

  - **[VERIFICADO] Enlaces de pago y publirreportajes**: la política de spam de enlaces de Google incluye como infracción "publirreportajes o publicidad nativa donde se recibe pago por artículos que incluyen enlaces que pasan crédito de ranking, o enlaces con anchor text optimizado en artículos, guest posts o notas de prensa distribuidos en otros sitios". No es infracción tener esos enlaces **si van calificados con `rel="nofollow"` o `rel="sponsored"`**. Por eso "no publirreportaje" es una buena regla de clase: si el medio te publica pagando, el enlace debe ir marcado, y entonces no transfiere autoridad de ranking.
  - **[VERIFICADO] DA y DR no son de Google**: Domain Authority es una métrica de Moz y Domain Rating de Ahrefs; Google ha dicho (John Mueller 2019; Gary Illyes 2017, según prensa especializada) que no las usa. Sirven como **filtro práctico para descartar sitios débiles**, no como garantía de que el enlace mejore tu posición.
  - [EXPERTO] Los umbrales (1.200 sesiones, DR>20, DA>24, 3 meses, 1 año) son reglas de trabajo de la clase, sin fuente oficial: úsalos como tales y anota que lo son.

- **Descubrir y comprobar un medio, paso a paso [CLASE]**
  1. **Búsqueda manual** en Google de blogs/revistas del sector en el que se quiere el enlace (ejemplo de clase: "revista de marketing digital" → varias revistas especializadas del sector).
  2. **Métricas clave con Similarweb**: visitas mensuales y de qué país viene el tráfico (ejemplo de clase: un medio del sector con cientos de miles de visitas mensuales y su ranking dentro de España).
  3. **Temática y recurrencia**: comprobar que publica sobre el tema objetivo y con qué frecuencia (fecha de publicación de los artículos recientes).
  4. **Contenido sensible**: buscar `site:dominio.com "casino"` en Google y mirar las fechas de lo que sale.
  - [EXPERTO] Similarweb da **estimaciones**, no los datos reales del medio (los reales solo los tiene su propio Analytics): úsalo para ordenar y descartar, y guarda la captura con la fecha. Para el "origen del tráfico" hay que mirar el desglose por países, no solo el ranking mundial.
  - **[CLASE] Ojo con una incoherencia del propio ejemplo**: el medio que la clase usa como caso bueno muestra en la búsqueda `site:` contenido de casinos de abril y agosto de 2026. Con la regla del taller (último contenido de casinos de hace más de 1 año) **quedaría descartado**. En el examen, aplica la regla tal cual; en un proyecto real, decide y anota tu criterio.

- **El entregable mensual a cliente [CLASE]**
  - Se acuerda con el cliente un número de enlaces ganados al mes en medios de terceros. El entregable es una **hoja de cálculo** con una fila por artículo publicado: Web · Temática · URL final · Tráfico mensual · Anchor text 1 · Link 1 · Anchor text 2 · Link 2.
  - Ejemplo de clase (cliente: una escuela de negocios): dos revistas de marketing con decenas de miles de visitas mensuales; anchor 1 "Escuela de negocios" → home; anchor 2 con el nombre de su máster → página del máster. Patrón: un enlace de marca/categoría a la home y otro con la keyword a la página que genera negocio (coherente con variar el anchor text, Ch 4).

## Key Concepts

- **Slug**: la parte final de la URL que identifica una página concreta dentro de una carpeta o del dominio.
- **TLD**: la extensión final del dominio, tras el punto.
- **Subdominio**: prefijo antes del dominio principal que funciona como una web propia dentro del mismo dominio.
- **Carpeta de idioma**: indica región y/o idioma al que va destinado el contenido de la URL.
- **URL estática / dinámica**: sin parámetros / con parámetros.
- **Link juice**: nombre coloquial de la autoridad que un enlace transmite (ver PageRank en Ch 1).
- **Anchor text**: texto clicable del enlace (Ch 4).
- **Publirreportaje**: contenido pagado con apariencia editorial; si lleva enlace debe calificarse como `sponsored`/`nofollow`.
- **Medio con autoridad**: en la clase, el que cumple los criterios de tráfico, temática, frescura y métricas de la tabla de arriba.

## Mental Models

- El menú es un **ranking de prioridades del negocio**, no un índice del sitio: lo que entra recibe mucha autoridad y lo que sobra la diluye.
- Piensa en la autoridad como agua que baja desde la Home por tuberías (enlaces): las páginas cercanas a la Home y con más entradas reciben más.
- El enlazado externo es el mismo mecanismo con las tuberías fuera de tu casa: no basta con estar enlazado, importa **desde dónde** y **hacia qué página** apunta.

## Anti-patterns

- **Todos los servicios en una sola página**: no permite trabajar una intención concreta por URL (caso de la clínica de psicología con una sola página de áreas de trabajo).
- **Anchor text genérico** ("click aquí", "leer más") en enlaces internos: desperdicia la señal de keyword y Google lo señala como mala práctica.
- **Menú con todo**: sin priorizar, reparte la autoridad entre demasiadas URLs.
- **Enlazar internamente a páginas 404/500**: tira la autoridad (ver Ch 1).
- **Elegir un medio solo por DR/DA**: son métricas de terceros; comprueba también origen del tráfico, temática, frescura y contenido sensible.
- **Aceptar un publirreportaje con enlace sin calificar**: es lo que la política de spam de Google señala como infracción.

## Reference Tables

**Checklist rápido de una URL bien formada**

| Comprobación | Sí/No |
|---|---|
| `https://` | |
| Todo en minúsculas | |
| Palabras separadas con `-`, sin `_` | |
| Sin ñ, acentos, puntos, comas ni símbolos | |
| Sin parámetros innecesarios (estática) | |
| Carpetas que reflejan la jerarquía (no más profundas de lo necesario) | |
| Slug con la keyword de la página | |

**Umbrales de trabajo del enlazado externo (de clase, sin fuente oficial)**: ≥ 1.200 sesiones/mes · DR (Ahrefs) > 20 · DA (Moz) > 24 · ≤ 3 meses sin publicar · último contenido de casinos hace > 1 año.

## Worked Example

**Diseñar menú, footer y enlazado desde contenido para una tienda de ropa online (árbol de clase):**

1. Inventario de URLs por nivel: Home; Pantalones (Largos, Cortos), Gorras, Camisas (De rayas, De cuadros, Lisas), Blog.
2. Priorizar por negocio: qué categorías tienen más búsquedas y cuáles dejan más margen aunque busquen poco; qué artículos de blog empujan a comprar.
3. Menú principal: Pantalones, Camisas, Gorras y Blog (lo prioritario). Footer: páginas legales y alguna página con peso medio (guía de tallas, envíos).
4. Enlazado desde el cuerpo de la Home: subcategorías destacadas que no están en menú ni footer, con anchor text con su keyword ("pantalones cortos de hombre").
5. Desde una página ya optimizada (p. ej. "Pantalones"), enlazar contextualmente a un artículo del Blog relevante que no esté en menú, con anchor descriptivo.
6. Justificar cada decisión con captura (SERP, herramienta, menú de un competidor) y comprobar que ninguna URL enlazada devuelve 404.

## Key Takeaways

1. Un servicio clave, una URL; la URL se escribe en minúsculas, con guiones, sin acentos ni parámetros innecesarios.
2. Cuanto más cerca de la Home y más enlaces internos reciba una URL, más autoridad tiene; el orden es Home → menú y footer → cuerpo de la Home → sin enlazar.
3. Menú = lo más importante del negocio; footer = legales y URLs de peso medio; contenido = páginas contextuales que no están en menú ni footer.
4. El anchor text lleva la keyword de la página enlazada, nunca "click aquí".
5. En enlazado externo, filtra el medio por origen y volumen de tráfico, temática, frescura, ausencia de contenido sensible y métricas de terceros (DR/DA, que Google no usa).
6. Un publirreportaje con enlace debe ir calificado como `sponsored`/`nofollow`; si no, es una infracción de la política de spam de Google.

## Connects To
- **Ch 1**: PageRank, link juice, códigos HTTP y páginas huérfanas; aquí solo se aplican a la arquitectura y el menú.
- **Ch 4**: anchor text, tipos de enlace, políticas de link spam y E-E-A-T; el enlazado externo de aquí es la aplicación práctica.
- **Ch 5**: topic clusters y pillar pages son la misma lógica de árbol y enlazado interno aplicada a contenido.
- **Ch 7**: reglas de URL y checklist técnico; el snippet de URLs de Ch 7 se ha contrastado con Google en este capítulo.
- **Ch 8**: la tabla keyword → URL objetivo es la entrada del despliegue de URLs y del anchor text.

## Fuentes (consultadas 2026-09-23)
- Google Search Central, "URL structure best practices" — developers.google.com/search/docs/crawling-indexing/url-structure
- Google Search Central, "Link best practices" (crawlable links, anchor text, internal links) — developers.google.com/search/docs/crawling-indexing/links-crawlable
- Google Search Central, "Spam policies for Google web search" (link spam) — developers.google.com/search/docs/essentials/spam-policies
- Google Search Central, "Understanding page experience in Google Search results" — developers.google.com/search/docs/appearance/page-experience
- Search Engine Journal, "Domain Authority: Is It A Google Ranking Factor?" y Search Engine Roundtable, "Google Says Internal Links Pointing To Same Page Don't Add More Information Than Other Links" (fuentes secundarias sobre declaraciones de Google; no son documentación oficial)

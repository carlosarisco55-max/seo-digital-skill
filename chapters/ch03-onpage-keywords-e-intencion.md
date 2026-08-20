# Capítulo 3: SEO on-page, keyword research e intención de búsqueda

## Core Idea
El SEO on-page empieza por entender qué quiere realmente el buscador (intención) antes de escribir una sola palabra, y se comunica al buscador mediante una jerarquía de señales textuales — title tag, meta description, encabezados H1-H6 — que deben ser coherentes entre sí y con el contenido real de la página. Optimizar el elemento equivocado (ej. pulir el copy de un title cuando el problema real es que la página no cubre la intención correcta) es la causa más común de esfuerzo on-page desperdiciado.

## Frameworks Introducidos

- **Los 4 tipos de intención de búsqueda (search intent)**
  - Cuándo usarlo: como primer filtro antes de cualquier optimización de keyword — determina qué *tipo* de página necesitas crear, no solo qué palabras incluir.
  - Cómo: **Informacional** — el usuario quiere aprender algo ("qué es...", "cómo..."); optimiza con contenido educativo profundo. **Navegacional** — el usuario busca un sitio o página específica (nombre de marca); optimiza asegurando que tu propia marca/producto sea fácil de encontrar y distinguir. **Comercial** (comercial investigation) — el usuario investiga marcas/productos antes de decidir (comparativas, reseñas); optimiza con contenido comparativo y de confianza. **Transaccional** — intención de compra o acción inmediata ("comprar", "precio", "cerca de mí"); optimiza con páginas de producto/landing con conversión directa, sin fricción de navegación.
  - Regla práctica: analiza la SERP real para tu keyword objetivo antes de asumir la intención — si los 10 primeros resultados son todo comparativas, escribir una guía puramente informacional para esa keyword competirá contra el formato equivocado, sin importar cuán bien escrita esté.
  - (fuente: Semrush, "4 Types of Keywords in SEO", semrush.com/blog/types-of-keywords-commercial-informational-navigational-transactional, 2025-01-21, consultado 2026-08)

- **Proceso de keyword research (de semilla a priorización)**
  - Cuándo usarlo: al planificar contenido nuevo o al auditar qué keywords ya cubres sin saberlo.
  - Cómo, en 4 pasos: (1) **Semillas** — parte de keywords semilla (broad) y expándelas con un keyword tool para generar cientos/miles de variantes con volumen de búsqueda y dificultad estimada. (2) **Qué ya rankea tu propio sitio** — Search Console (limitado a 1.000 keywords) o herramientas de terceros (sin ese límite) revelan keywords por las que ya apareces sin haberlas targeteado a propósito — a menudo la mina de oro más barata de explotar. (3) **Qué rankea la competencia** — identifica competidores reales (mismo tipo de negocio, no solo mismo tamaño de marca) y analiza qué páginas les traen más tráfico y qué keywords targetean esas páginas; repite con varios competidores. (4) **Gap analysis** — cruza tu propio set de keywords contra el de la competencia para encontrar temas que ellos cubren y tú no.
  - Métricas clave a interpretar juntas, nunca por separado: **volumen de búsqueda** (cuántas veces se busca al mes) y **dificultad de keyword** (cuánta competencia hay) — un volumen alto con dificultad altísima puede valer menos esfuerzo que un volumen medio con dificultad baja, dependiendo de tu autoridad actual.
  - (fuente: Ahrefs, "How to Do Keyword Research for SEO", ahrefs.com/seo/keyword-research, consultado 2026-08)

- **Jerarquía de encabezados (H1-H6) como estructura semántica**
  - Cuándo usarlo: al estructurar cualquier página de contenido largo (artículo, guía, página de producto con descripción extensa).
  - Cómo: un H1 único por página (normalmente el título) define el tema principal; los H2 dividen el contenido en secciones principales — si alguien escanea solo los H2, debería entender la estructura completa del artículo; los H3 subdividen secciones H2 extensas o complejas (pasos, comparaciones, puntos relacionados). Regla de oro: nunca saltar niveles (un H3 no puede aparecer sin un H2 padre) — rompe la jerarquía tanto para crawlers como para tecnología de accesibilidad. Como referencia práctica de densidad: coloca un encabezado por cada bloque de 250-350 palabras de texto corrido: bloques más largos sin subdividir dañan la legibilidad y la señal de estructura temática.
  - (fuente: Yoast, "How to use headings on your site", yoast.com/how-to-use-headings-on-your-site, 2025-12-11, consultado 2026-08)

## Key Concepts

- **Title tag (meta title)**: titular clicable en SERP, navegador y redes sociales — primera impresión del usuario; influye tanto en CTR como (en menor medida) en cómo los motores entienden el tema de la página.
- **Meta description**: resumen breve bajo el title en SERP; no es factor de ranking directo, pero condiciona el CTR — Google puede reescribirla automáticamente si el snippet original no encaja bien con la query del usuario.
- **Keyword semilla (seed keyword)**: término inicial, amplio, que alimenta a una herramienta de keyword research para generar cientos de variantes relacionadas.
- **Keyword difficulty (KD)**: puntuación estimada de cuán competido está posicionar para una keyword — se usa junto al volumen, nunca en solitario.
- **Content Gap**: informe que compara las keywords de un competidor contra las tuyas para encontrar temas que ellos cubren y tú no.
- **SERP features**: elementos añadidos a los resultados de búsqueda más allá del listado clásico (featured snippet, People Also Ask, AI Overview, carrusel de imágenes) — cambian qué formato de contenido conviene targetear.
- **Semantic SEO**: enfoque que optimiza para relevancia temática y contexto (entidades, sinónimos, subtemas relacionados) en vez de para una sola keyword exacta repetida.

## Mental Models

- Antes de escribir, pregunta "¿qué formato ya está ganando en la SERP para esta keyword?" (¿vídeo, lista, comparativa, guía larga?) — replicar el formato que ya funciona no es copiar, es respetar la señal de intención que el propio buscador ya validó con datos reales de clics.
- Trata volumen y dificultad como un plano de dos ejes, no como un ranking único: una keyword de volumen medio y dificultad baja puede generar más tráfico neto en 3 meses que una de volumen alto y dificultad altísima que tardará años en rankear con tu autoridad actual.
- Usa los encabezados como un "índice para humanos que escanean" antes que como "casillas para meter la keyword" — si alguien solo lee tus H2 y no entiende de qué trata el artículo, la estructura ha fallado independientemente de cuánto SEO técnico tenga.
- Piensa el content gap analysis como una fuente de prioridades, no de imitación ciega: que un competidor cubra un tema no significa automáticamente que debas cubrirlo tú — cruza el gap con tu propia intención de negocio (¿ese tema atrae al Buyer Persona correcto?).

## Anti-patterns

- **Optimizar el title tag de una página que no cubre la intención de búsqueda correcta**: si la SERP para tu keyword objetivo es 100% comparativas y tu página es un artículo puramente informacional, ningún ajuste de title/meta arreglará el desajuste de fondo — hay que rehacer el formato del contenido, no el copy del snippet.
- **Keyword stuffing en encabezados**: rellenar H2/H3 con variantes forzadas de la keyword en vez de lenguaje natural reduce confianza y legibilidad — Google evalúa relevancia temática y contexto, no solo repetición literal.
- **Saltar niveles de encabezado (H1 → H3 directo)**: rompe la jerarquía semántica para crawlers y para lectores de pantalla (accesibilidad) — un error técnico común causado por temas/plantillas mal configuradas, no solo por mala redacción.
- **Basar la priorización de keywords solo en volumen de búsqueda**: ignorar la dificultad y tu propia autoridad actual lleva a perseguir keywords inalcanzables mientras se ignoran oportunidades de volumen medio y dificultad baja, mucho más rentables a corto plazo.
- **Tratar la meta description como factor de ranking**: no lo es directamente — es una palanca de CTR, y optimizarla sin atender el título o el contenido real no mueve el ranking en sí.

## Reference Tables

**Los 4 tipos de intención y cómo optimizar cada uno**

| Intención | Qué busca el usuario | Formato de página recomendado |
|---|---|---|
| Informacional | Aprender algo | Guía/artículo educativo profundo |
| Navegacional | Encontrar un sitio/marca concreta | Página de marca/producto clara y fácil de encontrar |
| Comercial | Investigar antes de decidir | Comparativas, reseñas, contenido de confianza |
| Transaccional | Completar una acción (comprar) | Landing/producto con conversión directa, sin fricción |

**Jerarquía de encabezados**

| Nivel | Función | Regla |
|---|---|---|
| H1 | Tema principal de la página (único) | Uno solo por página |
| H2 | Secciones principales | Debe poder leerse como índice del artículo |
| H3 | Subsecciones dentro de un H2 | Solo si el H2 es extenso o tiene pasos/comparaciones |
| H4+ | Detalle adicional dentro de H3 | Uso opcional en contenido muy extenso |

## Worked Example

**Optimización on-page de un artículo que rankea en posición 8 para "mejores herramientas de email marketing":**

1. Analizar la SERP actual: los 5 primeros resultados son listas comparativas con tabla de precios y capturas de pantalla — la intención dominante es comercial/comparativa, no puramente informacional.
2. Diagnóstico: si el artículo propio es un ensayo de texto corrido sin tabla comparativa, el problema de fondo es de formato, no de title tag.
3. Reestructurar: convertir a formato lista con H2 por herramienta, tabla comparativa de precios/features cerca del inicio, y CTA transaccional por cada opción.
4. Reescribir title tag y meta description alineados al nuevo formato ("Las 12 Mejores Herramientas de Email Marketing en 2026 [Comparativa]") en vez del title genérico anterior.
5. Verificar jerarquía de encabezados: H1 único, un H2 por herramienta comparada, H3 opcional para "pros/contras" dentro de cada H2.
6. Monitorizar posición y CTR en Search Console durante 4-6 semanas — un cambio de formato tarda más en reflejarse que un simple ajuste de copy.

## Key Takeaways

1. Identifica la intención de búsqueda real (informacional/navegacional/comercial/transaccional) analizando la SERP actual antes de escribir — el formato equivocado no se arregla con mejor copy.
2. El keyword research combina 4 fuentes complementarias: brainstorming de semillas, tus propias keywords ya posicionadas, las de la competencia, y el gap entre ambas.
3. Volumen y dificultad se leen juntos, nunca por separado, y siempre en relación a tu autoridad actual.
4. Los encabezados son estructura semántica para humanos y máquinas por igual — jerarquía sin saltos, un tema por H2, densidad de aprox. 250-350 palabras por bloque.
5. La meta description no es factor de ranking directo — es palanca de CTR; no confundir ambos objetivos al escribirla.

## Connects To
- **Ch 1**: la estructura de encabezados y el enlazado interno dentro del contenido refuerzan la arquitectura de silos descrita en el Ch 1.
- **Ch 5**: el keyword research y el mapeo de intención de este capítulo son el insumo directo para construir topic clusters y pillar pages.
- **Ch 4**: el contenido que demuestra E-E-A-T (autoría, experiencia real) se construye sobre esta misma base de contenido on-page bien estructurado.

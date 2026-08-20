# Capítulo 2: Core Web Vitals, señales de página y diagnóstico de caídas

## Core Idea
Core Web Vitals mide experiencia real de usuario con tres métricas y umbrales numéricos concretos (no opiniones de diseño), y forma parte de lo que Google llama "page experience" — una señal más entre cientos, pero una de las pocas 100% cuantificable y accionable por un equipo técnico. Cuando el tráfico orgánico cae, existe un proceso de descarte reproducible (no intuición) para encontrar la causa real antes de tocar nada.

## Frameworks Introducidos

- **Core Web Vitals: LCP, INP, CLS — umbrales exactos**
  - Cuándo usarlo: para auditar y priorizar rendimiento técnico con datos, no sensaciones ("la web se siente lenta").
  - Cómo: cada métrica tiene un umbral "bueno", uno "malo" (todo lo intermedio es "necesita mejora"), medido en el **percentil 75** de las visitas reales de los últimos 28 días (vía Chrome UX Report / campo, no solo laboratorio):

| Métrica | Qué mide | Bueno | Malo | Percentil |
|---|---|---|---|---|
| **LCP** (Largest Contentful Paint) | Velocidad de carga percibida | ≤ 2.500 ms | > 4.000 ms | 75 |
| **INP** (Interaction to Next Paint) | Capacidad de respuesta | ≤ 200 ms | > 500 ms | 75 |
| **CLS** (Cumulative Layout Shift) | Estabilidad visual | ≤ 0,1 | > 0,25 | 75 |

  - Un sitio se clasifica "bueno" en una métrica si al menos el 75% de las visitas cumplen el umbral bueno; se clasifica "malo" si al menos el 25% caen en el umbral malo. Los umbrales se fijaron combinando investigación de percepción humana (rango de espera tolerable de 0,3-3s de Miller & Card) con datos reales de "qué % de sitios ya lo cumplen" (viabilidad), no como números arbitrarios.
  - INP sustituyó a First Input Delay (FID) en 2024 como la métrica oficial de interactividad — si encuentras contenido que menciona FID como vigente, está desactualizado.
  - (fuente: Google Search Central + web.dev, "Understanding Core Web Vitals" y "How the Core Web Vitals thresholds were defined", developers.google.com/search/docs/appearance/core-web-vitals, web.dev/articles/defining-core-web-vitals-thresholds, consultado 2026-08)

- **Técnicas de mayor impacto para mejorar cada métrica**
  - Cuándo usarlo: como checklist de arreglos técnicos priorizados por impacto real medido (no una lista genérica de "optimiza imágenes").
  - Cómo — **LCP**: (1) el recurso LCP (normalmente una imagen) debe ser descubrible directamente en el HTML fuente — evita `data-src` u otros atributos que dependan de JavaScript para cargar la imagen (el 7% de páginas la ocultan así); prefiere Server-Side Rendering sobre Client-Side Rendering. (2) Prioriza ese recurso con `fetchpriority="high"` y elimina `loading="lazy"` en la imagen LCP (lazy-load en el elemento LCP es contraproducente). (3) Asegura elegibilidad para bfcache (back/forward cache) para navegaciones instantáneas en visitas repetidas.
  - **CLS**: (1) fija `width`/`height` explícitos (o `aspect-ratio` en CSS) en toda imagen o contenido cargado después — el 66% de páginas tienen al menos una imagen sin tamaño definido, causa nº1 de CLS. (2) Asegura elegibilidad para bfcache (fue la mayor mejora de CLS observada en la web en 2022). (3) Nunca animes propiedades CSS que inducen layout (`top`, `left`, `margin`, `border-width`) — usa siempre `transform: translate()` en su lugar, que no dispara recálculo de layout.
  - **INP**: divide tareas largas de JavaScript en trozos más pequeños para no bloquear el hilo principal ("yield often").
  - (fuente: web.dev, "The most effective ways to improve Core Web Vitals", web.dev/articles/top-cwv, actualizado 2024-10-31, consultado 2026-08)

- **Proceso de diagnóstico de una caída de tráfico orgánico (orden de descarte)**
  - Cuándo usarlo: ante cualquier caída visible de tráfico o rankings — antes de hacer ningún cambio reactivo.
  - Cómo, en este orden: (1) **Confirma la caída y descarta acciones manuales** — cruza Search Console (Rendimiento) con tu analítica; si no coincide entre herramientas, sospecha de un fallo de medición antes que de SEO real; revisa también si hay una "acción manual" notificada. (2) **Revisa si coincide con una actualización de algoritmo de Google** — compara fechas contra el calendario oficial de updates. (3) **Comprueba si la plataforma de búsqueda se está quedando el tráfico** — si el ranking subió pero el tráfico bajó, filtra por keywords que ahora muestran AI Overviews u otras SERP features nuevas: esa pérdida está fuera de tu control directo. (4) **Revisa cambios técnicos**, planeados o no (deploys, migraciones, cambios de CMS). (5) **Revisa cambios de diseño** que hayan podido tocar elementos con peso SEO (encabezados, enlaces internos, contenido visible). (6) **Revisa el contenido en sí** — declive gradual (decay) vs. caída súbita son problemas distintos con arreglos distintos.
  - (fuente: Ahrefs, "How to Analyze a Sudden Drop in Website Traffic", ahrefs.com/blog/analyze-sudden-traffic-drop, 2025-08-12, consultado 2026-08)

- **Datos estructurados (structured data / schema.org): reglas generales de elegibilidad**
  - Cuándo usarlo: al implementar marcado para optar a rich results (estrellas, FAQs, recetas, productos, etc.) en SERP.
  - Cómo: usa uno de los tres formatos soportados, con **JSON-LD como recomendado** por Google (frente a Microdata o RDFa). Reglas no negociables: el marcado debe describir contenido *visible* en la página (no marques algo que el usuario no puede ver); no bloquees las páginas con datos estructurados vía robots.txt/noindex; coloca el marcado en la página que describe (no en otra); si tienes duplicados de la misma página, replica el mismo marcado en todos los duplicados, no solo en la canónica; usa el tipo y propiedad más específicos posibles de schema.org; cuantas más propiedades recomendadas incluyas (no solo las obligatorias), mejor calidad de resultado — ejemplo citado explícitamente por Google: los usuarios prefieren ofertas de trabajo con salario explícito, o recetas con reseñas reales de usuarios frente a sin ellas.
  - (fuente: Google Search Central, "General Structured Data Guidelines", developers.google.com/search/docs/appearance/structured-data/sd-policies, consultado 2026-08)

## Key Concepts

- **Campo (field) vs. Laboratorio (lab)**: los datos de campo (Chrome UX Report / CrUX) son mediciones reales de usuarios; los datos de laboratorio (Lighthouse, PageSpeed Insights en modo test) son simulaciones controladas — Google rankea con datos de campo, no de laboratorio, aunque el laboratorio sirve para depurar antes de publicar.
- **bfcache (back/forward cache)**: snapshot de memoria del navegador que permite navegación instantánea al volver atrás/adelante — mejora LCP y elimina CLS de un plumazo si la página es elegible.
- **Mobile-first indexing**: Google usa predominantemente la versión móvil del contenido de un sitio para indexar y rankear, incluso en búsquedas de escritorio.
- **hreflang**: atributo que declara variantes de idioma/región de la misma página; Google **no** lo usa para detectar el idioma (usa algoritmos propios para eso) — su función es señalar equivalencia entre páginas, no traducirlas ni clasificarlas.
- **x-default**: valor especial de hreflang para la página de fallback cuando ningún idioma/región del usuario coincide con las variantes declaradas.
- **Rich results**: resultados de búsqueda mejorados visualmente (estrellas, precio, FAQ desplegable) que dependen de datos estructurados válidos y del cumplimiento de políticas de contenido específicas por tipo.
- **Content decay**: declive gradual (meses/años) del tráfico de una página por quedar desactualizada frente a competidores más frescos — distinto de una caída súbita por penalización o bug técnico.

## Mental Models

- Trata Core Web Vitals como un problema de "dónde está el cuello de botella", no de "optimizar todo por igual": el 40% de sitios en CrUX fallan LCP (la métrica más difícil), mientras CLS es la que más sitios ya cumplen bien — prioriza LCP primero salvo que tus propios datos digan otra cosa.
- Ante una caída de tráfico, resiste la tentación de "arreglar algo ya": el proceso de descarte existe precisamente porque el primer sospechoso (ej. "seguro que fue el último cambio que hice") rara vez es la causa real — sigue el orden de eliminación antes de actuar.
- Cuando el ranking sube pero el tráfico baja, no es automáticamente un fallo tuyo: puede ser que la SERP le esté dando la respuesta directamente al usuario (AI Overview, featured snippet, PAA) — diagnostica esto explícitamente antes de asumir que "algo se rompió".
- Para hreflang, piensa en "declarar equivalencia", no en "traducir automáticamente para Google" — es una señal de relación entre URLs, no una herramienta de detección de idioma ni un sustituto de contenido realmente traducido.

## Anti-patterns

- **Optimizar solo con datos de laboratorio (Lighthouse) y nunca revisar el reporte de campo real en Search Console**: un Lighthouse en verde no garantiza buen CWV real si el hardware/red de tus usuarios reales es peor que el entorno simulado.
- **Animar `top`/`left`/`margin` en vez de `transform`**: páginas que animan propiedades que inducen layout tienen casi el doble de probabilidad de tener CLS "malo" que el promedio — es uno de los errores de CLS más fáciles de evitar y más comunes de cometer.
- **Marcar datos estructurados que no son visibles en la página**: viola las guías de Google directamente y puede marcarse como spam, no solo perder elegibilidad de rich result.
- **Actuar sobre una caída de tráfico sin confirmar primero que es real en dos fuentes distintas**: perseguir un "problema" que en realidad es un glitch de medición desperdicia semanas de trabajo técnico innecesario.
- **Asumir FID (First Input Delay) como la métrica de interactividad vigente**: fue reemplazada por INP en 2024 — cualquier auditoría o herramienta que siga reportando solo FID está desactualizada.

## Reference Tables

**Umbrales Core Web Vitals (percentil 75, datos de campo)**

| Métrica | Bueno | Necesita mejora | Malo |
|---|---|---|---|
| LCP | ≤ 2.500 ms | 2.500-4.000 ms | > 4.000 ms |
| INP | ≤ 200 ms | 200-500 ms | > 500 ms |
| CLS | ≤ 0,1 | 0,1-0,25 | > 0,25 |

**Proceso de diagnóstico de caída de tráfico (orden fijo)**

| Paso | Pregunta | Herramienta |
|---|---|---|
| 1 | ¿Es una caída real, confirmada en 2 fuentes? ¿Hay acción manual? | Search Console + Analytics |
| 2 | ¿Coincide con un algorithm update de Google? | Calendario de updates + Ahrefs Site Explorer |
| 3 | ¿El buscador se está quedando el tráfico (AI Overview, SERP features nuevas)? | Search Console, filtro por SERP features |
| 4 | ¿Hubo un cambio técnico, planeado o no? | Logs de deploy, control de versiones |
| 5 | ¿Hubo un cambio de diseño que tocó elementos SEO? | Historial de cambios de contenido/diseño |
| 6 | ¿Es declive gradual (content decay) del contenido? | Reporte de tráfico declinante por página |

## Worked Example

**Auditoría de rendimiento de una landing con LCP en 4.200 ms (percentil 75, campo real):**

1. Revisar en el HTML fuente si la imagen hero (candidata a LCP) está en un `<img src=...>` estándar o detrás de `data-src` / carga vía JS — se encuentra que está detrás de un componente React que la inyecta tras hidratación (CSR puro).
2. Diagnóstico: el "resource load delay" es el cuello de botella — Google no puede descubrir la URL de la imagen hasta ejecutar JS.
3. Arreglo: mover a Server-Side Rendering para esa sección (o al menos renderizar el `<img>` en el HTML inicial), añadir `fetchpriority="high"` y confirmar que no tiene `loading="lazy"`.
4. Verificación secundaria: revisar CLS — se detecta que el banner de cookies se anima con `margin-top`, empujando el contenido; se cambia a `transform: translateY()`.
5. Medir de nuevo en campo (no solo laboratorio) tras 28 días — el percentil 75 de LCP debería bajar significativamente si el diagnóstico fue correcto; si no mejora, el cuello de botella real puede estar en el servidor (TTFB) y no en el front-end.

## Key Takeaways

1. Los tres Core Web Vitals tienen umbrales numéricos exactos y públicos (LCP ≤2.500ms, INP ≤200ms, CLS ≤0,1) medidos en percentil 75 de datos de campo reales — no son una opinión de diseño.
2. La causa más común de mal LCP es que el recurso principal no sea descubrible en el HTML fuente (depende de JS); la causa más común de mal CLS es contenido sin `width`/`height` definidos.
3. INP reemplazó a FID en 2024 — cualquier referencia a FID como métrica vigente está desactualizada.
4. Ante una caída de tráfico, sigue el proceso de descarte en orden (confirmar → algorithm update → SERP features que absorben clics → cambios técnicos → cambios de diseño → content decay) antes de actuar; saltarse pasos lleva a arreglar el síntoma equivocado.
5. hreflang declara equivalencia entre variantes de idioma/región — no traduce ni sustituye contenido realmente localizado, y Google no lo usa para detectar el idioma de una página.

## Connects To
- **Ch 1**: el renderizado JS descrito aquí para LCP es la misma etapa de "rendering" del proceso de crawling/indexing del Ch 1 — un problema de LCP por CSR suele ser también un problema de indexación.
- **Ch 5**: content decay conecta directamente con la estrategia de refresco de contenido y topic clusters.
- **Ch 6**: la absorción de tráfico por AI Overviews (paso 3 del diagnóstico de caídas) es el fenómeno central del capítulo de SEO en la era de la IA generativa.

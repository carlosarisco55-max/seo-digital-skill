# Capítulo 5: Estrategia de contenido — topic clusters y mantenimiento

## Core Idea
Organizar el contenido como una red de temas relacionados (topic clusters) en vez de una colección suelta de posts individuales es lo que convierte cobertura dispersa en autoridad temática reconocible tanto por buscadores clásicos como por motores de IA — y esa autoridad se erosiona sola con el tiempo (content decay) si no existe un proceso deliberado de mantenimiento.

## Frameworks Introducidos

- **Topic clusters (pillar + cluster pages + enlazado interno)**
  - Cuándo usarlo: al planificar la arquitectura de contenido de un sitio o blog con más de un puñado de artículos sobre el mismo tema amplio.
  - Cómo, tres componentes: (1) **Pillar page** — cubre un tema amplio a alto nivel, introduce los subtemas principales y enlaza hacia cada cluster page; debe funcionar como respuesta creíble por sí sola para alguien que busca el término principal. (2) **Cluster pages** — cada una profundiza en un subtema o long-tail específico que el pillar es demasiado amplio para cubrir en detalle; targetea una keyword/pregunta concreta cada una. (3) **Enlazado interno** — tres reglas: cada cluster enlaza al pillar con anchor text descriptivo; el pillar enlaza a cada cluster relevante (idealmente en la sección donde introduce ese subtema); los clusters se enlazan entre sí solo cuando el tema realmente se solapa, nunca de forma forzada.
  - Por qué funciona: el enlazado denso elimina páginas huérfanas por diseño (ver Ch 1), ayuda a Googlebot a descubrir y re-rastrear contenido nuevo, y concentra "link equity" — si el pillar gana enlaces externos como recurso de referencia, parte de esa autoridad se reparte hacia los clusters que enlaza.
  - (fuente: HubSpot, "Topic clusters: The next evolution of SEO", blog.hubspot.com/marketing/topic-clusters-seo, 2026-06-17; y Ahrefs, "How to Build a Topic Cluster in 10 Minutes", ahrefs.com/blog/topic-clusters, consultado 2026-08)

- **Proceso de construcción de un topic cluster (5 pasos)**
  - Cuándo usarlo: como checklist operativo al lanzar un cluster nuevo desde cero.
  - Cómo: (1) elegir el tema core (candidato a pillar); (2) validar con keyword research (volumen, intención, preguntas relacionadas en "People Also Ask" y en listas de fuentes citadas por AI Overviews — ambas revelan qué subtemas el propio buscador ya agrupa como relacionados); (3) escribir el pillar; (4) construir el contenido de cluster de soporte; (5) conectar todo con enlazado interno siguiendo las tres reglas de arriba. Los dos primeros pasos son de planificación (mapear candidatos); los tres últimos son de ejecución, cluster por cluster.
  - (fuente: HubSpot, blog.hubspot.com/marketing/topic-clusters-seo, 2026-06-17, consultado 2026-08)

- **Estructurar una pieza de contenido a partir de lo que ya premia la SERP [CLASE]**
  - Cuándo usarlo: ya tienes la keyword (del estudio de audiencia y keywords, Ch 8) pero no sabes qué forma debe tener el contenido.
  - Cómo, en 4 pasos: (1) busca la keyword en Google y mira los *titles* de los 3-5 primeros resultados — si varios usan un número ("Top 8…", "14 mejores…") es señal de que el formato esperado es un listado; (2) entra en cada resultado y observa cómo trocean la información (resumen corto por punto, bullets de "uso principal"/"ventaja clave", tabla resumen al inicio); (3) identifica recursos reutilizables — tablas, FAQ, bloque de autoría del contenido (E-E-A-T, ver Ch 4) — y decide cuáles aportan a tu pieza; (4) revisa también qué cita el AI Overview/Modo IA para la misma consulta (Ch 6): si ya cubriste los pasos anteriores, suele coincidir.
  - [EXPERTO] Esto es investigación de **formato**, no plantilla para copiar: fijarte en la estructura que premia Google (listado, tabla, FAQ) no es lo mismo que "refritar" contenido ajeno. Para que el contenido sea realmente propio tiene que aportar algo que no esté ya en la red — experiencia genuina, datos propios, un ángulo que los primeros resultados no cubren.
  - (fuente: método de un curso de posgrado, 2026-09; contrastado con las guías de contenido útil de Google, ver Ch 6)

- **Decisión de mantenimiento de contenido: actualizar, consolidar, redirigir o podar**
  - Cuándo usarlo: al auditar contenido existente con tráfico en declive (content decay) — antes de reescribir nada, hay que diagnosticar la causa.
  - Cómo: primero distingue **declive gradual sin cambios previos** (decay real: el contenido se quedó quieto, el mundo se movió — la solución es refrescar) de **caída tras un cambio previo en la propia página** (puede que el cambio anterior haya degradado algo que funcionaba — la solución puede ser revertir, no refrescar de nuevo). Aplicar el arreglo equivocado (ej. refrescar una página que en realidad debería consolidarse con otra) desperdicia esfuerzo y puede empeorar el problema.
  - Google favorece contenido actualizado recientemente para queries con señal implícita de "frescura" (ej. "mejores [X]", "cómo [Y]") — contenido sin tocar en 2+ años queda en desventaja estructural frente a competidores mantenidos, incluso si el original era objetivamente más completo.
  - (fuente: Ahrefs, "What Is Content Decay?", ahrefs.com/blog/content-decay, 2026-03-13, consultado 2026-08)

## Key Concepts

- **Pillar page**: página ancla de un topic cluster, cobertura amplia de un tema, punto de entrada y de enlace hacia los clusters.
- **Cluster page**: página de soporte que profundiza en un subtema específico dentro del paraguas del pillar.
- **Hub and spoke**: nombre alternativo del mismo modelo (pillar = hub, clusters = spokes).
- **Content decay**: declive gradual (meses/años) de tráfico y rankings de una página por quedar desactualizada, sin que medie una penalización o bug técnico — se detecta comparando tráfico histórico contra tendencia reciente.
- **Query fan-out**: técnica que usan AI Overviews y AI Mode de Google para descomponer una búsqueda en múltiples subconsultas relacionadas antes de generar la respuesta (ver Ch 6) — un cluster con cobertura profunda tiene más páginas indexadas elegibles para aparecer citadas en esas subconsultas.
- **People Also Ask (PAA)**: caja de preguntas relacionadas en la SERP de Google — fuente directa de candidatos a cluster pages, porque revela qué subtemas el propio Google ya asocia con la keyword principal.
- **Refrito de contenido [CLASE]**: reescribir lo mismo que ya dicen los primeros resultados sin aportar nada propio. Mirar la estructura que premia Google es investigación de formato válida; copiar el contenido sin genuina experiencia o dato propio detrás es refrito, y compite peor frente a contenido con E-E-A-T real.

## Mental Models

- Antes de escribir un pillar, pregunta "¿esta página sola respondería de forma creíble a alguien que solo lee esto y no hace clic en ningún cluster?" — si la respuesta es no, el pillar es demasiado superficial y no cumplirá su función de ancla.
- Usa PAA y las fuentes citadas en AI Overviews como un mapa gratuito de qué subtemas agrupa el propio buscador — no adivines candidatos a cluster page desde cero cuando el buscador ya te está mostrando su propia taxonomía implícita.
- Trata el mantenimiento de contenido como un proceso recurrente con presupuesto propio, no como una tarea "cuando haya tiempo" — el content decay es progresivo e invisible hasta que ya perdiste terreno significativo; auditar trimestralmente el contenido con tráfico declinante es más barato que reconstruirlo después.
- Ante una página con tráfico en declive, resuelve primero "¿decay natural o consecuencia de un cambio mío anterior?" antes de decidir la acción — son diagnósticos distintos con arreglos opuestos (refrescar vs. revertir).

## Anti-patterns

- **Crear cluster pages sin validar intención/volumen real primero**: escribir subtemas "porque suenan relacionados" sin pasar por keyword research produce clusters bonitos en el diagrama pero sin tráfico potencial real.
- **Silo virtual sin enlazado disciplinado** (ya visto en Ch 1 aplicado a arquitectura, aquí aplicado a contenido): un cluster page que no enlaza de vuelta al pillar, o un pillar que "olvida" enlazar a un cluster nuevo, rompe la señal de relación temática que es la razón de ser del modelo.
- **Refrescar contenido que en realidad necesita ser revertido**: si la caída de tráfico ocurrió justo después de un cambio de contenido (no como decay gradual sin cambios previos), añadir más contenido nuevo encima sin diagnosticar qué se rompió puede enterrar aún más el problema original.
- **Tratar cada pieza de contenido como aislada, sin plan de mantenimiento**: publicar y no volver a tocar un artículo durante años, incluso en temas con señal de frescura implícita ("mejores herramientas de X"), garantiza declive estructural frente a competidores que sí refrescan.
- **Confundir "más páginas" con "más autoridad temática"**: un cluster de 20 páginas delgadas y redundantes no genera la misma autoridad que uno de 6 páginas realmente profundas y bien diferenciadas — la calidad de cada nodo importa tanto como la cantidad de nodos.
- **Refritar la estructura de la SERP sin aportar nada propio**: copiar el listado/tabla/FAQ de los primeros resultados sin experiencia o dato genuino detrás no compite con contenido que sí lo tiene.

## Reference Tables

**Decisión de mantenimiento de contenido**

| Situación detectada | Acción recomendada |
|---|---|
| Declive gradual, sin cambios previos en la página | Refrescar (actualizar datos, ejemplos, profundidad) |
| Caída justo después de un cambio propio | Comparar antes/después; considerar revertir el cambio |
| Múltiples páginas delgadas compitiendo por el mismo tema | Consolidar en una sola página más completa + redirect 301 |
| Página sin tráfico ni potencial de intención real | Podar (eliminar + redirect a página relevante, o 404/410 si no hay equivalente) |

**Componentes de un topic cluster**

| Componente | Función | Cantidad típica |
|---|---|---|
| Pillar page | Cobertura amplia, ancla del cluster | 1 por tema core |
| Cluster pages | Profundidad en subtemas/long-tail | Varias por pillar (según cobertura de keyword research) |
| Enlaces cluster→pillar | Señal de relación temática ascendente | Obligatorio en cada cluster |
| Enlaces pillar→cluster | Distribución de autoridad descendente | Obligatorio para cada cluster relevante |

## Worked Example

**Construcción de un topic cluster para una agencia de marketing digital sobre "email marketing":**

1. Validar el tema core con keyword research: "email marketing" tiene volumen alto pero dificultad alta; se confirma como candidato a pillar.
2. Extraer subtemas de PAA y AI Overviews para "email marketing": "cómo segmentar una lista de email", "qué es el email marketing automation", "mejores asuntos de email para abrir tasas altas", "email marketing vs. redes sociales" — cada uno, un candidato a cluster page con su propio volumen/dificultad a validar individualmente.
3. Escribir el pillar ("Guía completa de Email Marketing") cubriendo cada subtema a alto nivel, con una sección dedicada a cada uno que enlaza al cluster correspondiente con anchor text descriptivo ("cómo segmentar tu lista de email").
4. Producir cada cluster page en profundidad, cada una enlazando de vuelta al pillar y, cuando el solapamiento es real, entre sí (ej. el cluster de "segmentación" enlaza al de "automation" porque ambos comparten flujo de trabajo).
5. A los 6 meses, auditar tráfico por página dentro del cluster — si alguna cluster page muestra decay, aplicar el framework de mantenimiento (refrescar vs. consolidar vs. podar) antes de asumir que el cluster completo necesita más contenido nuevo.

## Key Takeaways

1. Un topic cluster son tres piezas obligatorias trabajando juntas — pillar, clusters, y enlazado interno bidireccional — no basta con escribir contenido relacionado si no está enlazado según las reglas.
2. Usa PAA y las fuentes que ya cita el propio Google en AI Overviews como mapa gratuito de subtemas relacionados antes de inventar candidatos a cluster page desde cero.
3. El content decay es progresivo e invisible — audita contenido con tráfico declinante de forma recurrente (trimestral, no reactiva) en vez de esperar a notarlo por una caída grande.
4. Antes de refrescar una página en declive, diagnostica si la caída fue gradual (decay real) o consecuencia de un cambio previo tuyo — son arreglos distintos.
5. Calidad por nodo importa tanto como cantidad de nodos — un cluster de pocas páginas realmente profundas supera a uno de muchas páginas delgadas y redundantes.

## Connects To
- **Ch 1**: la lógica de silos de arquitectura del Ch 1 y el topic cluster de este capítulo son la misma idea aplicada a nivel de URLs (Ch 1) y a nivel de contenido/enlazado (aquí).
- **Ch 3**: el keyword research e intención de búsqueda del Ch 3 es el insumo de planificación de este capítulo (pasos 1-2 del proceso de construcción de cluster).
- **Ch 6**: el query fan-out de AI Overviews premia directamente a los sitios con clusters profundos, porque cada subconsulta generada por la IA tiene más probabilidad de encontrar una página propia elegible entre tus cluster pages.
- **Ch 7**: la sección on-page de metadatos y encabezados de ch07 es la implementación técnica de cada pieza de contenido estructurada aquí.
- **Workflow**: [`workflows/optimizacion-onsite-contenidos.md`](../workflows/optimizacion-onsite-contenidos.md) aplica este framework para producir el entregable real (contenido optimizado por página).

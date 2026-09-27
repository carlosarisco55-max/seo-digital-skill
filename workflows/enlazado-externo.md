# Workflow: enlazado externo (selección de medios y URLs a impulsar)

Produce un **entregable real**: la selección de medios de terceros donde conseguir un enlace, las URLs de tu web a impulsar y el texto ancla de cada una, con la hoja de entrega mensual al cliente. Base teórica: [`ch09`](../chapters/ch09-arquitectura-navegacion-y-enlazado.md) (criterios del medio y contraste con la política de spam de Google) y [`ch04`](../chapters/ch04-offpage-autoridad-y-eeat.md) (tipos de enlace, anchor text, link spam). Plantilla de salida: [`templates/enlazado-externo.md`](../templates/enlazado-externo.md).

## Cuándo usarlo

Cuando ya está definida la arquitectura (workflow `arquitectura-enlazado-interno`) y se sabe qué URLs de la web generan más negocio: toca conseguir enlaces hacia ellas desde medios con autoridad.

## Reglas duras (no negociables)

1. **Se enlaza hacia las URLs con mayor potencial de negocio**, directo o indirecto; no hacia cualquier página.
2. **Anchor text = keyword por la que se quiere posicionar esa URL**, con variación (un enlace de marca/categoría a la Home y otro con la keyword a la página de servicio).
3. **Contenido nuevo y editorial**: no publirreportaje. Si el medio cobra por publicar con enlace, el enlace debe ir con `rel="sponsored"` o `rel="nofollow"` (política de spam de Google); entonces no cuenta como autoridad de ranking.
4. **No se compran ni intercambian enlaces de forma sistemática** para posicionar (Ch 4).
5. **Los umbrales son de clase, no de Google**: ≥ 1.200 sesiones/mes, DR (Ahrefs) > 20, DA (Moz) > 24, ≤ 3 meses sin publicar, último contenido de casinos hace > 1 año. Anótalos como criterios de trabajo.
6. **Cada medio elegido se justifica con captura** (búsqueda, Similarweb, portada con fechas, búsqueda `site:`).

## Entradas necesarias

- Las URLs prioritarias del sitio y sus keywords (del workflow de arquitectura y del estudio de keywords).
- El país en el que se quiere posicionar.
- Acceso a Similarweb (plan gratuito o conector) y, si se dispone, a Ahrefs/Moz para DR/DA.

## Pasos

| # | Paso | Herramienta | Salida |
|---|---|---|---|
| 0 | **Elegir las URLs a impulsar** (mayor potencial de negocio directo o indirecto) y **definir el anchor text** de cada una a partir de su keyword | Arquitectura + estudio de keywords | Tabla URL → keyword → anchor |
| 1 | **Buscar medios** del sector en Google (por ejemplo "revista de [tu sector]", "blog de [tu sector]") | Google | Lista larga de candidatos |
| 2 | **Filtrar por tráfico**: visitas mensuales y país de origen. En Similarweb: busca el dominio → bloque "Total Visits" (visitas estimadas) → bloque "Top Countries" (desglose por país) | Similarweb (estimaciones) | Candidatos con métricas |
| 3 | **Comprobar temática y recurrencia**: publica sobre el tema y hace poco que publicó | Portada y artículos con fecha | Candidatos vigentes |
| 4 | **Descartar contenido sensible**: búsqueda `site:dominio.com "casino"` y revisar fechas | Google | Candidatos limpios |
| 5 | **Métricas de terceros** (opcional según proyecto): DR > 20 y DA > 24 | Ahrefs / Moz | Candidatos que pasan el filtro |
| 6 | **Seleccionar 5 medios** y asignar URL de destino y anchor a cada uno | Manual | Hoja de entrega (web, temática, URL final, tráfico, anchor 1, link 1, anchor 2, link 2) |
| 7 | **QA**: coherencia con la política de spam, evidencia por decisión y umbrales anotados como "de clase" | Plantilla | Entregable + capturas |

## Criterios de calidad

- Los 5 medios cumplen los criterios o las excepciones están justificadas por escrito.
- Cada URL de destino tiene su anchor con keyword y un anchor de marca en la Home.
- Hay captura de cada comprobación (tráfico, temática/fecha, `site:`).
- El plan no depende de comprar enlaces sin calificar.

## Qué NO hacer

- No elegir un medio solo por DR/DA.
- No dar por buenos los números de Similarweb como si fueran los reales del medio.
- No contactar a los medios ni cerrar acuerdos sin aprobación humana.
- No inventar tráfico ni métricas: si no hay dato, `SIN DATO`.

## Cómo lo ejecuta Claude con las herramientas disponibles

- Prepara la tabla de URLs y anchors, aplica los criterios a los candidatos que le pases, redacta la justificación y monta la hoja de entrega.
- Puede buscar candidatos y comprobar temática/recurrencia con `firecrawl-search`/`WebFetch`; con el conector de Similarweb autorizado podría leer las métricas, si no, las capturas las hace el humano.
- **Lo que hace el humano**: hacer las capturas de Similarweb/Google, decidir con criterio de negocio y aprobar cualquier contacto con medios.

## Connects To

- **`workflows/arquitectura-enlazado-interno.md`**: define qué URLs merece la pena impulsar.
- **`ch04`**: anchor text natural, tipos de enlace y link spam.
- **`ch09`**: criterios de selección del medio y contraste clase-vs-Google.

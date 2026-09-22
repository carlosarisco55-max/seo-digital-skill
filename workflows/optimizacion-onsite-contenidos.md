# Workflow: optimización onsite y de contenidos

Produce un **entregable real** (metadatos optimizados por página + contenido de al menos 3 piezas, con imágenes y alt text) para un sitio concreto. Base teórica: [`ch07`](../chapters/ch07-implementacion-tecnica-checklist.md) (metadatos, triángulo, Hn, alt text), [`ch05`](../chapters/ch05-topic-clusters-y-estrategia-contenido.md) (cómo estructurar cada pieza) y [`ch01`](../chapters/ch01-crawling-indexacion-arquitectura.md) (enlazado interno y autoridad). Plantilla de salida: [`templates/optimizacion-onsite-contenidos.md`](../templates/optimizacion-onsite-contenidos.md).

## Cuándo usarlo

Después del estudio de audiencia y keywords (`workflows/estudio-audiencia-keywords.md`): ya tienes la tabla keyword → URL objetivo, y toca convertir cada fila en metadatos y contenido reales.

## Reglas duras (no negociables)

1. **Una keyword principal por página**, con 1-2 secundarias como mucho — nunca al revés (varias keywords principales compitiendo en la misma página).
2. **Un solo H1 por página, nunca 0 ni 2+.** Es la regla de clase/accesibilidad, no una norma de Google (ver `ch07`), pero se aplica igual.
3. **Ninguna cifra de longitud es un límite real de Google** (ver `ch07`) — úsalas como rango orientativo, no las trates como validación/error binario.
4. **El contenido no es un refrito**: mirar la SERP da el formato (listado, tabla, FAQ), no el texto a copiar. Cada pieza necesita un ángulo o dato propio que los primeros resultados no tengan.
5. **Alt text real y único por imagen**, nunca relleno de keywords.

## Entradas necesarias

- Tabla keyword → URL objetivo del estudio de audiencia y keywords (o el mapa de páginas del sitio).
- Acceso al contenido actual de cada página (si existe) para no partir de cero.
- 3-5 competidores/resultados que ya posicionan para cada keyword principal.

## Pasos

| # | Paso | Herramienta | Salida |
|---|---|---|---|
| 0 | **Inventario de páginas**: una fila por página objetivo (home, landings, piezas de blog) | Tabla keyword→URL del estudio previo | Lista de páginas a optimizar |
| 1 | **Title + meta description** por página, con keyword principal en el title | Manual, contrastado con `ch07` | Title y meta description + su longitud |
| 2 | **H1 + jerarquía de encabezados**: H1 único con la keyword principal; H2/H3 con las secundarias/subtemas | Manual | Árbol de encabezados por página |
| 3 | **Investigar el formato que premia la SERP** para la keyword principal (framework de `ch05`): title de los primeros resultados, cómo trocean la info, tablas/FAQ/autoría | Google, navegador | Formato decidido (listado, guía, comparativa…) + captura |
| 4 | **Redactar el contenido**: mínimo 3 piezas — 1 página de servicio + 2 de intención comercial o informacional — con el formato del paso 3 y un ángulo/dato propio | Documento (.docx o similar) por pieza | Contenido completo, no un esquema |
| 5 | **Imágenes**: mínimo 2 por contenido, con alt text único y descriptivo (no relleno de keywords) | Manual | Lista imagen → alt text |
| 6 | **Enlazado interno de la pieza**: anchor text descriptivo, enlaza al pillar/páginas relacionadas (ver `ch01`, `ch05`) | Manual | Enlaces salientes de la pieza |
| 7 | **QA** con la plantilla y empaquetado | Plantilla | Entregable + capturas de evidencia |

## Criterios de calidad

- Cada página tiene title, meta description, H1 y jerarquía de encabezados — ninguna celda vacía sin motivo.
- El formato del contenido se justifica con una captura de la SERP, no "porque sí".
- Ninguna pieza es un refrito: se puede señalar el ángulo o dato propio que aporta.
- Todas las imágenes tienen alt text único.

## Qué NO hacer

- No copiar el contenido de un competidor cambiando solo palabras sueltas.
- No meter la keyword principal a la fuerza en title/meta si rompe la legibilidad.
- No dejar el "peso de imagen <100kb" (dato de clase, no de Google) como bloqueante si penaliza la calidad visual — es una referencia, no un límite oficial.
- No entregar un esquema o resumen como si fuera el contenido final: la última columna del entregable es la pieza completa, no un borrador.

## Cómo lo ejecuta Claude con las herramientas disponibles

- Redacta title/meta description/H1 y el borrador de contenido, y **prepara la hoja de entrega**.
- Analiza el HTML propio o de competidores en local/vía `firecrawl-search` para ver cómo estructuran su contenido (título, tablas, FAQ).
- **Lo que hace el humano**: mirar la SERP real de España y decidir el formato con criterio de negocio, aportar el dato/ángulo propio que hace el contenido no-refrito, y aprobar el contenido final antes de publicar.

## Connects To

- **`workflows/estudio-audiencia-keywords.md`**: entrega la tabla keyword→URL que este workflow convierte en metadatos y contenido.
- **`ch01`**: el enlazado interno de cada pieza alimenta el modelo de autoridad (PageRank) del capítulo 1.

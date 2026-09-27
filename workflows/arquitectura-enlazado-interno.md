# Workflow: arquitectura web y enlazado interno

Produce un **entregable real**: el despliegue de todas las URLs de un sitio (con sintaxis correcta), el diseño de qué se enlaza desde el menú principal y el footer (justificado), y la estrategia de enlazado interno desde la Home y desde otra página. Base teórica: [`ch09`](../chapters/ch09-arquitectura-navegacion-y-enlazado.md), con apoyo de [`ch01`](../chapters/ch01-crawling-indexacion-arquitectura.md) (PageRank, 404, huérfanas) y [`ch08`](../chapters/ch08-audiencia-customer-journey-y-estudio-de-keywords.md) (tabla keyword → URL). Plantilla de salida: [`templates/arquitectura-enlazado-interno.md`](../templates/arquitectura-enlazado-interno.md).

## Cuándo usarlo

Después del estudio de audiencia y keywords y de la optimización onsite: ya tienes keyword → URL objetivo y metadatos, y toca decidir **qué páginas existen, cómo se llaman y cómo se enlazan**.

## Reglas duras (no negociables)

1. **Un servicio clave, una URL exclusiva** (una intención principal por URL, Ch 8).
2. **Sintaxis limpia**: minúsculas, guiones (nunca `_`), sin ñ/acentos/símbolos, sin parámetros innecesarios, `https://`. Son reglas de clase; Google recomienda guiones, trata mayúsculas y minúsculas como URLs distintas y admite caracteres no ASCII codificados (ver Ch 9).
3. **Menú = lo más importante del negocio**; footer = legales y URLs de peso medio; contenido = páginas contextuales que no están en menú ni footer.
4. **Anchor text con la keyword de la página enlazada**, nunca genérico.
5. **Ninguna URL enlazada devuelve 404/500** y ninguna página importante queda sin enlace interno (huérfana).
6. **Cada decisión se justifica con una captura** (SERP, herramienta o menú de un competidor de referencia), no "porque sí".

## Entradas necesarias

- Tabla keyword → URL objetivo y metadatos por página.
- Lista de servicios/productos con su importancia de negocio (volumen de búsqueda, retorno, papel en el journey).
- 2-3 webs de referencia del sector para comparar menús y footers.

## Pasos

| # | Paso | Herramienta | Salida |
|---|---|---|---|
| 0 | **Inventario** de páginas y servicios clave | Tabla keyword → URL | Lista de URLs por nivel |
| 1 | **Árbol de la web**: Home → categorías → subcategorías; comprobar profundidad razonable (Ch 1) | Manual | Diagrama de niveles |
| 2 | **Despliegue de URLs**: escribir cada URL con la sintaxis correcta (protocolo, dominio, carpeta de idioma, carpetas, slug con la keyword) | Checklist de URL (Ch 9) | Tabla de URLs revisada |
| 3 | **Clasificar por importancia de negocio**: alto volumen; poco volumen pero mucho retorno; informacionales estratégicos que empujan a comprar | Datos del estudio de keywords | URLs priorizadas |
| 4 | **Menú principal y footer**: elegir qué se enlaza en cada uno y justificarlo | Menús de referencia (captura) | Propuesta de menú y footer |
| 5 | **Enlazado desde el contenido**: elegir URLs no enlazadas desde menú/footer que se enlazarán desde el cuerpo de la Home y desde otra página (preferible una de las ya optimizadas), con su anchor text | Manual | Tabla origen → destino → anchor |
| 6 | **QA**: comprobar 404/500, huérfanas, anchors genéricos y URLs mal formadas | Screaming Frog o revisión manual | Checklist QA |

## Criterios de calidad

- Cada URL cumple el checklist de sintaxis; ninguna es dinámica sin motivo.
- El menú tiene pocas entradas y cada una tiene justificación de negocio.
- Toda decisión de enlazado tiene captura o dato detrás.
- No hay páginas importantes sin ningún enlace interno.

## Qué NO hacer

- No poner todo en el menú "por si acaso".
- No usar "click aquí"/"leer más" como anchor.
- No inventar el volumen de búsqueda de una URL: si no hay dato, `SIN DATO` y se justifica por journey/retorno.
- No dar por verificado que enlazar lo mismo desde menú y contenido "desperdicia" autoridad: es criterio de clase (ver matiz en Ch 9).

## Cómo lo ejecuta Claude con las herramientas disponibles

- Redacta el despliegue de URLs, el diseño de menú/footer y la tabla de enlazado con su justificación, y prepara la hoja de entrega.
- Puede rastrear el sitio (Screaming Frog o `firecrawl-map`) para comprobar 404, huérfanas y anchors si el sitio ya existe.
- **Lo que hace el humano**: decidir la prioridad de negocio real, hacer las capturas de menús de referencia y de la SERP, y aprobar el diseño.

## Connects To

- **`workflows/optimizacion-onsite-contenidos.md`**: entrega los metadatos y las páginas que este workflow conecta entre sí.
- **`workflows/enlazado-externo.md`**: las URLs que aquí se priorizan son las que se impulsan desde fuera.
- **`ch09`**: método completo con contraste clase-vs-Google.

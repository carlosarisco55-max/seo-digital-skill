# Diagnóstico de caída de tráfico orgánico

Para cuando el usuario reporta (o sospecha) una caída de tráfico orgánico y necesita saber la causa real antes de actuar. Este workflow ejecuta el proceso de descarte de [ch02](../chapters/ch02-core-web-vitals-y-diagnostico.md) en orden fijo — saltar pasos es el error más común en este diagnóstico.

## Principio

**Nunca saltar el orden.** El sospechoso obvio (un cambio técnico reciente, por ejemplo) rara vez es la causa real. Cada paso descarta una categoría antes de pasar a la siguiente.

## Paso 1 — Confirmar la caída en 2 fuentes

- Search Console (impresiones/clics) y Analytics (sesiones) deben coincidir en la caída. Si solo una fuente la muestra, es un problema de medición, no de tráfico real.
- Descartar acción manual: revisar la sección "Acciones manuales" de Search Console.

## Paso 2 — ¿Coincide con un algorithm update?

- Contrastar la fecha exacta de la caída contra el calendario de updates de Google.
- Si coincide, es la explicación más probable — pero sigue documentando los pasos siguientes para tener evidencia, no solo asumir.

## Paso 3 — ¿El buscador se quedó el tráfico? (absorción)

- Comprobar si aparecen AI Overviews, AI Mode u otras SERP features nuevas en las keywords afectadas.
- **Tell del cheatsheet**: si el ranking sube pero el tráfico baja, sospecha absorción antes que fallo propio.
- Usa `firecrawl-search` o `firecrawl-seo-audit` para verificar cómo se ve hoy la SERP de las keywords principales afectadas — no asumas que sigue igual que cuando se creó el contenido.

## Paso 4 — ¿Hubo un cambio técnico propio?

- Deploy, migración, cambio de dominio/HTTPS, cambio de CMS, cambio de robots.txt/sitemap.
- Si lo hay, compara el sitio antes/después con `firecrawl-seo-audit` sobre las páginas afectadas para ver qué cambió exactamente en metadata/estructura/enlazado.

## Paso 5 — ¿Hubo un cambio de diseño que tocó elementos SEO?

- Rediseños que eliminan H1, cambian URLs sin redirect, o quitan enlazado interno son la causa más común y más ignorada.

## Paso 6 — ¿Es content decay gradual sin cambios previos?

- Si ninguno de los pasos 2-5 explica la caída, es probablemente decay natural — ver [ch05](../chapters/ch05-topic-clusters-y-estrategia-contenido.md) para decidir entre refrescar, consolidar o podar según la [tabla de decisión del cheatsheet](../cheatsheet.md#decisión-rápida-contenido-con-tráfico-en-declive).

## Entregable

Documenta el resultado de cada paso (confirmado / descartado / evidencia encontrada) aunque la causa se identifique en un paso temprano — el histórico de descarte es lo que hace el diagnóstico defendible, no solo la conclusión final. Usa [`templates/informe-diagnostico-trafico.md`](../templates/informe-diagnostico-trafico.md).

## Rerun

```
workflow: seo-digital/diagnostico-caida-trafico
sitio: [url]
periodo afectado: [fechas]
keywords/páginas afectadas: [lista]
```

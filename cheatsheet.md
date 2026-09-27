# Cheatsheet — SEO Digital

## Umbrales Core Web Vitals (percentil 75, datos de campo)
| Métrica | Bueno | Necesita mejora | Malo |
|---|---|---|---|
| LCP (velocidad de carga) | ≤ 2.500 ms | 2.500-4.000 ms | > 4.000 ms |
| INP (interactividad) | ≤ 200 ms | 200-500 ms | > 500 ms |
| CLS (estabilidad visual) | ≤ 0,1 | 0,1-0,25 | > 0,25 |

Nota: INP sustituyó a FID en 2024 — si ves FID como métrica vigente, la fuente está desactualizada.

## Decisión rápida: ¿en qué etapa falla mi página?
| Síntoma en Search Console | Etapa | Primera acción |
|---|---|---|
| "Detectada: sin indexar" en volumen alto | Crawling | Auditar inventario percibido (duplicados/parámetros) |
| "Rastreada: sin indexar" | Indexing | Revisar calidad/originalidad, señales de canonical |
| Indexada pero sin impresiones | Serving | Revisar intención de búsqueda y calidad relativa |
| Errores 5xx/429 en Crawl Stats | Capacidad de rastreo | Revisar rendimiento del servidor |

## Decisión rápida: caída de tráfico — orden de diagnóstico
1. Confirmar en 2 fuentes + descartar acción manual (Search Console + Analytics)
2. ¿Coincide con un algorithm update? (calendario de updates)
3. ¿El buscador se quedó el tráfico? (AI Overviews / SERP features nuevas)
4. ¿Hubo cambio técnico (deploy, migración)?
5. ¿Hubo cambio de diseño que tocó elementos SEO?
6. ¿Es content decay gradual sin cambios previos?

Nunca saltar el orden — el sospechoso obvio rara vez es la causa real.

## Decisión rápida: ¿qué tipo de página necesito para esta keyword?
| Intención | Señal en la SERP | Formato a crear |
|---|---|---|
| Informacional | Guías/artículos en el top 10 | Contenido educativo profundo |
| Navegacional | Resultados de marca dominan | Página de marca/producto clara |
| Comercial | Comparativas/reseñas dominan | Tabla comparativa + reseñas |
| Transaccional | Fichas de producto/landing dominan | Página de conversión sin fricción |

## Decisión rápida: contenido con tráfico en declive
| Diagnóstico | Acción |
|---|---|
| Decay gradual, sin cambios previos | Refrescar (datos, ejemplos, profundidad) |
| Caída justo tras un cambio propio | Comparar antes/después, considerar revertir |
| Varias páginas delgadas del mismo tema | Consolidar + redirect 301 |
| Sin tráfico ni intención real | Podar (404/410 o redirect a página relevante) |

## Umbrales y defaults técnicos
- Crawl budget solo relevante en: sitios 1M+ páginas (cambios semanales) o 10K+ páginas (cambios diarios).
- Crawl depth de referencia: investigar cualquier página objetivo a más de 5 clics del home.
- Densidad de encabezados: uno cada 250-350 palabras de texto corrido.
- robots.txt controla rastreo, NO indexación — usa `noindex` para desindexar de verdad.
- rel="canonical" nunca debe ir en robots.txt — solo en `<link>`, header HTTP o sitemap.
- Enlaces pagados/patrocinados: siempre `rel="nofollow"` o `rel="sponsored"`, o es link spam según política de Google.

## Tells y smells (heurísticas rápidas)
- Si el ranking sube pero el tráfico baja → sospecha absorción por AI Overview/SERP feature antes que fallo propio.
- Si el LCP es malo y el elemento es una imagen con `data-src` → el problema es descubribilidad en HTML, no compresión.
- Si el CLS es malo y hay banners/cookies animados → revisa si animan `top`/`margin` en vez de `transform`.
- Si una keyword de volumen alto no despega en meses → revisa dificultad real vs. tu autoridad actual, no solo el copy.
- Si el anchor text de tus backlinks es mayoritariamente la misma keyword exacta → señal de sobre-optimización, no de relevancia.
- Si un cluster de contenido no genera tráfico proporcional a su tamaño → sospecha páginas delgadas/redundantes, no falta de más páginas.
- Si consideras invertir tiempo en llms.txt como prioridad alta → revisa primero la evidencia de adopción real (Ch 6) antes de asumir impacto.

## Checklist mínima antes de publicar contenido nuevo
- [ ] Intención de búsqueda validada contra la SERP real (no asumida)
- [ ] Un H1 único, jerarquía de H2/H3 sin saltos
- [ ] Title tag y meta description alineados al formato ganador en SERP
- [ ] Autoría clara (Who) + transparencia sobre uso de IA si aplica (How) + propósito genuino para la audiencia (Why)
- [ ] Enlazado interno: al menos un enlace hacia el pillar/cluster relacionado, y desde él hacia esta página
- [ ] Párrafos clave autoconclusivos (sin depender de "como se dijo antes") para extraibilidad en IA
- [ ] Datos estructurados aplicables (JSON-LD) solo sobre contenido visible en la página

## Framework de priorización técnica (adaptado de RICE / revenue-at-risk)
Puntúa cada fix por: **Alcance** (nº de URLs/sesiones afectadas) × **Impacto** (tráfico o ingreso en riesgo) × **Confianza** (probabilidad de que el fix recupere ese valor) ÷ **Esfuerzo** (horas de implementación). Prioriza por score, no por "severidad" abstracta de una herramienta de auditoría — un problema "crítico" en tráfico irrelevante pesa menos que uno "medio" en una página de alto valor comercial.

## URLs y enlazado externo (Ch 9)

| Tema | Regla de clase | Contraste con Google |
|---|---|---|
| Separador en la URL | Guion `-`, nunca `_` | Google recomienda guiones |
| Mayúsculas | No permitidas | Google trata `/APPLE` y `/apple` como URLs distintas |
| Ñ, acentos, símbolos | No | Admite no ASCII codificado; evitarlos es criterio de limpieza |
| Parámetros | URLs estáticas | Google: recorta los que no cambian el contenido |
| Longitud | (Ch 7: < 75, convención) | Google no da ninguna longitud |
| HTTPS | Google lo impulsa | Recomendado, pero no factor de ranking fuerte |
| Importancia de URLs | Home → menú y footer → cuerpo de la Home → sin enlazar | Cada página importante necesita al menos un enlace interno |
| Medio para enlazar | ≥ 1.200 sesiones/mes · país objetivo · temática afín · contenido nuevo · no publirreportaje · DR > 20 · DA > 24 · ≤ 3 meses sin publicar · sin casinos (> 1 año) | DR/DA no son de Google; publirreportaje con enlace = `sponsored`/`nofollow` |


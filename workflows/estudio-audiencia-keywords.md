# Workflow: estudio de audiencia, customer journey y palabras clave

Produce un **entregable real** (searcher personas + customer journey + tabla de keywords con URL objetivo y evidencias) sobre un proyecto concreto. Base teórica: [`ch08`](../chapters/ch08-audiencia-customer-journey-y-estudio-de-keywords.md) y [`ch03`](../chapters/ch03-onpage-keywords-e-intencion.md). Plantilla de salida: [`templates/estudio-audiencia-keywords.md`](../templates/estudio-audiencia-keywords.md).

## Cuándo usarlo
Al empezar un proyecto SEO, un trabajo académico o el rediseño de una arquitectura web. Es la **fase 0** de todo lo demás: sin esto, arquitectura, contenidos y autoridad se construyen a ciegas.

## Reglas duras (no negociables)
1. **Nunca inventes volúmenes, KD ni posiciones.** Si no hay dato de herramienta, la celda dice `SIN DATO` y se anota qué herramienta lo resolvería. Un ejemplo de clase no es un dato del proyecto.
2. **Toda persona sintética se etiqueta `HIPÓTESIS`** hasta validarla con al menos una fuente propia (Search Console/GA4, ventas/soporte, entrevistas) o la SERP.
3. **La intención se decide mirando la SERP real** (en España, en navegador, con captura). `WebSearch` de esta sesión es solo EE. UU. y no sirve para juzgar SERPs de España.
4. **Cada decisión enlaza una evidencia** (`evidencias/NN-descripcion.png` + fecha + herramienta).
5. **Exclusiones del cliente primero**: términos con los que no se quiere trabajar se listan antes de investigar.

## Entradas necesarias
- Descripción del negocio, oferta y precio; sectores/segmentos.
- Buyer personas existentes (si las hay), y datos propios: ventas, objeciones, motivos de abandono.
- Web actual o URL (si existe) y acceso a Search Console/GA4 (si existe).
- 3-5 competidores reales (mismo tipo de negocio, no solo mismas marcas grandes).
- Mercado/idioma/geo (ej. España, español).

## Pasos

| # | Paso | Herramienta | Salida |
|---|---|---|---|
| 0 | **Exclusiones y alcance** con el cliente/director | Conversación | Lista de términos vetados + geo + idioma |
| 1 | **Searcher personas** (1-3): parte de la buyer persona y añade cómo busca | Datos propios + `WebSearch`/Google Académico + IA para redactar | Persona con perfil/objetivos/dolores, marcada `HIPÓTESIS` o `VALIDADA` |
| 2 | **Customer journey** de la persona principal: 8-14 nodos (búsquedas/preguntas reales) desde la idea remota hasta contratar | IA + Autosuggest + "Más preguntas" + AnswerThePublic | Tabla etapa → pregunta → intención → contenido posible + dibujo en el estilo de clase (zigzag; verde oscuro/amarillo = informativa, naranja = comercial, rojo/granate = transaccional; flechas de PR) |
| 3 | **Semillas y expansión**: Autosuggest, PAA, ATP, Trends (estacionalidad) y herramienta de volúmenes | Google, ATP (3/día gratis), Trends, Semrush (prueba 7 días) | Lista larga con volumen y fuente/fecha |
| 4 | **Posicionamiento propio** (si existe) | Search Console (≤1.000 filas) o Semrush | Keywords por las que ya apareces |
| 5 | **Competencia**: por qué posicionan | Semrush/Ahrefs; o inspección de sus SERPs y páginas | Keywords y páginas que les traen tráfico |
| 6 | **Gap y oportunidades**: qué cubren ellos y tú no; qué no cubre nadie | Cruce en Sheets | Lista de huecos |
| 7 | **Intención por keyword** con SERP real (3 intenciones de clase + navegacional) | Navegador + captura | Columna intención + pantallazo + SERP features (AIO, PAA, local) |
| 8 | **Asignación keyword → URL/contenido**: una intención principal por URL; detecta canibalización | Sheets | Tabla final keyword → URL objetivo → tipo de página |
| 9 | **Priorización**: relevancia de negocio × volumen ÷ dificultad; marca quick wins | Sheets | Columna prioridad (P1/P2/P3) |
| 10 | **Nodos que dependen de terceros** (mejores X, opiniones, comparativas) → pasan al plan de relevancia y autoridad | Journey | Lista de oportunidades de PR |
| 11 | **QA** (checklist de la plantilla) y empaquetado | Plantilla | Entregable + carpeta de evidencias |

## Criterios de calidad
- Cada keyword tiene: intención, URL objetivo, evidencia y fuente/fecha del volumen.
- Ninguna keyword informacional apunta a una página de servicio.
- No hay dos URLs con la misma intención principal.
- Los huecos de journey sin keyword de volumen están cubiertos por persona/journey y así se declara.
- Todo lo `SIN DATO` tiene el paso que lo resolvería.
- Los números del resumen (totales por intención, validadas/hipótesis) se calculan desde la tabla, no a mano.
- La intención de cada keyword es una sola: journey, tabla y SERP dicen lo mismo.

## Qué NO hacer
- No rellenar volúmenes "plausibles".
- No tratar la persona de la IA como cliente real.
- No copiar la tabla de ejemplo de clase como si fuera el proyecto.
- No decidir intención "por sentido común" sin captura cuando hay duda (la propia clase pide mirar la SERP).

## Capturas de SERP y Trends con Playwright (probado 2026-09-21)
Se pueden automatizar **si se hace como lo haría una persona**: Chrome real en ventana visible con perfil persistente, `locale es-ES`, pausas de 7-13 s y ~10-15 consultas por sesión. En headless, Google responde con reCAPTCHA (SERP) y 429 (Trends). Si aparece la verificación, **la resuelve una persona** en la ventana (el script espera y, si no, se detiene; no se esquiva). Esperar a que desaparezca "Buscando…" antes de capturar, o la SERP sale a medio cargar. Los resultados salen geolocalizados (ciudad de la IP) y sin sesión: declararlo.

## Cómo lo ejecuta Claude con las herramientas disponibles
- Redacta personas, journey y estructura, y **prepara las hojas y la carpeta de evidencias**.
- Lee/edita la web del proyecto en local (auditar el código propio es gratis y fiable antes de scrapear nada).
- `firecrawl-search`/`firecrawl-seo-audit` para analizar páginas de competidores (estructura, títulos, encabezados).
- **Lo que hace el humano**: abrir las SERPs de España y capturarlas, sacar volúmenes de Semrush/Keyword Planner, decidir con criterio de negocio. Claude le dice qué buscar, qué capturar y cómo nombrarlo.

## Anatomía de un buen entregable (destilada de casos reales)
Destilado de dos entregables reales (uno de equipo, uno individual). Aquí queda solo la **forma y el criterio**: los casos con sus datos no viven en esta skill. Si el proyecto es un cliente concreto, esa capa aplicada va aparte.

**Ojo:** un primer entregable suele quedarse en fase 1, sin volúmenes, sin prioridad (P1/P2/P3) y sin plan de medición. Copia la forma y el criterio, no el estado inacabado: los pasos 3-5 y 9 se hacen igualmente.

### Forma de la entrega
1. **Punto de partida**: qué se vende, a quién y con qué planes, con fuente. Lo que es hipótesis se dice desde el principio.
2. **Personas**: una por segmento, con el mismo formato (perfil, objetivos, dolores, qué buscaría) y la etiqueta de hipótesis visible, más qué la validaría.
3. **Journey**: un recorrido por persona, en 3 etapas por intención; cada etapa dice qué contenido propio la cubre.
4. **Método**: las 4 fuentes, cada una con qué se hará y con qué herramienta, aunque aún no se haya hecho.
5. **Resultado con estado honesto**: totales por intención + cuántas keywords están comprobadas en Google España, cuántas con otro buscador y cuántas son hipótesis. Volumen, KD y CPC: pendiente, no estimado.
6. **Tablas keyword → página, por intención**: transaccionales a home y landings de servicio (una por segmento si hay varios); comerciales a comparativas y precios en el blog; informacionales a blog por segmento y blog transversal. Una columna de validación por fila.
7. **Validación en la SERP**: keyword → qué premia Google → intención → decisión de contenido.
8. **Hallazgos**: qué cambió después de mirar la SERP.
9. **Descartadas, con motivo.**
10. **Evidencia numerada** (capturas con fecha y herramienta).

Un entregable más completo añade: auditoría propia con "qué falta y cómo cerrarlo", CSV (`id; keyword; intención; ámbito; sector; categoría; evidencia; volumen; KD; notas`), scripts reproducibles y los límites de la evidencia declarados (SERP geolocalizada, sin sesión iniciada).

### Intuición que funcionó (copiar el criterio)
- **La SERP corrige a la cabeza.** Una keyword pensada para la home puede resultar de otra intención al mirarla (p. ej., Google premia herramientas de hágalo-usted-mismo cuando tú vendes un servicio): cámbiala antes de asignar.
- **Cómo se entrega o se aprueba el producto no es una keyword** si no tiene demanda visible: se usa como mensaje en anuncios y landing, no como objetivo SEO.
- **Descartar es parte del entregable.** Con motivo: empleo, cursos (busca aprender, no delegar), gratis o barato (choca con el posicionamiento), genéricas dominadas por grandes, locales si no eres local, otros países.
- **Contrasta la cifra interna con lo que publica la SERP.** El precio se da como rango por tipo de proveedor, con fuente y fecha, no como una cifra única.
- **Un patrón repetible por segmento**: una landing de servicio + una pieza de blog, igual que el ejemplo de clase.
- **La SERP destapa competidores** que el análisis previo no tenía (uno directo nuevo; uno de SEO que sale en casi todo lo transaccional).
- **Mide en tu muestra lo enseñado en clase** (p. ej., la presencia del resumen de IA en tus capturas): convierte teoría en evidencia propia.
- **Persona que no encaja con los segmentos, fuera.**

### Fallos que aparecieron (no repetir)
- Una cifra interna que el propio estudio desmiente y sigue en las fichas de persona.
- Fichas con porcentajes o índices sin fuente y sin etiqueta de hipótesis (la slide la llevaba; la ficha, no).
- Leyenda del journey distinta entre personas, y la misma búsqueda con intención distinta en el journey y en la tabla.
- Contadores del resumen que no cuadran con las tablas.
- Una "keyword" que en realidad son dos búsquedas unidas con "o".
- Cabeceras de tabla ilegibles y cuadros que tapan filas: revisar cada slide ya renderizada.
- "[Insertar captura]" en la entrega: si aún no hay evidencia, se muestra como pendiente a la vista, no como si estuviera.

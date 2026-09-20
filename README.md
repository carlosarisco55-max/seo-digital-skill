# seo-digital

Skill de [Claude Code](https://claude.com/claude-code) de SEO **accionable**: combina conocimiento de fuentes primarias con workflows que producen entregables reales sobre un sitio concreto, no solo teoría.

## Qué hace

- **Auditoría SEO completa** de un dominio: recolección de datos (con `firecrawl-seo-audit`), interpretación con los frameworks de la skill y priorización con **RICE**. Resultado: un informe real.
- **Diagnóstico de caída de tráfico** con un proceso de descarte de 6 pasos en orden fijo (confirmar → actualización de algoritmo → absorción por SERP features/IA → cambios técnicos → cambios de diseño → content decay).
- Consulta por temas: crawling e indexación, Core Web Vitals, on-page e intención de búsqueda, link building y E-E-A-T, topic clusters, y SEO para buscadores de IA (AI Overviews, GEO).

## Qué incluye

| Ruta | Contenido |
|---|---|
| `SKILL.md` | Punto de entrada y frameworks principales |
| `chapters/` | 7 capítulos (técnico, Core Web Vitals, on-page, off-page, clusters, IA generativa, checklist de implementación) |
| `workflows/` | `auditoria-tecnica-seo.md` y `diagnostico-caida-trafico.md` |
| `templates/` | Plantillas del informe de auditoría y del diagnóstico de tráfico |
| `checklists/` | Auditoría rápida y pre-publicación |
| `cheatsheet.md`, `patterns.md`, `glossary.md` | Referencia rápida, patrones y glosario |

## Cómo usarla

1. Copia la carpeta a `~/.claude/skills/seo-digital/`.
2. Pide, por ejemplo: *"audita el SEO de midominio.com"* o *"¿por qué bajó el tráfico de este sitio?"*.
3. Para la auditoría necesitas la skill `firecrawl-seo-audit` (Firecrawl, con su propia API key). Sin ella puedes seguir el workflow a mano.

## Fuentes

Google Search Central, web.dev, Search Quality Rater Guidelines, Moz, Ahrefs, Backlinko, HubSpot, Search Engine Land/Journal, Semrush, Yoast y Lighthouse. Cada capítulo indica sus notas de fuente. Generada a partir de investigación web (2026-08), sin documento de curso.

**Ojo con el hype:** los datos cambian rápido (por ejemplo, la adopción real de `llms.txt` por bots de IA es mínima). Verifica la evidencia antes de priorizar tácticas nuevas.

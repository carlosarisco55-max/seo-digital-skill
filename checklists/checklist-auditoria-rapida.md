# Checklist de auditoría rápida

Extraído de [ch07](../chapters/ch07-implementacion-tecnica-checklist.md) como checklist independiente — úsalo para una verificación rápida sin pasar por el workflow completo de auditoría, o como paso final de [`workflows/auditoria-tecnica-seo.md`](../workflows/auditoria-tecnica-seo.md).

## Crítico

- [ ] HTTPS activo
- [ ] robots.txt permite rastreo de páginas importantes
- [ ] Sin `noindex` accidental en páginas clave
- [ ] Title tags únicos en cada página
- [ ] Un solo `<h1>` por página

## Alta prioridad

- [ ] Meta descriptions presentes y únicas
- [ ] Sitemap enviado a Search Console
- [ ] Canonical URLs configuradas
- [ ] Responsive / mobile-friendly
- [ ] Core Web Vitals en verde (LCP ≤2.500ms, INP ≤200ms, CLS ≤0,1)

## Media prioridad

- [ ] Datos estructurados implementados donde aplique
- [ ] Estrategia de enlazado interno (pillar ↔ clusters)
- [ ] Alt text en imágenes
- [ ] URLs descriptivas
- [ ] Breadcrumbs

## Continuo

- [ ] Revisar errores de rastreo en Search Console
- [ ] Actualizar sitemap con cada cambio de contenido
- [ ] Monitorizar cambios de ranking
- [ ] Revisar enlaces rotos
- [ ] Auditar content decay periódicamente

## Qué hacer si algo no se puede verificar

Si un ítem requiere una herramienta que no está disponible en la sesión actual (Search Console, PageSpeed real), márcalo como **"no verificable"** explícitamente en el informe — no lo omitas ni asumas que está bien.

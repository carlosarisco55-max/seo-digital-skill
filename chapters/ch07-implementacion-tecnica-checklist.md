# Capítulo 7 — Implementación técnica y checklist rápido

**Fuente**: Lighthouse SEO audits + Google Search Central (vía skill `seo` de `web-quality-skills`, fusionada aquí el 2026-08-18). Este capítulo es deliberadamente distinto en formato al resto: es **código listo para copiar y un checklist de auditoría**, no un framework conceptual — para cuando ya sabes qué hacer (ver ch01-ch06) y solo necesitas el snippet exacto.

## Crawlability

**robots.txt:**
```text
User-agent: *
Allow: /

Disallow: /admin/
Disallow: /api/
Disallow: /private/

# No bloquear recursos necesarios para el renderizado
# ❌ Disallow: /static/

Sitemap: https://example.com/sitemap.xml
```

**Meta robots:**
```html
<meta name="robots" content="index, follow">              <!-- por defecto -->
<meta name="robots" content="noindex, nofollow">           <!-- páginas a excluir -->
<meta name="robots" content="index, nofollow">              <!-- indexable, no seguir enlaces -->
<meta name="robots" content="max-snippet:150, max-image-preview:large">
```

**Canonical URLs:**
```html
<link rel="canonical" href="https://example.com/page">
<!-- Auto-referenciado (recomendado) -->
<link rel="canonical" href="https://example.com/current-page">
```
Recuerda (ch01): robots.txt controla **rastreo**, nunca indexación — para eso está `noindex` o el canonical.

## Sitemap XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  <url>
    <loc>https://example.com/</loc>
    <lastmod>2026-08-15</lastmod>
    <changefreq>daily</changefreq>
    <priority>1.0</priority>
  </url>
</urlset>
```

- Máximo 50.000 URLs o 50MB por sitemap; usa sitemap index si el sitio es más grande.
- Solo URLs canónicas e indexables.
- Actualiza `lastmod` cuando cambie el contenido y súbelo a Search Console.

## Estructura de URLs

```
✅ https://example.com/products/blue-widget
❌ https://example.com/p?id=12345
❌ https://example.com/products/item/category/subcategory/blue-widget-2024-sale
```
Guiones (no guión bajo), minúsculas, cortas (<75 caracteres), keyword natural, evitar parámetros, siempre HTTPS.

## On-page: title, meta description, encabezados

**El triángulo de metadatos [CLASE]**: title + meta description (lo que se ve en la SERP) arriba; H1 (encabezado principal) y resto de encabezados (H2-H6, contextuales) abajo; en el centro, el objetivo de la página. Los cuatro deben compartir la keyword principal (title/H1) o keywords secundarias/contextuales (meta description/resto de encabezados) — nunca inventarse cada uno por su lado.

```html
<!-- Title: 50-60 caracteres, keyword al principio, marca al final -->
<title>Blue Widgets for Sale | Premium Quality | Example Store</title>

<!-- Meta description: 150-160 caracteres, con CTA -->
<meta name="description" content="Shop premium blue widgets with free shipping. 30-day returns. Rated 4.9/5 by 10,000+ customers.">
```
**[CLASE + VERIFICADO]** Google no fija un límite de caracteres — trunca por ancho en píxeles (~600px), no por cifra exacta. El rango 50-60 (title) / 150-160 (meta description) de arriba es convención práctica del sector, no un dato oficial de Google. El propio material de clase se contradice entre sí (una diapositiva da 60/150, otra 65/155): si preguntan en el examen, anota ambas cifras.

```html
<!-- Jerarquía correcta: un solo H1, sin saltar niveles -->
<h1>Blue Widgets - Premium Quality</h1>
  <h2>Product Features</h2>
    <h3>Durability</h3>
  <h2>Customer Reviews</h2>
```
(Ver ch03 para cómo elegir la keyword de cada title/H1 según intención de búsqueda.)

**Regla de clase sobre H1 [CLASE]**: nunca 0, nunca 2+ H1 por página; el resto de niveles (H2…H6) se anidan según la keyword principal tenga subtemas. Ejemplo de clase — keyword "tipos de sopas" (H1) → "sopas de pescado" (H2) → "sopa de arroz de pescadores" (H3), y así para cada tipo. **[VERIFICADO]** Google (John Mueller) ha confirmado que usar 1 o 100 H1 no afecta al ranking, mientras tengan sentido para el usuario — la regla de "un solo H1" es buena práctica de accesibilidad y claridad, no una norma de Google. En el examen responde como en clase.

## Imágenes

```html
<img src="blue-widget-product-photo.webp"
     alt="Blue widget with chrome finish, side view showing control panel"
     width="800" height="600" loading="lazy">
```
Nombre de fichero descriptivo, alt text real (no relleno de keywords), WebP/AVIF, lazy load bajo el fold. **[CLASE]** Como referencia de clase, el peso no debería superar ~100kb por imagen. **[VERIFICADO]** Google no publica ese límite en KB en su guía oficial de imágenes — solo pide imágenes ligeras y formatos modernos; trátalo como convención práctica del taller, no como cifra de Google.

## Enlazado interno

```html
<!-- ❌ -->
<a href="/products">Click here</a>
<!-- ✅ -->
<a href="/products/blue-widgets">Browse our blue widget collection</a>
```
Anchor text descriptivo, breadcrumbs para la jerarquía. (Ver ch05 para la estrategia de enlazado bidireccional entre pillar page y cluster pages.)

## Datos estructurados (JSON-LD)

**Organization:**
```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Organization",
  "name": "Example Company",
  "url": "https://example.com",
  "logo": "https://example.com/logo.png",
  "sameAs": ["https://twitter.com/example", "https://linkedin.com/company/example"]
}
</script>
```

**Article:**
```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Article",
  "headline": "How to Choose the Right Widget",
  "image": "https://example.com/article-image.jpg",
  "author": {"@type": "Person", "name": "Jane Smith"},
  "datePublished": "2026-01-15",
  "dateModified": "2026-01-20"
}
</script>
```

**Product:**
```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Product",
  "name": "Blue Widget Pro",
  "offers": {"@type": "Offer", "price": "49.99", "priceCurrency": "USD", "availability": "https://schema.org/InStock"},
  "aggregateRating": {"@type": "AggregateRating", "ratingValue": "4.8", "reviewCount": "1250"}
}
</script>
```

**FAQPage:**
```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [{
    "@type": "Question", "name": "What colors are available?",
    "acceptedAnswer": {"@type": "Answer", "text": "Blue, red, and green."}
  }]
}
</script>
```

**BreadcrumbList:**
```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "BreadcrumbList",
  "itemListElement": [
    {"@type": "ListItem", "position": 1, "name": "Home", "item": "https://example.com"},
    {"@type": "ListItem", "position": 2, "name": "Products", "item": "https://example.com/products"}
  ]
}
</script>
```

Validar siempre en [Google Rich Results Test](https://search.google.com/test/rich-results) o [Schema.org Validator](https://validator.schema.org/).

## Mobile SEO

```html
<meta name="viewport" content="width=device-width, initial-scale=1">
```
```css
/* Tap targets: mínimo 48x48px, texto legible sin zoom */
.mobile-friendly-link { padding: 12px; font-size: 16px; min-height: 48px; min-width: 48px; }
body { font-size: 16px; line-height: 1.5; }
```
(Ver ch02 para umbrales exactos de Core Web Vitals — LCP ≤2.500ms, INP ≤200ms, CLS ≤0,1 — mobile-first indexing hace que esto sea prioritario.)

## SEO internacional

```html
<link rel="alternate" hreflang="en" href="https://example.com/page">
<link rel="alternate" hreflang="es" href="https://example.com/es/page">
<link rel="alternate" hreflang="x-default" href="https://example.com/page">
<html lang="es-ES">
```

## Checklist de auditoría rápida

**Crítico**
- [ ] HTTPS activo
- [ ] robots.txt permite rastreo de páginas importantes
- [ ] Sin `noindex` accidental en páginas clave
- [ ] Title tags únicos en cada página
- [ ] Un solo `<h1>` por página

**Alta prioridad**
- [ ] Meta descriptions presentes y únicas
- [ ] Sitemap enviado a Search Console
- [ ] Canonical URLs configuradas
- [ ] Responsive / mobile-friendly
- [ ] Core Web Vitals en verde (ch02)

**Media prioridad**
- [ ] Datos estructurados implementados donde aplique
- [ ] Estrategia de enlazado interno (ch05)
- [ ] Alt text en imágenes
- [ ] URLs descriptivas
- [ ] Breadcrumbs

**Continuo**
- [ ] Revisar errores de rastreo en Search Console
- [ ] Actualizar sitemap con cada cambio de contenido
- [ ] Monitorizar cambios de ranking
- [ ] Revisar enlaces rotos
- [ ] Auditar content decay periódicamente (ch05)

## Herramientas

| Herramienta | Uso |
|---|---|
| Google Search Console | Monitorizar indexación, detectar errores |
| Google PageSpeed Insights | Rendimiento + Core Web Vitals |
| Rich Results Test | Validar datos estructurados |
| Lighthouse | Auditoría SEO completa |
| Screaming Frog | Análisis de rastreo a fondo |

## Entregable de onsite y contenidos

Para producir el entregable real (hoja de cálculo título/meta/H1 por página + docx de contenido optimizado, método de un curso de posgrado), usa [`workflows/optimizacion-onsite-contenidos.md`](../workflows/optimizacion-onsite-contenidos.md) con la plantilla [`templates/optimizacion-onsite-contenidos.md`](../templates/optimizacion-onsite-contenidos.md).

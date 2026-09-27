# Plantilla: arquitectura web y enlazado interno

Proyecto: `[nombre]` · Fecha: `[AAAA-MM-DD]` · Autor: `[nombre]`
Flujo de trabajo: [`workflows/arquitectura-enlazado-interno.md`](../workflows/arquitectura-enlazado-interno.md)

## 1. Despliegue de URLs

Árbol de la web (nivel 0 = Home):

```
Home
  [Categoría 1]
    [Subcategoría 1.1]
  [Categoría 2]
  [Blog]
```

| Nivel | Nombre de la página | URL completa | Keyword principal | Intención | ¿Cumple la sintaxis? |
|---|---|---|---|---|---|
| 0 | `[Home]` | `[https://...]` | `[...]` | `[...]` | `[sí/no: minúsculas, guiones, sin acentos ni parámetros]` |

## 2. Menú principal y footer (con justificación)

| Ubicación | URL enlazada | Anchor text | Por qué (volumen / retorno / papel en el journey) | Evidencia |
|---|---|---|---|---|
| Menú principal | `[URL]` | `[keyword]` | `[...]` | `evidencias/NN-....png` |
| Footer | `[URL]` | `[...]` | `[legal / peso medio]` | `evidencias/NN-....png` |

## 3. Enlazado desde el contenido

| Desde (página y zona) | Hacia | Anchor text | Motivo (contextual, no está en menú/footer) |
|---|---|---|---|
| Home (cuerpo) | `[URL]` | `[keyword]` | `[...]` |
| `[Otra página ya optimizada]` | `[URL]` | `[keyword]` | `[...]` |

## 4. Checklist QA

- [ ] Un servicio clave, una URL
- [ ] Todas las URLs en minúsculas, con guiones, sin ñ/acentos/símbolos y sin parámetros innecesarios
- [ ] Menú con pocas entradas, cada una justificada por negocio
- [ ] Footer con legales y URLs de peso medio
- [ ] Anchor text con keyword, ninguno genérico
- [ ] Ninguna URL enlazada devuelve 404/500 y no hay páginas huérfanas
- [ ] Cada decisión tiene captura o dato de respaldo (`SIN DATO` si no hay)

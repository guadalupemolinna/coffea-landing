# Coffea — Landing page

Landing page estática de una sola página para la cafetería ficticia **Coffea**, basada en el template de Figma *Coffea — Free Responsive Coffee Shop Website Template* (Figma Community). Proyecto de la cátedra **Diseño UX-UI 2026** (Licenciatura en Sistemas de Información).

- **Stack:** HTML5 semántico + CSS3 (custom properties, Flexbox, Grid, scroll-snap, `@layer`).
- **Sin:** JavaScript, frameworks, preprocesadores, bundlers ni CMS.
- **Deploy:** Netlify (sitio estático, deploy continuo desde `main`).

## Estructura

```
coffea-landing/
├── index.html
├── 404.html
├── favicon.svg
├── netlify.toml
├── README.md
├── css/
│   ├── main.css            # @import de las capas en orden
│   ├── tokens.css          # design tokens (custom properties)
│   ├── base.css            # reset, tipografía base, :focus-visible
│   ├── layout.css          # .container
│   ├── utilities.css       # .sr-only, .skip-link, prefers-reduced-motion
│   └── components/
│       ├── header.css
│       ├── hero.css
│       ├── categories.css
│       ├── product-card.css
│       ├── carousel.css
│       ├── promo.css
│       ├── testimonial-card.css
│       ├── newsletter.css
│       └── footer.css
└── assets/
    ├── img/                # AVIF + fallback JPG
    └── icons/              # SVG
```

## Convenciones

- **BEM:** `.product-card`, `.product-card__title`, `.product-card--featured`.
- **Tokens:** todo color, fuente, radio y espaciado sale de `css/tokens.css`.
- **Mobile-first:** estilos base para 360 px y `@media (min-width: …)` hacia arriba.
- **Capas:** `tokens → base → layout → components → utilities`, definidas por el orden de los `@import` en `main.css`.
- **Unidades:** `rem` para tipografía y espacios; `clamp()` para títulos fluidos.
- **Interacciones:** todo con CSS (hover, foco, carruseles con scroll-snap, menú con `<details>`, favoritos con checkbox).

### Breakpoints

| Nombre | Rango | Contenedor |
|---|---|---|
| base | 360–767 px | 100 % − 2 × 16 px |
| md | ≥ 768 px | 100 % − 2 × 32 px |
| lg | ≥ 1024 px | 100 % − 2 × 48 px |
| xl | ≥ 1440 px | 1444 px centrado |

## Cómo levantarlo en local

No hay build. Opciones:

1. Abrir la carpeta en VS Code e iniciar **Live Server** sobre `index.html` (`http://127.0.0.1:5500`).
2. O servir la carpeta con cualquier servidor estático, por ejemplo `npx serve .`

## Despliegue (Netlify)

1. Subir el repositorio a GitHub o GitLab.
2. En Netlify: **Add new site → Import an existing project** y elegir el repositorio.
3. **Build command:** vacío. **Publish directory:** `.`
4. La rama `main` publica a producción; cada Pull/Merge Request genera un Deploy Preview.
5. HTTPS y redirección HTTP → HTTPS los gestiona Netlify.

`netlify.toml` define el directorio de publicación, headers de seguridad y caché `immutable` para `css/` y `assets/`.
Como los archivos de `css/` y `assets/` se sirven con caché inmutable, **si se modifica un archivo hay que renombrarlo con versión** (por ejemplo `main.v2.css`) y actualizar la referencia.

### Newsletter

El formulario usa **Netlify Forms** (`data-netlify="true"` con honeypot). No requiere JavaScript ni backend; las suscripciones aparecen en el panel de Netlify, pestaña *Forms*.

## Decisiones y desvíos respecto del PRD

Estas decisiones deben validarse con diseño (Fase 3).

| Tema | Decisión |
|---|---|
| Flechas del carrusel | Decorativas (`aria-hidden`), visibles solo desde 1800 px, donde caben sin generar scroll horizontal. En pantallas menores el carrusel se desplaza con swipe/trackpad y scroll-snap. |
| Imágenes laterales del CTA (promo) | En tablet (≥ 768 px) la imagen izquierda sangra fuera del borde para no pisar el texto; ambas imágenes completas desde 1600 px. El PRD dice "imagen izquierda reducida" en md. |
| Imágenes laterales del newsletter | Visibles desde 1440 px (el PRD indica 1024 px) para evitar superposición con el formulario. |
| `@layer` y validador W3C | `main.css` usa `@import … layer()` (CSS Cascading Level 5), requerido por el PRD §6. El validador CSS del W3C todavía no soporta esa sintaxis y la reporta como error; el resto de los archivos valida sin errores. |
| Tamaño de la lupa | `--size-search-icon` es una estimación (30 px en el botón de 61 px); confirmar con el nodo 0:45 del Figma. |
| Copy | Se corrigieron los typos del Figma (Our, Our story, INFORMATION, Plans & pricing, products). Marca unificada como "Coffea". |
| Moneda y contenido | "Rs." y los textos de testimonios son placeholders del template. |
| Idioma | El contenido está en inglés (`lang="en"`), igual que el diseño. |

## Estado de la Definition of Done

- [x] 9 secciones implementadas
- [x] Sin JavaScript
- [ ] Aprobadas contra el Figma a 1920 px (±4 px)
- [ ] 0 errores en validadores HTML y CSS del W3C (ver excepción de `@layer`)
- [ ] Lighthouse ≥ 90 Performance y ≥ 95 Accessibility, Best Practices y SEO (medido sobre la URL de Netlify)
- [ ] Probado en Chrome, Firefox, Safari (macOS e iOS) y Samsung Internet
- [ ] Publicado en Netlify con deploy continuo desde `main`

### Resultados de Lighthouse (completar tras el deploy)

| Métrica | Resultado |
|---|---|
| Performance (mobile) | — |
| Accessibility | — |
| Best Practices | — |
| SEO | — |

## Licencias

Las fotos del template de Figma Community pueden provenir de bancos de imágenes (algunas se llaman `istockphoto-…`). **Confirmar la licencia o reemplazarlas por imágenes propias antes de publicar.**

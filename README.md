# Coffea — Landing page

Landing page estática de alta fidelidad para la cafetería **Coffea**, desarrollada a partir del diseño de Figma *Coffea — Free Responsive Coffee Shop Website Template* (Figma Community). Proyecto de la cátedra **Diseño UX-UI 2026** (Licenciatura en Sistemas de Información).

- **Stack:** HTML5 semántico + CSS3 (custom properties, Flexbox, Grid, scroll-snap, `@layer`).
- **Sin:** JavaScript, frameworks, preprocesadores, bundlers ni CMS.
- **Deploy:** Netlify (sitio estático, deploy continuo desde `main`).
- **Fidelidad:** QA visual calibrado al milímetro para resolución de referencia **1920 px de ancho** (desfasaje < 2 px respecto al diseño original de Figma).

---

## Estructura del Proyecto

```
coffea-landing/
├── index.html
├── 404.html
├── favicon.svg
├── netlify.toml
├── README.md
├── css/
│   ├── main.css            # @import de las capas en orden (@layer)
│   ├── tokens.css          # Design tokens (colores, fuentes, medidas, radios)
│   ├── base.css            # Reset, tipografía base, :focus-visible
│   ├── layout.css          # .container (1444 px centrado)
│   ├── utilities.css       # .sr-only, .skip-link, prefers-reduced-motion
│   └── components/
│       ├── header.css      # Header absoluto (55 px top, lupa 61 px)
│       ├── hero.css        # Hero 1000 px (texto en x: 238 px, y: 294 px)
│       ├── categories.css  # Franja 220 px, 4 ítems en 845 px, íconos 82 px
│       ├── carousel.css    # Carrusel (título a 64 px, flechas a 80 px de bordes)
│       ├── product-card.css# Cards 366x570 px, gap 4 px, fav a 18 px
│       ├── promo.css       # CTA 335 px, botón 258x51 px con doble chevron
│       ├── testimonial-card.css # Cards 441x235 px y 417x207 px, avatares 56 px
│       ├── newsletter.css  # Franja 320 px, input pill 364x44 px
│       └── footer.css      # Franja 358 px, separación vertical de 42 px
└── assets/
    ├── img/                # AVIF + fallback JPG + figma.png (overlay de QA)
    └── icons/              # SVG vectoriales
```

---

## Especificaciones Oficiales del PRD (1920 px)

| Sección | Medida / Propiedad | Especificación PRD y Tokens |
|---|---|---|
| **Header** | Posición y Contenedor | Absoluto sobre el hero a **55 px** del borde superior (`--header-top`), alineado al contenedor de **1444 px** (`--container`). |
| | Logo | Minúscula `coffea`, **32 px**, Playfair Display 700 (`--fs-logo`). |
| | Navegación | 6 links uppercase Poppins **18 px** (`--fs-md`), `login` en peso 600, los demás en 500. Gap de **40 px**. |
| | Buscador | Botón circular blanco de **61 px** (`--size-search`), ícono de lupa centrado. |
| **Hero** | Dimensiones | Alto estricto de **1000 px** (`--h-hero`), fondo `--color-espresso` con imagen cover a la derecha. |
| | Bloque de texto | Posicionado a **238 px** del borde izquierdo y **294 px** del superior (`--hero-content-top`). |
| | Tipografía | Eyebrow Outfit **20 px** (`--fs-lg`), H1 Playfair Display **72/82 px** (`--fs-hero`, `--lh-tight`), párrafo Outfit **18/26 px**. |
| | Botón CTA | "Order Now" con padding **16 × 40 px**, radio pill (`--radius-pill`), fondo blanco. |
| **Categorías** | Franja | Alto de **220 px** (`--h-categories`), fondo `--color-sand`. |
| | Grilla | 4 ítems centrados en **845 px** (`--w-categories`), íconos de **82 px** (`--size-icon-cat`), labels Poppins 18 px. |
| **Our Special Coffee / Dessert** | Título H2 | Playfair Display **32 px** (`--fs-h2`), separación estricta de **64 px** al carrusel (`--space-64`). |
| | Carrusel | 4 cards visibles de **366 × 570 px** (`--w-card`, `--h-card`), gap de **4 px** (`--space-4`). |
| | Flechas | Posicionadas exactamente a **80 px de cada borde** de la pantalla (`--space-80`). |
| | Product Card | Fondo `--color-sand-20`, borde 1.5 px `--color-sand`, radio 18 px, padding 16 px. |
| | Imagen y Favorito | Imagen de **334 × 364 px** (radio 12 px), corazón de **33 px** a **18 px** exactos de los bordes superior y derecho. |
| | Contenido de Card | Nombre Outfit **38 px**, descripción Outfit 20 px en `--color-maroon`, precio Poppins 20 px semibold, botón con radio 8 px y padding **10 × 26 px**. |
| **CTA Granos de Café** | Franja | Alto de **335 px** (`--h-promo`), fondo `--color-sand`. |
| | Contenido | Título Playfair Display **40/50 px** (`--fs-cta`, `--lh-cta`), botón pill `--color-espresso` de **258 × 51 px** (`--w-btn-cta`, `--h-btn-cta`) con doble chevron. |
| | Imágenes laterales | Altura completa de 335 px calzadas a los bordes. |
| **Testimonios** | Encabezado | Eyebrow Reggae One **32 px** (`--font-accent`) + Título Playfair Display **32 px** (`--font-display`). |
| | Cards | Fondo `--color-sand-40`, borde 2 px, padding 28 px. Central destacada: **441 × 235 px** (`--w-testimonial-featured`, `--h-testimonial-featured`); laterales: **417 × 207 px** (`--w-testimonial`, `--h-testimonial`). |
| | Avatar y Paginador | Avatar circular de **56 px** (`--size-avatar`), rating de estrellas a la derecha y paginador de 3 puntos. |
| **Newsletter** | Franja | Alto de **320 px** (`--h-newsletter`), fondo `--color-sand`. |
| | Formulario | Input pill de **364 × 44 px** (`--w-input`, `--size-touch`) con ícono de correo, botón "Subscribe" pill espresso de 44 px. |
| **Footer** | Franja | Alto de **358 px** (`--h-footer`), fondo `--color-espresso`. |
| | Columnas | Logo Playfair 32 px + 4 columnas con títulos de **24 px** (`--fs-footer-h`) y 3 links de **18 px** (`--fs-md`). |
| | Separación vertical | **42 px** (`--space-42`) entre títulos y listas de enlaces. |
| | Redes Sociales | Columna SOCIAL MEDIA con 4 íconos SVG de **24 px** (`1.5rem`). |

---

## Encastre Geométrico Vertical a 1920 px

```
[Y =    0 px] ── Header absoluto (Y = 55 px, alto 61 px)
[Y =    0 px] ── Hero (alto estricto: 1000 px)
[Y = 1000 px] ── Categorías (alto estricto: 220 px)
[Y = 1220 px] ── Our Special Coffee (padding + H2 32 px + gap 64 px + track 570 px + padding)
[Y = 1998 px] ── Our Special Dessert (padding + H2 32 px + gap 64 px + track 570 px + padding)
[Y = 2776 px] ── CTA Granos de Café / Promo (alto estricto: 335 px)
[Y = 3111 px] ── Testimonios (encabezado + cards 235/207 px + pager)
[Y = ~3580 px] ─ Newsletter (alto estricto: 320 px)
[Y = ~3900 px] ─ Footer (alto estricto: 358 px)
```

---

## Convenciones de Desarrollo

- **BEM:** `.product-card`, `.product-card__title`, `.product-card--featured`.
- **Tokens:** Todos los valores de color, fuente, radio, espaciado y dimensiones salen de `css/tokens.css`.
- **Mobile-first:** Estilos base optimizados para 360 px con mejoras progresivas mediante `@media (min-width: …)`.
- **Capas CSS:** `tokens → base → layout → components → utilities` gestionadas mediante `@layer`.
- **Unidades:** `rem` para tipografía y cotas escalables; `clamp()` para textos fluidos.
- **Interacciones 100 % CSS:** Hover, estados de foco `:focus-visible`, scroll-snap en carruseles, menú mobile con `<details>/<summary>`, selección de favoritos mediante checkboxes accesibles.

### Breakpoints

| Nombre | Rango | Contenedor |
|---|---|---|
| **base** | 360–767 px | 100 % − 2 × 16 px |
| **md** | ≥ 768 px | 100 % − 2 × 32 px |
| **lg** | ≥ 1024 px | 100 % − 2 × 48 px |
| **xl** | ≥ 1440 px | 1444 px centrado |

---

## Cómo levantarlo en local

El proyecto no requiere ningún proceso de compilación ni empaquetado:

1. Abrir la carpeta en VS Code e iniciar **Live Server** sobre `index.html` (`http://127.0.0.1:5500`).
2. O bien servir mediante cualquier servidor estático local, por ejemplo:
   ```sh
   npx serve .
   ```

---

## Despliegue (Netlify)

1. Conectar el repositorio a Netlify.
2. **Build command:** vacío.
3. **Publish directory:** `.`
4. Cada push a `main` despliega automáticamente a producción.
5. Los formularios del newsletter se procesan con **Netlify Forms** (`data-netlify="true"` con honeypot para protección antispam).

---

## Decisiones y Desvíos Documentados

| Tema | Decisión y Justificación |
|---|---|
| **Flechas del carrusel** | Decorativas (`aria-hidden`), visibles desde 1800 px para evitar desbordes y posicionadas a **80 px de cada borde** de la pantalla según PRD. En pantallas menores se utiliza desplazamiento táctil / trackpad con scroll-snap. |
| **Imágenes laterales del CTA** | En tablet sangran fuera del viewport para priorizar la legibilidad del texto; a pantalla completa (≥ 1600 px) se muestran íntegras encastradas a 335 px. |
| **Imágenes del newsletter** | Visibles desde 1024 px/1440 px para mantener despejado el campo de suscripción. |
| **Tipografía y typos** | Se corrigieron los typos originales del mockup de Figma (ej. "INFOTNATION" → "INFORMATION", "ger 15% off" → "get 15% off", marcas unificadas a "Coffea"). |
| **Moneda** | Estandarizada a USD en el HTML para mantener consistencia con el idioma inglés (`lang="en"`). |

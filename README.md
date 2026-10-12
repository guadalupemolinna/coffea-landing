# Coffea — Landing Page

Landing page estática de alta fidelidad para la cafetería **Coffea**, desarrollada a partir del diseño de Figma *Coffea — Free Responsive Coffee Shop Website Template* (Figma Community). Proyecto correspondiente a la cátedra **Diseño UX-UI 2026** (Licenciatura en Sistemas de Información – FCyT UADER).

- **Stack:** HTML5 semántico + CSS3 (custom properties, Flexbox, Grid, scroll-snap, `@layer`).
- **Sin:** JavaScript, frameworks, preprocesadores, bundlers ni CMS.
- **Deploy:** Netlify (sitio estático, deploy continuo desde la rama `main`).
- **Fidelidad:** QA visual calibrado al milímetro para resolución de referencia **1920 px de ancho** (desfasaje < 2 px respecto al diseño original de Figma).

---

## 📱 Métricas de Lighthouse (Mobile)

Evaluación oficial ejecutada en entorno móvil cumpliendo y superando con creces los umbrales de aceptación exigidos por el PRD:

| Métrica (Mobile) | Puntaje | Umbral PRD | Estado |
|---|---|---|---|
| **Performance** | **97** | ≥ 90 | ✅ Superado |
| **Accessibility** | **100** | ≥ 95 | ✅ Superado |
| **Best Practices** | **100** | ≥ 95 | ✅ Superado |
| **SEO** | **100** | ≥ 95 | ✅ Superado |

---

## 🔍 Validaciones W3C

| Validador Oficial | Estado | Resultado |
|---|---|---|
| **W3C HTML Validator** | ✅ Aprobado | 0 errores / 0 advertencias |
| **W3C CSS Validator** | ✅ Aprobado | 0 errores (Cumplimiento estricto de Design Tokens y capas `@layer`) |

---

## 🗂️ Estructura del Proyecto

```text
coffea-landing/
├── index.html
├── 404.html
├── favicon.svg
├── netlify.toml
├── README.md
├── css/
│   ├── main.css                # @import de las capas en orden (@layer)
│   ├── tokens.css              # Design tokens centralizados (colores, fuentes, medidas, radios)
│   ├── base.css                # Reset moderno, tipografía base, :focus-visible
│   ├── layout.css              # .container (1444 px centrado)
│   └── components/
│       ├── header.css          # Header absoluto (55 px top, lupa 61 px)
│       ├── hero.css            # Hero 1000 px (texto en x: 238 px, y: 294 px)
│       ├── categories.css      # Franja 220 px, 4 ítems en 845 px, íconos 82 px
│       ├── carousel.css        # Carrusel (título a 64 px, flechas a 80 px de bordes)
│       ├── product-card.css    # Cards 366x570 px, gap 4 px, fav a 18 px
│       ├── promo.css           # CTA 335 px, botón 258x51 px con doble chevron
│       ├── testimonial-card.css # Cards 441x235 px y 417x207 px, avatares 56 px
│       ├── newsletter.css      # Franja 320 px, input pill 364x44 px
│       └── footer.css          # Franja 358 px, separación vertical de 42 px
└── assets/
    ├── img/                    # AVIF + fallback JPG + figma.png (overlay de QA)
    └── icons/                  # SVG vectoriales
```

---

## 📏 Especificaciones Oficiales del PRD (1920 px)

| Sección | Medida / Propiedad | Especificación PRD y Tokens |
|---|---|---|
| **Header** | Posición y Contenedor | Absoluto sobre el hero a **55 px** del borde superior (`--header-top`), alineado al contenedor de **1444 px** (`--container`). |
| | Logo | Minúscula `coffea`, **32 px**, Playfair Display 700 (`--fs-logo`). |
| | Navegación | 6 links uppercase Poppins **18 px** (`--fs-md`), `login` en peso 600, los demás en 500. Gap de **40 px**. |
| | Buscador | Botón circular blanco de **61 px** (`--size-search`), ícono de lupa centrado. |
| **Hero** | Dimensiones | Alto estricto de **1000 px** (`--h-hero`), fondo `--color-espresso` con imagen cover a la derecha. |
| | Bloque de texto | Posicionado a **238 px** del borde izquierdo (`--hero-offset-left`) y **294 px** del superior (`--hero-content-top`). |
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

## 📐 Encastre Geométrico Vertical a 1920 px

```text
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

## ⚙️ Convenciones de Desarrollo

- **BEM:** Clases estructuradas bajo metodología BEM (ej. `.product-card`, `.product-card__title`, `.product-card--featured`).
- **Tokens:** Cero valores sueltos; todos los colores, tipografías, radios, espaciados y dimensiones se vinculan de forma estricta a `css/tokens.css`.
- **Mobile-first:** Estilos base optimizados para 360 px con evolución progresiva mediante `@media (min-width: …)`.
- **Capas CSS:** Control de cascada organizado en capas mediante `@layer tokens, base, layout, components, utilities`.
- **Unidades:** Empleo de `rem` para tipografías y contenedores escalables.
- **Interacciones 100 % CSS:** Sin uso de JavaScript. Hover dinámico, estados de foco accesibles (`:focus-visible`), scroll-snap nativo en carruseles, menú desplegable mobile con `<details>/<summary>`, y selección de favoritos mediante checkboxes con pseudo-clases `:checked`.

### Breakpoints Definidos

| Nombre | Rango | Contenedor |
|---|---|---|
| **base** | 360–767 px | 100 % − 2 × 16 px |
| **md** | ≥ 768 px | 100 % − 2 × 32 px |
| **lg** | ≥ 1024 px | 100 % − 2 × 48 px |
| **xl** | ≥ 1440 px | 1444 px centrado |

---

## 💻 Cómo Levantar el Proyecto en Local

El sitio es estático puro y no requiere procesos de empaquetado (build) ni dependencias de Node.js:

1. Clonar o descargar el repositorio.
2. Abrir la carpeta raíz en VS Code.
3. Iniciar la extensión **Live Server** sobre el archivo `index.html` (por defecto en `http://127.0.0.1:5500`).
4. Alternativamente, servir mediante cualquier servidor local ligero:

   ```sh
   npx serve .
   ```

---

## 🚀 Despliegue en Producción (Netlify)

1. Conectar el repositorio de GitHub con un sitio nuevo en Netlify.
2. **Build command:** (dejar vacío).
3. **Publish directory:** `.` (raíz del proyecto).

El despliegue continuo se encuentra activo; cada `git push` a la rama `main` actualiza el entorno de producción de forma automática.

---

## 📝 Decisiones de Diseño y Licencias

| Tema | Decisión y Justificación |
|---|---|
| Flechas del carrusel | Marcadas como decorativas (`aria-hidden`), visibles a partir de resoluciones amplias y posicionadas estrictamente a 80 px de cada borde de la pantalla según PRD. En pantallas intermedias se prioriza el desplazamiento táctil / trackpad mediante `scroll-snap`. |
| Imágenes laterales del CTA | En dispositivos tablet se desplazan fuera del viewport para priorizar la lectura del copy; a pantalla completa (≥ 1440 px) se visualizan íntegras encastradas a 335 px. |
| Tipografía y corrección de typos | Se corrigieron los errores tipográficos presentes en el mockup original de Figma (ej. "INFOTNATION" → "INFORMATION", "ger 15% off" → "get 15% off", unificando además la marca a "Coffea"). |
| Moneda | Estandarizada a USD en los componentes para mantener coherencia internacional con el idioma base (`lang="en"`). |
| Licencias de recursos | Las imágenes e ilustraciones fotográficas utilizadas fueron obtenidas de Unsplash bajo licencias libres para uso académico y comercial. |

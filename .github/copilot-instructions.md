# Instrucciones del proyecto — Dashboard con Tailwind CSS

## Stack tecnológico (ÚNICAMENTE esto)

Este proyecto usa **exclusivamente**:

- ✅ **HTML5**
- ✅ **Tailwind CSS v4** (vía CDN: `https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4`)

## Prohibiciones — NO usar

| Tecnología | Motivo |
|---|---|
| ❌ JavaScript / TypeScript | Sin lógica de programación |
| ❌ React, Vue, Angular, Svelte, etc. | Sin frameworks frontend |
| ❌ Node.js, npm, yarn, pnpm | Sin runtime ni gestores de paquetes |
| ❌ Webpack, Vite, Parcel, Gulp | Sin build tools |
| ❌ CSS plano o archivos `.css` externos | Todo el estilo va con Tailwind utility classes |
| ❌ Preprocesadores CSS (Sass, Less, PostCSS) | No aplica |
| ❌ `cdn.tailwindcss.com` | Esa CDN es de Tailwind v3, no usar |
| ❌ Snippets de Tailwind v3 (`@apply`, `@tailwind`, `@layer`, `theme()`, `@config`, `@screen`) | Sintaxis obsoleta |
| ❌ Cualquier otra tecnología, librería o dependencia | Solo HTML + Tailwind CSS v4 |

## Diseño responsive — Mobile First

- **Mobile First**: el diseño base es para móvil (< 640px). Los breakpoints `sm:`, `md:`, `lg:`, `xl:` se usan SOLO para mejorar la experiencia en pantallas más grandes.
- **KPIs en móvil**: usar `snap-x snap-mandatory overflow-x-auto` para scroll horizontal con snapping. En `sm:` cambiar a grid.
- **Tablas**: envolver en `overflow-x-auto` con `-mx-4` para que el scroll ocupe todo el ancho en móvil. Usar `min-w-full` en la tabla.
- **Tipografía responsive**: usar `text-[10px] sm:text-xs`, `text-xs sm:text-sm`, `text-sm sm:text-base` según el contexto.
- **Padding/spacing**: usar `p-3 sm:p-4`, `gap-3 sm:gap-4`, `py-4 sm:py-6` para escalar suavemente.
- **Grids**: `grid-cols-1` (base) → `sm:grid-cols-2` → `lg:grid-cols-3` → `xl:grid-cols-7`.
- **Ocultar/mostrar**: usar `hidden sm:flex`, `sr-only sm:not-sr-only`, `sm:hidden` para controlar visibilidad según viewport.

## Accesibilidad (WCAG) — Obligatorio

Toda la maquetación debe cumplir con estos requisitos de accesibilidad:

- **Skip link**: enlace "Saltar al contenido principal" al inicio del `<body>`, visible solo al recibir foco (`sr-only focus:not-sr-only`).
- **Landmarks HTML5 semánticos**: `<header role="banner">`, `<main id="contenido-principal" role="main">`, `<footer role="contentinfo">`, `<section aria-labelledby="...">`, `<article>`, `<nav>`.
- **Encabezados jerárquicos**: `h1` → `h2` → `h3` → `h4` en orden. Cada sección con un `h2` y un `id` referenciado desde `aria-labelledby`.
- **Roles ARIA**: `role="alert"` en alertas, `role="img"` en barras de progreso, `role="table"` en tablas, `role="list"` y `role="listitem"` en listas semánticas.
- **Atributos `aria-label`**: en todos los elementos interactivos o informativos que no tengan texto visible suficiente (ej: avatar, tarjetas KPI, tablas).
- **Atributos `aria-hidden="true"`**: en todos los iconos/emojis decorativos para que no se lean con screen reader.
- **`scope` en tablas**: `scope="col"` en cada `<th>`.
- **Contraste de color**: cumplir WCAG AA. Textos grises claros solo para secundarios. Usar `text-green-700` y `text-red-700` en lugar de `text-green-600`/`text-red-500` si es necesario para contraste.
- **Foco visible**: `focus:outline-none focus:ring-2 focus:ring-blue-400` en elementos interactivos. `focus-within:bg-gray-50` en filas de tabla.
- **Texto alternativo**: `aria-label` descriptivo en barras de progreso para que el screen reader interprete el valor.
- **Zoom**: todo debe funcionar hasta 200% de zoom sin perder contenido. Usar unidades relativas.
- **Modo de alto contraste**: no usar solo color para transmitir información (ej: iconos + texto + color).
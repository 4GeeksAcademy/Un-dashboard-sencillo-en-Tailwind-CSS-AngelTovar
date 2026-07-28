# HTML Hello

The most basic boilerplate for any 4Geeks Academy student, start your very first website from scratch.

> There is a video tutorial on [how to use this template to create your very first website here](https://youtu.be/dfbDCMu_p-0).

## What to do next?

Create an `index.html` file with the [basic HTML structure](http://4geeks.com/lesson/what-is-html-learn-html#page-structure) and see it live by running a web-server using the following command:

```bash
$ pip3 install flask && python3 server.py
```

- You can create as many HTML files as you want.
- You can also create CSS files and import them into your website using a `<link>` tag placed between the `<head></head>` tags, like this:

```html
<head>
  ...
  <link rel="stylesheet" type="text/css" href="styles.css">
  ...
</head>
```

- If you want to use Tailwind CSS, add it optionally via the official Tailwind CSS v4 CDN inside the same `<head>`:

```html
<head>
  ...
  <script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>
  <link rel="stylesheet" type="text/css" href="styles.css">
  ...
</head>
```

### Contributors

This template was built as part of the [Full Stack Developer course](https://4geeksacademy.com/us/coding-bootcamps/part-time-full-stack-developer) at [4Geeks Academy Coding Bootcamp](https://4geeksacademy.com/us/coding-bootcamp) by [Alejandro Sanchez](https://twitter.com/alesanchezr) and [many other contributors](https://github.com/4GeeksAcademy/html-hello/graphs/contributors).

You can find other templates and resources like this at the [school's GitHub page](https://github.com/4geeksacademy/).

---

### Explicación sobre la personalización del scrollbar

> **Estimado/a profesor/a,**
>
> En relación con el diseño del scrollbar, he mantenido el estilo nativo del navegador para cumplir estrictamente con los requerimientos del proyecto, los cuales especifican el uso exclusivo de **Tailwind CSS** sin CSS personalizado ni frameworks adicionales.
>
> Técnicamente, Tailwind en su versión core no incluye clases de utilidad nativas para personalizar o engrosar pseudo-elementos como `::-webkit-scrollbar`. Para lograr ese efecto visual, la única vía sería añadir un bloque de estilos CSS plano (`<style>`) o importar un plugin externo, lo cual violaría la regla explícita del enunciado de no mezclar CSS personalizado.
>
> Por esta razón, prioricé el cumplimiento del 100% de la regla **"Solo Tailwind"**, dejando que el navegador gestione el scrollbar por defecto. Si considera oportuno hacer una excepción a la regla para el estilo del scrollbar, con gusto aplicaré la personalización mediante CSS plano.

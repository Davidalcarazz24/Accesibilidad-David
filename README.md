# README / Accesibilidad WCAG 2.2 (Promt-David)

## ES Español

### Proceso de desarrollo del prompt
- Partí del archivo `indexsinaccesibilidad` como referencia y decidí no tocarlo.
- Definí en el prompt una lista clara de tareas: semántica HTML5, ARIA solo cuando aporta, formularios con `label`, navegación por teclado, foco visible, contraste y textos alternativos.
- Añadí restricciones para que el asistente generara una carpeta nueva (`Promt-David`) con `index.html`, `css/styles.css` y `js/app.js`, manteniendo el contenido original pero rehaciendo la estructura accesible.

### Pasos para validar la accesibilidad
1. Pasé el HTML por **WAVE** y corregí errores de estructura, etiquetas y alternativas de imagen.
2. Revisé con **axe DevTools** para detectar problemas de ARIA, formularios y navegación.
3. Ejecuté **Lighthouse** (Accesibilidad) y repetí ajustes hasta no tener fallos relevantes.
4. Hice una comprobación manual con teclado: Tab/Shift+Tab, Enter y foco visible.

### Problemas encontrados y soluciones aplicadas
- **Faltaban `label` en inputs:** añadí `label` + `id/for` y `aria-describedby` para ayudas/errores.
- **Encabezados desordenados:** reorganicé a un único `h1` y jerarquía correcta (`h2`, `h3`).
- **Imágenes sin `alt` útil:** escribí `alt` descriptivos y dejé `alt=""` en decorativas.
- **Foco poco visible o perdido:** añadí estilos `:focus-visible` y ajustes para que no quede oculto.
- **Bajo contraste en algunos textos:** ajusté CSS con cambios mínimos para mejorar la lectura.

### Capturas de validación (enlace)
- Carpeta/URL con capturas: **[PEGAR AQUÍ EL ENLACE A TU DRIVE/ONE DRIVE/GITHUB]**
- Incluí capturas de: WAVE, axe DevTools y Lighthouse.

---

## EN English

### Prompt development process
- I used `indexsinaccesibilidad` as the base reference and kept it untouched.
- In the prompt I listed clear tasks: HTML5 semantics, ARIA only when needed, forms with `label`, keyboard navigation, visible focus, contrast, and descriptive alt text.
- I added rules so the assistant generated a new folder (`Promt-David`) with `index.html`, `css/styles.css`, and `js/app.js`, reusing the original content but rebuilding it with accessibility fixes.

### Accessibility validation steps
1. I checked the HTML with **WAVE** and fixed structure, labels, and image alternatives.
2. I used **axe DevTools** to catch ARIA, form, and keyboard-related issues.
3. I ran **Lighthouse** (Accessibility) and iterated until the main issues were gone.
4. I did a manual keyboard test: Tab/Shift+Tab, Enter, and visible focus.

### Issues found and applied solutions
- **Missing input labels:** I added `label` + `id/for` and `aria-describedby` for help/errors.
- **Heading hierarchy problems:** I kept one `h1` and fixed the order (`h2`, `h3`).
- **Non-descriptive/missing `alt`:** I wrote descriptive `alt` text and used `alt=""` for decorative images.
- **Weak or lost focus:** I added `:focus-visible` styles and made sure focus is not hidden.
- **Low contrast text:** I adjusted CSS with minimal changes to improve readability.

### Validation screenshots link
- Folder/URL with screenshots: **[PASTE YOUR DRIVE/ONE DRIVE/GITHUB LINK HERE]**
- It contains screenshots from: WAVE, axe DevTools, and Lighthouse.

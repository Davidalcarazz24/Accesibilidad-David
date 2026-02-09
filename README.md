

## ES Español

### Qué incluye este README
- El **prompt completo** usado para generar la versión accesible.
- Los **asistentes** usados: ChatGPT y Codex.
- Las **herramientas de validación** usadas y el proceso seguido.
- El enlace a las **capturas** de las validaciones.

### Proceso de desarrollo del prompt
- Partí del archivo `indexsinaccesibilidad` como base y dejé claro que **no se puede modificar**.
- Pedí crear una carpeta nueva llamada `Promt-David` con `index.html`, `css/styles.css` y `js/app.js`, reutilizando la información del original pero rehaciendo la versión accesible.
- Añadí requisitos concretos: semántica HTML5, jerarquía de encabezados, labels en formularios, ARIA solo cuando aporta, teclado/foco visible, contraste y `alt` descriptivos.
- Ajusté el prompt para que el código incluya comentarios en tercera persona, estilo estudiante, sin emojis y sin mencionar IA.

### Asistentes usados
- **ChatGPT**: para diseñar y ajustar el prompt.
- **Codex**: para aplicar el prompt al proyecto y generar los archivos finales.

### Pasos seguidos para validar la accesibilidad
1. **WAVE (WebAIM)**: revisión de estructura, formularios, `alt` y encabezados.
2. **axe DevTools (Deque)**: detección de fallos de ARIA, teclado y elementos interactivos.
3. **Lighthouse (Chrome DevTools)**: comprobación de accesibilidad y repetición de ajustes.
4. Revisión manual: navegación con Tab/Shift+Tab y foco visible.

### Problemas encontrados y soluciones aplicadas
- Faltaban `label` y asociaciones `for/id`: se añadieron y se usó `aria-describedby` en ayudas/errores.
- Encabezados mal ordenados: se dejó un solo `h1` y se reordenó el resto.
- Imágenes sin `alt` útil: se añadieron `alt` descriptivos y `alt=""` en decorativas.
- Foco poco visible: se reforzó `:focus-visible` y se evitó que el foco quede oculto.
- Contraste mejorable: se ajustó CSS con cambios mínimos.

### Enlace a capturas de validación
- WAVE + axe DevTools + Lighthouse (capturas): **[PEGAR AQUÍ EL ENLACE]**

### Explicación del proceso de trabajo y resultados obtenidos
Se usó `indexsinaccesibilidad` como referencia sin modificarlo y se creó un proyecto nuevo en `Promt-David` con `index.html`, `styles.css` y `app.js`. Luego se corrigió la estructura semántica, se revisó la jerarquía de encabezados, se mejoraron formularios e imágenes y se comprobó teclado, foco y legibilidad. El resultado es una versión más coherente en accesibilidad y con mejores resultados en las herramientas de validación.




## PROMPT COMPLETO (Copilot/IDE)

> Actúa como auditor y refactor de accesibilidad web. Debes actualizar el proyecto para cumplir **WCAG 2.2** en niveles **A, AA y AAA**, sin romper diseño ni funcionalidad.
>
> **Entrada:** existe un archivo base llamado `indexsinaccesibilidad` (HTML original). **No debe modificarse ni sobrescribirse.** Se debe **leer su contenido y reutilizar su información** (textos, estructura lógica, secciones, recursos) para crear una versión nueva accesible.
>
> **Salida:**  
> 1) Crea (o propone y genera) una **carpeta de proyecto** en el ordenador donde corresponda con el nombre: `Promt-David` (o dentro del workspace actual).  
> 2) Dentro, crea un proyecto nuevo completo **a partir de `indexsinaccesibilidad`**, generando los archivos necesarios y devolviendo su contenido completo:  
>    - `index.html` (versión accesible nueva, basada en el contenido de `indexsinaccesibilidad`)  
>    - `css/styles.css`  
>    - `js/app.js`  
>    - Si hacen falta más apartados/archivos (por ejemplo `components/`, `assets/`, `pages/`), créalos y justifica brevemente por qué.  
> 3) Restricción clave: **no tocar `indexsinaccesibilidad`**. La refactorización debe estar **solo** en los nuevos archivos dentro de `Promt-David`.  
> 4) Si el IDE no puede crear carpetas/archivos automáticamente, entonces:  
>    - Devuelve un **árbol de carpetas** y luego el contenido de cada archivo con separadores claros (`--- index.html ---`, etc.) para copiar y pegar sin perder nada.
>
> -------------------------------------------------------------------
> ## Requisitos obligatorios (HTML/CSS/JS) para WCAG 2.2
> 1) **Estructura y semántica (HTML5):** usar correctamente `<header> <nav> <main> <section> <article> <footer>` y landmarks; añadir “skip link” al contenido principal (`href="#main"`).  
> 2) **Jerarquía de encabezados:** corregir el orden de `<h1>…<h6>` sin saltos; dejar **un solo `<h1>`** para el título principal.  
> 3) **Formularios accesibles:**  
>    - `label` asociado a cada control (`for`/`id`).  
>    - `aria-required="true"` cuando aplique.  
>    - Errores accesibles con `aria-describedby` y región con `role="alert"` o `aria-live="polite"`.  
>    - `autocomplete` cuando aplique, y `fieldset/legend` para grupos de radio/checkbox.  
> 4) **Botones y enlaces:**  
>    - No usar `div/span` como botón/enlace; reemplazar por `<button>`/`<a>`.  
>    - Iconos sin texto: `aria-label` o texto visible; decorativos: `aria-hidden="true"`.  
> 5) **Imágenes:**  
>    - `alt` descriptivo en todas; decorativas: `alt=""` (y opcional `role="presentation"`).  
> 6) **ARIA (solo cuando aporte valor):**  
>    - En componentes interactivos personalizados (menús, modales, acordeones, tabs): aplicar patrones correctos (`role`, `aria-expanded`, `aria-controls`, `aria-selected`) y gestión de foco.  
>    - Evitar ARIA redundante en elementos semánticos nativos.  
> 7) **Teclado y foco (WCAG 2.2):**  
>    - Navegación completa por teclado, orden lógico de tabulación y sin trampas de foco.  
>    - Foco **muy visible** (`:focus-visible`) y que no quede oculto por cabeceras sticky (usar `scroll-margin-top`).  
>    - Si existe drag & drop, incluir alternativa sin arrastrar (botones/inputs).  
>    - Objetivos clic/tacto con tamaño mínimo cuando sea posible (CSS mínimo).  
> 8) **Contraste y legibilidad:**  
>    - Detectar y corregir contrastes insuficientes con cambios mínimos.  
>    - No usar solo color para comunicar estados; añadir texto/ayudas/indicadores.  
> 9) **Preferencias del usuario:**  
>    - Respetar `prefers-reduced-motion` si hay animaciones (CSS mínimo).  
> 10) **Robustez:**  
>    - Asegurar `lang` en `<html>`, `<title>` descriptivo, `id` únicos, y enlaces/inputs sin ambigüedad.
>
> -------------------------------------------------------------------
> ## Comentarios obligatorios (muy importante)
> - Añadir **comentarios** en HTML/CSS/JS explicando los cambios.  
> - Comentarios en **tercera persona**, tono **natural de estudiante** (claros, directos).  
> - Prohibido:
>   - Referirse al usuario (“tú”, “tu web”, “tu código”, nombres propios, etc.).  
>   - Mencionar IA, modelos, asistentes (ChatGPT, Copilot, etc.).  
>   - Usar emojis.  
> - Ejemplos válidos:
>   - `<!-- Se añade un enlace de salto para llegar al contenido principal con teclado. -->`
>   - `/* Se sube el contraste del texto para mejorar la lectura. */`
>   - `// Se controla el foco del modal para que no se pierda al navegar con Tab.`
>
> -------------------------------------------------------------------
> ## Validación obligatoria (documentar 3 herramientas + iteraciones)
> - Tras refactorizar, incluir un bloque final “**Proceso de validación**” con:  
>   1) **WAVE (WebAIM)**: resultados y cambios aplicados.  
>   2) **axe DevTools (Deque)**: resultados y cambios aplicados.  
>   3) **Lighthouse (Chrome DevTools)** o **Nu HTML Checker**: resultados y cambios aplicados.  
> - Iterar hasta que no queden errores críticos automáticos y dejar anotado lo comprobado manualmente (teclado/foco/alt/labels).
>
> Empieza ahora: lee `indexsinaccesibilidad`, crea la carpeta `Promt-David` con todos los archivos nuevos, refactoriza el contenido para hacerlo accesible y entrégame el contenido completo de cada archivo.

---

## EN English

### What this README includes
- The **full prompt** used to generate the accessible version.
- The **assistants** used: ChatGPT and Codex.
- The **validation tools** used and the steps followed.
- The link to **validation screenshots**.

### Prompt development process
- I used `indexsinaccesibilidad` as the base and made it clear it **must not be edited**.
- I required a new folder named `Promt-David` with `index.html`, `css/styles.css`, and `js/app.js`, reusing original content but rebuilding it for accessibility.
- I added specific rules: HTML5 semantics, heading hierarchy, form labels, ARIA only when needed, keyboard/focus visibility, contrast, and descriptive `alt`.
- I adjusted it so the code includes third-person student-style comments, no emojis, and no AI mentions.

### Assistants used
- **ChatGPT**: to design and refine the prompt.
- **Codex**: to apply the prompt and generate the final files.

### Accessibility validation steps
1. **WAVE (WebAIM)**: structure, forms, `alt`, headings.
2. **axe DevTools (Deque)**: ARIA, keyboard, interactive issues.
3. **Lighthouse (Chrome DevTools)**: accessibility audit and iterations.
4. Manual check: Tab/Shift+Tab navigation and visible focus.

### Issues found and fixes applied
- Missing `label` and `for/id`: added them and used `aria-describedby` for help/errors.
- Incorrect heading order: kept one `h1` and fixed the hierarchy.
- Images without meaningful `alt`: added descriptive `alt` and `alt=""` for decorative images.
- Weak focus visibility: improved `:focus-visible` and prevented hidden focus.
- Low contrast areas: updated CSS with minimal changes.

### Validation screenshots link
- WAVE + axe DevTools + Lighthouse screenshots: **[PASTE LINK HERE]**

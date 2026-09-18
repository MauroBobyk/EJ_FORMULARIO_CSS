# Documentación del Formulario de Registro

A continuación se explica cada una de las etiquetas HTML y atributos utilizados en el formulario.

---

## Etiquetas HTML

- **`<!DOCTYPE html>`**: Declaración que le indica al navegador que el documento es HTML5. Debe ser la primera línea del archivo.

- **`<html lang="es">`**: Etiqueta raíz que envuelve todo el contenido de la página. El atributo `lang="es"` especifica que el idioma del contenido es español.

- **`<head>`**: Contiene metadatos e información sobre el documento que no se muestra directamente en la página (título, codificación, configuración de viewport, etc.).

- **`<meta charset="UTF-8">`**: Define la codificación de caracteres como UTF-8, lo que permite usar caracteres especiales como tildes y eñes.

- **`<meta name="viewport" content="width=device-width, initial-scale=1.0">`**: Configura la escala y el ancho de la página para que se vea correctamente en dispositivos móviles.

- **`<title>`**: Define el título de la página que aparece en la pestaña del navegador.

- **`<body>`**: Contiene todo el contenido visible de la página web.

- **`<div>`**: Contenedor genérico de bloque. Se usa para agrupar y organizar elementos.

- **`<h1>`**: Encabezado de nivel 1, el más importante. Se utiliza para el título principal de la página.

- **`<p>`**: Párrafo. Representa un bloque de texto.

- **`<form>`**: Define un formulario HTML para enviar datos al servidor.

- **`<!-- ... -->`**: Comentario HTML. No se muestra en el navegador, sirve para documentar el código.

- **`<fieldset>`**: Agrupa elementos relacionados dentro de un formulario, dibujando un borde alrededor de ellos.

- **`<legend>`**: Define un título o descripción para el contenido de un `<fieldset>`.

- **`<label>`**: Etiqueta de texto asociada a un control de formulario. Al hacer clic en el `label`, el control asociado recibe el foco.

- **`<input>`**: Campo de entrada de datos. Es una etiqueta auto-cerrada (no necesita etiqueta de cierre).

- **`<select>`**: Crea una lista desplegable de opciones para que el usuario elija una.

- **`<option>`**: Define cada una de las opciones dentro de un elemento `<select>`.

- **`<textarea>`**: Campo de texto multilínea para que el usuario escriba texto extenso.

- **`<a>`**: Ancla o enlace. Permite navegar a otra página o sección.

- **`<button>`**: Botón clickeable que puede ejecutar acciones dentro del formulario.

---

## Atributos

### Atributos del `<form>`

- **`action="#"`**: Especifica la URL a la que se enviarán los datos del formulario. El valor `"#"` indica que los datos se envían a la misma página.

- **`method="POST"`**: Define el método HTTP para enviar los datos. `POST` envía los datos en el cuerpo de la petición (más seguro y sin límite de tamaño), a diferencia de `GET` que los envía en la URL.

- **`id="registroForm"`**: Identificador único del formulario. Permite referenciarlo desde JavaScript o asociar elementos con CSS.

### Atributos del `<input>`

- **`type`**: Define el tipo de campo de entrada. Los valores usados son:
  - **`type="text"`**: Campo de texto de una sola línea.
  - **`type="email"`**: Campo para direcciones de correo electrónico. El navegador valida automáticamente el formato.
  - **`type="tel"`**: Campo para números de teléfono. En móviles muestra un teclado numérico.
  - **`type="date"`**: Campo selector de fecha. Despliega un calendario nativo del navegador.
  - **`type="password"`**: Campo de contraseña. Oculta los caracteres ingresados con puntos o asteriscos.
  - **`type="radio"`**: Botón de opción única. Solo se puede seleccionar una opción dentro del mismo grupo.
  - **`type="checkbox"`**: Casilla de verificación. Permite seleccionar múltiples opciones independientes.

- **`id`**: Identificador único del elemento. Se usa para vincular un `<label>` con su `<input>` mediante el atributo `for`.

- **`name`**: Nombre del campo. Es el identificador que se envía al servidor junto con el valor ingresado por el usuario.

- **`value`**: Valor predefinido o valor que se envía al servidor cuando el campo está seleccionado/marcado.

- **`placeholder`**: Texto de sugerencia que se muestra dentro del campo cuando está vacío. Desaparece al empezar a escribir.

- **`required`**: Atributo booleano que indica que el campo es obligatorio. El formulario no se enviará si está vacío.

- **`minlength="8"`**: Establece la cantidad mínima de caracteres que el usuario debe ingresar (en este caso, 8 para la contraseña).

- **`checked`**: Atributo booleano que hace que un `radio` o `checkbox` aparezca seleccionado por defecto.

- **`rows="4"`**: Define la cantidad de líneas visibles en un `<textarea>`.

### Atributos del `<label>`

- **`for`**: Asocia el `label` con el `id` de un elemento de formulario. Al hacer clic en el texto del label, el campo asociado recibe el foco.

### Atributos del `<button>`

- **`type="submit"`**: Botón que envía el formulario al servidor. Equivale a hacer clic en "Enviar".

- **`type="reset"`**: Botón que restablece todos los campos del formulario a sus valores iniciales.

### Atributos del `<a>`

- **`href="#"`**: URL de destino del enlace. El valor `"#"` apunta a la misma página (usado como marcador de posición).

---

## Estructura del formulario

| Sección | Elementos |
|---|---|
| **Datos Personales** | Nombre (`text`), Email (`email`), Teléfono (`tel`), Fecha de nacimiento (`date`) |
| **Información Adicional** | País (`select`), Género (`radio`), Intereses (`checkbox`), Comentarios (`textarea`) |
| **Seguridad** | Contraseña (`password`), Confirmar contraseña (`password`) |
| **Términos** | Checkbox de aceptación + enlace |
| **Acciones** | Botón Enviar (`submit`) + Botón Limpiar (`reset`) |

---

# Documentación del CSS

A continuación se explica **cada símbolo, selector, pseudo-clase y propiedad** utilizada en el archivo `styles.css`, ordenado por categorías para facilitar el aprendizaje.

---

## 1. Selectores: cómo "apuntar" a los elementos HTML

Un **selector** le dice al CSS a qué elemento HTML queremos aplicar los estilos.

### 1.1 Selector universal `*`

```css
* { ... }
```

| Símbolo | Significado |
|---------|-------------|
| `*` | Selecciona **todos** los elementos del documento HTML. |

> En nuestro CSS lo usamos junto con `::before` y `::after` para hacer un "reset": eliminar márgenes y paddings por defecto que pone el navegador.

---

### 1.2 Selector de tipo (etiqueta)

```css
body { ... }
h1   { ... }
p    { ... }
```

Simplemente se escribe el nombre de la etiqueta HTML. Selecciona **todas** las etiquetas de ese tipo en la página.

---

### 1.3 Selector de atributo `[ ]`

```css
input[type="text"]    /* todos los <input> cuyo type sea "text" */
input[type="email"]   /* todos los <input> cuyo type sea "email" */
input[required]       /* todos los <input> que tengan el atributo required */
input[name="terminos"]/* el <input> cuyo atributo name sea exactamente "terminos" */
```

| Símbolo | Significado |
|---------|-------------|
| `[atributo]` | Selecciona elementos que **tienen** ese atributo, sin importar su valor. |
| `[atributo="valor"]` | Selecciona elementos cuyo atributo es **exactamente igual** a ese valor. |

---

### 1.4 Agrupación de selectores `,`

```css
input[type="text"],
input[type="email"],
select,
textarea {
    /* estos estilos se aplican a TODOS los selectores listados */
}
```

| Símbolo | Significado |
|---------|-------------|
| `,` (coma) | Aplica el mismo bloque de estilos a **varios selectores distintos** a la vez. Equivale a decir "tanto A como B como C". |

---

### 1.5 Selector de hijo directo `>`

```css
body > div       /* el <div> que es hijo DIRECTAMENTE del <body> */
fieldset > div   /* los <div> que son hijos DIRECTOS de un <fieldset> */
form > div:last-child  /* el ÚLTIMO <div> que es hijo directo de <form> */
```

| Símbolo | Significado |
|---------|-------------|
| `>` | Selecciona solo los elementos que son **hijos directos** (inmediatos), no nietos ni descendientes más profundos. |

**Ejemplo práctico:**

```html
<form>
    <div>           ← seleccionado por form > div
        <div>       ← NO seleccionado (es nieto, no hijo directo)
        </div>
    </div>
</form>
```

---

### 1.6 Selector de hermano adyacente `+`

```css
h1 + p              /* el <p> que está INMEDIATAMENTE después de un <h1> */
label:has(+ input[required])  /* <label> seguido inmediatamente por un <input required> */
```

| Símbolo | Significado |
|---------|-------------|
| `+` | Selecciona el elemento que está **justo después** del primero, al mismo nivel (hermanos). |

**Ejemplo:**

```html
<h1>Título</h1>
<p>Este párrafo</p>   ← seleccionado por h1 + p (está justo después del h1)
<p>Este otro no</p>    ← NO seleccionado (no está inmediatamente después del h1)
```

---

## 2. Pseudo-clases: estados especiales de los elementos

Una **pseudo-clase** empieza con `:` y representa un **estado** del elemento.

| Pseudo-clase | ¿Cuándo se activa? | Ejemplo en nuestro CSS |
|---|---|---|
| `:hover` | Cuando el mouse pasa **por encima** del elemento. | `button:hover` → cambia color al pasar el mouse. |
| `:focus` | Cuando el elemento tiene el **foco** (se hizo clic o se llegó con Tab). | `input:focus` → borde violeta al escribir. |
| `:active` | Cuando el elemento está siendo **clickeado** (presionado). | `button:active` → botón vuelve a su lugar al hacer clic. |
| `:checked` | Cuando un radio o checkbox está **seleccionado/marcado**. | `input[type="radio"]:checked` → se pinta de violeta. |
| `:last-child` | Selecciona el **último hijo** de un contenedor. | `fieldset > div:last-child` → sin margen inferior. |
| `:valid` | Cuando el contenido del campo **cumple** las reglas de validación. | Borde verde en campos correctos. |
| `:invalid` | Cuando el contenido **NO cumple** las reglas de validación. | Borde rojo en campos incorrectos. |
| `:focus-visible` | Cuando el foco llega por **teclado** (Tab), no por mouse. | Anillo violeta visible para accesibilidad. |

---

### 2.1 Pseudo-clase de negación `:not()`

```css
input:valid:not([type="radio"]):not([type="checkbox"])
```

| Símbolo | Significado |
|---------|-------------|
| `:not(selector)` | Selecciona elementos que **NO cumplen** con el selector indicado. |

La línea anterior significa: *"inputs que son válidos, pero que NO son radio NI checkbox"*.

---

### 2.2 Pseudo-clase funcional `:has()`

```css
fieldset > div > div label:has(input:checked)
form > div:has(input[name="terminos"])
```

| Símbolo | Significado |
|---------|-------------|
| `:has(selector)` | Selecciona un elemento si **contiene dentro** algún elemento que cumpla el selector. |

La primera línea significa: *"un `<label>` que contiene adentro un `<input>` que está marcado (checked)"*.

> :has() es una pseudo-clase moderna (2023+). Funciona en todos los navegadores actuales.

---

## 3. Pseudo-elementos `::before` y `::after`

```css
legend::before { ... }
label::after  { ... }
```

| Pseudo-elemento | Significado |
|-----------------|-------------|
| `::before` | Crea un elemento **virtual** ANTES del contenido del elemento. |
| `::after` | Crea un elemento **virtual** DESPUÉS del contenido del elemento. |

Estos elementos no existen en el HTML: los crea CSS. **Siempre necesitan** la propiedad `content` (aunque sea vacía `''`).

```css
legend::before {
    content: '';        /* obligatorio: puede ser texto, imagen, o vacío */
    display: inline-block;
    width: 10px;
    height: 10px;
    background: #4f46e5;
    border-radius: 50%;  /* se dibuja un círculo violeta antes del texto */
}
```

---

## 4. Media Queries `@media`

```css
@media (max-width: 600px) {
    /* estilos que SOLO se aplican en pantallas de 600px de ancho o menos */
    body { padding: 1rem; }
}
```

| Parte | Significado |
|-------|-------------|
| `@media` | Regla que aplica estilos solo si se cumple una **condición**. |
| `(max-width: 600px)` | Condición: "cuando el ancho máximo sea 600px". Es decir, pantallas de 600px **o menos**. |

> Esto se llama **diseño responsive**: los estilos se adaptan automáticamente al tamaño de la pantalla (celular, tablet, escritorio).

---

## 5. Propiedades CSS utilizadas

### 5.1 Modelo de caja (Box Model)

| Propiedad | ¿Qué hace? | Ejemplo |
|---|---|---|
| `box-sizing: border-box` | El `padding` y el `border` se incluyen dentro del `width`/`height`. Más fácil de calcular. | — |
| `margin` | Espacio **externo** (fuera del borde). | `margin: 0` → sin margen. |
| `margin-bottom` | Espacio externo solo **abajo**. | `margin-bottom: 1.2rem` |
| `margin-top` | Espacio externo solo **arriba**. | `margin-top: 0.3rem` |
| `margin-right` | Espacio externo solo a la **derecha**. | `margin-right: 0.4rem` |
| `padding` | Espacio **interno** (dentro del borde). | `padding: 2.5rem` |
| `padding-right` | Espacio interno solo a la **derecha**. | `padding-right: 2.5rem` |

---

### 5.2 Tipografía

| Propiedad | ¿Qué hace? | Ejemplo |
|---|---|---|
| `font-family` | Define la fuente (tipografía) del texto. | `'Segoe UI', system-ui, sans-serif` |
| `font-size` | Tamaño de la letra. | `2rem` (32px), `0.9rem` (~14px) |
| `font-weight` | Grosor de la letra. `400`=normal, `600`=semi-negrita, `700`=negrita. | `font-weight: 700` |
| `font-style` | Estilo: `normal`, `italic` (cursiva). | `font-style: italic` |
| `line-height` | Altura de cada línea de texto (interlineado). `1.6` = 160% del tamaño. | `line-height: 1.6` |
| `text-align` | Alineación horizontal: `left`, `center`, `right`. | `text-align: center` |
| `text-decoration` | Decoración: `underline` (subrayado), `none` (sin). | `text-decoration: underline` |
| `color` | Color del texto. | `color: #1e293b` |

---

### 5.3 Colores y fondos

| Propiedad | ¿Qué hace? | Ejemplo |
|---|---|---|
| `color` | Color del **texto**. | `color: white` |
| `background` | Fondo (atajo: color + imagen + repetición + posición). | `background: #ffffff` |
| `background-image` | Imagen o degradado de fondo. | `url("data:image/svg...")` |
| `background-repeat` | Si la imagen de fondo se repite: `repeat`, `no-repeat`. | `background-repeat: no-repeat` |
| `background-position` | Posición de la imagen de fondo. | `background-position: center` |

**Formatos de color usados:**

| Formato | Ejemplo | Descripción |
|---|---|---|
| Hexadecimal | `#4f46e5` | 6 dígitos: RRGGBB (rojo, verde, azul). `00`=nada, `FF`=máximo. |
| `rgba()` | `rgba(79, 70, 229, 0.15)` | R=rojo, G=verde, B=azul (0-255), A=transparencia (0=invisible, 1=opaco). |
| Palabras clave | `white`, `transparent` | Nombres predefinidos. `transparent` = completamente invisible. |
| `linear-gradient()` | `linear-gradient(135deg, #667eea 0%, #764ba2 100%)` | Degradado lineal: ángulo, color inicial, color final. |

---

### 5.4 Bordes y sombras

| Propiedad | ¿Qué hace? | Ejemplo |
|---|---|---|
| `border` | Atajo: ancho + estilo + color del borde. | `border: 2px solid #cbd5e1` |
| `border-color` | Solo el color del borde. | `border-color: #4f46e5` |
| `border-radius` | Redondea las esquinas. `50%` = círculo perfecto. | `border-radius: 10px` |
| `box-shadow` | Sombra alrededor del elemento. | `box-shadow: 0 4px 6px rgba(0,0,0,0.1)` |
| `outline` | Línea externa (no ocupa espacio). Para accesibilidad. | `outline: 2px solid #4f46e5` |
| `outline-offset` | Distancia entre el borde y el outline. | `outline-offset: 2px` |

**Sintaxis de `box-shadow`:**

```
box-shadow: <desplazamientoX> <desplazamientoY> <desenfoque> <expansion> <color>;
```

Ejemplo: `0 4px 6px -1px rgba(0,0,0,0.1)` → sin desplazamiento horizontal, 4px hacia abajo, 6px de desenfoque, -1px de contracción, color negro semitransparente.

---

### 5.5 Dimensiones

| Propiedad | ¿Qué hace? | Ejemplo |
|---|---|---|
| `width` | Ancho del elemento. | `width: 100%` |
| `max-width` | Ancho **máximo** (no crece más allá). | `max-width: 650px` |
| `height` | Alto del elemento. | `height: 18px` |
| `min-height` | Alto **mínimo** (no se encoge más). | `min-height: 100vh` |

---

### 5.6 Flexbox

Flexbox es un sistema para distribuir elementos en filas o columnas.

| Propiedad | ¿Qué hace? | Ejemplo |
|---|---|---|
| `display: flex` | Activa flexbox en el contenedor. | — |
| `display: inline-flex` | Igual que flex, pero el contenedor se comporta como elemento en línea. | — |
| `flex-direction` | Dirección: `row` (fila →), `column` (columna ↓). | `flex-direction: column` |
| `flex-wrap` | ¿Los elementos pasan a otra línea? `wrap` = sí. | `flex-wrap: wrap` |
| `gap` | Espacio **uniforme** entre todos los hijos. | `gap: 1.5rem` |
| `justify-content` | Alineación en el eje principal: `center`, `flex-start`, etc. | `justify-content: center` |
| `align-items` | Alineación en el eje secundario: `center`, `flex-start`, etc. | `align-items: center` |
| `flex` | Cuánto se estira el elemento para ocupar espacio disponible. | `flex: 1` |
| `flex-shrink` | Si el elemento puede encogerse: `0` = no. | `flex-shrink: 0` |

---

### 5.7 Otras propiedades

| Propiedad | ¿Qué hace? | Ejemplo |
|---|---|---|
| `cursor` | Cambia la forma del cursor del mouse. `pointer` = manito. | `cursor: pointer` |
| `resize` | Permite redimensionar un elemento: `vertical`, `horizontal`, `none`. | `resize: vertical` |
| `vertical-align` | Alineación vertical de elementos en línea. | `vertical-align: middle` |
| `appearance: none` | Elimina el estilo nativo del sistema operativo. | — |
| `content` | Contenido de un pseudo-elemento (`::before`/`::after`). **Obligatorio**. | `content: ' *'` |
| `position: relative` | Permite que el elemento se posicione respecto a su lugar original. | — |
| `transform` | Aplica transformaciones: rotar, escalar, mover. | `transform: translateY(-2px)` |
| `outline: none` | Quita el contorno azul del navegador. | — |
| `inherit` | Hereda el valor de la propiedad del elemento padre. | `font-family: inherit` |

---

### 5.8 Unidades de medida

| Unidad | Significado | Ejemplo |
|---|---|---|
| `px` | Píxeles. Medida fija. | `width: 18px` |
| `rem` | Relativa al tamaño de fuente del elemento raíz (`<html>`). 1rem ≈ 16px por defecto. | `padding: 2rem` (32px) |
| `%` | Porcentaje relativo al elemento padre. | `width: 100%` (todo el ancho disponible) |
| `vh` | Viewport Height: porcentaje de la altura de la ventana. `100vh` = toda la pantalla. | `min-height: 100vh` |
| `deg` | Grados. Se usa en degradados y transformaciones. | `linear-gradient(135deg, ...)` |

---

## 6. Resumen visual de símbolos

| Símbolo | Nombre | ¿Qué hace? |
|---------|--------|------------|
| `*` | Selector universal | Selecciona todos los elementos. |
| `,` | Agrupación | Aplica lo mismo a varios selectores. |
| `>` | Hijo directo | Solo hijos inmediatos, no nietos. |
| `+` | Hermano adyacente | El elemento que está justo después. |
| `:` | Pseudo-clase | Un estado del elemento (`:hover`, `:focus`). |
| `::` | Pseudo-elemento | Crea un elemento virtual (`::before`, `::after`). |
| `[ ]` | Selector de atributo | Filtra por atributo y valor. |
| `:not()` | Negación | Elementos que NO cumplen algo. |
| `:has()` | Contención | Elementos que contienen algo dentro. |
| `@media` | Media Query | Estilos condicionales según pantalla. |
Estado del proyecto
Proyecto funcional de frontend estático para pruebas y control básico de dispositivos Arduino/ESP32 desde el navegador.

⚖️ Licencia y Limitación de Responsabilidad Este proyecto está publicado bajo la licencia GNU General Public License v3.0 (GPL-3.0). Podés consultar los términos completos en el archivo LICENSE.

¿Qué significa esto para las clases y proyectos? Libertad de uso: Sos libre de descargar, modificar, usar y distribuir este código para tus trabajos prácticos, proyectos personales o profesionales. Código abierto obligado: Si modificás este software y decidís compartirlo o publicarlo, estás obligado a hacerlo de forma pública y bajo esta misma licencia GPLv3. Sin garantías ("As Is"): El software se entrega tal cual está, con fines puramente educativos. No se ofrece ninguna garantía de funcionamiento. Exención de responsabilidad: El autor no se hace responsable por códigos que no compilen, fallas en el sistema, ni por cualquier daño físico o rotura de componentes de hardware (como placas Arduino, sensores o actuadores) derivados del uso de este programa. El uso corre por cuenta y riesgo del usuario.

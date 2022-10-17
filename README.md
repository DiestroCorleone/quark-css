# QUARK CSS

## Un framework liviano y simple para desarrollo front end.

![v1.1.1](https://img.shields.io/github/v/release/DiestroCorleone/quark-css?display_name=tag)

### Características

- Incluye todo lo necesario para armar un sitio estático, con algunos extras.
- Modo oscuro
- Simple sistema de columnas con opciones basadas en Flexbox y Grid
- Íconos de [Font Awesome 4](https://www.w3schools.com/icons/fontawesome_icons_intro.asp) incluídos.
- Características de personalización.
- Responsivo.

### Qué necesitás?

Descargá el siguiente [archivo ZIP](https://github.com/DiestroCorleone/quark-css/tree/main/files)

El mismo contiene:

- El arhivo `HTML index.html`.
- El archivo CSS `quark.css`.
- El archivo JavaScript `quark-control.js`.

#### El HTML

Es un template para arrancar tu sitio lo antes posible. Cuenta con links al archivo CSS, al JavaScript, y a Font Awsome, además de una barra de navegación responsive y varias otras etiquetas que son elementales en un sitio web (descripción, keywords, autor, theme-color, etc.).
Recordá que es fundamental que mantengas este template como base de tus páginas para el correcto funcionamiento de Quark.
En el `head` verás:

```html
<link rel="stylesheet" href="quark.css" />
<link
  rel="stylesheet"
  href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css"
/>
```

Podés modificar el link a `"quark.css"` para dirigirlo al directorio donde hayas guardado el archivo.
Asimismo, en el final del sitio, te encontrarás con un footer predeterminado, cuyo contenido podrás modificar, asociado a un script al final del código, que mantendrá el sitio mostrando siempre el año actual. Además del link a quark-control.js, que también podés modificar si lo guardaste en otra ruta que no sea el directorio predeterminado.

```html
<!----------FOOTER---------->
<footer class="back-tertiary color-secondary padded-hard text-center">
  <small
    >Developedi with &#9829; by
    <a href="YOUR WEBSITEr" target="_blank" title="b">YOUR WEBSITE</a> -
    <span id="year"></span
  ></small>
</footer>
<!---------SCRIPTS--------->
<script type="text/javascript" src="quark-control.js"></script>
<script type="text/javascript">
  window.onload = () => showYear();

  function showYear() {
    const year = new Date().getFullYear();
    document.getElementById("year").innerHTML = year;
  }
</script>
```

Por último, notarás que la etiqueta body tiene por ID `"body"`. Esto es necesario para que funcione el toggle de modo oscuro.

#### Lo que deberás agregar

##### Google Fonts

Dentro de la etiquetas head, debajo de la línea comentada GOOGLE FONTS, pegá el link de las fuentes que hayas seleccionado. Quark CSS está preparado, out-of-the-box, para usar **hasta dos fuentes** predeterminadas.

```html
<!----------GOOGLE FONTS---------->
<link rel="preconnect" href="https://fonts.googleapis.com" />
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
<link
  href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;800&display=swap"
  rel="stylesheet"
/>
```

##### Colores y fuentes predeterminadas

Debajo del comentario `QUARK CSS`, definirás hasta 4 colores, que luego se aplicarán a todas las clases del framework (es fundamental que el **primary** sea el color de texto y el **secondary** el color de fondo, y que contrasten entre sí pues han de invertirse con del modo oscuro), y hasta 2 fuentes que hayas importado previamente con Google Fonts.

```html
<!----------QUARK CSS---------->
<style type="text/css">
  /*Define colors and for your website*/
  :root {
    /*Body text color*/
    --primary: #;
    /*Body background color*/
    --secondary: #;
    /*Main accent color*/
    --tertiary: #;
    /*2nd accent color*/
    --quaternary: #;
    /*Main font*/
    --main-font: YOUR FONT, sans-serif;
    /*Secondary font*/
    --secondary-font: YOUR FONT, sans-serif;
  }
</style>
```

##### La barra de navegación

El template incluye una `nav` por defecto, con estilos básicos para que ocupe todo el ancho superior de la pantalla.
Los primeros dos links no deben borrarse, pues son el botón de menú hamburguesa y cerrar en responsive. El último puede borrarse si no vas a emplear el toggle de modo oscuro, caso contrario dejarlo.
Entre ambas, podés agregar cuantos links tu web necesite.

```html
<!----------NAV---------->
<nav class="col-full" id="menu">
  <div class="col-3-quarter no-margin">
    <ul class="flex flex-row between no-margin col-full">
      <!----------MANDATORY, DON'T DELETE---------->
      <li class=""><a title="MENU" href="#menu" class="">&#9776;</a></li>
      <li class=""><a title="CLOSE MENU" href="#" class="">x</a></li>
      <!----------END MANDATORY, DON'T DELETE---------->
      <!----------YOUR LINKS HERE---------->
      <li class=""><a title="" href="#">LINK</a></li>
      <li class=""><a title="" href="#">LINK</a></li>
      <li class=""><a title="" href="#">LINK</a></li>
      <li class=""><a title="" href="#">LINK</a></li>
      <!----------OPTIONAL, DELETE IF YOU DON'T WANT DARK MODE SWITCH---------->
      <li class="" onclick="darkMode();" title="Toggle Dark Mode">
        <i class="fa fa-fw fa-lightbulb-o"></i>
      </li>
      <!----------END, DELETE IF YOU DON'T WANT DARK MODE SWITCH---------->
    </ul>
  </div>
</nav>
```

##### Y listo!

Ya podés comenzar a usar Quark CSS para armar tu página en tiempo record!

### Layout

Estas clases, aplicadas a un `div` o la etiqueta que prefieras (se pueden combinar), aplicarán lo siguiente:

- `grid-center`: Tu contenedor tendrá un `display: grid` y `align-items: center`, ideal para centrar elementos.
- `flex`: Anadirá `display: flex` al contenedor, para luego aplicar lo que sigue.
- `flex-row` y `flex-column`: Elegí la orientación del flex. Ambas **se volverán columnas en responsive**, así que si querés que sigan siendo filas en pantallas pequeñas, deberás optar por flex-row-on-phone.
- `between` y `around`: Combinadas con flex, añadirán `justify-content` de `space-between` o `around` según corresponda.

### Sistema de grilla

Con las siguientes clases podrás armar un layout responsivo para tu sitio.

- `col-full`: Un ancho del 100%.
- `col-3-quarter`: Un ancho de 75%.
- `col-2-third`: 66%.
- `col-half`: 50%.
- `col-half`: 45%.
- `col-2-third`: 66%.
- `col-quarter`: 25%.

En responsive, todas adoptarán un **ancho del 100%**.

### Texto y alineación

Bastante autoexplicativas.

- `main-font` y `secondary-font`: Según definamos en el head.
- `font-bold` y `font-light`.
- `text-center`, `text-left` y `text-right`.
- `text-shadow`: Suave sombra paralela para textos.

### Colores y fondos

De acuerdo a los colores elegidos en el head, podrás aplicar el siguiente las siguientes clases para definir colores de texto y fondo.

- `color-primary`, `color-secondary`, `color-tertiary`, `color-quaternary`: Aplicarán el color correspondiente al texto del elemento.
- `back-primary`, `back-secondary`, `back-tertiary`, `back-quaternary`: Un fondo del color elegido.

Los hovers de color y background son similares a los anteriores, añadiendo `hover-` al inicio del nombre de las clases (`hover-color-primary`, `hover-back-secondary`, etc.).

### Bordes y hover

Empleando los colores que definimos en el encabezado, podrás aplicar el siguiente set de clases para definir bordes y hover states.

- `border-sm-primary`, `border-sm-secondary`, `border-sm-tertiary`, `border-sm-quaternary`: Aplicarán un fino borde del color correspondiente.
- `border-md-primary`, `border-md-secondary`, `border-md-tertiary`, `border-md-quaternary`: Un borde de 2px del color elegido.
- `border-bottom-sm-primary`, `border-bottom-sm-secondary`, `border-bottom-sm-tertiary`, `border-bottom-sm-quaternary`: Aplicarán un fino border bottom del color correspondiente.
- `border-bottom-md-primary`, `border-bottom-md-secondary`, `border-bottom-md-tertiary`, `border-bottom-md-quaternary`: Un border bottom de 2px del color elegido.

Los hovers de border son similares a los anteriores, añadiendo `hover-` al inicio del nombre de las clases (`hover-border-sm-primary`, `hover-border-bottom-md-primary`, etc.).

### Imágenes

Las clases que te ayudarán con las imágenes (aunque pueden aplicarse a cualquier elemento) son:

- `img-responsive`: Dará un `width: 100%` y `height: auto`.
- `cover`, `contain`, `fill`: Darán el `object-fit` correspondiente al elemento aplicado.

### Márgenes y padding

- `margin-xsm`, `margin-sm` y `margin-md`: Márgenes de menor a mayor.
- `no-margin`: Un `margin: 0 auto`, también útil para centrar horizontalmente.
- `padded-sm`, `padded`, `padded-hard`: Paddings de menor a mayor.

### Alturas

- `full-height` y `full-vh`: Alturas de 100% y 100vh, respectivamente.
- `eighty-vh`: Altura de 80vh.
- `half-height` y `half-vh`: Alturas de 50% y 50vh, respectivamente.
- `third-height`: Altura de 30%.
- `auto-height`: Altura automática.

### Responsive

- `show-on-phone`: Elemento que no se mostrará a menos que el viewport sea de 800px o menos.
- `hide-on-phone`: Este es lo opuesto, se oculta en un viewport de 800px o menos.

### Otros estilos

- `parallax`: Esta clase aplicará el popular efecto al contenedor que tenga la imagen de fondo.
- `rounded-soft` y `rounded-hard`: Redonderá los bordes del elemento con dos intensidades, menor y mayor.
- `box-shadow`: Sombra paralela para el elemento elegido.
- `over-hidden`: Esconderá el overflow del contenedor al que lo apliquemos.
- `invisible`: `display: none` para aquello a lo que lo apliquemos.
- `float-button`: Un botón flotante en la esquina inferior derecha, para lo que deseemos; volver arriba, contacto por WhatsApp, etc.

Desarrollado con :heart: por [@DiestroCorleone](https://github.com/DiestroCorleone)

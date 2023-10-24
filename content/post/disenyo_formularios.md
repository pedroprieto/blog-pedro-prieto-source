+++
title = "Diseño de formularios"
date = 2019-10-29T12:00:00+01:00
tags = ["css", "formularios"]
categories = ["diw", "diw-estilos-multimedia"]
draft = false
author = "Pedro Prieto"
+++

En este artículo se analizarán algunas recomendaciones de diseño relacionadas con los formularios web. El objetivo es aprender a diseñar formularios que muestren la información de manera limpia, clara y de forma adaptada a cualquier tipo de dispositivo.

<!--more-->


## Estructura y diseño visual (código) {#estructura-y-diseño-visual--código}

A continuación se muestran algunos consejos relacionados con el código HTML y CSS utilizado en formularios.


### Fieldset {#fieldset}

La etiqueta `<fieldset>` se utiliza para agrupar controles relacionados. Se suele utilizar junto con la etiqueta `<legend>`, que muestra un texto a modo de título.

```html
<form>
  <fieldset>
    <legend>Título</legend>

    <!-- Controles del formulario -->

  </fieldset>

</form>
```


### Agrupación de controles {#agrupación-de-controles}

Los controles de formulario son elementos en línea. Por tanto, para que aparezcan en líneas distintas es conveniente agruparlos mediante etiquetas de bloque. En este punto se puede optar por etiquetas `<p>` o `<div>`:

```html
<form>
  <fieldset>
    <legend>Título</legend>

    <div><!-- Control de formulario --></div>
    <div><!-- Control de formulario --></div>
    <div><!-- Control de formulario --></div>

  </fieldset>

</form>
```

O por listas (ordenadas o desordenadas):

```html
<form>
  <fieldset>
    <legend>Título</legend>

    <ul>
      <li><!-- Control de formulario --></li>
      <li><!-- Control de formulario --></li>
      <li><!-- Control de formulario --></li>
    </ul>

  </fieldset>

</form>
```

En caso de utilizar listas es posible ocultar los puntos mediante el siguiente código CSS:

```css
form ul, form ol {
    list-style: none;
    padding: 0;
}
```


### Campos {#campos}

Para identificar los controles se deben utilizar los atributos `id` y `name`. El atributo `id` se utiliza para a programación de cliente (_front-end_), mientras que el atributo `name` se utiliza para el envío de los datos al servidor (_back-end_). Es muy importante tener en cuenta que normalmente **hay que utilizar los dos**.

```html
<form>
  <fieldset>
    <legend>Título</legend>

    <ul>
      <li><input type="text" name="name" id="name"></li>
      <li><input type="text" name="lname" id="lname"></li>
      <li><input type="email" name="email" id="email"></li>
    </ul>

  </fieldset>

</form>
```


### Etiquetas (labels) {#etiquetas--labels}

Para mostrar la información asociada a un control se debe utilizar la etiqueta `<label>`. Dicha etiqueta utiliza el atributo `for` para indicar el control al que va asociado. El valor del atributo `for` debe ser el valor del atributo `id` del control correspondiente.

El uso de etiquetas tiene varias ventajas:

-   El usuario puede pulsar con el ratón sobre la etiqueta y activar el control asociado.
-   Dispositivos como lectores de pantalla o lectores braille necesitan las etiquetas para poder mostrar la información asociada al control.

<!--listend-->

```html
<form>
  <fieldset>
    <legend>Título</legend>

    <ul>
      <li>
        <label for="name">Nombre</label>
        <input type="text" name="name" id="name">
      </li>
      <li>
        <label for="lname">Apellidos</label>
        <input type="text" name="lname" id="lname">
      </li>
      <li>
        <label for="email">Email</label>
        <input type="text" name="email" id="email">
      </li>
    </ul>

  </fieldset>

</form>
```


### Alineación {#alineación}

La alineación de controles o etiquetas puede conseguirse utilizando cualquiera de las técnicas vistas en el artículo de [técnicas para crear layouts](/post/tecnicas_layout/).

En el caso concreto de formularios es recomendable utilizar `flexbox` o `display: inline-block` definiendo una anchura igual para las etiquetas junto con otra anchura igual para los controles. La separación entre ambos puede realizarse utilizando el margen.

A continuación se muestra un ejemplo del código utilizando `display: inline-block`:

```css
label {
    display: inline-block;
    width: 7em;
}

input {
    display: inline-block;
    width: 9em;
}
```

Es posible (y recomendable) utilizar etiquetas `<span>` para agrupar etiquetas y controles y así poderlos procesar correctamente en CSS.

```html
<form>
  <fieldset>
    <legend>Título</legend>

    <ul>
      <li class="grupo-control">
        <span class="etiqueta"><label for="name">Nombre</label></span>
        <span class="control"><input type="text" name="name" id="name"></span>
      </li>
      <li class="grupo-control">
        <span class="etiqueta"><label for="lname">Apellidos</label></span>
        <span class="control"><input type="text" name="lname" id="lname"></span>
      </li>
      <li class="grupo-control">
        <span class="etiqueta"><label for="email">Email</label></span>
        <span class="control"><input type="text" name="email" id="email"></span>
      </li>
    </ul>

  </fieldset>

</form>
```

Partiendo del código anterior, se muestra a continuación el código necesario para alinear los campos utilizando `flexbox`:

```css
.grupo-control {
  display: flex;
}

.etiqueta {
    flex: 1 1 0;
}

.control {
  flex: 2 1 0;
}

input {
  width: 100%;
  margin: 0;
  padding: 0;
}
```


### Pistas (Placeholders) {#pistas--placeholders}

Es posible utilizar pistas para indicar al usuario qué información debe introducir en cada campo del formulario. Para ello se puede utilizar el atributo `placeholder`.

```html
<form>
  <fieldset>
    <legend>Título</legend>

    <ul>
      <li>
        <span class="etiqueta"><label for="name">Nombre</label></span>
        <span class="control"><input type="text" name="name" id="name" placeholder="Nombre"></span>
      </li>
      <li>
        <span class="etiqueta"><label for="lname">Apellidos</label></span>
        <span class="control"><input type="text" name="lname" id="lname" placeholder="Apellidos"></span>
      </li>
      <li>
        <span class="etiqueta"><label for="email">Email</label></span>
        <span class="control"><input type="text" name="email" id="email" placeholder="Email"></span>
      </li>
    </ul>

  </fieldset>

</form>
```


### Validación {#validación}

Los formularios pueden ser **validados** tanto en el **cliente** como en el **servidor**. Suele ser una buena práctica utilizar **ambas formas de validación**:

-   La validación en **servidor** es **fundamental**, ya que siempre es necesario verificar los datos que recibe la aplicación para evitar errores, código malicioso o incompatibilidad con los tipos de datos definidos en la base de datos.
-   La validación en **cliente** no es obligatoria, aunque ofrece varias **ventajas**, como mejorar la **experiencia de usuario**, **optimizar la cantidad de datos** utilizada en la conexión o **disminuir la carga de proceso del servidor**.

La utilización de HTML5 junto con los navegadores actuales permiten incorporar validación en entorno de cliente de manera muy sencilla. Algunas de las recomendaciones a seguir son:

-   Utilizar las etiquetas `<input>` definidas en HTML5: `<input type="date">`, `<input type="email">`, `<input type="number">`,... Más información [sobre etiquetas input](https://developer.mozilla.org/es/docs/Web/HTML/Elemento/input).
-   Utilizar el atributo `required` para indicar que un campo es obligatorio.
-   Utilizar atributos de validación específicos: `min`, `max`, `minlength`, `maxlength`, `pattern`,...
-   Utilizar [mensajes de error personalizados](https://developer.mozilla.org/es/docs/Learn/HTML/Forms/Validacion_formulario_datos#Mensajes_de_error_personalizados) (requiere JavaScript).
-   Utilizar las [pseudo-clases `:valid` y `:invalid`](https://developer.mozilla.org/es/docs/Web/CSS/:invalid) de CSS para personalizar la apariencia visual de los campos correctos o incorrectos.

Puede consultarse más información sobre validación en este [artículo de MDN sobre validación de formularios](https://developer.mozilla.org/es/docs/Learn/HTML/Forms/Validacion_formulario_datos).


### Relleno automático de campos {#relleno-automático-de-campos}

La mayoría de los navegadores permiten almacenar valores introducidos en formularios anteriores y sugerir posibles valores a la hora de rellenar el formulario actual. Para ello se puede utilizar la característica de [autocomplete](https://developer.mozilla.org/es/docs/Web/HTML/Atributos/autocomplete).


### Ejemplo completo {#ejemplo-completo}

A continuación puedes ver un [ejemplo de formulario utilizando las recomendaciones descritas](https://jsbin.com/bebozar/3/edit?html,css,output).


## Usabilidad y accesibilidad {#usabilidad-y-accesibilidad}


### Alineación de etiquetas {#alineación-de-etiquetas}

Las **etiquetas** de los formularios suelen colocarse **arriba o a la izquierda** de los controles. Cuando se colocan a la izquierda, pueden **alinearse** a la **izquierda** o a la **derecha**. Cada una de estas opciones tiene sus ventajas e inconvenientes.

|                                        | Arriba | Izquierda | Derecha |
|----------------------------------------|--------|-----------|---------|
| Útil para tipos de datos conocidos     | X      |           |         |
| Procesamiento rápido                   | X      |           | X       |
| No problemas con etiquetas largas      | X      |           | X       |
| Asociación etiqueta-control clara      |        |           | X       |
| Ocupa poco espacio vertical            |        | X         | X       |
| Favorece el escaneo de etiquetas       |        | X         |         |
| Útil para tipos de  datos desconocidos |        | X         |         |


### Datos obligatorios y opcionales {#datos-obligatorios-y-opcionales}

-   Se debe **minimizar** el número de **datos opcionales**.
-   Si la mayoría de datos son obligatorios: indicar los opcionales.
-   Si la mayoría de datos son opcionales: indicar los obligatorios.
-   Es mejor utilizar indicadores mediante **texto**; también se puede utilizar `*` para los campos **obligatorios**.
-   Se deben asociar los indicadores con las etiquetas.


### Longitud de los campos {#longitud-de-los-campos}

-   El tamaño de los campos puede ofrecer información sobre su contenido.
-   Muchos tamaños: ruido adicional
-   En caso de duda, tamaño igual para todos los campos.


### Acciones {#acciones}

-   Es recomendable mostrar el mínimo número de acciones posibles (idealmente sólo 1).
-   En caso de mostrar más de una acción, diferenciar visualmente la opción principal de las secundarias.


### Ayuda {#ayuda}

-   Se debe minimizar la cantidad de ayuda mostrada.
-   En caso de necesitar instrucciones, mostrar la ayuda adosada a los campos que la necesiten (ayuda dinámica).


### Entrada de datos {#entrada-de-datos}

-   Se debe mostrar claramente el camino a seguir para completar el formulario.
-   En caso de que el formulario sea **muy largo**, se debe ofrecer la posibilidad de **salvar el progreso**.
-   Es conveniente permitir la **entrada flexible de datos** (por ejemplo, en números de teléfono: 999-112233, 999112233, 999 11 22 33, 999 112 233, etc.).


### Control por teclado {#control-por-teclado}

-   Se debe tener en cuenta el uso del teclado para rellenar formularios. Para ello puede utilizarse el atributo [tabindex](http://www.w3schools.com/tags/att_global_tabindex.asp).


### Retroalimentación {#retroalimentación}

-   Se debe utilizar validación automática en campos con alta tasa de error.
-   Es recomendable utilizar sugerencias para evitar errores.
-   **Siempre** se debe mostrar un **mensaje** cuando se **envíe un formulario** indicando si la acción ha tenido éxito o si se ha producido un error.


### Errores {#errores}

-   Se debe comunicar claramente que ha ocurrido un error: en la **parte superior** de la página utilizando **contraste visual**.
-   Además, se debe indicar qué **campos** son los que contienen **errores**.


### Progreso de envío {#progreso-de-envío}

-   Es recomendable mostrar indicaciones de las acciones en progreso.
-   Es muy recomendable **desactivar el botón de envío** después de que el usuario lo haya pulsado. De esta manera evitamos que se produzcan envíos duplicados.


### Envío {#envío}

-   Se debe mostrar claramente si los datos se han enviado con éxito.
-   Se debe indicar alguna **referencia a la acción que se ha realizado**: actualización, creación de información nueva, pago,...


## Referencias {#referencias}

-   [Recomendaciones para diseño de formularios (en inglés)](http://www.slideshare.net/AaronGustafson/learning-to-love-forms-web-directions-south-07)
-   [Consejos de usabilidad de formularios (en inglés)](http://www.slideshare.net/psykoreactor/best-practices-for-form-design)

+++
title = "Técnicas para crear layouts"
date = 2019-10-28T18:02:00+01:00
tags = ["css", "layout", "flexbox", "grid"]
categories = ["diw", "diw-estilos-multimedia"]
draft = false
+++

En la actualidad existen muchas maneras de crear layouts utilizando CSS. A las técnicas tradicionales (`float`, `inline-block`) se suman otras nuevas aportadas por CSS3, como [flexbox](https://developer.mozilla.org/es/docs/Web/CSS/CSS%5FFlexible%5FBox%5FLayout/Conceptos%5FBasicos%5Fde%5FFlexbox) o [CSS Grid Layout](https://developer.mozilla.org/es/docs/Web/CSS/CSS%5FGrid%5FLayout).

<!--more-->

A continuación veremos las principales técnicas de creación de layouts utilizadas en el diseño web.


## Float {#float}

Se utilizan para layouts que no necesitan centrado vertical ni alturas de capas iguales.

Ventajas:

-   Método más popular.
-   Al ser el método más popular, los fallos que se producen están muy bien documentados y se han desarrollado muchos métodos para corregirlos.

Desventajas:

-   Necesitan ser reseteados ([clearfix](http://stackoverflow.com/questions/8554043/what-is-clearfix)). Si se utilizan _media queries_ para personalizar la apariencia en función del dispositivo será necesario hacer un _clear_ para cada adaptación.
-   No se pueden alinear en vertical.
-   Las alturas de las capas no son iguales.
-   Dependen del orden en que aparezcan las capas en el HTML.


## Inline-block {#inline-block}

Se utilizan cuando se necesitan layouts con las siguientes características:

-   Sitios que necesitan alineación vertical.
-   Para evitar tener que realizar el _clear_ de los floats cuando se utilizan _media queries_.
-   Para realizar menús horizontales utilizando listas.

Ventajas:

-   Posibilidad de alineación vertical.
-   No necesitan hacer _clear_ en diseños complejos adaptados a muchos dispositivos con _media queries_.

Desventajas:

-   Las alturas de las capas no son iguales.
-   Dependen del orden en que aparezcan las capas en el HTML.
-   Tienen un fallo que consiste en **crear un espacio en blanco adicional** (_whitespace bug_) entre los elementos. La solución si utilizamos listas consiste en utilizar tipos de documento HTML5 y no cerrar los elementos `<li>`. En este [enlace](http://blog.karenmenezes.com/2013/aug/30/inline-block-conundrum-part-2/) se muestra el problema.

Ejemplo de galería con `inline-block`: <http://karenmenezes.com/inlineblockgrid/>


## Display table {#display-table}

La propiedad `display: table` automáticamente transforma la apariencia de una capa en la de una tabla. De esta manera se consigue un diseño basado en columnas de manera muy sencilla sin tener que utilizar tablas reales (que, recordemos, no son recomendables).

Sin embargo, para tener un control total es necesario replicar la estructura de una tabla utilizando `divs`, por lo que se termina cayendo en el mismo error que al diseñar utilizando tablas.

```html
<div class="tableWrap">
  <div class="tableBlock">

    <div class="tableRow">
      <div class="tableCell"> </div>
      <div class="tableCell"> </div>
      <div class="tableCell"> </div>
    </div>

    <div class="tableRow">
      <div class="tableCell"> </div>
      <div class="tableCell"> </div>
      <div class="tableCell"> </div>
    </div>

  </div>
</div>
```

Ventajas:

-   Posibilidad de alineación vertical.
-   Permite crear capas de alturas iguales.

Desventajas:

-   Es necesario crear `<div>` adicionales para simular la estructura de las tablas. No obstante, la especificación indica que no es obligatorio.
-   Dependen del orden en que aparezcan las capas en el HTML.
-   Para separar las celdas no se pueden utilizar los márgenes: hay que utilizar la propiedad `border-collapse` del elemento padre.
-   Es posible que el contenido traspase los límites de las celdas.
-   Es difícil de adaptar para crear diseños responsivos con varios puntos de ruptura.
-   Problemas con IE6 y IE7.


## Cajas Flexibles (FlexBox) {#cajas-flexibles--flexbox}

**FlexBox** ofrece un mecanismo muy completo para realizar layouts. Tiene una gran variedad de opciones y es muy versátil. En este [videotutorial sobre Flexbox](https://youtu.be/DVtKcX6U4Ro) se explica su funcionamiento.

Los siguientes recursos también son muy interesantes:

-   <https://css-tricks.com/snippets/css/a-guide-to-flexbox/>
-   <https://developer.mozilla.org/es/docs/Web/Guide/CSS/Cajas%5Fflexibles>
-   <http://demo.agektmr.com/flexbox/>

Ventajas:

-   Independencia del orden en que aparezcan las capas en el HTML. Elimina la necesidad de utilizar JavaScript para esto.
-   Ofrecen alineación vertical.
-   Permiten crear capas con la misma altura.
-   Permiten la estructura en filas o columnas de manera sencilla.
-   Ofrecen una gran flexibilidad en cuanto a las opciones a utilizar.
-   Las cajas pueden ocupar automáticamente el espacio disponible, crecer o menguar a petición.

Desventajas:

-   Existe una especificación inicial que ha quedado desfasada (hay que tener cuidado al buscar tutoriales en Internet).
-   La sintaxis es algo compleja.
-   Es necesario utilizar prefijos para soportar todos los navegadores.
-   No es compatible con IE9 y anteriores.


## Grid layout {#grid-layout}

Su funcionamiento consiste en definir una serie de zonas dispuestas a modo de rejilla para a continuación asignar cada capa o sección a la zona correspondiente.

Tiene múltiples ventajas, entre las que destacan las siguientes:

-   **Eliminación** total de la necesidad de definir **capas contenedoras**. Bastará con tener una capa para cada área independiente de la página.
-   Independencia del orden en que aparezcan las capas en el HTML.
-   **Independencia completa** entre **HTML** y **presentación visual**.

Para aprender más sobre Grid Layout puedes consultar:

-   <https://css-tricks.com/snippets/css/complete-guide-grid/>
-   <https://www.w3schools.com/css/css%5Fgrid.asp>
-   <https://developer.mozilla.org/es/docs/Web/CSS/CSS%5FGrid%5FLayout/Conceptos%5FB%C3%A1sicos%5Fdel%5FPosicionamiento%5Fcon%5FRejillas>
-   <https://developer.mozilla.org/es/docs/Web/CSS/grid-template-areas>


## Algunos consejos de diseño {#algunos-consejos-de-diseño}

-   Los bloques que aparecen uno **debajo del otro no presentan problemas**: se muestran correctamente si son `display: block` (recordemos que estos elementos introducen saltos de línea, por lo que se muestran uno a continuación del otro).
-   El **problema** aparece cuando tenemos capas que deben aparecer a la **derecha o izquierda** de otras. En ese caso tendremos que utilizar alguno de los métodos propuestos.
-   La manera más sencilla de diseñar el layout consiste en hacer **agrupaciones por filas o columnas**:
    -   Se deben buscar las **filas** que lleguen a los extremos de las capas contenedoras.
    -   Dentro de cada fila se procederá a agrupar por **columnas** que lleguen a su vez a los extremos de los contenedores.
    -   Se continuará de esta manera (filas, columnas,...) hasta completar el diseño.

{{< figure src="/./disenyo_layout.png" alt="Agrupación por filas y columnas" caption="Figura 1: Agrupación por filas y columnas" link="../../images/02_02_disenyo.png" >}}

Por último, es recomendable pensar en el layout más adecuado para **dispositivos móviles** o pantallas pequeñas. Este tema será abordado con más detalle en otros artículos.

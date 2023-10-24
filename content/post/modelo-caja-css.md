+++
title = "Notas sobre el modelo de cajas en CSS"
date = 2019-10-21T11:47:00+02:00
tags = ["css", "modelo-caja"]
categories = ["diw", "diw-estilos-multimedia"]
draft = false
author = "Pedro Prieto"
+++

El [modelo de caja de CSS](https://developer.mozilla.org/es/docs/Web/CSS/CSS_Modelo_Caja/Introducci%C3%B3n_al_modelo_de_caja_de_CSS) tiene como objetivo definir el comportamiento de los elementos en HTML. En concreto define el **contenido**, **relleno**, **bordes** y **márgenes**. Se utiliza en gran medida para disponer los elementos en una estructura determinada (el denominado **layout**). En este artículo veremos un par de características relacionadas con él que pueden ser de mucha utilidad: la propiedad `box-sizing` y el comportamiento de la **anchura y altura** de las cajas.

<!--more-->


## La propiedad `box-sizing` {#la-propiedad-box-sizing}

Existe una propiedad en CSS3 denominada `box-sizing` que permite cambiar la definición de anchura para ésta que incluya el **contenido, relleno (padding) y bordes** (no se incluye el margen). En este [enlace](http://www.w3schools.com/cssref/css3_pr_box-sizing.asp) puedes consultar su funcionamiento. De esta manera, al utilizar el código `box-sizing: border-box;`, no habrá que hacer sumas para calcular el ancho total de las cajas.

Es habitual utilizar este código si se va a usar esta propiedad:

```css
* {
    box-sizing: border-box;
}
```


## Altura y anchura de los elementos {#altura-y-anchura-de-los-elementos}

La utilización de porcentajes en la definición de anchuras y alturas tiene algunas diferencias:

-   La **anchura** de los elementos es **independiente de su contenido**: depende del ancho del elemento contenedor o del ancho de la ventana del navegador en última instancia.
-   La **altura** de los elementos es **dependiente** de su contenido: si el contenido ocupa más espacio, la altura será mayor; si ocupa menos, será menor.

Debido a estas características, la utilización del **porcentaje** como unidad de medida varía: mientras que puede utilizarse **sin problemas en la anchura** aunque no se defina una anchura absoluta de base (ya que el 100% corresponde al ancho del contenedor), para que pueda utilizarse en la **altura** deberá definirse una **altura de referencia** en algún elemento **contenedor** para que pueda funcionar correctamente.

Para solucionar este problema puede utilizarse la unidad `vh` en lugar del porcentaje. Puedes encontrar la explicación en este [enlace](http://stackoverflow.com/questions/1622027/percentage-height-html-5-css).

A continuación se muestra un ejemplo de cómo especificar altura de capas: [ver ejemplo de altura de capas](http://jsbin.com/hajuki/edit?html,css,output).

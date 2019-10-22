+++
title = "Variables y preprocesadores CSS"
date = 2019-10-22T09:54:00+02:00
tags = ["css", "variables", "preprocesadores", "sass", "less"]
categories = ["diw", "diw-estilos-multimedia"]
draft = false
+++

En los últimos años han aparecido una gran cantidad de [preprocesadores CSS](https://developer.mozilla.org/es/docs/Glossary/Preprocesador%5FCSS) que permiten incorporar técnicas de lenguajes de programación (variables, anidamiento, [mixins](https://es.wikipedia.org/wiki/Mixin),...) a la creación de hojas de estilo. La desventaja que tienen es que el código debe **compilarse** para generar CSS válido que pueda ser utilizado por el navegador.

Frente a esto, es interesante conocer que CSS permite definir **variables** que pueden ser reutilizadas en todo el documento, proporcionando una alternativa sencilla y estándar, aunque lógicamente menos potente.

<!--more-->


## Preprocesadores CSS {#preprocesadores-css}

Los preprocesadores CSS permiten utilizar un lenguaje especial para definir código CSS. Dicho lenguaje depende del preprocesador elegido y suele ser muy parecido al CSS convencional.

El lenguaje debe ser **compilado** a CSS para que los navegadores puedan usarlo. A continuación podemos ver un ejemplo de **SASS**:

```sass
$font-stack:    Helvetica, sans-serif
$primary-color: #333

body
  font: 100% $font-stack
  color: $primary-color

nav
  ul
    margin: 0
    padding: 0
    list-style: none

  li
    display: inline-block

  a
    display: block
    padding: 6px 12px
    text-decoration: none
```

Y el resultado de la compilación en CSS:

```css
body {
  font: 100% Helvetica, sans-serif;
  color: #333;
}
nav ul {
  margin: 0;
  padding: 0;
  list-style: none;
}
nav li {
  display: inline-block;
}
nav a {
  display: block;
  padding: 6px 12px;
  text-decoration: none;
}
```

A continuación se enumeran algunos de los preprocesadores CSS más utilizados son:

-   [SASS](https://sass-lang.com/)
-   [LESS](http://lesscss.org/)
-   [PostCSS](https://postcss.org/)
-   [Stylus](http://stylus-lang.com/)


## Variables CSS {#variables-css}

Una de las características quizá más interesantes de utilizar un preprocesador CSS es la posibilidad de crear **variables** que puedan ser reutilizadas en el resto de la hoja de estilos. De esta manera se pueden definir determinados valores (por ejemplo, colores) para poder utilizarlos en múltiples clases CSS. Pensemos por ejemplo en la creación de una biblioteca de componentes CSS personalizados: puede ser interesante **parametrizar** determinados aspectos como el color o el color de fondo para diseñar distintos componentes (botones, menús, tablas,...) que muestren un aspecto visual común y que permitan una posterior personalización.

Es posible hacer uso de esta característica sin tener que recurrir a un preprocesador haciendo uso de las **[propiedades personalizadas CSS](https://developer.mozilla.org/es/docs/Web/CSS/Using%5FCSS%5Fcustom%5Fproperties)**. A continuación se muestra un ejemplo:

{{< highlight css "linenos=table, linenostart=1, hl_lines=2 7 16 23" >}}
:root {
  --color-fondo-principal: brown;
}

.uno {
  color: white;
  background-color: var(--color-fondo-principal);
  margin: 10px;
  width: 50px;
  height: 50px;
  display: inline-block;
}

.dos {
  color: white;
  background-color: var(--color-fondo-principal);
  margin: 10px;
  width: 75px;
}

.tres {
  color: white;
  background-color: var(--color-fondo-principal);
  margin: 10px;
  width: 100px;
}

{{< /highlight >}}

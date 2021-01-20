+++
title = "Conceptos básicos de CSS"
date = 2019-10-21T11:28:00+02:00
tags = ["css"]
categories = ["diw", "diw-estilos-multimedia"]
draft = false
+++

Este artículo tiene como objetivo ofrecer una introducción sobre **CSS**, explicar los tipos de hojas de estilo, el modelo de cascada y herencia, comprobar qué características están disponibles en los distintos navegadores y proporcionar una serie de recursos donde encontrar información más detallada.

<!--more-->


## Introducción {#introducción}

Las hojas de estilo en cascada **CSS** - _Cascade Style Sheet_ en inglés - se utilizan para **diseñar y dar formato** a las páginas web escritas con HTML. Las razones de su aparición son las siguientes:

-   **HTML** ofrece muy **pocas opciones** para dar formato al texto. Su función es estructurar el texto en secciones tales como tablas, listas, párrafos, etc., pero en cuanto a diseño visual resulta un tanto pobre.
-   El diseñador de páginas web se encontraba con archivos HTML extremadamente **liosos**, ya que en el mismo texto se agrupaban contenidos, estructuras e instrucciones de formato visual, por lo que su modificación y elaboración resultaba ser muy complicada.
-   La **modificación** del formato utilizado en un sitio web compuesto por un gran número de páginas resultaba **muy difícil**, ya que se tenían que cambiar manualmente los estilos de cada una de las páginas que formaban el sitio.

Frente a esta situación, el organismo W3C decidió crear un sistema por el que las **instrucciones de formato** se encontraran **separadas** de los otros elementos. Así, a partir de la versión 4 de HTML se desaconseja utilizar elementos de formato y se sugiere la utilización de las hojas de estilo en cascada o CSS.

Un ejemplo de las posibilidades que ofrecen las hojas de estilo se puede encontrar visitando la página [Zengarden](http://www.csszengarden.com/), donde se puede observar el efecto que produce en la misma página HTML utilizar una hoja de estilo u otra.


## Estructura modular {#estructura-modular}

La versión actual de CSS es **CSS 3**. Esta especificación se ha dividido en una serie de [módulos](https://en.wikipedia.org/wiki/Cascading%5FStyle%5FSheets#CSS%5F3) que son desarrollados por separado. Cada uno de dichos módulos hace referencia a una serie de funcionalidades (color, modelo de caja, fuentes, bordes, _layout_, _media queries_, selectores,...).


## Tipos de hojas de estilo {#tipos-de-hojas-de-estilo}

Una hoja de estilos contiene datos de formato relativos a los elementos definidos en la página HTML. Por lo tanto, ambos (documento HTML y hoja de estilo) deben estar relacionados de alguna manera. Existen tres maneras de utilizar hojas de estilo:

-   **Aplicar estilos directamente a elementos HTML**. De esta manera se escribe el código CSS dentro del atributo style de la etiqueta HTML en cuestión.Por ejemplo, para aplicar un estilo css a un párrafo:

<!--listend-->

```html
<p style="código_css">HOLA</p>
```

-   **Hojas de estilos internas**. Se utilizan para aplicar estilos a la página en la cual se utiliza. El código de la hoja de estilo se ubicará en la cabecera de la página web, entre las etiquetas siguientes:

<!--listend-->

```html
<style type="text/css">
        <!--  Código_css  -->
</style>
```

-   **Hojas de estilos externas**. Se utilizan para aplicar el mismo formato a varias páginas de un portal. Se definen en un archivo externo que será consultado por todas las páginas HTML del sitio web, reutilizando por tanto el código. Para ello se escribirá el código CSS en un documento externo con extensión css. Posteriormente se vinculará a la página web mediante la utilización de la siguiente **etiqueta** en la **cabecera** del documento HTML en cuestión:

<!--listend-->

```html
<link rel="stylesheet" type="text/css" href="nombre_archivo_css.css">
```


## Cascada y herencia {#cascada-y-herencia}

CSS permite definir estilos en varios sitios, tal como hemos visto en el punto anterior. Además, es posible que un elemento reciba estilos de varios orígenes distintos. Algunos ejemplos de ello son:

-   Un elemento tiene asignado un nombre de clase y un identificador. En la hoja de estilos se definen estilos para dicho identificador y dicho nombre de clase.
-   Un elemento hereda el valor de una propiedad definida en alguno de los elementos que lo contienen.
-   Un elemento recibe un estilo de una hoja externa, de una hoja interna y de un estilo aplicado directamente en la etiqueta.

En casos como los descritos, ¿cómo se resuelven los conflictos si se definen valores distintos para la misma propiedad? ¿Son más importantes los estilos definidos para nombres de clase? ¿Los definidos en hojas internas?

La regla general es la siguiente: **los estilos aplicados a selectores más concretos tienen mayor peso que los aplicados a selectores más generales**. En caso de empate, el **último** estilo que se aplica es el que prevalece (las hojas de estilo externas se considera que se cargan antes que las hojas de estilo internas).

En concreto, el procedimiento que se aplica es el siguiente (fuente: <https://www.w3.org/TR/CSS22/cascade.html#cascade>):

-   Se cuenta 1 si la declaración está incluida en un atributo `style`; si no, se cuenta 0. (Peso "**a**", mayor importancia).
-   Se cuenta el número de identificadores (ID) que aparezcan en el selector. (Peso "**b**").
-   Se cuenta el número de atributos (distintos al ID) , clases y pseudo-clases en el selector. (Peso "**c**").
-   Se cuenta el número de nombres de elementos y pseudo-elementos en el selector. (Peso "**d**", menor importancia).

Para determinar qué estilo se aplica en caso de conflicto se mira el resultado: el número más alto en la casilla de mayor peso es el que se aplica; en caso de empate, se comprueban los números de los pesos más bajos sucesivamente.

```html
 *             {}  /* a=0 b=0 c=0 d=0 -> especificidad = 0,0,0,0 */
 li            {}  /* a=0 b=0 c=0 d=1 -> especificidad = 0,0,0,1 */
 li:first-line {}  /* a=0 b=0 c=0 d=2 -> especificidad = 0,0,0,2 */
 ul li         {}  /* a=0 b=0 c=0 d=2 -> especificidad = 0,0,0,2 */
 ul ol+li      {}  /* a=0 b=0 c=0 d=3 -> especificidad = 0,0,0,3 */
 h1 + *[rel=up]{}  /* a=0 b=0 c=1 d=1 -> especificidad = 0,0,1,1 */
 ul ol li.red  {}  /* a=0 b=0 c=1 d=3 -> especificidad = 0,0,1,3 */
 li.red.level  {}  /* a=0 b=0 c=2 d=1 -> especificidad = 0,0,2,1 */
 #x34y         {}  /* a=0 b=1 c=0 d=0 -> especificidad = 0,1,0,0 */
 style=""          /* a=1 b=0 c=0 d=0 -> especificidad = 1,0,0,0 .
                      Éste último es el que se aplica.*/

<head>
  <style type="text/css">
    #x97z { color: red }
  </style>
  </head>
<body>
  <p id="x97z" style="color: green">
</body>
```

En el ejemplo, el párrafo tendrá color verde, ya que el valor de su peso "a" es 1. Como el peso "a" es el más importante, es el que se impone a los demás.


### !important {#important}

Existe una manera de sobreescribir estilos CSS sin importar las reglas de especificidad: añadiendo `!important` a la regla correspondiente:

```css
p {
    color: red !important;
}
#parrafo1 {
    color: green;
}
```

```html
<p id="parrafo1">Será ROJO a pesar de que la regla es menos específica</p>
```


## Hojas de estilo alternativas {#hojas-de-estilo-alternativas}

Es posible incluir más de una hoja de estilo en un sitio web y ofrecer al usuario la posibilidad de usar una u otra mediante el uso de **hojas de estilo alternativas**.

Algunos navegadores (como Firefox) permiten seleccionar la hoja de estilos a través de sus menús (en Firefox, menú _Ver_ / _Estilo de página_).

Para incluir hojas de estilo alternativas se debe utilizar la etiqueta `<link rel="alternate stylesheet">`. A continuación se muestra un ejemplo:

```html
<link rel="stylesheet"
      title="Estilo principal"
      href="./css/estilos.css">

<link rel="alternate stylesheet"
      title="Estilo alternativo 1"
      href="./css/estilos1.css">

<link rel="alternate stylesheet"
      title="Estilo alternativo 2"
      href="./css/estilos2.css">
```


## Compatibilidad entre navegadores {#compatibilidad-entre-navegadores}

En ocasiones es difícil saber si una determinada propiedad CSS, sobre todo las más recientes, es compatible con una determinada versión de navegador. Para ello son muy útiles los siguientes enlaces:

-   [Can I Use? (¿Puedo utilizar...?)](http://caniuse.com/)
-   [Tabla de compatibilidad de propiedades CSS con los principales navegadores](http://www.w3schools.com/cssref/css3%5Fbrowsersupport.asp)


## Recomendaciones de diseño con CSS {#recomendaciones-de-diseño-con-css}

En el diseño de interfaces es recomendable definir **clases de estilos** para aplicar a determinadas secciones, elementos destacados, etc. De esta manera se conseguirá un código altamente **modular** que permitirá realizar cambios tanto de apariencia como de estructura con relativa facilidad.

Por tanto, se intentará **priorizar el uso de clases** por encima del uso de selectores basados en nombres o agrupaciones de elementos. En [este artículo](/post/estrategias_diseno_css/) se intenta entrar más en detalle sobre el tema.


## Enlaces de referencia de CSS {#enlaces-de-referencia-de-css}

-   [Curso de CSS de Mozilla](https://developer.mozilla.org/es/docs/Learn/CSS) - Excelente curso de CSS de la Fundación Mozilla
-   [Cursos de CSS en desarrolloweb.com](https://desarrolloweb.com/home/css) - Cursos completos de CSS
-   [Tutorial CSS en W3Schools](https://www.w3schools.com/css/default.asp) - Tutorial completo sobre CSS
-   [W3Schools howtos](http://w3schools.com/howto/) - Recetas para crear componentes en CSS
-   [CSS Tricks](https://css-tricks.com) - Sitio web con infinidad de recursos
-   [CSSScript.com](https://www.cssscript.com) - Más recursos CSS
-   [Guía de referencia de propiedades CSS](http://www.w3schools.com/cssref/) - Listado de propiedades CSS
-   <http://librosweb.es/css/> - Curso completo de CSS pero algo anticuado
-   <https://www.websiteplanet.com/blog/html-guide-beginners/> - Conceptos básicos de HTML

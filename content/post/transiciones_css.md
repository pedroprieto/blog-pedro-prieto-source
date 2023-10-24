+++
title = "Transformaciones, transiciones y animaciones en CSS"
date = 2019-11-12T00:09:00+01:00
tags = ["css", "animaciones", "transiciones", "transformaciones"]
categories = ["diw", "diw-estilos-multimedia"]
draft = false
author = "Pedro Prieto"
+++

En este artículo estudiaremos las herramientas disponibles en CSS para crear transformaciones, transiciones y animaciones.

<!--more-->


## Transformaciones {#transformaciones}

Las transformaciones CSS permiten **mover**, **rotar**, **escalar** o **inclinar** elementos. CSS permite realizar transformaciones **2D** y **3D**.

Las transformaciones en principio son **estáticas**: es decir, no están animadas (aunque pueden estarlo mediante transiciones o animaciones). Un ejemplo de transformación sería el siguiente:

```css
#div1 {
  transform: rotate(20deg); /* Rotación 2D de 20º */
}

#div2 {
    transform: rotateY(150deg); /* Rotación 3D de 150º en el eje Y */
}
```

En este enlace puede verse un [ejemplo de rotación 2D](https://www.w3schools.com/css/tryit.asp?filename=trycss3_transform_rotate). En este otro puede verse un [ejemplo de rotación 3D](https://www.w3schools.com/css/tryit.asp?filename=trycss3_transform_rotateY).

En los siguientes enlaces puede consultarse información más detallada sobre las distintas transformaciones que pueden realizarse en CSS:

-   [Transformaciones 2D](https://www.w3schools.com/css/css3_2dtransforms.asp)
-   [Transformaciones 3D](https://www.w3schools.com/css/css3_3dtransforms.asp)


## Transiciones {#transiciones}

Las **transiciones CSS** permiten realizar **cambios graduales de determinadas propiedades con una duración determinada**. Para definir una transición es necesario especificar:

1.  La(s) propiedad(es) a animar
2.  La duración de la transición
3.  Opcionalmente, el retraso y la curva de velocidad de la transición

Es importante tener claro que la transición se ejecutará **cuando se produzca un cambio en el valor de la propiedad definida en la transición**. Por ejemplo, si se define una transición para la propiedad `width` de una capa, la transición se producirá cuando se realice un cambio en la anchura de dicha capa. Los cambios de valor de la propiedad pueden realizarse básicamente de **dos maneras**:

1.  A través de una [pseudo-clase](https://www.w3schools.com/css/css_pseudo_classes.asp) (como por ejemplo, `:hover`, que se activa al pasar el ratón por encima)
2.  A través de JavaScript

Por último, hay que tener en cuenta que **solo se pueden realizar transiciones (y animaciones) sobre propiedades CSS que sean [animables](https://www.w3schools.com/cssref/css_animatable.asp)**.

A continuación se muestra un ejemplo de transición de la propiedad `width` de una capa (en este enlace puede verse el [ejemplo en ejecución](https://www.w3schools.com/css/tryit.asp?filename=trycss3_transition1)):

```css
div {
  width: 100px;
  height: 100px;
  background: red;
  transition: width 2s;
}

div:hover {
  width: 300px;
}
```

En el ejemplo se ha definido una transición para la propiedad `width` con una duración de 2 segundos. Cuando cambie el valor de dicha propiedad, el cambio no se realizará bruscamente, sino que se realizará **progresivamente hasta alcanzar el nuevo valor pasados 2 segundos**. En este caso el cambio de valor de `width` se produce al pasar el ratón por encima de la capa, aunque también funcionaría si se cambia el valor de dicha propiedad `width` a través de JavaScript.

A continuación se muestra un [ejemplo de transición con pseudo-clases y JavaScript](https://jsbin.com/qugopah/1/edit?html,css,js,output).

En el siguiente enlace puede consultarse más [información sobre transiciones CSS](https://www.w3schools.com/css/css3_transitions.asp).


## Animaciones {#animaciones}

Las animaciones CSS permiten ejecutar **cambios de estilos** sobre un determinado elemento de manera **gradual** a través de una serie de **estados** denominados **fotogramas clave (keyframes)**.

Un ejemplo de animación sería el siguiente:

```css
/* Definición de la animación */
@keyframes cambios{
    0% {
        background-color: red;
        width: 100px;
    }
    25% {
        background-color: yellow;
        width: 50px;
        transform: translate(0, 100px);
    }
    50% {
        background-color: blue;
        width: 100px;
        transform: translate(100px, 100px);

    }
    75% {
        background-color: blue;
        width: 150px;
        transform: translate(100px, 0);

    }
    100% {
        background-color: red;
        width: 100px;
        transform: translate(0, 0);

    }
}
/* Elemento que recibe la animación */
div {
    width: 100px;
    height: 100px;
    background-color: red;
    animation-name: cambios;
    animation-duration: 4s;
    animation-iteration-count: infinite;
}
```

El funcionamiento del ejemplo se describe a continuación:

-   En primer lugar se definen los fotogramas clave mediante `@keyframes` indicando el nombre de la animación (`cambios`).
-   En este caso se definen 5 fotogramas clave que representan los estilos deseados en los instantes de tiempo definidos en porcentajes.
-   En cada fotograma clave es posible definir varios estilos.
-   Los cambios de estilos entre fotogramas clave se realizan progresivamente mediante **transiciones**.
-   Por último, se asigna la animación a la capa deseada mediante la propiedad `animation-name` indicando el nombre de la animación definida con anterioridad (`cambios`) y se especifica un tiempo mediante `animation-duration`.
-   Opcionalmente se pueden definir el número de veces que se ejecutará la animación con `animation-iteration-count`.

Para obtener más información sobre animaciones pueden consultarse los siguientes enlaces:

-   <https://www.w3schools.com/css/css3_animations.asp>
-   <https://developer.mozilla.org/es/docs/Web/CSS/@keyframes>

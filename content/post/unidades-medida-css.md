+++
title = "Unidades de medida"
date = 2019-10-21T12:28:00+02:00
tags = ["css", "medida", "unidades", "viewport"]
categories = ["diw", "diw-estilos-multimedia"]
draft = false
+++

En este artículo estudiaremos las unidades de medida más utilizadas en CSS, así como las diferencias más importantes entre las unidades **relativas** y las unidades **absolutas**.

<!--more-->

CSS define distintas unidades para representar medidas. Dichas unidades se pueden consultar en el siguiente enlace: [unidades CSS 2.1](http://www.w3schools.com/cssref/css%5Funits.asp).

CSS 3 define algunas unidades adicionales: [unidades CSS 3](http://www.w3.org/TR/css3-values/).

El uso de una u otra unidad vendrá marcado por el tipo de **pantalla objetivo** (referencia: [aquí](http://www.w3.org/Style/Examples/007/units)):

|           | Recomendado               | Uso ocasional | No recomendado     |
|-----------|---------------------------|---------------|--------------------|
| Pantalla  | em, px, %                 | ex            | pt, cm, mm, in, pc |
| Impresión | em, cm, mm, in, pt, pc, % | px, ex        |                    |

A continuación veremos un pequeño resumen de las características de las unidades más utilizadas.


## Unidades absolutas {#unidades-absolutas}

Las unidades absolutas se pueden consultar en este enlace: [unidades absolutas](http://www.w3.org/TR/css3-values/#absolute-lengths).

| unidad | definición                     |
|--------|--------------------------------|
| ‘cm’   | centímetro                     |
| ‘mm’   | milímetros                     |
| ‘in’   | pulgadas (1in = 2.54cm)        |
| ‘px’   | píxeles (1px = 1/96in)         |
| ‘pt’   | puntos (1pt = 1/72in = 0.35mm) |
| ‘pc’   | picas (1pc = 12pt = 4.23mm)    |

La relación entre unidades de medida es la siguiente: 1in = 2.54cm = 25.4mm = 72pt = 6pc

En general se utilizarán las unidades absolutas cuando se pretenda determinar el **tamaño exacto** que tendrán los elementos. Estas unidades son especialmente útiles para definir el **tamaño de imágenes** o capas que queremos que ocupen exactamente el tamaño de una imagen.

Estas unidades son también útiles para definir estilos para **hojas impresas** (por ejemplo, para especificar el tamaño de una fuente en puntos).

El inconveniente de estas unidades es que **no se adaptan bien a tipos de pantalla distintos** (móviles, tabletas,...) o de distintos tamaños.


## Unidades relativas {#unidades-relativas}

Las unidades relativas se pueden consultar en este enlace: [unidades relativas](http://www.w3.org/TR/css3-values/#relative-lengths). Las unidades relativas expresan tamaños en función de otros.

| unidad | relativa a                                              |
|--------|---------------------------------------------------------|
| ‘em’   | tamaño de letra del elemento                            |
| ‘ex’   | altura del carácter 'x' del tipo de letra del elemento  |
| ‘ch’   | anchura del carácter '0' del tipo de letra del elemento |
| ‘rem’  | tamaño de letra del elemento raíz                       |
| ‘vw’   | 1% de la anchura del viewport                           |
| ‘vh’   | 1% de la altura del viewport                            |
| ‘vmin’ | 1% de la dimensión más pequeña del viewport             |
| ‘vmax’ | 1% de la dimensión más alta del viewport                |

La ventaja de utilizar estas unidades es que se **adaptan muy bien a distintos tipos y tamaños de pantalla**.

El valor de las medidas relativas no se hereda directamente, sino que se hereda su **valor real una vez calculado**.

A continuación estudiaremos las características de las unidades más utilizadas.


### Unidad 'em' {#unidad-em}

Esta unidad hace referencia al **tamaño de letra calculado heredado por el elemento**. Por tanto, para calcular el valor real aplicado habrá que determinar los **valores que se van heredando** de los elementos **contenedores**. A continuación se muestra un ejemplo:

```css
html {
  font-size: 12px;
  text-indent: 1em; /* 1em = 12px */
}

p {                 /* Hereda 1em = 12px; */
  font-size: 0.5em; /* Tamaño = 6px */
}

p span {            /* Hereda 1em = 6px */
  font-size: 0.5em; /* Tamaño = 3px */
}
```


### Unidad 'rem' {#unidad-rem}

Esta unidad tiene una **referencia fija**, que es el **tamaño de letra definido en el elemento raíz**. Por tanto, para calcular el valor real aplicado simplemente hay que mirar el elemento raíz. A continuación se muestra un ejemplo:

```css
html {
  font-size: 12px;
  text-indent: 1rem; /* 1em = 12px */
}

p {
  font-size: 0.5rem; /* Tamaño = 6px */
}

p span {
  font-size: 0.5rem; /* Tamaño = 6px */
}
```

Estas unidades simplifican los cálculos al tener una referencia fija (no hay que ir calculando valores heredados de los elementos contenedores).


### Porcentaje {#porcentaje}

El porcentaje suele tomarse como una unidad relativa más. Un porcentaje de un 100% hace referencia al tamaño calculado del elemento contenedor (un tamaño de un 100% en un tipo de letra hace referencia al tamaño del tipo de letra aplicado en el elemento contenedor). Por tanto, para calcular el valor real aplicado habrá que determinar los **valores que se van heredando** de los elementos **contenedores**. A continuación se muestra un ejemplo:

```css
body {
  width: 1024px; /* 100% = 1024px */
}

div {            /* Hereda 100% = 1024px */
  width: 50%;    /* Anchura = 512px */
}

div div {        /* Hereda 100% = 512px */
  width: 50%;    /* Anchura = 256px */
}
```


### Unidades 'vw', 'vh', 'vmin' y 'vmax' {#unidades-vw-vh-vmin-y-vmax}

Estas unidades hacen referencia al tamaño del **[viewport](https://www.w3schools.com/css/css%5Frwd%5Fviewport.asp)**. CSS define el _viewport_ como el **tamaño del área que se utiliza para representar la página web**. Coincide con el `<body>` incluyendo los márgenes. Es importante indicar que en los **navegadores móviles** el _viewport_ tiene un **tamaño superior al tamaño real** de la pantalla: es por ello que las páginas web se muestran completas como vistas desde un zoom de alejamiento (este tema será tratado con más detalle más adelante).

Estas unidades tienen una **referencia fija**, que es el ancho ('vw'), alto ('vh'), dimensión más pequeña ('vmin') o dimensión más grande ('vmax') del _viewport_. Por tanto, para calcular el valor real aplicado simplemente hay que mirar el elemento raíz. A continuación se muestra un ejemplo:

```css
/* Suponemos que el ancho de la pantalla
del dispositivo es de 1024px, por lo que
100vw = 1024px */

div {            /* 1vw = 1024/100 */
  width: 50vw;   /* Anchura = 512px */
}

div div {         /* 1vw = 1024/100 */
  width: 50vw;    /* Anchura = 512px */
}
```

Como ocurre con las unidades 'rem', las unidades relativas al _viewport_ simplifican los cálculos al tener una referencia fija.

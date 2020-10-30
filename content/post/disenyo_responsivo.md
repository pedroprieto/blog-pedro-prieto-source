+++
title = "Diseño responsivo"
date = 2019-11-04T12:44:00+01:00
tags = ["css", "responsive"]
categories = ["diw", "diw-estilos-multimedia"]
draft = false
+++

En este artículo trataremos los fundamentos del diseño web adaptable o adaptativo (_Responsive Web Design_ en inglés).

<!--more-->

> El diseño web adaptable (también **diseño web adaptativo** o **responsivo**; este último calco del inglés _responsive web design_), es una filosofía de diseño y desarrollo cuyo objetivo es adaptar la apariencia de las páginas web al dispositivo que se esté utilizando para visitarlas. Hoy día las páginas web se ven en multitud de dispositivos como tabletas, teléfonos inteligentes, libros electrónicos, portátiles, PC, etcétera. Además, aún dentro de cada tipo, cada dispositivo tiene sus características concretas: tamaño de pantalla, resolución, potencia de CPU, sistema operativo o capacidad de memoria entre otras. Esta tecnología pretende que con un único diseño web, todo se vea correctamente en cualquier dispositivo. ---_Fuente: [Wikipedia](https://es.wikipedia.org/wiki/Dise%C3%B1o%5Fweb%5Fadaptable)_


## Mobile First {#mobile-first}

La tendencia actual consiste en diseñar siguiendo la filosofía **Mobile First**, o _Móvil primero_. Esta teoría aboga por **realizar el diseño pensando en dispositivos móviles** y posteriormente añadir o modificar características para adaptar el diseño a otro tipo de dispositivos y pantallas.

La justificación de esta metodología está en que es necesario abordar en primer lugar un **diseño que pueda funcionar en los dispositivos con mayores limitaciones**: tamaños pequeños de pantalla, menor potencia de proceso o menor velocidad de conexión. Los dispositivos móviles, pese a su desarrollo en los últimos años, son los más afectados por dichas limitaciones, sobre todo la relacionada con el tamaño de pantalla. Un diseño que se ajuste a estos dispositivos funcionará sin problemas en el resto, por lo que se trata de un **diseño universal**.

Una vez garantizado que el diseño base es capaz de funcionar en todos los dispositivos independientemente de sus limitaciones, se puede proceder a **enriquecer** el diseño de manera que ofrezca **más funcionalidades** o **aproveche mejor las características del resto de dispositivos**. Dichas mejoras **solo serán visibles en los dispositivos que puedan aprovecharlas** y **no afectarán negativamente** en ningún caso al diseño base.

Puedes consultar información más detallada sobre la filosofía _Mobile First_ en estos enlaces:

-   [Qué es mobile first y cómo puede mejorar tu posicionamiento](https://www.initcoms.com/que-es-mobile-first-posicionamiento/)


## Dispositivos y resoluciones de pantalla {#dispositivos-y-resoluciones-de-pantalla}

A continuación vamos a explicar algunos conceptos relacionados con las resoluciones de pantalla de los dispositivos y cómo afectan al Desarrollo Web, en concreto al diseño con CSS.


### Resolución nativa {#resolución-nativa}

Cada dispositivo (móvil, tablet, monitor, televisión,...) tiene una **resolución nativa** (también llamada **física**) indicada en sus especificaciones. Esta resolución se expresa en el formato `anchura x altura` (por ejemplo, 1024 x 768 píxeles).


### Resolución CSS (`device-width`) {#resolución-css--device-width}

Sin embargo, la **resolución nativa no se suele utilizar como referencia en CSS** en dispositivos que no sean monitores o pantallas convencionales. Esto es debido a que determinados **dispositivos**, como teléfonos móviles o tablets, tienen un **tamaño de pantalla muy pequeño**. Por hacernos una idea, el tamaño de letra por defecto en los navegadores es de 16px. Este tamaño de letra puede ser aceptable en un monitor con una resolución 1440x900 con un tamaño de pantalla de 22 pulgadas, pero resultaría muy pequeño en un teléfono de resolución 1920x1024 de 5 pulgadas.

Por tanto, en lugar de tomar la resolución física o nativa como referencia, se toma como referencia otro valor denominado **resolución CSS** (anchura CSS, también llamada _CSS width_ o `device-width`, y altura CSS o _CSS height_). Esta resolución está ajustada al tamaño del dispositivo, por lo que el **tamaño del texto** y los elementos en general será adecuado para una correcta visualización.

En <http://mydevice.io/devices/> puedes consultar una lista con las resoluciones CSS de los dispositivos más conocidos.


### El _ViewPort_ {#el-viewport}

Por último, existe un tercer valor de resolución utilizado en el diseño web, que es la resolución del _ViewPort_. El _ViewPort_ se corresponde con el **ancho de la pantalla del navegador web**.

Este concepto fue desarrollado por Apple en el iPhone y tenía como objetivo solucionar el problema del tamaño de la pantalla a la hora de visualizar páginas web. Consiste en **hacer creer al navegador** que el **ancho de la pantalla es mayor que su anchura CSS**. De esta manera las **páginas web** se podrán **mostrar exactamente igual que en navegadores de escritorio** pero aparecerán con un tamaño más pequeño, como si se hubiera hecho un **zoom de alejamiento**. De esta manera consiguieron que la navegación a través del móvil fuera igual que la de escritorio, con la pequeña diferencia del zoom.

{{< figure src="/./viewport.png" caption="Figura 1: Viewport" >}}

Es importante dejar claro que la resolución del _ViewPort_ es **distinta de la resolución física y la resolución CSS**. En los sistemas **Android** el ancho es de **800px** y en los sistemas **iOS** es de **980px**.


### Etiqueta `<meta name="viewport">` {#etiqueta-meta-name-viewport}

En el diseño adaptativo se busca que la apariencia visual de la página web esté ajustada al tamaño de la pantalla. Para ello se utiliza la etiqueta [meta name="viewport"](https://developer.mozilla.org/es/docs/M%C3%B3vil/Viewport%5Fmeta%5Ftag). Esta etiqueta sirve para **indicar al navegador** qué **tamaño** debe definir para su _ViewPort_. En la mayoría de ocasiones utilizaremos la etiqueta de la siguiente manera:

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

Este código indica al navegador que debe utilizar la **anchura CSS** (`width=device-width`) como ancho del _ViewPort_. De esta manera las páginas se adaptarán a una resolución adecuada para el tamaño de pantalla del dispositivo.

> **¡IMPORTANTE!** Esta etiqueta **sólo debe utilizarse** con diseños web **optimizados para móvil** o diseños web **adaptativos**. Si la página no está adaptada para móvil no se debe usar, ya que se visualizaría de manera incorrecta.

Puedes consultar más información relacionada con esta etiqueta en este [artículo sobre ViewPort en MDN](https://developer.mozilla.org/es/docs/M%C3%B3vil/Viewport%5Fmeta%5Ftag).


## Media queries {#media-queries}

Las _media queries_ son expresiones que se utilizan en CSS3 para **identificar el dispositivo** al que va dirigido un determinado **conjunto de reglas de estilo CSS**.

Una _media query_ es una **expresión lógica** que sólo puede tomar dos valores: verdadero o falso. Si la expresión es **verdadera**, el **conjunto de reglas** de estilo definidas en su interior se **aplica**; si es falsa, no se aplica.

Cada expresión _media query_ está formada por un **tipo de medio** (_Media Type_) y cero o más **características del medio** para comprobar las características concretas del dispositivo.


### Tipos de medio (Media Types) {#tipos-de-medio--media-types}

Un _Media Type_ define un tipo de dispositivo. Los tipos de medio disponibles actualmente son:

-   `all`. Se utiliza para hacer referencia a **todos los dispositivos**. Si no se indica ningún _media type_ es el que se utiliza **por defecto**.
-   `screen`. Se utiliza para hacer referencia a **pantallas** (móvil, tabletas, ordenadores, portátiles,...).
-   `print`. Se utiliza para hacer referencia a **impresoras**. Define las reglas de estilo que se aplicarán al imprimir la página.
-   `speech`. Se utiliza para hacer referencia a **sintetizadores de voz**.


### Características del medio (Media Features) {#características-del-medio--media-features}

Se pueden utilizar expresiones adicionales al _Media Type_ para **determinar de manera más concreta las características del dispositivo**. Algunas de las características más utilizadas son:

-   `width` - Indica la **anchura** del _ViewPort_ del dispositivo. Sólo se incluyen los dispositivos cuya anchura del _ViewPort_ se corresponda con la indicada.
-   `max-width` - Indica la anchura máxima del _ViewPort_ del dispositivo. Los dispositivos con una anchura del _ViewPort_ **igual o inferior** a la indicada estarán incluidos en la regla.
-   `min-width` - Indica la anchura mínima del _ViewPort_ del dispositivo. Los dispositivos con una anchura del _ViewPort_ **igual o superior** a la indicada estarán incluidos en la regla.

Existe otra propiedad relacionada con la anchura de los dispositivos denominada `device-width`, pero en el borrador más reciente de la especificación [han sido declaradas obsoletas](https://drafts.csswg.org/mediaqueries-4/#mf-deprecated).

En este enlace se puede consultar todas las [Características del medio disponibles](https://developer.mozilla.org/es/docs/CSS/Media%5Fqueries#Funciones%5FMultimedia).


### Sintaxis {#sintaxis}

Para definir una _Media Query_ se sigue la siguiente sintaxis en CSS:

```css
@media mediatype and|not|only (media_feature) {
   Código CSS;
}
```

También es posible definir que una determinada hoja de estilos se aplique para un determinado tipo de medios. En este caso, el código a incluir sería:

```html
<link rel="stylesheet" media="mediatype and|not|only (media_feature)" href="estilos.css">
```


### Ejemplo {#ejemplo}

A continuación se muestra un ejemplo de uso de _Media Queries_:

```css
/* Estilos Mobile First: se aplican por defecto a todos los tamaños de pantalla */
/* Como se puede ver, no están dentro de ninguna Media Query */
body {
    background-color: lightblue;
}
p {
    color: black;
}

/* Estilos para pantallas de anchura CSS mínima 300px */
@media screen and (min-width: 300px) {
    body {
        background-color: green;
    }

    p {
        color: white;
    }
}

/* Estilos para pantallas de anchura CSS de más de 700px*/
@media screen and (min-width:701px) {
    body {
        background-color: red;
    }
    p {
        color: white;
    }
}
```

En el siguiente enlace puedes ver el [ejemplo anterior funcionando](https://jsbin.com/cemaqos/edit?html,css,output) (cambia el tamaño de la ventana de salida para comprobar los cambios).


### Mobile First y Media Queries {#mobile-first-y-media-queries}

Tal como se puede ver en el ejemplo anterior, se ha tenido en cuenta la filosofía **Mobile First** para realizar el diseño con Media Queries:

-   En primer lugar, se han definido unos estilos de base **que no están dentro de ninguna Media Query**. Dichos estilos son los estilos que se aplicarán a todos los dispositivos y que **deben estar pensados para dispositivos móviles o de pantalla pequeña**. En esta sección estará el **layout** para **vista móvil** y en general todos los estilos apropiados para dichos dispositivos. Normalmente las distintas secciones de la web (menús, cabeceras, contenido,...) se suelen disponer **en una única columna** para favorecer la usabilidad en este tipo de dispositivos.
-   A continuación se ha definido una Media Query con una **anchura mínima** de 300px. En esa Media Query se incluirán los estilos que se necesiten **añadir o cambiar** para adecuar la vista a dispositivos con un tamaño de pantalla intermedio. Estos estilos **solo serán utilizados por dispositivos con esa anchura mínima** de pantalla. Por tanto, será en el interior de esta Media Query donde incluiremos posibles cambios en el **layout** para cambiar la disposición de los elementos principales de nuestra web y que se vean de otra manera para pantallas de tamaño medio (por ejemplo, capas posicionadas en dos o más columnas).
-   Por último, se ha definido una Media Query con una **anchura mínima** de 700px. Aquí se incluirán los estilos que se necesiten **añadir o cambiar** para adecuar la vista a dispositivos con un tamaño de pantalla grande.

Algunos **consejos importantes** a tener en cuenta para diseñar con **Media Queries y Mobile First**:

-   Crear los **estilos de base fuera de cualquier Media Query**.
-   Crear un layout de **columna única** para el estilo de base. Dado que HTML posiciona automáticamente los elementos `<div>` uno debajo de otro, **no es necesario utilizar ninguna técnica específica de layout (`flexbox`, `grid`) en los estilos de base**.
-   Utilizar `min-width` y no `max-width` para las Media Queries. De esta manera se asegura realizar los cambios de pantallas más pequeñas a pantallas más grandes.
-   Utilizar tantos **cortes de resolución** como se necesiten. Normalmente se utilizan 2 ó 3 cortes, pero pueden utilizarse más. En este enlace pueden consultarse los [cortes de resolución utilizados por la librería Bootstrap](https://getbootstrap.com/docs/4.3/layout/overview/#responsive-breakpoints).
-   Si se utiliza solo `min-width` es necesario recordar que los estilos definidos tanto fuera de las Media Queries como en las Media Queries que hagan referencia a tamaños inferiores se **siguen aplicando**.

A continuación puedes ver un [ejemplo con estilos definidos en varias Media Queries](https://jsbin.com/ketaqer/edit?html,css,output) (cambia el tamaño de la ventana de salida para ver cómo cambia la apariencia en función de la resolución).


### Más información {#más-información}

En los siguientes enlaces puede consultarse más información sobre Media Queries:

-   [CSS Media Queries en MDN](https://developer.mozilla.org/es/docs/CSS/Media%5Fqueries)
-   [CSS Media Queries Examples en W3Schools](https://www.w3schools.com/css/css3%5Fmediaqueries%5Fex.asp)


### Curiosidad: Modelo de Rejilla {#curiosidad-modelo-de-rejilla}

Muchos diseños actuales se basan en el **modelo de rejilla**. Básicamente consiste en dividir la página en un número de columnas (usualmente 12) y disponer las capas de manera que ocupen un número de columnas determinado. Este tipo de diseños se suele combinar con _media queries_ para realizar diseños responsivos.

A continuación se muestran dos enlaces con información más detallada sobre este tema:

-   [Tutorial de diseño basado en rejilla](https://www.w3schools.com/css/css%5Frwd%5Fgrid.asp).
-   [Cómo combinar el diseño en rejilla con _media queries_ para realizar diseños reponsivos](https://www.w3schools.com/css/css%5Frwd%5Fmediaqueries.asp).


### Curiosidad: Font boosting (Chrome Mobile) {#curiosidad-font-boosting--chrome-mobile}

El navegador Chrome para móviles **cambia el tamaño de la letra** de algunos **elementos de bloque** en función de la **altura** de los mismos para favorecer su legibilidad. Esta característica hace que los estilos que se muestran no coincidan en ocasiones con los estilos establecidos en las hojas de estilo.

Para **desactivar** esta característica basta con **especificar una altura** (`height`) o altura máxima (`max-height`) a la capa en cuestión.

Para desactivarlo de manera global basta con establecer una altura máxima con un valor muy grande a nivel global.

```css
html * {
    max-height:1000000px;
}
```

Para más información puedes consultar los siguientes artículos de _Stack Overflow_:

-   <http://stackoverflow.com/questions/11289166/chrome-on-android-resizes-font>
-   <http://stackoverflow.com/questions/13430897/how-to-override-font-boosting-in-mobile-chrome>


## Simulación de tamaños de pantalla {#simulación-de-tamaños-de-pantalla}

Las [herramientas de desarrollo de los navegadores](/post/herramientas-desarrollo/#herramientas-de-desarrollo-de-navegadores) incorporan un modo de **Vista de Diseño Adaptable** para simular cómo se verá la página en distintos tamaños de pantalla:

-   [Responsive Design View (Firefox)](https://developer.mozilla.org/es/docs/Tools/Responsive%5FDesign%5FView)
-   [Device Mode (Chrome)](https://developers.google.com/web/tools/chrome-devtools/device-mode/)

Es importante saber que en última instancia el mejor test siempre es **comprobar la apariencia visual desde un dispositivo nativo** (tablet, teléfono móvil,..).


## Evolución futura {#evolución-futura}

Las tendencias actuales en el campo del diseño adaptativo van enfocadas a **personalizar el código que proporciona el servidor** en función del tipo de cliente que hace la petición.

Así, en lugar de responder a todos los dispositivos con la misma versión de los archivos HTML y CSS (que incluye todas las adaptaciones para todos los dispositivos mediante _media queries_), el **servidor** es capaz de **detectar el tipo de dispositivo** que realiza la petición (móvil, tablet, ordenador,...) y ofrecerle **únicamente el código que necesita**. Así, un móvil recibiría únicamente el código CSS optimizado para móvil, sin incluir las _media queries_ correspondientes a tablets u ordenadores.

De esta manera se reduce el tamaño de los archivos y se aumenta la velocidad de carga de los sitios.


## Referencias {#referencias}

-   [Guía de RWD en W3Schools](http://www.w3schools.com/css/css%5Frwd%5Fintro.asp)
-   [Aspectos básicos del diseño web adaptable (Google)](https://developers.google.com/web/fundamentals/design-and-ux/responsive/?hl=es)
-   [Diseño Responsivo (MDN)](https://developer.mozilla.org/es/docs/Web%5FDevelopment/Mobile/Dise%C3%B1o%5Fresponsivo)
-   [Responsive Design (MDN)](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS%5Flayout/Responsive%5FDesign)
-   [The building blocks of responsive design (MDN)](https://developer.mozilla.org/en-US/docs/Web/Progressive%5Fweb%5Fapps/Responsive/responsive%5Fdesign%5Fbuilding%5Fblocks)

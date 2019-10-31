+++
title = "Fuentes en CSS"
date = 2019-10-31T16:12:00+01:00
tags = ["css", "fuentes"]
categories = ["diw", "diw-estilos-multimedia"]
draft = false
+++

En este artículo se aborda el uso de tipos de letra (fuentes) en CSS: cómo incorporar fuentes desde **servidores externos**, qué tipos de **fuente genéricos** existen y cómo establecer **tipos de fuentes seguros** para que sean compatibles con todos los navegadores y sistemas operativos.

<!--more-->


## Tipos de fuente {#tipos-de-fuente}

En general podemos distinguir 5 grandes tipos de fuentes:

**Serif**
: Tipo de letra con remates en los extremos de las líneas. Se suele utilizar mucho en textos impresos. Tiene un aspecto visual más formal.

**Sans-Serif**
: Tipo de letra sin remates. Suele utilizarse para textos en pantalla. Se considera más informal.

**Monospaciada**
: Tipo de letra monoespaciada: todos los caracteres ocupan el mismo ancho. Se suele utilizar para código.

**Cursiva**
: Tipo de letra que simula la escritura a mano.

**Fantasía**
: Tipo de letra que muestra caracteres extraños o personalizados.

{{< figure src="/./font_types.png" caption="Figura 1: Tipos de fuente" >}}


## Fuentes en CSS {#fuentes-en-css}

En CSS se pueden distinguir dos tipos de fuentes que pueden utilizarse con la propiedad `font-family`:

**Genéricas**
: Son unos tipos de fuente consideradas **seguras**, ya que son compatibles con todos los navegadores y sistemas operativos. El tipo de letra que se mostrará corresponderá al tipo de letra configurada por defecto en el sistema correspondiente. Por ejemplo, si un navegador Firefox tiene definida "Arial" como tipo de letra Sans-Serif predeterminada, un tipo de letra `sans-serif` en CSS se mostrará en pantalla como "Arial". En este enlace se puede ver un [ejemplo de los tipos de letra genéricos en CSS](https://jsbin.com/nuhuzux/edit?html,css,output). Dichos tipos genéricos son:
    -   `serif`
    -   `sans-serif`
    -   `monospace`
    -   `cursive`
    -   `fantasy`

**Tipos de letra concretos**
: Por ejemplo, `font-family: "Arial"`. Hay que tener en cuenta que especificar un tipo de letra concreto implica dar por supuesto que dicho tipo de letra **está instalada en el sistema operativo del cliente** (a no ser que se importe un tipo de letra desde un archivo o servidor externo, que veremos en un apartado posterior). Si el tipo de letra especificado no está disponible, el navegador mostrará el tipo de letra que tenga configurado por defecto. Además, es casi seguro que [distintos sistemas operativos mostrarán las fuentes de manera diferente](https://www.w3.org/Style/Examples/007/fonts.en.html).


## Configuración segura de tipos de fuentes {#configuración-segura-de-tipos-de-fuentes}

A la hora de definir los tipos de fuente mediante la propiedad `font-family` es una buena práctica especificar no una, sino **varios tipos de fuente separados por comas** indicando **en último lugar un tipo de fuente genérica**. El navegador tratará de cargar el tipo de fuente de la primera opción y si no lo consigue, probará el siguiente. De esta manera garantizamos en última instancia que se mostrará un tipo de fuente adecuado (_serif_, _sans-serif_, _monospace_, _cursive_ o _fantasy_) independientemente del navegador o sistema operativo utilizado.

Algunos ejemplos de tipos de fuente seguros son:

```css

font-family: "Times New Roman", Times, serif;
font-family: Arial, Helvetica, sans-serif;
font-family: "Courier New", Courier, monospace;
```


## Cargar fuentes desde archivos o URLs {#cargar-fuentes-desde-archivos-o-urls}

Para incluir una fuente desde un archivo (tanto almacenado en el propio servidor como en una URL ajena) se utiliza la propiedad `@font-face` de CSS:

```css
@font-face {
    font-family: miFuente;
    src: url(ruta_archivo_fuente.woff);
}
```

Una vez importada puede utilizarse así:

```css
div {
  font-family: miFuente;
}
```

Algunos servicios como [Google Fonts](https://fonts.google.com/) ofrecen la posibilidad de seleccionar una o varias fuentes para incorporar a nuestra web utilizando etiquetas `<link>` en el archivo HTML o `@import` en CSS (este último método es [menos aconsejable](https://stackoverflow.com/questions/1022695/difference-between-import-and-link-in-css)).

A continuación se muestra un ejemplo para incorporar la fuente `Roboto`:

```html
<link href="https://fonts.googleapis.com/css?family=Roboto&display=swap" rel="stylesheet">
```

De manera alternativa se puede cargar a través de CSS (menos aconsejable, tal como hemos comentado antes):

```html
<style>
  @import url('https://fonts.googleapis.com/css?family=Roboto&display=swap');
</style>
```

Si [accedemos a la URL](https://fonts.googleapis.com/css?family=Roboto&display=swap) definida en la etiqueta `<link>` o en `@import` veremos que el código corresponde a código CSS que hace uso de la regla `@font-face` para cargar las fuentes correspondientes.

Una vez incluida la etiqueta `<link>` en el archivo HTML o la regla `@import` en CSS podremos hacer uso de la fuente en los ficheros CSS de la siguiente manera:

```css
font-family: 'Roboto', sans-serif;
```


## Más información {#más-información}

Para obtener más información sobre fuentes se puede consultar el artículo "[Optimización de fuentes web](https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/webfont-optimization?hl=es)" de Google. En él se explica con mayor detalle la teoría relacionada con fuentes, tipos de formatos para almacenar fuentes (formatos `woff`, `woff2` o `truetype`), compresión o subdivisión de Unicode para seleccionar los caracteres correspondientes a una determinada familia de lenguajes (latino, cirílico, griego,...).


## Referencias {#referencias}

-   <https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/webfont-optimization?hl=es>
-   <https://developer.mozilla.org/es/docs/Web/CSS/@font-face>
-   <https://www.w3schools.com/cssref/css3%5Fpr%5Ffont-face%5Frule.asp>
-   <https://www.w3.org/Style/Examples/007/fonts.en.html>
-   <https://stackoverflow.com/questions/14676613/how-to-import-google-web-font-in-css-file>
-   <https://stackoverflow.com/questions/56141957/difference-between-font-face-and-import-url>
-   <https://stackoverflow.com/questions/1022695/difference-between-import-and-link-in-css>

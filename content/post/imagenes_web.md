+++
title = "Imágenes en la web"
date = 2019-11-11T13:22:00+01:00
tags = ["css", "imagenes"]
categories = ["diw", "diw-estilos-multimedia"]
draft = false
+++

Las imágenes incluidas en los sitios web son responsables de gran parte del **tamaño de descarga**. Por tanto, es de vital importancia utilizar las técnicas adecuadas tanto para su **correcta visualización** (independientemente del tipo de dispositivo utilizado) como para su **optimización de tamaño** de cara a mejorar la velocidad de carga del sitio.

<!--more-->


## Fundamentos técnicos {#fundamentos-técnicos}


### Tipos de imagen {#tipos-de-imagen}

{{< figure src="https://upload.wikimedia.org/wikipedia/commons/thumb/6/6b/Bitmap%5FVS%5FSVG.svg/320px-Bitmap%5FVS%5FSVG.svg.png" caption="Figura 1: Imagen raster y vectorial" >}}

Podemos distinguir entre dos grandes grupos de imágenes:

-   **Mapas de bits** (_raster_) - Son imágenes compuestas por **píxeles**. Son las captadas por las cámaras o creadas por programas de edición.
-   **Vectoriales** - Son imágenes que muestran su información mediante **descripciones matemáticas**. Están creadas exclusivamente por programas de edición.

Las imágenes de [mapa de bits](https://es.wikipedia.org/wiki/Imagen%5Fde%5Fmapa%5Fde%5Fbits) se suelen utilizar en **fotografías**. Tienen una **resolución fija**, por lo que **al ampliarse pierden calidad** (a este proceso se le denomina [aliasing](https://es.wikipedia.org/wiki/Aliasing#En%5Fla%5Fcomputación%5Fgráfica)). Suelen ocupar **mucho espacio de almacenamiento** y por ello se suelen almacenar en formatos que soportan **compresión**.

Las imágenes [vectoriales](https://es.wikipedia.org/wiki/Gráfico%5Fvectorial) se suelen utilizar en **diseño** (carteles, folletos, logos, cómics,...). No tienen una resolución fija, por lo que **no pierden calidad al ampliarse**. Suelen ocupar **poco espacio de almacenamiento**. No están pensadas para imágenes de muy alta complejidad. Para mostrarse en pantallas se tienen que **convertir a mapas de bits** mediante un proceso llamado **render**.


### Profundidad de color {#profundidad-de-color}

La [profundidad de color](https://es.wikipedia.org/wiki/Profundidad%5Fde%5Fcolor) se refiere a la **cantidad de bits** utilizados para representar **un píxel** de una imagen. Actualmente se utiliza una profundidad de color de 32 bits:

-   8 bits para el color rojo (256 gamas de rojo)
-   8 bits para el color verde (256 gamas de verde)
-   8 bits para el color azul (256 gamas de azul)
-   8 bits para el [canal alfa](https://es.wikipedia.org/wiki/Composición%5Falfa) (256 gamas de transparencia/opacidad)


### Resolución {#resolución}

La [resolución de imagen](https://es.wikipedia.org/wiki/Resolución%5Fde%5Fimagen) indica la **cantidad de píxeles** que componen una imagen. Está directamente relacionada con el **nivel de detalle**: a mayor resolución, mayor nivel de detalle.

Normalmente se especifica en formato `ancho x alto` o en **megapíxeles** (multiplicación del ancho por el alto): por ejemplo, una imagen de 1600 x 1200 píxeles = 1.920.000 píxeles = 1.92 Megapíxeles.


### Compresión {#compresión}

El **tamaño** de una imagen sin comprimir depende de la **resolución** y de la **profundidad de color**. Así, una imagen de 1600x1200px con color de 32 bits tendrá un tamaño:

Tamaño = 1600 \* 1200 \* 32 = 61440000 bits = 7680000 Bytes = **7.32 MB**

Es necesario por tanto **comprimir** la imagen mediante alguno de los formatos específicos creados para ello.


## Formatos {#formatos}

Los formatos más utilizados en el **diseño web** son:
Algunos de los formatos más habituales son:

-   BMP - Mapa de bits sin compresión.
-   ICO - Mapa de bits sin compresión. Utilizado para iconos.
-   JPEG - Mapa de bits comprimido. Utilizado para fotografías.
-   PNG - Mapa de bits con o sin compresión. Utilizado para fotografías o dibujos.
-   APNG - Mapa de bits animado con o sin compresión.
-   GIF - Mapa de bits animado con compresión. Utilizado para animaciones de **baja calidad**.
-   WebP - Mapa de bits con compresión. Utilizado para fotografías o dibujos (no soportado en Safari).
-   SVG - Imagen vectorial.

Para más información se puede consultar este artículo sobre [compatibilidad de formatos de imagen en navegadores](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Image%5Ftypes).


## Software {#software}

A continuación se indican algunos de los programas **Open Source** más utilizados para la edición de imágenes:

-   [GIMP](http://www.gimp.org.es/) - Programa de edición de imágenes de **mapa de bits** similar a Photoshop.
-   [Inkscape](https://inkscape.org/es/) - Programa de edición de imágenes **vectoriales**.


## Optimización de imágenes para web {#optimización-de-imágenes-para-web}

La optimización de imágenes es fundamental para mejorar el **tiempo de carga** de los sitios web. Uno de las técnicas más interesantes para ello es la utilización de la etiqueta `<picture>` de HTML. Esta etiqueta permite especificar **diferentes versiones de una imagen** para **distintos tipos de dispositivos**. De esta manera, el dispositivo solo descargará aquella imagen que sea más apropiada para sus características, como puede ser el formato (`webp`, `jpeg`,...) o la resolución. A continuación se muestra un ejemplo de uso:

```html
<picture>
  <source media="(min-width: 650px)" srcset="img_650.jpg">
  <source media="(min-width: 465px)" srcset="img_465.jpg">
  <img src="img.jpg" alt="Flowers">
</picture>
```

En el ejemplo se proporcionan tres archivos de imagen con distinta resolución. Si el dispositivo tiene una anchura de más de 650 píxeles se mostrará la imagen `img_650.jpg`; si su anchura es mayor de 465px, se mostrará `img_465.jpg`; por último, si su resolución es inferior a 465px **o no soporta la etiqueta** `<picture>`, cargará `img.jpg`.

A continuación se indican algunos enlaces con más información sobre el tema:

-   [MDN - El elemento `<picture>`](https://developer.mozilla.org/es/docs/Web/HTML/Elemento/picture)
-   [MDN - Imágenes responsivas](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia%5Fand%5Fembedding/Responsive%5Fimages)
-   [Generador de imágenes responsivas](https://www.responsivebreakpoints.com/)


## Aplicar estilos a imágenes {#aplicar-estilos-a-imágenes}

En ocasiones hacer que las imágenes se muestren adecuadamente puede ser complicado. En el siguiente enlace se muestran algunas [técnicas para personalizar la apariencia de las imágenes mediante CSS](https://www.w3schools.com/css/css3%5Fimages.asp). En él se muestran técnicas de **centrado**, **diseño responsivo** o **creación de efectos o filtros**.

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

Se define la **relación de aspecto** como la proporción entre la anchura y la altura. Así, una imagen de **1600 x 1200** píxeles tiene una relación de aspecto de **1.33**.


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

La optimización de imágenes es fundamental para mejorar el **tiempo de carga** de los sitios web. Una de las opciones más interesantes consiste en especificar **diferentes versiones de una imagen** para **distintos tipos de dispositivos**. De esta manera, el dispositivo solo descargará aquella imagen que sea más apropiada para sus características, como puede ser el formato (`webp`, `jpeg`,...) o la resolución. Así, un dispositivo de **baja resolución** descargará una imagen de **peor calidad y menor tamaño**, optimizando así su velocidad de descarga y evitando utilizar una resolución que no puede aprovechar, mientras que un dispositivo de **alta resolución** descargará una imagen de **mejor calidad**.

HTML5 define **dos opciones** para proporcionar diferentes versiones de una imagen:

-   El atributo `srcset`
-   La etiqueta `<picture>`.

Ambas opciones pueden utilizarse incluso de manera combinada. Sin embargo, cada una está pensada para un caso de uso distinto. Podemos distinguir **3 casos de uso**:

-   Utilizar imágenes de distinta resolución que van a ocupar la **misma proporción de pantalla** en todos los dispositivos. Por ejemplo, una imagen que va a ocupar el 100% de la pantalla tanto en dispositivos móviles como pantallas grandes. A este caso lo denominaremos **cambio de resolución**.
-   Utilizar imágenes de distinta resolución que van a ocupar **distinta proporción de pantalla** en función del dispositivo.se van a mostrar. Por ejemplo, una imagen que va a ocupar el 100% de la pantalla en dispositivos móviles pero un 50% en pantallas grandes. A este caso lo llamaremos **cambio de resolución con distintos tamaños**.
-   Por último, utilizar imágenes con **distinta relación de aspecto** (relación entre el ancho y el alto) en función del dispositivo. Por ejemplo, una imagen apaisada con la información más importante en la parte central se verá adecuadamente en pantallas grandes; sin embargo, en dispositivos móviles se verá muy delgada. En este último caso es conveniente proporcionar una **versión recortada** de la imagen que muestre los detalles importantes. A este caso se le denomina **dirección de arte**.

{{< figure src="/./art_direction.png" caption="Figura 2: Problema de dirección de arte. Fuente: MDN Web Docs" >}}


### Cambio de resolución {#cambio-de-resolución}

En este caso supondremos que la imagen va a ocupar el **mismo ancho de pantalla** en todo tipo de dispositivos. En el ejemplo se asumirá que la imagen va a ocupar siempre el 100% del ancho de pantalla, tanto en pantallas grandes como en móviles. En estos casos lo recomendable es utilizar el atributo `srcset` del elemento `<img>`. Este atributo proporciona al navegador una serie de opciones para que **elija la mejor opción en función de la resolución**. Es el navegador el encargado de elegir, no se fuerza elección alguna.

En este caso, para optimizar la elección de la imagen a cargar, habrá que tener en cuenta **únicamente el tamaño de las imágenes**. Pongamos por ejemplo que disponemos de 3 versiones de una imagen: los anchos de resolución de las imágenes son `450px`, `850px` y `1400px`. Así, tendremos que:

-   Un dispositivo con un ancho de **900px** debería mostrar la imagen de **1400px**, ya que la anterior se quedaría corta y perdería calidad al ampliarla.
-   Un dispositivo con un ancho de **700px** debería utilizar la imagen de **850px**.
-   Un dispositivo de **380px** debería utilizar la imagen de **450px**.

El código a utilizar sería el siguiente:

```html
<img alt="Imagen" src="imagen_450.jpg"
 srcset="imagen_450.jpg 450w, imagen_850.jpg 850w, imagen_1400.jpg 1400w">
```

En el código anterior tenemos que:

-   Se utiliza el atributo `src` para indicar la imagen a utilizar por defecto en caso de que el navegador no soporte `srcset`.
-   Se utiliza el atributo `srcset` para indicar una lista de posibles imágenes indicando su resolución.
-   La resolución en este caso se indica mediante la unidad `w`, que hace referencia a la anchura (_width_). `imagen_450.jpg 450w` significa que ese archivo de imagen tiene una resolución de 450px.
-   De manera alternativa se puede indicar la resolución utilizando **descriptores**: `1x`, `1.5x`, `2x`,... Estos descriptores hacen referencia a la densidad de píxeles de la pantalla: `1x` es resolución convencional, mientras que `2x` es la resolución utilizada por dispositivos de alta resolución, como las pantallas Retina de Apple. Así, sería posible utilizar `imagen_1400.jpg 2x`, indicando que esa versión de imagen debe ser utilizada por dispositivos de alta resolución únicamente.


### Cambio de resolución: distintos tamaños de imagen {#cambio-de-resolución-distintos-tamaños-de-imagen}

En este caso supondremos que la imagen va a ocupar el **distinto ancho de pantalla** según el tipo de dispositivo. Siguiendo con el caso del ejemplo anterior (versiones de imagen con resolución 450px, 850px y 1400px), asumiremos que se ha creado código CSS que haga uso de `media queries` con las siguientes reglas:

-   En pantallas **grandes** (>768px), la imagen ocupará un **50%** de la pantalla.
-   En pantallas **pequeñas** (<768px), la imagen ocupará el **100%** de la pantalla.

En este caso, para optimizar la elección de la imagen a cargar habrá que tener en cuenta no solo el tamaño de las imágenes, sino también **qué espacio van a ocupar**. Así, tendremos que:

-   Si la resolución del dispositivo es de **900px**, en principio parece que debería utilizar la imagen de 1400px. Sin embargo, en nuestro código CSS hemos configurado las imágenes para que ocupen un 50% de la pantalla. Por tanto, la imagen ocupará 450px. Bastará entonces con cargar la **imagen de 854px**.
-   Si la resolución del dispositivo es de **700px** queremos que la imagen se muestre ocupando un 100% de la pantalla. Por tanto, se deberá cargar también la imagen de **854px**.
-   Para cargar la imagen de 1400px el **dispositivo** deberá tener una **resolución mínima de 1701px**: en este caso la imagen ocupará un 50% de la pantalla, es decir, 850.5px, por lo que no le bastará con la de 850px y deberá cargar la de 1400px,

Para que el navegador tenga en cuenta los tamaños que van a ocupar las imágenes en los distintos tipos de dispositivo hay que utilizar el atributo `sizes` del elmento `<img>`: este atributo permite especificar condiciones de tamaño en forma de `media queries` junto con una referencia al tamaño que ocupará la imagen (por ejemplo, en unidades `vw`).

El código a utilizar sería el siguiente:

```html
<img alt="Imagen" src="imagen_450.jpg"
 srcset="imagen_450.jpg 450w, imagen_850.jpg 850w, imagen_1400.jpg 1400w"
 sizes="(min-width: 768px) 50vw, 100vw">
```

En el código anterior tenemos que:

-   Se añade el atributo `sizes` a la imagen.
-   Este atributo indica una lista de tamaños con indicación opcional de `media queries`.
-   Así, `(min-width: 768px) 50vw` indica que en dispositivos con anchura mínima de 768px van a mostrar la imagen ocupando un 50% de la pantalla (`50vw`).
-   El elemento `100vw`, al no tener media query, indica que si no se cumple ninguna otra condición la imagen ocupará un 100% de la pantalla.

> ¡IMPORTANTE! El atributo `sizes` no cambia el ancho de la imagen. Simplemente tiene una función **informativa** para determinar qué resolución se debería cargar. Para cambiar el tamaño de la imagen habrá que utilizar reglas y media queries CSS convencionales.


### Dirección de arte {#dirección-de-arte}

Esta técnica consiste en mostrar diferentes **versiones** de la imagen en función de la anchura del dispositivo. Normalmente se utiliza para **recortar imágenes** y que **se vea la información más importante en pantallas pequeñas**.

Por ejemplo, supongamos que se quiere mostrar **2 versiones distintas** de la imagen en función del tipo de dispositivo:

-   En pantallas **grandes** (>768px) se mostrará la imagen `img_wide.jpg`, que es una versión completa de la imagen en formato apaisado.
-   En pantallas **pequeñas** (<768px) se mostrará la imagen `img_mobile.jpg`, que es una versión **recortada** de la imagen en formato cuadrado.

Para la dirección de arte se utiliza la etiqueta `<picture>`. Esta etiqueta permite definir **varios archivos de imagen** a través de etiquetas `<source>` junto con **media queries** para hacer que se muestre una determinada imagen en función de la resolución del dispositivo. Esta etiqueta **fuerza al navegador a escoger la imagen necesaria**, a diferencia del atributo `srcset`, que permite al navegador elegir.

El código a utilizar sería el siguiente:

```html
<picture>
  <source media="(min-width: 768px)" srcset="img_wide.jpg">
  <source srcset="img_mobile.jpg">
  <img src="img_mobile.jpg" alt="Imagen">
</picture>
```

El funcionamiento del código es el siguiente:

-   El primer elemento `<source>` define un archivo de imagen que se deberá utilizar en dispositivos cuya anchura sea **mayor de 768px**.
-   El segundo elemento `<source>` define un archivo de imagen que se deberá utilizar en el **resto de casos**.
-   El elemento `<img>` es **obligatorio** incluirlo, ya que proporciona en primer lugar el atributo `alt` con la descripción textual de la imagen y ofrece **compatibilidad** con los navegadores que no soporten la etiqueta `<picture>`.

> Es importante dejar claro que el elemento `<picture>` está pensado para los casos de dirección de arte (mostrar imágenes **distintas** en función del dispositivo). Si lo que se pretende es ofrecer **distintas resoluciones de la misma imagen**, entonces es mejor utilizar elementos `<img>` con atributos `srcset` y `sizes`.

Por último, señalar que se puede utilizar simultáneamente el elemento `<picture>` para dirección de arte y además proporcionar alternativas de resolución con el atributo `srcset` (ya que éste se puede utilizar también en los elementos `<source>`).


### Referencias {#referencias}

A continuación se indican algunos enlaces con más información sobre el tema:

-   [Google - Imágenes responsivas](https://developers.google.com/web/fundamentals/design-and-ux/responsive/images?hl=es)
-   [MDN - Imágenes responsivas](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia%5Fand%5Fembedding/Responsive%5Fimages)
-   [Generador de imágenes responsivas](https://www.responsivebreakpoints.com/)
-   [MDN - El elemento `<picture>`](https://developer.mozilla.org/es/docs/Web/HTML/Elemento/picture)


## Aplicar estilos a imágenes {#aplicar-estilos-a-imágenes}

En ocasiones hacer que las imágenes se muestren adecuadamente puede ser complicado. En el siguiente enlace se muestran algunas [técnicas para personalizar la apariencia de las imágenes mediante CSS](https://www.w3schools.com/css/css3%5Fimages.asp). En él se muestran técnicas de **centrado**, **diseño responsivo** o **creación de efectos o filtros**.

La técnica más importante para crear imágenes responsivas (que se adapten correctamente a la capa contenedora) consiste en introducir la etiqueta `<img>` dentro de una etiqueta `<div>` y establecer el ancho de la imagen al 100%. De esta manera, redimensionando la etiqueta `<div>` contenedora se podrá cambiar el tamaño de la imagen. El código sería el siguiente:

```css
img {
    width: 100%;
}

.img_container {
    /* Aquí es donde se debe cambiar el ancho deseado de la imagen */
}
```

```html
<div class="img_container">
  <img src="" alt="">
</div>
```

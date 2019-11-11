+++
title = "Audio y vídeo en HTML"
date = 2019-11-12T00:55:00+01:00
tags = ["css", "audio", "video"]
categories = ["diw", "diw-estilos-multimedia"]
draft = false
+++

HTML5 define las etiquetas `<audio>` y `<video>` para incorporar archivos de audio y vídeo respectivamente en páginas web. En este artículo veremos cómo utilizar dichas etiquetas, qué **formatos** de vídeo y audio son compatibles con los distintos navegadores y qué **programas** podemos utilizar para **editar** y **realizar conversiones** entre distintos formatos.

<!--more-->


## Audio {#audio}


### Etiqueta `<audio>` {#etiqueta-audio}

Los archivos de audio pueden insertarse en una página web mediante la etiqueta `<audio>`. Dicha etiqueta permite especificar **varios archivos de audio** de manera **ordenada**. De esta manera, el navegador **intentará reproducir el primer archivo de la lista para el que tenga soporte**.

```html
 <audio controls>
  <source src="cancion.ogg" type="audio/ogg">
  <source src="cancion.mp3" type="audio/mpeg">
  El navegador no soporta la etiqueta audio.
</audio>
```

En el ejemplo anterior, el navegador intentará reproducir el archivo `cancion.ogg`; en caso de que no soporte ese tipo de archivo, intentará reproducir `cancion.mp3`.

La etiqueta `<audio>` admite varios atributos. En el caso del ejemplo, el atributo `controls` indica que se deben mostrar los controles de reproducción.

Para más información sobre las opciones de la etiqueta `<audio>` se pueden consultar los siguientes enlaces:

-   <https://developer.mozilla.org/es/docs/Web/HTML/Elemento/audio>
-   <https://www.w3schools.com/tags/tag%5Faudio.asp>


### Formatos de audio {#formatos-de-audio}

Los principales formatos utilizados para audio son:

-   **MP3** - Formato más utilizado. Compatible con **todos los navegadores**.
-   **OGG** - Formato OGG Vorbis. No compatible con IE ni con Safari.
-   **WAV** - No compatible con IE.

Para más información sobre compatibilidad de formatos multimedia puede consultarse:

-   <https://developer.mozilla.org/es/docs/Web/HTML/Formatos%5Fadmitidos%5Fde%5Faudio%5Fy%5Fvideo%5Fen%5Fhtml5>


### Programas de edición de audio {#programas-de-edición-de-audio}

-   [Audacity](https://www.audacityteam.org/) - Programa de edición de audio Open Source.


## Vídeo {#vídeo}


### Etiqueta `<video>` {#etiqueta-video}

Los archivos de vídeo pueden insertarse en una página web mediante la etiqueta `<video>`. Dicha etiqueta permite especificar **varios archivos de vídeo** de manera **ordenada**. De esta manera, el navegador **intentará reproducir el primer archivo de la lista para el que tenga soporte**.

```html
 <video width="320" height="240" controls>
  <source src="video.mp4" type="video/mp4">
  <source src="video.ogg" type="video/ogg">
  El navegador no soporta la etiqueta video.
</video>
```

En el ejemplo anterior, el navegador intentará reproducir el archivo `video.mp4`; en caso de que no soporte ese tipo de archivo, intentará reproducir `video.ogg`.

La etiqueta `<video>` admite varios atributos. En el caso del ejemplo, el atributo `controls` indica que se deben mostrar los controles de reproducción.

Para más información sobre las opciones de la etiqueta `<video>` se pueden consultar los siguientes enlaces:

-   <https://developer.mozilla.org/es/docs/Web/HTML/Elemento/video>
-   <https://www.w3schools.com/tags/tag%5Fvideo.asp>


### Formatos de vídeo {#formatos-de-vídeo}

Los principales formatos utilizados para vídeo son:

-   **MP4** - Contenedor MP4, códec de vídeo H264 y códec de audio AAC. Formato más utilizado. Compatible con **todos los navegadores**.
-   **OGG** - Contenedor OGG, códec de vídeo Theora y códec de audio Vorbis. No compatible con IE ni con Safari.
-   **WebM** - Contenedor WebM, códec de vídeo VP8 y códec de audio Vorbis. No compatible con IE ni con Safari.

Para más información sobre compatibilidad de formatos multimedia puede consultarse:

-   <https://developer.mozilla.org/es/docs/Web/HTML/Formatos%5Fadmitidos%5Fde%5Faudio%5Fy%5Fvideo%5Fen%5Fhtml5>


### Programas de edición de vídeo {#programas-de-edición-de-vídeo}

-   [Openshot](https://www.openshot.org/es/) - Editor de vídeo Open Source
-   [Handbrake](https://handbrake.fr/) - Conversor de formatos de vídeo
-   [OBS Studio](https://obsproject.com/es/) - Software de grabación de vídeo y transmisión en vivo

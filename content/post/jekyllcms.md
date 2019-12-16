+++
title = "Fundamentos del CMS Jekyll"
date = 2019-11-19T12:30:00+01:00
tags = ["css", "jekyll", "cms"]
categories = ["diw", "diw-estilos-multimedia"]
draft = false
+++

[Jekyll](https://jekyllrb.com) es un [gestor de contenido](https://es.wikipedia.org/wiki/Sistema%5Fde%5Fgestión%5Fde%5Fcontenidos) de tipo **estático** (_static site generator_). No depende de ninguna base de datos ni de ningún lenguaje de servidor. Utiliza ficheros de texto para almacenar los contenidos y los datos. Dado que no utiliza tecnologías de servidor, es necesario realizar un proceso de **generación** o compilación para producir archivos HTML válidos que puedan ser alojados en un servidor y procesados adecuadamente por un navegador web convencional.

<!--more-->

En Jekyll podemos distinguir varias categorías de archivos:

-   Ficheros de **configuración** - Almacenan la configuración general del sitio y las opciones de personalización.
-   Ficheros de **contenido** - Almacenan los contenidos de las páginas del sitio.
-   Ficheros de **datos** - Permiten crear estructuras de datos que pueden ser mostrados en las distintas páginas del sitio o utilizarse para generar estructuras, menús de navegación, listas,...
-   Ficheros de **plantillas** - Se utilizan para crear la estructura de las páginas que componen el sitio web.

Jekyll utiliza un sistema de plantillas denominado _Liquid_ para combinar los distintos tipos de ficheros y crear el resultado final: un sitio web totalmente estático que utiliza únicamente HTML, CSS y JavaScript.

La documentación de Jekyll puede consultarse [en este enlace](https://jekyllrb.com/docs/).


## Instalación {#instalación}

Las instrucciones de instalación de Jekyll pueden consultarse [aquí](https://jekyllrb.com/docs/installation/). Utiliza el ecosistema **Ruby** para ejecutarse.

Una vez instado Ruby se puede proceder a instalar Jekyll mediante el siguiente comando:

```sh
gem install jekyll bundler
```


## Uso básico {#uso-básico}

Jekyll se ejecuta desde la linea de comandos. Su uso básico permite:

-   Crear un nuevo sitio Jekyll mediante `jekyll new NOMBRE_PROYECTO`. Este comando crea un nuevo proyecto Jekyll en la carpeta `./NOMBRE_PROYECTO`. Todas las acciones que se indican a continuación se deben ejecutar dentro de dicha carpeta.
-   Generar el sitio web en la carpeta `./_site` mediante `bundle exec jekyll build`.
-   Lanzar un servidor web para visualizar el proyecto en el navegador mediante `bundle exec jekyll serve`. Una vez lanzado se puede acceder al sitio web a través del navegador en `http://localhost:4000`. Mediante este comando se pueden ver los cambios automáticamente sin necesidad de tener que generar el proyecto cada vez.

Puede obtenerse más información en <https://jekyllrb.com/docs/quickstart/>.


## Organización de archivos {#organización-de-archivos}

La organización de archivos y carpetas en un proyecto Jekyll se puede consultar en <https://jekyllrb.com/docs/structure/>. Jekyll está pensado para utilizar [temas](https://jekyllrb.com/docs/themes/), aunque se puede crear una estructura propia a partir de los siguientes archivos:

`_config.yml`
: Fichero _YAML_ de configuración. En él se detallan las opciones de configuración del proyecto.

`_layouts`
: Carpeta que incluye los ficheros de **plantilla**. Cada fichero es un fichero HTML que se utiliza para englobar el contenido de las distintas páginas que componen el sitio. El nombre del fichero es el nombre de la plantilla. La etiqueta `{{content}}` se utiliza para incluir el contenido de la página que está usando la plantilla. Más información en <https://jekyllrb.com/docs/layouts/>.

`_includes`
: Carpeta que incluye los ficheros HTML que se utilizan como _parciales_ para ser incluidos en plantillas u otras páginas del sitio. La etiqueta `{% include ARCHIVO.html%}` se utilizará para incluir el contenido del fichero `_includes/ARCHIVO.html`. Más información en <https://jekyllrb.com/docs/includes/>.

Carpeta principal
: Los ficheros HTML (o MarkDown) que aparezcan en la carpeta principal del proyecto formarán las páginas estáticas del sitio. Cada página tendrá definido un _front matter_ donde se indicará, entre otras cosas, qué plantilla utilizará dicha página.

`_site`
: Carpeta que contiene el sitio web generado por Jekyll una vez realizadas todas las tareas de procesado (inyección del contenido de los archivos parciales, aplicación de plantillas, procesado de datos, etc.). El contenido de esta carpeta puede ser publicado en cualquier servidor HTTP.


## Front matter {#front-matter}

El _front matter_ es el contenido de texto que aparece al comienzo de cualquier archivo que deba ser procesado por Jekyll. Si Jekyll encuentra un archivo que no tenga definido un _front matter_ no lo procesa y lo copia a la misma localización del directorio `_site`. El _front matter_ está delimitado entre dos líneas formadas por un **tres guiones**. Su aspecto es parecido al siguiente:

```yaml
---
layout: mi_layout
permalink: /url/estatica/de/la/pagina
title: Título de la página
---
```

En el _front matter_ se pueden definir datos en forma `variable: valor` que luego podrán ser utilizados por el sistema Liquid de plantillas. Su uso más básico permite definir las siguientes características de la página:

`layout`
: Indica el archivo de plantilla que se utilizará para mostrar la página. El nombre definido en esta variable hace referencia al archivo del mismo nombre sin la extensión presente en la carpeta `_layouts`.

`permalink`
: Indica la URL estática que tendrá la página web en caso de querer que se muestre alguna distinta al nombre del archivo.

`title`
: El título de la página.

Normalmente todos los ficheros que necesiten acceder al sistema de plantillas de Jekyll tendrán definido un _front matter_. Aquellos otros que no lo necesiten (por lo general, archivos CSS, JS, imágenes y demás) no tendrán definido un _front matter_ (es posible que algunos de ellos, dependiendo del tipo de aplicación, sí que lo necesiten).

Puede consultarse más información sobre el _front matter_ en <https://jekyllrb.com/docs/frontmatter/>.


## Integración con GitHub Pages {#integración-con-github-pages}

Jekyll está integrado en el servicio de GitHub Pages. Si se sube un repositorio con un proyecto Jekyll a la rama de GitHub Pages (`gh-pages`), este se compilará automáticamente y será publicado en Internet. Por tanto, no es necesario compilarlo antes de subirlo ni subir la carpeta `_site`.

En estos enlaces puede consultarse más información sobre [GitHub Pages](https://pages.github.com/) y [Jekyll y GitHub Pages](https://help.github.com/articles/using-jekyll-as-a-static-site-generator-with-github-pages/).

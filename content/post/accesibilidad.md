+++
title = "Pautas de accesibilidad"
date = 2019-10-14T13:37:00+02:00
tags = ["accesibilidad", "accesibility", "wai", "aria"]
categories = ["diw", "diw-planificacion-interfacesweb"]
draft = false
+++

La accesibilidad web es una práctica inclusiva que tiene como objetivo que **no haya ninguna barrera que impida o limite el uso y acceso a Internet** a personas con cualquier tipo de discapacidad.

<!--more-->


## Accesibilidad web {#accesibilidad-web}

{{< figure src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/19/Preferences-desktop-assistive-technology.svg/200px-Preferences-desktop-assistive-technology.svg.png" caption="Figura 1: Accesibilidad web. Fuente: Wikimedia" >}}

Muchas de las personas que tienen algún tipo de discapacidad, tanto de tipo físico como de tipo intelectual, necesitan utilizar dispositivos especiales para acceder a los contenidos de Internet. Otras necesitan acceder a la información de manera adaptada, con contenidos simplificados para poder comprenderlos mejor. El organismo [W3C](https://www.w3.org/WAI/design-develop/es) desarrolla estándares web denominados _Recomendaciones_ relacionados con esta área.


## WCAG {#wcag}

_Web Content Accessibility Guidelines_ (WCAG) es un conjunto de recomendaciones desarrolladas por el organismo [W3C](https://www.w3.org/WAI/design-develop/es) cuyo objetivo es mejorar la accesibilidad de los contenidos web. WCAG define [12 directrices agrupadas en 4 principios](https://es.wikipedia.org/wiki/Web%5FContent%5FAccessibility%5FGuidelines#Principios). Para cada directriz se definen tres niveles de cumplimiento: A, AA y AAA.

-   [Introducción a las Pautas de Accesibilidad para el contenido web (WCAG)](https://www.w3.org/WAI/standards-guidelines/wcag/es)
-   [WCAG 2.1 de un vistazo](https://www.w3.org/WAI/standards-guidelines/wcag/glance/es)


### Validación {#validación}

Existen varias herramientas de validación de las reglas WCAG. La mayoría de ellos no es capaz de analizar todas las recomendaciones y simplemente hacen sugerencias sobre apartados que podrían estar mal diseñados. En este [enlace](https://www.usableyaccesible.com/recurso%5Fmisvalidadores.php) se comentan algunas de ellas. Uno de los más sencillos de usar es <http://wave.webaim.org/>.


## Principales recomendaciones {#principales-recomendaciones}

Las recomendaciones de la WCAG son bastante amplias, por lo que a no ser que se sea un experto en la materia pueden parecer difíciles de seguir. Por ello citaremos a continuación unas recomendaciones sencillas y fáciles de llevar a la práctica.


### Corregir problemas de usabilidad {#corregir-problemas-de-usabilidad}

El hecho de que un sitio sea más usable para el público general tiene como consecuencia que también será más efectivo para las personas con discapacidad.


### Informarse sobre las tecnologías de accesibilidad {#informarse-sobre-las-tecnologías-de-accesibilidad}

Es recomendable informarse sobre cómo utilizan las tecnologías las personas con algún tipo de discapacidad. La mejor manera para ello es verlos en persona, pero la mayoría de nosotros no tiene esa posibilidad. A continuación se muestran algunos sitios con recursos sobre el tema:

-   [Asociación de lectura fácil](http://www.lecturafacil.net/content-management-es/)
-   [Web Accesibility in Mind](http://webaim.org/intro/)


### Implementar cambios en las páginas web {#implementar-cambios-en-las-páginas-web}

A continuación se enumeran los puntos más importantes para mejorar la accesibilidad de un sitio web.

-   Añadir un **atributo** `alt` con información adecuada a **cada imagen** del sitio. La descripción debe ser breve y concisa, evitando repetir las mismas palabras en todas las descripciones.
-   Utilizar correctamente los **encabezados**. Los encabezados `<h1>` deben utilizarse para el título de la página o título principal del contenido; los `<h2>` para las secciones; los `<h3>` para las subsecciones, etc. Así se facilita la navegación a través del teclado.
-   Utilizar etiquetas `<label>` para los campos de los **formularios**. De esta manera se asocian las etiquetas con los campos y los lectores de pantalla pueden interpretarlos correctamente.
-   Añadir un **enlace** del tipo _Ir al contenido principal_ al principio de cada página. Así se evita tener que esperar tiempo escuchando las entradas del menú de navegación cada vez que se carga una página nueva.
-   Hacer que haya un nivel de **contraste** adecuado entre el texto y el fondo.
-   Utilizar **plantillas accesibles** si se utiliza un gestor de contenido.
-   Utilizar las especificaciones [WAI-ARIA](https://www.w3.org/WAI/standards-guidelines/aria/).

En los siguientes enlaces se ofrece una información más detallada sobre **consejos de diseño y desarrollo**:

-   [Introducción al diseño y al desarrollo](https://www.w3.org/WAI/design-develop/es)
    -   [Consejos para creadores de contenidos](https://www.w3.org/WAI/tips/writing/)
    -   [Consejos para diseñadores web](https://www.w3.org/WAI/tips/designing/)
    -   [Consejos para desarrolladores web](https://www.w3.org/WAI/tips/developing/)


## WAI-ARIA {#wai-aria}

WAI-ARIA es una documento técnico publicado por el [W3C](https://www.w3.org/WAI/design-develop/es) que especifica cómo **mejorar la accesibilidad de páginas web**. Presta especial atención a los siguientes aspectos:

-   **Contenido dinámico** generado a partir de **AJAX**. La mayoría de las páginas utilizan AJAX para realizar peticiones al servidor sin necesidad de recargar la página. Por ello, el contenido de determinadas áreas de la página puede cambiar y la persona que lo está utilizando puede no darse cuenta. ARIA establece algunas estrategias a implementar para que los cambios en la página sean notificados al usuario cuando se produzcan.
-   **Componentes de interfaz de usuario** tales como pestañas, acordeones, migas de pan,... Estos componentes normalmente se implementan utilizando etiquetas HTML genéricas (por ejemplo, etiquetas `DIV`) sin ningún tipo de significado semántico. ARIA ofrece algunas técnicas para **anotar** las etiquetas correspondientes y añadirles información sobre su uso y/o propósito.

A continuación se muestran algunos recursos sobre las tecnologías WAI-ARIA:

-   [Sitio web WAI-ARIA](https://www.w3.org/WAI/standards-guidelines/aria/)
-   [Técnicas ARIA para desarrolladores](https://www.w3.org/TR/wai-aria-practices/)

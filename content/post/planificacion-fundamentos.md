+++
title = "Fundamentos de la planificación de interfaces web"
date = 2019-09-30T10:28:00+02:00
tags = ["krug", "planificacion", "usabilidad"]
categories = ["diw", "diw-planificacion-interfacesweb"]
draft = false
+++

Antes de proceder a la edición de código e incluso antes de la creación de un prototipo es necesario tener claros algunos **principios de diseño** y tomar algunas decisiones relacionadas con el estilo general del sitio, que normalmente vendrán recogidas en la **[guía de estilo](/post/planificacion-guia-estilo)**.

<!--more-->

En este artículo nos centraremos en analizar algunos de los principios generales de diseño más importantes a tener en cuenta. Para ello se tomará como base el libro "[Don't Make Me Think](http://www.sensible.com/dmmt.html)" (_No me hagas pensar_), de Steven Krug.


## Don't make me think! {#don-t-make-me-think}

"No me hagas pensar" es el principio más importante que toda página debería seguir en cuanto a usabilidad. El objetivo principal de toda página web debería ser que fuera evidente, auto-explicativa. El usuario debería ser capaz de ver de un vistazo lo que la página propone sin gastar mucho tiempo pensando sobre ello.

¿Cómo de evidente? Lo suficiente como para que una persona que no sea experta en el tema propuesto en la página y que apenas sepa usar el navegador sea capaz de llegar al sitio y decir "Ah, esta página va de...".


## Errores típicos {#errores-típicos}

-   Nombres poco claros, como nombres de marcas, específicos del funcionamiento interno de la empresa o siglas o nombres técnicos.
-   Enlaces y botones que no se muestran de manera obvia y se confunden con texto normal.
-   Asumir que el usuario conoce una información que en realidad desconoce.
-   No saber en qué lugar del sitio web se está ni cómo volver a un sitio conocido (como por ejemplo, la página principal).
-   No ofrecer un punto de entrada claro para empezar a utilizar el sitio.
-   No mostrar los elementos típicos (menús de navegación, etc.) en los sitios habituales.
-   Sobrecargar la página con información de manera que no se sepa qué es importante o qué no.
-   Mezclar el contenido de la página con la publicidad de la misma de manera que sea muy difícil diferenciar ambas cosas.

El objetivo principal es eliminar todas aquellas preguntas que se pueda hacer el usuario a la hora de utilizar la página.


## Diseño orientado al escaneo, no a la lectura {#diseño-orientado-al-escaneo-no-a-la-lectura}

1.  Sigue las **convenciones** del diseño web.
    -   Los elementos (menús, logo, contenido,...) están dispuestos de manera convencional.
    -   Los elementos (cuadros de búsqueda, iconos de vídeo o audio, redes sociales,...) son reconocibles.
2.  Dispone de una **jerarquía** clara.
    -   Queda claro qué apartados son más importantes que otros.
    -   Los encabezados de distintos niveles son perfectamente distinguibles unos de otros.
    -   Las capas agrupan correctamente los contenidos relacionados entre sí.
3.  Las páginas están **divididas en áreas** bien definidas.
4.  Los **enlaces y botones** se distinguen del texto normal.
5.  No hay contenido que **distraiga** al usuario.
    -   No hay demasiadas zonas que llamen la atención del usuario de manera evidente (animaciones, exclamaciones, anuncios parpadeando,...).
    -   La página muestra un aspecto organizado y es fácil reconocer cada una de las áreas en que está dividida.
6.  El contenido está **estructurado** de manera que sea fácil escanear la página.
    -   Hay encabezados que separan las secciones de texto.
    -   Queda claro qué encabezado está relacionado con el contenido.
    -   Los párrafos son cortos.
    -   Se utilizan listas para esquematizar el contenido.
    -   La cursiva y la negrita se utilizan pero de manera puntual.


## Elecciones sencillas {#elecciones-sencillas}

-   Los usuarios buscan elecciones sencillas.
-   Es más recomendable ofrecer pocas opciones  en varios pasos que muchas opciones en pocos pasos.
-   Las opciones que se ofrecen deben ser lo suficientemente distintas como para no dudar entre una u otra.
-   Las instrucciones deben desaparecer o minimizarse al máximo. En caso de aparecer, deben ser:
    -   Breves (mínima cantidad de información que sea útil).
    -   Oportunas (deben aparecer exclusivamente cuando sean necesarias).
    -   Visibles (deben captar la atención del usuario y no pasar desapercibidas).


## Omisión de palabras inútiles {#omisión-de-palabras-inútiles}

-   Es conveniente eliminar la mayoría de palabras inútiles en la página.
-   Una vez escrito el texto, es conveniente analizarlo para intentar eliminar la mitad de las palabras.
-   Se debe intentar evitar textos de bienvenida y descripciones al principio de las secciones y en la página principal.
-   Las instrucciones deben escribirse de manera concisa.


## Diseño de la navegación {#diseño-de-la-navegación}


### Tipos de usuarios {#tipos-de-usuarios}

-   Orientados a la navegación.
-   Orientados a la búsqueda.


### Objetivos del menú de navegación {#objetivos-del-menú-de-navegación}

-   Ayudar a encontrar lo que se está buscando.
-   Indicar la localización actual dentro del sitio.
-   Mostrar el contenido del sitio web.
-   Explicar cómo utilizar el sitio.
-   Dar confianza en la calidad del sitio.


### Convenciones {#convenciones}

-   Los menús de navegación deben aparecer en los sitios convencionales.
-   La navegación debe de mostrarse de manera consistente en todas las páginas, con algunas excepciones:
    -   Páginas de pago online.
    -   Páginas de registro, suscripción, personalización de preferencias,...
-   Es conveniente mostrar el logo de la página que actúe de enlace a la página principal en la parte superior izquierda.


### Elementos de la navegación {#elementos-de-la-navegación}


#### Navegación primaria. {#navegación-primaria-dot}

-   Muestra las secciones principales del sitio.


#### Utilidades {#utilidades}

-   Son herramientas que utilizará el usuario. Ejemplos: cuadro de búsqueda, carrito de compra, "mi cuenta", enlaces para iniciar sesión,...
-   Se deben mostrar las cuatro o cinco más importantes en lugar visible (junto a la navegación primaria, por ejemplo).
-   El resto deben mostrarse en el pie de página.


#### Enlace a la página principal {#enlace-a-la-página-principal}

-   En el logo de la empresa.
-   En la navegación principal.


#### Navegación secundaria y posteriores {#navegación-secundaria-y-posteriores}

-   Se debe prestar atención a todos los niveles de navegación, no solo a los principales.
-   De esta manera se asegura una coherencia a todos los niveles.


### Búsqueda {#búsqueda}

-   Es conveniente mostrar un cuadro de búsqueda en las utilidades.
-   El cuadro de búsqueda debe mostrarse de manera convencional (icono de buscar o palabra "Buscar").
-   No deben mostrarse muchas opciones de búsqueda o filtrado en primera instancia. En su lugar, se deben mostrar cuando ya se haya realizado la primera búsqueda con el objeto de ayudar a filtrar los resultados.


### Nombres de las páginas {#nombres-de-las-páginas}

-   Se debe mostrar el nombre de cada una de las páginas en la parte superior del contenido.
-   El nombre debe resaltarse de manera adecuada, ya que es el elemento de mayor jerarquía de la página.
-   El nombre debe concordar con el nombre de la opción del menú que ha conducido a dicha página.


### Localización {#localización}

-   El menú de navegación debe resaltar la sección o secciones en las que se está en cada momento.
-   El resaltado debe ser evidente.


### Migas de pan {#migas-de-pan}

-   Deben aparecer en la parte superior.
-   Se debe utilizar "**>**" para separar niveles.
-   El último nivel (nombre de la página actual) no debe ser un enlace y debe aparecer destacado.


### Pestañas {#pestañas}

-   Son evidentes y fáciles de usar.
-   Deben estar correctamente configuradas para resaltar la sección actual.


### Test de navegación {#test-de-navegación}

El diseñador siempre piensa que el usuario va a llegar a la página deseada a través de la página principal y desde allí a través de la navegación. Sin embargo, en multitud de ocasiones se llega a una página directamente a través de un enlace enviado por otra persona o a través de un buscador.
Por ello, al llegar a una página interior de un sitio web directamente se debería poder contestar a las siguientes preguntas sin demasiada dificultad:

-   ¿Qué sitio es éste? (Nombre del sitio o compañía)
-   ¿En qué página estoy? (Nombre de la página)
-   ¿Cuáles son las secciones principales? (Navegación primaria)
-   ¿Qué opciones tengo en este nivel? (Navegación local)
-   ¿En qué lugar me encuentro dentro de la jerarquía? (Localización)
-   ¿Dónde puedo realizar una búsqueda?


## Referencias {#referencias}

-   [Don't make me think](http://www.sensible.com/dmmt.html), enlace a la web del autor del libro, Steven Krug
-   <https://amybughunter.wordpress.com/2014/08/16/book-summary-dont-make-me-think-by-steve-krug/>
-   <http://www.squeezedbooks.com/articles/dont-make-me-think-a-common-sense-approach-to-web-usability-%282nd-edition%29--summary.html>

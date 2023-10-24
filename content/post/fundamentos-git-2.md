+++
title = "Fundamentos de git II"
date = 2019-09-23T12:18:00+02:00
tags = ["git"]
categories = ["diw", "diw-herramientas-desarrollo"]
draft = false
author = "Pedro Prieto"
+++

Este artículo tiene como objetivo profundizar en el manejo de Git con el uso de **ramas** y **repositorios remotos**.

<!--more-->


## Videotutoriales {#videotutoriales}

-   [Sesión 2.1](https://youtu.be/goMcUY9dZzM)
-   [Sesión 2.2](https://youtu.be/1vMheWF6VXo)
-   [Sesión 2.3](https://youtu.be/aYDyT85NOLg)
-   [Sesión 2.4](https://youtu.be/hBJMwbxb-fc)


## Índice {#índice}

-   Ramas
-   Fusiones de ramas
-   Conflictos
-   Remotos
-   Flujos de trabajo con ramas


## Referencias {#referencias}

-   [Libro de Git](https://git-scm.com/book/es/v2/)
-   [Hoja de referencia de Git](https://training.github.com/downloads/es_ES/github-git-cheat-sheet/)
-   [Hoja de referencia de Git (PDF)](https://training.github.com/downloads/es_ES/github-git-cheat-sheet.pdf)
-   [Herramienta "Visualizing Git"](http://git-school.github.io/visualizing-git/) (muy interesante para comprender el funcionamiento interno de Git y el trabajo con ramas y remotos)


## Contenidos {#contenidos}


### Ramas {#ramas}


#### Definición de ramas {#definición-de-ramas}

-   Una rama es un puntero que apunta a un determinado commit.
-   Un repositorio debe tener una rama como mínimo.
-   El nombre de la rama que se crea por defecto es `master`. Este nombre no es especial ni tiene una función o significado especial.
-   Existe un puntero especial llamado `HEAD` que apunta a la rama en la que estamos en ese momento.
-   Al cambiar de rama se modifica el contenido del directorio de trabajo: éste se muestra tal como estaba en la rama a la que hemos saltado.
-   La creación y el cambio de ramas se realizan de forma instantánea: no tienen apenas coste.
-   El trabajo con ramas es muy interesante por los siguientes motivos:
    -   Se pueden hacer pruebas sin modificar el código en producción.
    -   Se puede separar el trabajo en tareas o subproyectos que no afecten unos a otros.
    -   Cada miembro del equipo puede trabajar sin ser interferido por los demás.


#### Crear ramas {#crear-ramas}

```bash
git branch <nombre_rama>
```


#### Ver ramas disponibles {#ver-ramas-disponibles}

```bash
git branch
```


#### Cambiar de rama {#cambiar-de-rama}

```bash
git checkout <nombre_rama>
```


#### Fusionar una rama {#fusionar-una-rama}

-   Primero nos posicionamos en la rama sobre la que se va a realizar la fusión
-   Para realizar la fusión ejecutar:

<!--listend-->

```bash
git merge <nombre_rama_a_fusionar>
```


#### Eliminar una rama {#eliminar-una-rama}

```bash
git branch -d <nombre_rama>
```


### Remotos {#remotos}


#### Clonar un repositorio {#clonar-un-repositorio}

```bash
git clone <URL_REPOSITORIO>
```


#### Ver remotos {#ver-remotos}

```bash
git remote -v
```


#### Añadir, eliminar y renombrar remotos {#añadir-eliminar-y-renombrar-remotos}

```bash
git remote add <NOMBRE_REMOTO> <URL_REPOSITORIO>   # Añadir remoto
git remote rm <NOMBRE_REMOTO>                      # Eliminar remoto
git remote rename <NOMBRE_ORIGINAL> <NOMBRE_NUEVO> # Renombrar remoto
```


#### Traer información del remoto {#traer-información-del-remoto}

```bash
# Este comando NO realiza la fusión en la rama local
# Si se desean incorporar los cambios habría que realizar un git merge
git fetch [NOMBRE_REMOTO] # El nombre del remoto por defecto es ORIGIN
```


#### Traer y fusionar cambios del remoto {#traer-y-fusionar-cambios-del-remoto}

```bash
git pull [NOMBRE_REMOTO] [NOMBRE_RAMA] # Pull = fetch + merge
```


#### Enviar cambios al remoto {#enviar-cambios-al-remoto}

```bash
git push [NOMBRE_REMOTO] [NOMBRE_RAMA]
```


#### Enviar los cambios de una rama al remoto y crear una rama remota asociada {#enviar-los-cambios-de-una-rama-al-remoto-y-crear-una-rama-remota-asociada}

```bash
git push -u NOMBRE_REMOTO NOMBRE_RAMA
```

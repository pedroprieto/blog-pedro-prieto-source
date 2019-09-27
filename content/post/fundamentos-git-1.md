+++
title = "Fundamentos de Git I"
date = 2019-09-23T11:51:00+02:00
categories = ["diw", "diw-herramientas-desarrollo"]
draft = false
+++

En este artículo se pretende dar una introducción a los comandos más comunes del software de control de versiones **Git**.

<!--more-->


## Videotutoriales {#videotutoriales}

-   [Sesión 1.1](https://www.youtube.com/watch?v=DuewUoPnAmg&index=2&list=PLQg%5FBl-6Gfo9k0KQg5vaaV9r6Hg--nMA7)
-   [Sesión 1.2](https://www.youtube.com/watch?v=uwqvuJ5lrIs&list=PLQg%5FBl-6Gfo9k0KQg5vaaV9r6Hg--nMA7&index=3)


## Índice {#índice}

-   Breve introducción a Git
-   Entornos: consola y escritorio
-   Instalación
-   Configuración
-   Creación de repositorios
-   Cómo guardar cambios
-   Historial de cambios
-   Cómo deshacer cambios
-   Etiquetado


## Referencias {#referencias}

-   [Libro de Git](https://git-scm.com/book/es/v2/)
-   [Hoja de referencia de Git](https://github.github.com/training-kit/downloads/es%5FES/github-git-cheat-sheet/)
-   [Hoja de referencia de Git (PDF)](https://services.github.com/on-demand/downloads/es%5FES/github-git-cheat-sheet.pdf)


## Contenidos {#contenidos}


### Instalación {#instalación}

-   [https://git-scm.com/download](https://git-scm.com/download)


### Configuración {#configuración}

```bash
# Opciones obligatorias (nombre y correo)
git config --global user.name "Nombre y apellido"
git config --global user.email CORREO@ELECTRONICO

# Editor de preferencia. Como ejemplos se incluyen el Notepad y el Notepad ++ en Windows
# Ejecutar sólo una de los tres comandos siguientes
git config --global core.editor notepad # Notepad de Windows
git config --global core.editor "'C:/Program Files/Notepad++/notepad++.exe' -multiInst -notabbar -nosession -noPlugin" # Notepad ++
git config --global core.editor "'C:/Program Files (x86)/Notepad++/notepad++.exe' -multiInst -notabbar -nosession -noPlugin" # Notepad ++ 32 bit

# Almacenamiento de credenciales para no pedir usuario y contraseña de GitHub cada vez que se suban cambios al servidor
# Ejecutar sólo uno de los dos comandos siguientes en función del sistema
git config --global credential.helper cache   # Para Linux
git config --global credential.helper wincred # Para Windows
```


### Creación de repositorios {#creación-de-repositorios}

```bash
git init
```


### Ciclo de vida {#ciclo-de-vida}

{{< figure src="https://git-scm.com/book/en/v2/images/lifecycle.png" >}}


### Revisando el estado {#revisando-el-estado}

```bash
git status
```


### Ignorar archivos {#ignorar-archivos}

-   Archivo `.gitignore`
-   Plantillas de archivos [.gitignore](https://github.com/github/gitignore).


### Visualizar cambios {#visualizar-cambios}

```bash
git diff
git diff <archivo>
```


### Añadir archivos al área de preparación (stage) {#añadir-archivos-al-área-de-preparación--stage}

```bash
git add <archivo> # Añadir archivos individuales
git add .         # Añadir todos los archivos nuevos o modificados
```


### Visualizar cambios de los archivos en el área de preparación {#visualizar-cambios-de-los-archivos-en-el-área-de-preparación}

```bash
git diff --staged
git diff --staged <archivo>
```


### Confirmar cambios (commit) {#confirmar-cambios--commit}

```bash
git commit -m "MENSAJE"
```


### Historial de cambios {#historial-de-cambios}

```bash
git log
git log --graph
```


### Ver cambios realizados en anteriores commits {#ver-cambios-realizados-en-anteriores-commits}

```bash
git show <commit>
```


### Quitar archivo del área de preparación {#quitar-archivo-del-área-de-preparación}

```bash
git reset HEAD <archivo>
```


### Eliminar las modificaciones con respecto al último commit {#eliminar-las-modificaciones-con-respecto-al-último-commit}

```bash
# ¡PELIGRO! Todos los cambios que se hayan hecho al archivo desde el último commit se eliminarán
git checkout -- <archivo>
```


### Etiquetado {#etiquetado}

```bash
git tag
```

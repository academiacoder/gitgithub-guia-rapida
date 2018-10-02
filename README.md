# Git y GitHub, La Guía Rápida

## Indice

1. [Instalación](#id1)
    1. Mac
    2. Windows
    3. Linux
2. Configuración básica
3. Inicializar Proyecto
4. Enviar cambios al Stage
    1. Eliminar cambio del stage
5. Realizar un commit
    1. Ver lista de commits
    2. Volver atras en commits
6. Ramas
7. .gitignore
8. GitHub
    1. Sincronizar nuestro proyecto
    2. Clonar proyecto
9. Despedida


<div id="id1"></div>

## 1 - Instalación

### 1.1 - Mac
Es muy probable que en Mac ya lo tengamos instalado, para comprobarlo vamos a la terminal y tipeamos **git --version**. De todas formas en caso de que no lo tengamos instalado o que queramos comprobar si la versión que tenemos es la última disponible, ingresamos en git-scm.com/downloads en esa página veremos la última versión disponible de Git.

### 1.2 - Windows
En windows no viene instalado por defecto, para descargarlo van a git-scm.com/downloads y descargan el instalador correspondiente a su versión de Windows.

Una vez que lo instalan se les instalará una herramienta llamada Git Bash la cual les brindará una terminal a mi parecer bastante mejor que la por defecto en windows (CMD) así que les recomiendo usar Git Bash, de paso esta herramienta les añade una opción en el menú que se abre al hacer click derecho sobre una carpeta que les da la opción de **Abrir Git Bash Aquí**, con esa herramienta van a abrir una ventana de Git Bash directamente en la carpeta seleccionada.

![Git Bash Here](https://i.stack.imgur.com/7BI04.png)

### 1.3 - Linux
Para Linux lo tenemos más que simple. Dependiendo la distribución que utilicemos ejecutamos uno de los códigos a continuación

* Fedora - **sudo yum install git-core**
* Debian - **sudo apt-get install git**


## 2 - Configuración básica
Una vez tenemos instalado Git, desde la terminal ejecutamos los siguientes comandos para configurar nuestro nombres de usuario y mail.

**git config --global user.name "nombredeusuario"**
**git config --global user.email "maildelusuario**

Con eso ya configuramos Git ahora vamos a comprobar la configuración.

**git config --list**

Si algo está mal solamente ejecutan nuevamente los comandos de user.name o user.email y sobreescriben la configuración.


## 3 - Inicializar proyecto y comprobar estado
Para inicializar un proyecto de Git simplemente en la carpeta principal de nuestro proyecto, abierta desde la terminal ejecutamos.

**git init**

Y para comprobar el estado actual del repositorio ejecutamos.

**git status**


## 4 - Enviar cambios al Stage
Podemos enviar archivos de manera individual con el siguiente comando

**git add nombrearchivo.ext**

También podemos enviar todos los archivos que tengan una extensión específica

**git add \*.ext**

O podemos enviar todos los archivos que hayan cambiado en nuestro proyecto de una sola vez

**git add .**

### 4.1 - Eliminar cambio del stage
Para esto simplemente utilizamos el comando que nos muestra git en pantalla al ejecutar git status y le agregamos el nombre del archivo con la extensión.

### 4.2 - Eliminar todos los cambios del Stage
Simplemente usamos el comando

**git reset**


## 5 - Realizar un commit
Para definitivamente guardar nuestros cambios a un punto donde podamos regresar a ellos ejecutamos

**git commit -m "mensaje del commit"**

El comando -m le indica que vamos a agregarle un mensaje identificador al commit que estamos realizando para que nos sea más fácil identificar que cambios hemos realizado en ese commit específico.

### 5.1 - Ver lista de commits
Para ver los commits que hemos realizado y sus datos, inclusive el identificador para que podamos volver a el usamos

**git log**


### 5.2 - Volver atrás en commits
Para descartar el último commit

**git reset --hard HEAD^**

Si queremos volver atrás un número X de commits por ejemplo 3

**git reset --hard HEAD~3**


## Ramas
Las ramas nos permiten trabajar en nuestro proyecto sin tocar el código principal.

Para abrir una rama ejecutamos

**git branch nombrerama**

Para ir a trabajar en esa rama

**git checkout nombrerama**

Para trasladar todos los cambios que realizamos en esa rama especifica a la rama principal.
Primero vamos a la rama principal.

**git checkout master**

Y ahora fusionamos las ramas indicandole que rama queremos fusionar

**git merge nombrerama**

Podemos también realizar fusiones a otras ramas que no sean la principal, para esto en lugar de usar git checkout master deberán ir a la rama que quieran y desde ahí ejecutar la fusión.


## 7 - .gitignore
Si queremos evitar que Git revise cambios en archivos y no los tenga en cuenta debemos crear un archivo en nuestro repositorio, con el nombre **.gitignore**

Dentro de ese archivo le añadimos simplemente que archivos no queremos que tenga en cuenta

**nombrearchivo.ext**

o podemos decirle que no tenga en cuenta todos los archivos de una extensión epecífica

**\*.extensión**

o podemos decirle que no tome en cuenta una carpeta entera con todo su contenido

**nombrecarpeta/**


## 8 - GitHub

### 8.1 - Sincronizar nuestro proyecto
Para sincronizar nuestro proyecto con GitHub primero debemos crearnos una cuenta y crear un proyecto (repositorio) en GitHub, una vez que lo creamos GitHub nos mostrará algo así

```
echo "# prueba" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/academiacoder/prueba.git
git push -u origin master
```

En nuestro ejemplo ya hemos realizado todo hasta el primer commit y más ya que hemos hecho otros commit.

Ahora solo tenemos que sincronizar nuestro proyecto con ese repositorio remoto con el comando

**git remote add origin `https://github.com/academiacoder/prueba.git`**

Obviamente no va a ser la misma dirección https que la mia va a ser la que a ustedes les brinde GitHub

Y luego enviamos todos nuestros commits con el comando.
**git push -u origin master**

### 8.2 - Clonar proyecto
Para clonar algún proyecto simplemente vamos a GitHub, buscamos el link al proyecto que queremos clonar y desde la linea de comandos ejecutamos

**git clone `https://github.com/academiacoder/prueba.git`**

Esto creará una carpeta con el nombre del proyecto y dentro ya tendremos un proyecto inicializado de Git completo.

## 9 - Despedida
Espero que esta guía les haya servido!

Gracias por mirar y por Aprender!

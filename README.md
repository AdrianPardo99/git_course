# Curso de sintaxis y uso de git como control de versiones y repositorio de trabajo
## Qué es Git?
Git es un software cuyo código fuente esta escrito en distintos lenguajes de programación como lo son C, Shell, Tcl, Perl, Python y otros más.

Este software es una herramienta poderosa de control de versiones de distintos proyectos de software y de otros archivos que no necesariamente son puramente aplicaciones de software, incluso puede funcionar para control de versiones de archivos (Tesis, notas, papers).

Este software es tan poderoso que uno de sus contribuidores principales es Linux Torvalds, como un reconocimiento a esta herramienta esta la integración tanto en sistemas locales para el control, mantenimiento y mejora de un sistema en pequeñas empresas.

También existen servidores y sitios dedicados al control de versiones de software tales paginas nombrando algunas son:
* Github
* Gitbucket
* GitLab
* Bitbucket

## Funcionalidad y ventajas del uso de Git
Si bien muchos pueden pensar en que trabajar con git como herramienta de control de versiones puede ser difícil de utilizar, la integración del software en distintos Sistemas Operativos, así como su sencilla terminal de comandos o incluso de GUI es sencilla de utilizar, al grado que incluso pequeños entornos de desarrollo como Atom, Netbeans, Sublime, VSCode y otros integran algunas herramientas que permiten trabajar de una forma más rápida y ágil.

## Instalación de git
Si bien podemos ir a la página oficial de git para descargar el motor de la aplicación en el caso de Windows, actualmente gracias a las nuevas políticas de Windows y su adopción del kernel de Linux es posible instalarlo rápidamente con un terminal que emule Linux en Windows o simplemente utilizar Linux como sistema base o servidor de versiones

### En sistemas basados en Debian
Si bien su distro más conocida es Ubuntu y que es sencillo de utilizar o de iniciar en el mundo de Linux, la base de dicho Sistema Operativo es Debian, y que otros sabores de Debian clásicos son todas las variantes de Ubuntu, Mint y otras más, la instalación de git solo bastara con:
```bash
  sudo apt install git -y
```

### En sistemas basados en RedHat
Para este caso solo nos bastara escribir:
```bash
  sudo dnf install git -y
  # O
  sudo yum install git -y
```

## Iniciando un repositorio de trabajo de versiones
Para poder trabajar con esto solo bastara con estar en la carpeta donde iniciaremos todo nuestro proyecto de trabajo, ya sea con la documentación o nuestra tesis, o con nuestra aplicación de trabajo, con ello escribiremos lo siguiente:
```bash
  git init
```
Esto nos permitirá crear un directorio llamado _.git_ el cual contendrá nuestro registro de trabajo en el cual es de suma importancia no borrar este directorio.
## Añadiendo archivos en nuestro repositorio local
Para añadir archivos tenemos varias formas de realizar este trabajo, por ello podremos añadir archivos de forma normal, es decir, escribiéndolos de forma específica o añadir todo un compendio de archivos simplemente escribiendo el directorio donde estamos trabajando, para ello un ejemplo de ello es:
```bash
  # Añade el archivo1 contenido en la carpeta directorio
  git add directorio/archivo1.c
  # Añade un compendio de archivos solo escribiendo la carpeta contenedora
  git add directorio/
  # Añade un archivo sencillo
  git add archivo.c
```
## Guardar los cambios realizados después de añadir los archivos
Una vez que realizan la operación _git add_ de todos los archivos o del archivo específicamente modificado hace falta generar un registro de los cambios realizados por el desarrollador o escritor, donde describa que tareas realizo de modo en que este sea entendido y que se lleve una historia del trabajo realizado, para ello un ejemplo de la realización de esto es:
```bash
  git commit -m "Mensaje de descripción del trabajo realizado....."
```
## Revisión de los registros realizados en el repositorio local

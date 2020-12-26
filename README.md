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
## Configurando git para conectarse con alguna plataforma como Github
Para antes de comenzar y en el supuesto de que exista una cuenta en esta plataforma o por el hecho de desear personalizar todos nuestros registros escribiremos lo siguiente en nuestro terminal:
```bash
  git config --global user.name "Nombre Apellido(s)"
  git config --global user.email "email@mail.com"
```
Con esto podremos estar seguros de que nuestro equipo tiene al menos nuestro nombre o alias con el que trabajamos en el repositorio de la computadora local.

## Configurando Github para conexión sin credenciales (vía ssh)
SSH es una aplicación ya sea de tipo cliente o servidor la cual nos permite conectarnos y nos permite realizar tareas push en el repositorio de forma sencilla y rápida en la cual solo nos preocuparemos por trabajar.

Para esto debemos tener instalado la aplicación de ssh y con ello ademas de lo ya previsto generaremos nuestro par de llaves de ssh (privada y publica):
```bash
  ssh-keygen
```
En el cual nos desplegara algunos parámetros con los que podemos trabajar o simplemente dar enter por default para generar nuestras llaves.

Finalmente para añadirlas a nuestro perfil de Github solo haremos uso de nuestra llave publica, que generalmente esta nombrada como _id_rsa.pub_ y la añadiremos a [Github](https://github.com/settings/keys) en donde le daremos simplemente nueva llave ssh y copiaremos el contenido de nuestra llave publica, resguardada con un nombre particular para poder realizar nuestros registros del repositorio local al repositorio de Github

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
Finalmente para ver los registros hechos en el repositorio simplemente escribiremos lo siguiente, lo cual nos despliega información importante como el hash del commit realizado, la posición en la que nos encontramos por si estamos viajando entre registros commit o por si estamos en alguna rama de trabajo, la cual sera explicada más adelante, el Autor del commit con su información, la fecha en que se realizo el commit y el mensaje descriptivo del commit, para obtenerlo:
```bash
  git log
```
## Verificando que archivos hemos modificado eliminado
Si bien en algunos entornos de desarrollo como lo son Atom, Sublime nos permiten ver los trabajos que hemos modificado mediante su misma interfaz en la línea de escritura o en el cambio de colores en nuestro coloreado de carpetas, podemos ver nuestro trabajo aun no registrado con la siguiente línea:
```bash
  git status
```
Para este caso podremos ver que archivos hemos módificado, creado, eliminado y que no los hemos registrado o añadido al repositorio con _git add_ por ello git es de suma ayuda ya que nos permite ver cuanto hemos logrado avanzar y trabajar.

## Conectando un repositorio local con un repositorio vacío de Github
Cuando creemos repositorios sin ninguna información al respecto generalmente necesitaremos conectar nuestro servidor local con nuestro servidor de Github el cual se encuentra vacío y es ahí donde subiremos todo nuestro trabajo y avance, con ello escribiremos:
```bash
  git remote add origin git@github.com:username/project_repository
```

## Creando un archivo que ignore extensiones de archivos o archivos que puedan no ser necesarios para nuestro proyecto
Generalmente el trabajar con algunos lenguajes o con trabajos escritos en LaTex estos nos generan archivos que muchas veces no son necesarios para que alguien más los trabaje o modifique, por ello git incluye un archivo muy importante que permite ignorar o descartar archivos que no sean necesarios llamado _.gitignore_, un ejemplo de su contenido puede ser:
```bash
  # Ignora archivos objeto
  *.o
  # Ignora archivos objeto de los headers
  *.gch
  # Ignora archivos con extensión log
  *.log
  # Y así puede ser llenado hasta el final sin ningún problema
```

## Trabajando colaborativamente por ramas (Branch)

## Añadiendo nuestro trabajo a Github
Finalmente para los casos en el que ya hemos trabajo y queremos trabajar colaborativamente podemos realizar un _push_ el cual nos permitirá resguardar nuestro avance en la plataforma de Github de modo en que nuestro equipo de trabajo puede trabajar sin ningún problema, por ello solo es necesario escribir:
```bash
  # Caso en el que trabajaremos constantemente
  git push
  # Para el caso en que se realice el push por primera vez
  git push --set-upstream origin master
```

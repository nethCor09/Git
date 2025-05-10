# Git
## ¿Qué es un control de versiones?
Usar un sistema de control de versiones (VCS por sus siglas en inglés) es una decisión muy acertada. Dicho sistema te permite regresar a versiones anteriores de tus archivos, regresar a una versión anterior del proyecto completo, comparar cambios a lo largo del tiempo, ver quién modificó por última vez algo que pueda estar causando problemas, ver quién introdujo un problema
y cuándo, y mucho más. Usar un VCS también significa generalmente que si arruinas o pierdes archivos, será posible recuperarlos fácilmente. Adicionalmente, obtendrás todos estos beneficios a un costo muy bajo.

## Sistemas de Control de Versiones
### Sistemas de Control de Versiones Locales
Son los más simples y antiguos. En este modelo, los desarrolladores gestionan el historial de cambios en sus archivos directamente en su máquina local, sin conexión a un servidor. Generalmente, se utiliza una base de datos simple para registrar los cambios, lo que implica que la colaboración con otros usuarios es difícil, ya que no hay un repositorio central para compartir versiones. Un ejemplo clásico es el uso de herramientas como RCS.

### Sistemas de Control de Versiones Centralizados
En este modelo, existe un único servidor central que contiene todos los archivos versionados, y los usuarios deben conectarse a este servidor para obtener o guardar cambios. Esto facilita el trabajo en equipo, ya que todos tienen acceso a la misma fuente de verdad, pero también representa un punto único de fallo: si el servidor se cae, nadie puede colaborar ni acceder al historial. Un ejemplo conocido de este tipo es Subversion (SVN).

### Sistemas de Control de Versiones Distribuidos
Estos sistemas, como Git, permiten que cada usuario tenga una copia completa del repositorio, incluyendo el historial de versiones. Esto ofrece mayor seguridad, ya que si el servidor principal falla, cualquier repositorio local puede restaurar todo el proyecto. También mejora la flexibilidad y la colaboración, ya que los desarrolladores pueden trabajar sin conexión y sincronizar sus cambios posteriormente con otros repositorios.

## ¿Qué es Git?
Git es un sistema de control de versiones distribuido que permite registrar y gestionar los cambios realizados en archivos, especialmente en proyectos de desarrollo de software. Con Git, cada colaborador tiene una copia completa del historial del proyecto en su máquina, lo que permite trabajar de forma independiente, fusionar cambios, y recuperar versiones anteriores. Su diseño está orientado al rendimiento, la integridad de los datos y la colaboración eficiente entre múltiples desarrolladores.

## Historia de Git

Como muchas de las grandes cosas en esta vida, Git comenzó con un poco de destrucción creativa y una gran polémica.

El kernel de Linux es un proyecto de software de código abierto con un alcance bastante amplio. Durante la mayor parte del mantenimiento del kernel de Linux (1991-2002), los cambios en el software se realizaban a través de parches y archivos. En el 2002, el proyecto del kernel de Linux empezó a usar un **DVCS** propietario llamado **BitKeeper**.

En el 2005, la relación entre la comunidad que desarrollaba el kernel de Linux y la compañía que desarrollaba BitKeeper se vino abajo y la herramienta dejó de ser ofrecida de manera gratuita. Esto impulsó a la comunidad de desarrollo de Linux (y en particular a **Linus Torvalds**, el creador de Linux) a desarrollar su propia herramienta basada en algunas de las lecciones que aprendieron mientras usaban BitKeeper. Algunos de los objetivos del nuevo sistema fueron los siguientes:
- Velocidad
- Diseño sencillo
- Gran soporte para desarrollo no lineal (miles de ramas paralelas)
- Completamente distribuido
- Capaz de manejar grandes proyectos (como el kernel de Linux) eficientemente (velocidad y tamaño de los datos)

Desde su nacimiento en el 2005, **Git** ha evolucionado y madurado para ser fácil de usar y conservar sus características iniciales. Es tremendamente rápido, muy eficiente con grandes proyectos y tiene un increíble sistema de **ramificación** (*branching*) para desarrollo no lineal.

## Algunos conceptos en Git

### ¿Qué es un repositorio?
Un repositorio es el espacio donde Git almacena todos los ficheros de un proyecto y su historial de cambios. Puede estar localizado en una máquina local (repositorio local) o en un servidor remoto (repositorio remoto, como GitHub o GitLab). Dentro del repositorio se encuentran tanto los ficheros del proyecto como la base de datos que registra todas las versiones, ramas, confirmaciones (commits) y configuraciones del control de versiones.

### ¿Qué es un fichero (archivo)?
Un fichero, también llamado archivo, los ficheros son los elementos principales que se rastrean; pueden ser código fuente, imágenes, documentación, etc. Git detecta los cambios que se hacen en estos ficheros (como adiciones, eliminaciones o modificaciones) y permite registrarlos como parte del historial del proyecto.

## Estados en Git
Git tiene tres **estados principales** en los que se pueden encontrar tus ficheros:
| **Modificado (Modified)** | **Preparado (Staged)** | **Confirmado (Committed)** |
|---------------------------|-------------------------|-----------------------------|
| El fichero ha sido cambiado pero **aún no se ha preparado** para ser confirmado. | El fichero ha sido marcado con `git add` para **incluirlo en el próximo commit**. | El fichero ya ha sido **guardado de forma permanente en la base de datos de Git**. |

## Áreas Principales de Git
Git también organiza tu proyecto en tres áreas clave:
| **Directorio de Git** (*Git directory*) | **Directorio de trabajo** (*Working directory*) | **Área de preparación** (*Staging area*) |
|----------------------------------------|------------------------------------------------|-------------------------------------------|
| Es donde se almacenan **todos los metadatos** del repositorio, como el historial de versiones y la base de datos de objetos. Este directorio es la parte central de Git y se copia al clonar un repositorio. | Es una **copia de los fichero** extraída desde el Git directory. Aquí puedes ver, editar o eliminar fichero. Representa una versión específica del proyecto que puedes modificar. | Es un archivo (ubicado dentro del Git directory) que **registra qué cambios serán incluidos en el próximo commit**. También se le conoce como "índice" (*index*), aunque actualmente se prefiere el término "área de preparación". |

#### Flujo de trabajo básico en Git
1. **Modificas** fichero en tu directorio de trabajo.  
2. **Preparas** esos fichero con `git add`, moviéndolos al área de preparación.  
3. **Confirmas** los cambios con `git commit`, almacenándolos en el directorio de Git.

#### Estado de los fichero en Git
- Si una versión del fichero está en el **Git directory**, está **confirmada**.
- Si ha sido cambiada y luego agregada al **staging area**, está **preparada**.
- Si ha sido modificada pero **no se ha preparado**, está en estado **modificado**.

## Instalación de Git

Para instalar Git en Debian, ejecuta los siguientes comandos en la terminal:
```bash
sudo apt install git
```
Verifica que la instalación fue exitosa:

```bash
git --version
```

## Configuración de Git
Una vez instalado Git, es recomendable realizar la configuración inicial global, la cual se aplicará a todos los repositorios del usuario. Puedes revisar la documentación en la siguiente guía oficial: [Configuración de Git por primera vez](https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup)

El  siguiente  comando  devuelve  una  lista  de  información  sobre  su  configuración  de  git, 
incluido el nombre de usuario y el correo electrónico: 
```bash
git config -l 
```


Con el siguiente comando puedes configurar tu nombre de usuario: 
```bash
git config --global user.name "nethcor343"
```
 
Este  comando  le  permite  configurar  la  dirección  de  correo  electrónico  del  usuario  que 
utilizará en sus confirmaciones. 

```bash
git config --global user.email "nethcordev343@gmail.com"
```
## Ruta de configuración
Git guarda la configuración en tres niveles, cada uno con su propio archivo:

| **Nivel**   | **Archivo de configuración**                      | **Descripción**                                                                 |
|-------------|---------------------------------------------------|---------------------------------------------------------------------------------|
| Sistema     | `/etc/gitconfig`                                  | Configuración para todos los usuarios del sistema (requiere privilegios root). |
| Usuario     | `~/.gitconfig` o `~/.config/git/config`           | Configuración específica para el usuario actual.                               |
| Proyecto    | `.git/config` (dentro del repositorio Git)        | Configuración específica para un repositorio en particular.

## Establecer un editor predeterminado
Puedes elegir un editor de texto como predeterminado para Git. Ejemplos:
### Visual Studio Code:
```bash
git config --global core.editor "code --wait"
```
### Nano:
```bash
git config --global core.editor nano
```
### Vim:
``` bash
git config --global core.editor vim
```
## Habilitar colores en la salida de Git
```bash
git config --global color.ui auto
```
## Fundamentos de Git
### Inicializando un repositorio en un directorio existente
Todo empieza desde aquí. El primer paso es inicializar un nuevo repositorio Git localmente 
en la raíz del proyecto. Puedes hacerlo con el siguiente comando:
```bash
git init
```
Git creará una carpeta oculta llamada **.git**, que contendrá todas las referencias asociadas al
sistema de control de versiones.

![git_init](/img/git_init.png)


## Agregar un archivo al área de preparación
El  siguiente  comando  agregará  un  archivo  al  área  de  preparacióno (Stage).
```bash
git add img/
```
![git_add](/img/git_Add.png)

Si desea agregar todos los archivos de su proyecto al área de preparación, puede usar un 
comodín .y se agregarán todos los archivos automáticamente. 
```bash
git add .
```
![git_add](/img/git_Add_..png)

## Revisando el Estado de tus Archivos
Este comando muestra el estado actual del repositorio, incluyendo los archivos modificados,
eliminados o agregados, así como también los archivos que se han añadido al área de Stage, junto con los que aún no han sido seguidos por Git.
```bash
git  status
```  
![git_status](/img/git_Status.png)

## confirmar cambios

### ¿Qué es un commit?
En cuanto al concepto de commit, debemos conocer que se refiere a la toma de una fotografía del estado actual de nuestro proyecto en un momento determinado. Cada vez que realizamos un commit, estamos guardando los cambios que hayamos realizado (y que nosotros seleccionemos) en nuestro proyecto en ese momento específico. Es una acción que guarda oficialmente esos cambios en el historial del repositorio. Cada commit incluye un mensaje descriptivo, un identificador único (hash), información del autor y una marca de tiempo, permitiendo rastrear qué se modificó, quién lo hizo y cuándo.
```bash
git commit 
```
Este comando abrirá un editor de texto predeterminado donde podrás escribir un mensaje de 
confirmación completo. Un  mensaje  de  confirmación  se  compone de un breve resumen de los cambios, una línea vacía y una descripción completa de los cambios después. 
 
### confirmar cambios con un mensaje 
Puedes  agregar  un  mensaje  de  confirmación  sin  abrir  el  editor.  Este  comando  solo  te 
permite especificar un breve resumen para tu mensaje de confirmación. 
```bash
git commit -m "your commit message here"
``` 
![git_status](/img/git_commit.png)
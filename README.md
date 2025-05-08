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
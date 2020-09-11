---
title: Como instalar Git en Windows 10
date: 2020-09-11 16:25:00 -0300
categories: [Windows, git]
tags: [git, github]
toc: false
seo: git, github, instalación de git en windows
date_modified: 2020-09-11 16:25:28 -0300
---

![upload-image]({{ "/assets/img/sample/git.png" | relative_url }})

Git, git, git...\! GitHub? No, git :\) 

Cuando empezamos a jugar con el código no nos preocupamos mucho por las modificaciones que le vamos haciendo a los archivos.*Hasta que hicimos nuestra primer cosita linda y la rompemos y no podemos volver atrás porque ya modificamos un montón de cosas y no nos acordamos del código anterior.* Y es ahí donde empezamos a hacer copias. Si no exploraste mucho por la web, lo más probable es que copies tu archivo y lo pegues, incluso en la misma carpeta, modificándole un poco el nombre para poder identificar cada archivo. 

Ahí es dónde aparece **git**. Git es un Sistema de Control de Versiones \(lo pueden encontrar también como SCV o VCS *Version Control System*\). Justamente, git viene a salvarnos cuando nuestro proyecto crece, o cuando hacemos cambios y nos arrepentimos. Usando git vamos a poder volver a la versión anterior. ¿Por qué? Porque un sistema de control de versiones registra los cambios que se realizan en un archivo o conjunto de archivos. Al tener esos cambios identificados, vamos a poder volver a la versión que querramos.  

Dentro de los SCV, git se encuentra dentro de los denominados **Distribuidos**. ¿Qué significa esto? Que cuando descarguemos una copia de algún repositorio en, por ejemplo, GitHub no sólo nos va a descargar la última copia instantánea de los archivos, sino que replica completamente el repositorio. 


Para poder instalar Git en nuestro Windows 10, vamos a ingresar a [su web oficial](https://git-scm.com/download/) y vamos a seleccionar la opción "Windows". Una vez haya terminado la descarga del instalador, lo vamos a ejecutar. La siguiente pantalla que nos va a aparecer es la licencia. Seleccionamos "Next".

![upload-image]({{ "/assets/img/sample/instalador.png" | relative_url }})

En la pantalla siguiente, nos dá la opción de elegir la carpeta en la cual vamos a instalar Git. En mi caso, dejé la ruta por defecto. Al dar click en "Next", nos aparecerán opciones para seleccionar los componentes a instalar. 
Acá tenemos que seleccionar lo siguiente: 
   - Windows Explorer Integration: nos va a permitir ejecutar git bash y git GUI desde la carpeta que estemos seleccionando desde un botón que añadirá en el menú que se despliega al hacer click con el botón derecho del mouse sobre la carpeta o archivo elegido.
   - Git LFS: reemplazará archivos grandes \( audio, video, gráficos, etc...\) con indicadores de texto dentro de Git, a la vez que almacenará el contenido del archivos en un servidor externo \(como GitHub\).
   - Associate .git\* configuration files with the default text editor: nos permitirá asociar un editor de texto por defecto para manejar los archivos .\*git
   - Associate .sh files to be run with Bash: abrirá los archivos .sh con Bash.
Si además queremos generar un acceso directo en el escritorio, tenemos que seleccionar la opción "Additional icons". Si quisiéramos generar un atajo en el menú de inicio, en la pantalla siguiente nos dejará crearlo. Si no queremos el atajo en el menu de inicio, basta con seleccionar "Don't create a Start Menu folder".

Una vez terminemos con la creación de atajos, nos permitirá seleccionar un editor por defecto. Yo seleccioné Visual Studio Code. 

![upload-image]({{ "/assets/img/sample/shortcuts.png" | relative_url }})

El paso siguiente es seleccionar cómo queremos usar Git desde la línea de comando. Acá vamos a dejar seleccionada la opción recomendada y le damos click a "Next".

También deberemos elegir cuál librería SSL/TLS queremos que Git utilice para las conexiones HTTPS. En este caso, yo voy utilizar la OpenSSL que para conectarnos con repositorios en GitHub está perfecto. La otra opción \(Windows Secure Channel\) se usa cuando trabajamos dentro de una organización que utiliza certificados validados. 

El siguiente paso está relacionado a la líneas que vamos a escribir en la terminal para utilizar Git. Vamos a seleccionar "Checkout Windows-style, commit Unix-style line endings". Esto es porque Git nos permite elegir cómo queremos configurar los finales de línea, pero para no entrar en detalles que puedan ser un tanto complejos, nos vamos a quedar con esta opción.

Paso siguiente: configurar nuestro emulador de terminal para usar Git Bash. Mi recomendación: usar MinTTY. La realidad es que se comporta mejor que la consola por defecto de Windows.

![upload-image]({{ "/assets/img/sample/path.png" | relative_url }})

Siguiente paso: elegir el comportamiento por defecto de "git pull". Más adelante vamos a hablar sobre esto, por ahora nos limitaremos a seleccionar "Default\(fast-forward or merge\)".

Respecto al manejo de credenciales, por el momento nos vamos a quedar con la opción "None". 

Luego de apretar "Next", se nos presenta una pantalla para configurar opciones extras. Recomiendo seleccionar "Enable file system caching" porque nos va otorgar lograr un mejor funcionamiento. 

En la sección de configuración de opciones experimentales nos vamos a fijar que "Enable experimental support for pseudo consoles" no esté seleccionado. Luego, hacemos click en "Install".

![upload-image]({{ "/assets/img/sample/merge.png" | relative_url }})

Una vez haya terminado la instalación, seleccionaremos "Launch Git Bash" para realizar algunas configuraciones.

![upload-image]({{ "/assets/img/sample/complete.png" | relative_url }})

Cuando abra la consola, vamos a ejecutar los siguientes comandos: 

   - ``git config --global user.name "Tu Nombre"`` Este comando nos va a permitir configurar nuestro nombre de usuario. 
   - ``git config --global user.name`` Nos va a servir para comprobar que nuestro nombre de usuario se configuró correctamente. 
   - ``git config --global user.email "tuemail@tuproveedor"`` Nos permitirá configurar nuestro e-mail.
   - ``git config --global user.email`` Nos va a mostrar si nuestro e-mail se configuró de manera correcta.

![upload-image]({{ "/assets/img/sample/config.png" | relative_url }})

Ahora lo que vamos a hacer es clonar un repositorio en [GitHub](https://github.com/). En este caso voy a clonar un repositorio propio para hacer una modificación y enviar esos cambios a mi repositorio en GitHub. 

Primero tenemos que dirigirnos a la URL del repositorio que queremos clonar. Una vez ahí, vamos a hacer click en el botón "Code". Desde la pestaña "Clone with HTTPS" vamos a copiar la URL.

![upload-image]({{ "/assets/img/sample/code.png" | relative_url }})

Ahora vamos a volver a nuestra terminal y nos vamos a mover hasta la carpeta donde queranmos ubicar el repositorio que vamos a clonar. En mi caso, la ubicación es una carpeta llamada "github" dentro del disco C. Para movernos hasta ahí vamos a usar el comando "cd" que significa "change directory"; en español: cambiar de directorio. Para esto voy a ejecutar los siguientes comandos: 

   - ``cd c:/`` Cambiará el directorio al disco C.
   - ``cd github`` Nos posicionará dentro de la carpeta "github".

Una vez dentro de la ubicación deseada vamos a ejecutar el comando que nos permitirá clonar el repositorio:
    ``git clone https://laURLdeTuRepositorio``

![upload-image]({{ "/assets/img/sample/clone.png" | relative_url }}) 

Luego de incluir un nuevo archivo podemos comprobar el estado de nuestro repositorio. Para ello nos servirá el siguiente comando: 
  
    ``git status``

En verde podemos ver el nuevo archivo listo para ser comentado e integrado al repositorio. Para agregar un comentario explicando cuál es el cambio, vamos a ejecutar lo siguiente: 

    ``git commit -m "contenido del mensaje que explica brevemente la modificación"``

Una vez hecho el commit, lo que queda es cargar el contenido del repositorio local \(la PC\) al repositorio remoto \(en este caso, GitHub\). El comando a utilizar en este caso es: 

    ``git push`` 

Al ejecutar el comando "git push", se va a abrir una ventana emergente de OpenSSH que nos va a pedir nuestro nombre de usuario de GitHub. Una vez ingresado el nombre de usuario, nos va a solicitar nuestra contraseña para la cuenta GitHub.         

![upload-image]({{ "/assets/img/sample/push.png" | relative_url }}) 

Acá abajo dejo la última captura de pantalla, donde se aprecia que el push se ha efectuado: 

![upload-image]({{ "/assets/img/sample/final.png" | relative_url }}) 

---
Si este tutorial te sirvió o si querés comentarme algo, no dudes en contactarme por [**Instagram**](https://www.instagram.com/kiky.tech/) o [**Twitter**](https://www.twitter.com/kikytech/).


---
title: Como instalar NetBeans en Linux - Ubuntu 20.4.1 LTS Focal Fossa
date: 2020-08-07 19:10:00 -0300
categories: [Linux, NetBeans]
tags: [ubuntu, java]
toc: false
seo:
  date_modified: 2020-08-07 19:31:28 -0300
---

![upload-image]({{ "/assets/img/sample/netbeans.png" | relative_url }})

Apache NetBeans es un Entorno de Desarrollo Integrado o IDE, por sus siglas en inglés Integrated Development Environment muy popular en el desarrollo de aplicaciones Java. 

Si estás por arrancar un curso y te pidieron instalar NetBeans, pero usás Ubuntu 20.04 y no sabés como hacerlo; llegaste al lugar indicado.  

Lo primero que vamos a hacer es ***actualizar*** todas los paquetes en nuestra lista. Para ello vamos a abrir la terminal \(Ctrl + Alt + t\) y tipeamos: 
   ``sudo apt update``

![upload-image]({{ "/assets/img/sample/sudoupdate.png" | relative_url }})

Vamos a ingresar nuestra contraseña y nos va a aparecer una pantalla como esta: 

![upload-image]({{ "/assets/img/sample/update.png" | relative_url }})

Una vez que terminó de actualizar todo, vamos a instalar Java en nuestro sistema, ya que ***es un requerimento de Netbeans tener instalado como mínimo Java 8 en su versión JDK*** (JDK viene del inglés Java Development Kit). Tipeamos en nuestra terminal: 
   ``sudo apt install default-jdk``

![upload-image]({{ "/assets/img/sample/jdk.png" | relative_url }})


Y ahora si: podemos instalar NetBeans. Como Ubuntu 20.04 trae incorporado ***snapd*** por defecto, nos queda tipear por terminal: 
   ``sudo snap install netbeans --classic``

![upload-image]({{ "/assets/img/sample/apache.png" | relative_url }})

Si todo salio bien \(se supone que si\) en la terminal nos aparecerá el mensaje: "netbeans 12.0 from Apache NetBeans✓ installed"

![upload-image]({{ "/assets/img/sample/instalado.png" | relative_url }})

Luego lo podemos ejecutar desde la misma terminal tipeando ``netbeans`` o podemos cerrar la terminal y abrir NetBeans desde el menú de aplicaciones. 

![upload-image]({{ "/assets/img/sample/abierto.png" | relative_url }})

![upload-image]({{ "/assets/img/sample/abriendo.png" | relative_url }})

Si por algún motivo quisiéramos desinstalar Apache Netbeans, deberíamos ingresar por terminal lo siguiente: 
   ``sudo snap remove netbeans``

---
Si este tutorial te sirvió o si querés comentarme algo, no dudes en contactarme por [**Instagram**](https://www.instagram.com/kiky.tech/)   


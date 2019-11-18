
![Docker logo](img/docker_logo.png)

## Docker for Developers - Introducción

#### Festival of Software UNISS] (http://www.uniss.edu.cu), 21 de marzo de 2017
#### Labs Docker Cuba] (http://docker.cuban.tech), 22 de marzo de 2017

###### http://twitter.com/olemislc DIFUNDE LA PALABRA-
###### http://cuban.tech DIFUNDE LA PALABRA-
________________________

###### Tráiganlos: [presentación en línea](http://slides.cuban.tech/uniss_20170321.html) /[código fuente](http://git.cuban.tech/slides.cuban.tech) /[docker image](http://hub.docker.com/r/tplcom/docker-presentation/)

###### Bajo licencia de[Attribution 4.0 International](http://creativecommons.org/licenses/by/4.0/).

--

#### Agradecimientos

#### Organizadores del Festival de Software UNISS (Gracias)
#### Basado en diapositivas para su presentación en[Python Meetup Thessaloniki](http://www.meetup.com/PyThess/), 15 de abril de 2016

###### http://twitter.com/theoploumis DIFUNDE LA PALABRA-

---

#### Who am I?

- Presidente de SciPyLA 2017
  * Ciencia + Pitón + América Latina
- Mantenedor de algunos plugins de Trac
- Proyecto Apache Bloodhound
- GT Python-Cuba, Fundación Python Software
- Comprometedor de Brython

--

#### Who I used to be? 

- Graduado de ISPJAE (CUJAE) .... hace unos años
- Ámbitos de competencia
  * Antivirus
  * TVC / ICRT
  * Programación (web, escritorio, Android, Smart TV, vestimenta)
  * Soporte para DevOps

--

#### Who I used to be? (contd.) 

- Campos de competencia (cont.)
  * Bus de campo (Modbus, DNP3, radio, CANbus, Profibus)
  * Datos grandes (Apache Hadoop / Spark, Machine learning)
  * Makers
    + Impresora 3D, CNC, Visualizador
    + DIY (Frambuesa Pi, Beaglebone Black, ODROID, MicroPython, Arduino)

---

### Visión general de la charla

- Historia y antecedentes
- Resumen de acopladores
- Casos de uso de Docker
- Comprensión de Docker
- Ejemplos de acopladores
- Ecosistema portuario
- Próximos eventos

---

### Primer contacto con Docker - PyCon 2014

Intro to Docker - PyCon 2014](img/docker.pycon2014.png)

---

#### The origins

| | |
|:----:|:----:|
| Futuro de los contenedores Linux - PyCon 2013](img/docker.pycon2013.png) | ![Docker in DjangoCon 2013](img/docker.djangocon2013.png) |[Docker in DjangoCon 2013].
| PyCon 2013 | DjangoCon 2013 | DjangoCon 2013

---

### Historia de Docker

 - Salomón Hykes ([@solomonstre](http://twitter.com/solomonstre))
 - dotCloud (ahora Docker Inc)
 - Marzo de 2013
 - Licencia de Apache 2.0
 - 30.000 estrellas en Github
 - 260.000 repositorios públicos en hub.docker.com
 - Docker Inc adquiere a todo el mundo <small><sup>TM</sup></small>
 - Docker se une a la "[Open Container Initiative](http://www.opencontainers.org/)", junio de 2015

---

#### What about today?

| | |
|:-----:|:------:|
| DockerCon 2017](img/dockercon.2017.small.png) | ![PyCon 2017](img/pycon.2017.small.png) |[PyCon 2017](img/pycon.2017.small.png)
| DockerCon 2017 | PyCon 2017 | PyCon 2017
| 5 pistas, 4 tutoriales, 4 charlas.
| 5.000 asistentes. 3.000 asistentes.

---

#### Docker Birthday #4

![Cumpleaños de Docker #4](img/Docker-bday-4.jpg)

---

#### Let me let me ask you

- ¿Quién sabe lo de[Docker](http://docker.com)?
- ¿Quién utiliza Docker para el desarrollo?
- ¿Quién utiliza Docker en la producción?
- ¿Quién lo intentó pero no pudo hacerlo?

---

### ¿Qué es Docker?

> Docker es una plataforma abierta para desarrollar, enviar y ejecutar aplicaciones.

> Docker le permite empaquetar una aplicación con todas sus dependencias en una unidad estandarizada para el desarrollo de software.

--

### Docker en el ecosistema de las TIC

Virtualización](img/app.containers.png)

---

### Docker contra VMs

!Docker vs virtualización tradicional](img/vms_vs_containers.jpg)

---

### Beneficios portuarios

 - Rápido (despliegue, migración, reinicio)
 - Seguro
 - Ligero (ahorra disco y CPU)
 - Código Abierto
 - Software portátil
 - Microservicios e integraciones (APIs)
 - Simplificar DevOps
 - Capacidades de control de versiones

--

#### Micro-what ## Servicios?

Arquitectura de microservicios](img/microservicios.png)

---

#### Common Docker usages

 - Entorno Sandbox (desarrollar, probar, depurar, educar)
 - Integración e implementación continuas
 - Escalar aplicaciones
 - Colaboración para el desarrollo
 - Configuración de la infraestructura
 - Desarrollo local
 - Aplicaciones de varios niveles
 - PaaS, SaaS

###### Ver los resultados de la[encuesta de 2016] (http://www.docker.com/survey-2016)

--

### Entorno de desarrollo

Entorno de desarrollo](img/devenv.jpg)

--

### Educación JupyterHub software

![JupyterHub](img/jupyterhub.gif)

--

### Educación - Despliegue de JupyterHub

![Componentes JupyterHub](img/jupyterhub-setup.png)

--

### Integración continua

Integración continua con Docker](img/dagda3.jpg)

--

### Entrega continua - Joomla

Entrega continua de Joomla](img/joomla-docker-cd.jpg)

--

### Escalado - de 10 a 1000

Descripción del problema de Apache Mesos](img/dockercon14_mesos.1.png)

###### Benjamin Hindman (Twitter) - DockerCon 2014[video](http://youtu.be/F1-UEIG7u5g)

--

### Escalado - regiones de servidores de aplicaciones

Regiones del servidor de aplicaciones Apache Mesos](img/dockercon14_mesos.2.png)

###### Benjamin Hindman (Twitter) - DockerCon 2014[video](http://youtu.be/F1-UEIG7u5g)

--

#### Scaling - ouch!

!Mensaje de correo electrónico de Apache Mesos](img/dockercon14_mesos.3.png)

###### Benjamin Hindman (Twitter) - DockerCon 2014[video](http://youtu.be/F1-UEIG7u5g)

--

### Escala - problema amplificado

![Apache Mesos - problema amplificado](img/dockercon14_mesos.4.png)

###### Benjamin Hindman (Twitter) - DockerCon 2014[video](http://youtu.be/F1-UEIG7u5g)

--

### Escala - Utilización

![Utilización de Apache Mesos](img/dockercon14_mesos.5.png)

###### Benjamin Hindman (Twitter) - DockerCon 2014[video](http://youtu.be/F1-UEIG7u5g)

--

### Escalado - Administrador de clústeres

! arquitectura Apache Mesos](img/dockercon14_mesos.6.png)

###### Benjamin Hindman (Twitter) - DockerCon 2014[video](http://youtu.be/F1-UEIG7u5g)

--

### Escala - Ejecución

![Asignación de recursos de Apache Mesos](img/dockercon14_mesos.7.png)

###### Benjamin Hindman (Twitter) - DockerCon 2014[video](http://youtu.be/F1-UEIG7u5g)

--

### Escalado - Apache Mesos soporta Docker desde 2014

Apache Mesos ](img/dockercon14_mesos.8.png)

###### Benjamin Hindman (Twitter) - DockerCon 2014[video](http://youtu.be/F1-UEIG7u5g)

--

### Contenedores en la plataforma Google Cloud Platform

| | |
|-----|-----|
Centro de datos de Google](img/google.datacenter.png) | ![GCE soporta Docker](img/gce.docker.png) ||[GCE soporta Docker](img/gce.docker.png)

- Todo en Google se ejecuta en un contenedor
  *[LMCTFY](https://github.com/google/lmctfy) y Docker
- 2 mil millones de envases por semana

--

### Grandes datos impulsados por Docker

![BlueData Epic Platform](img/bluedata.epic.png)

-----------------

###### Joe Beda, ingeniero principal de software, Google Cloud Platform
###### GlueCon - 22 de mayo de 2014

---

### La tecnología detrás de Docker

 - Linux[x86-64](http://www.wikiwand.com/en/X86-64)
 - [Ir](http://golang.org/) idioma
 - Arquitectura[Cliente - Servidor](http://www.wikiwand.com/en/Client%E2%80%93server_model) (deamon)
 - Union file systems ([UnionFS](http://www.wikiwand.com/en/UnionFS): AUFS, btrfs, vfs, etc.)
 - [Namespaces](http://en.wikipedia.org/wiki/Cgroups#NAMESPACE-ISOLATION) (pid, net, ipc, mnt, uts)
 - Grupos de control ([cgroups](http://www.wikiwand.com/en/Cgroups))
 - Formato de contenedor ([libcontainer](http://github.com/opencontainers/runc/tree/master/libcontainer "Libcontainer proporciona una implementación nativa de Go para crear contenedores con espacios de nombres, cgroups, capacidades y controles de acceso al sistema de archivos. Permite gestionar el ciclo de vida del contenedor realizando operaciones adicionales tras la creación del contenedor.")))

###### Ver más en[Understanding docker] (http://docs.docker.com/engine/understanding-docker/)

--
#### Código de muelle escrito en Go

| | |
|----|----|
| | [![Docker and Go](img/golang_docker.jpg)](http://golang.org/) | | [![Golang Book](img/golang.book.png)](http://golang.org/) |

--

### Los namespaces de Linux

![Linux namespaces](img/ns.jpg)

--

### Asignación de recursos con cgroups

![ejemplo de asignación de cgroups](img/cgroups.1.gif)

--

### Asignación de recursos con cgroups

![ejemplo de asignación de cgroups](img/cgroups.2.1.png)

---

### La arquitectura Docker

![Arquitectura de Docker](img/architecture.svg)
###### Ver más en[Understanding docker] (http://docs.docker.com/engine/understanding-docker/)

---

### Componentes de la rampa

 - (Docker) cliente
 - demonio
 - máquina
 - artificio
 - formar
 - enjambrar
 - registro

---

### Cliente portuario

Es la principal interfaz de usuario de Docker. Acepta comandos del usuario
y se comunica de un lado a otro con un demonio Docker.

---

### El demonio Docker

![Docker libs](img/docker-langs.small.png)

Funciona en una máquina anfitriona. El usuario no interactúa directamente con el demonio,
sino a través del cliente Docker con la api o tomas RESTful.

---

#### Docker engine

Un Cliente con un demonio como también como herramienta de composición de docker. Se suele denominar simplemente "docker".

---

### Máquina portuaria

![Logotipo de la máquina acopladora](img/docker_machine.png)

Una herramienta que facilita enormemente la creación de hosts Docker en su ordenador,
en proveedores de cloud computing y dentro de su propio centro de datos.
Crea servidores, instala Docker en ellos y configura el cliente para que hable con ellos.

---

#### Docker compose

![Docker componer logo](img/docker_compose.png)

Una herramienta para definir y ejecutar aplicaciones complejas con Docker
(por ejemplo, una aplicación multi-contenedor) con un solo archivo.

--

### Ejemplo de orquestación de contenedores

![Docker componer ejemplo](img/nginx_flask_postgres_docker.png)

---

#### Docker swarm

![Logotipo del enjambre del muelle](img/docker_swarm.png)

Una herramienta de agrupación nativa para Docker. Enjambres de piscinas juntos varios Docker
y los expone como un único host Docker virtual. Se puede escalar a múltiples hosts.

---

### Distribución portuaria

![Logotipo de distribución portuaria](img/docker_distribution.png)

Un servicio (alojado) que contiene repositorios de imágenes que responden a la API del Registro.

---

### Pasos de un flujo de trabajo Docker

```
docker run -i -t -d ubuntu:15.04 /bin/bash
```

 - Tira de la ubuntu:15.04[imagen] (http://docs.docker.com/engine/userguide/containers/dockerimages/ "Una capa de sólo lectura que es la base de su contenedor. Puede tener una imagen principal para abstraer la instantánea más básica del sistema de archivos") del[registro] (http://docs.docker.com/registry/ "The central place where all publicly published images live. Puedes buscarlo, subir tus imágenes allí y cuando sacas una imagen de un docker, viene el repositorio/hub.")
 - Crea un nuevo[contenedor] (http://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/ "A runnable instance of the image, basically it is a process isolated by docker that runs on top of the filesystem that an image provides.")
 - Asigna un sistema de ficheros y monta una capa de lectura-escritura[layer] (http://docs.docker.com/engine/reference/glossary/#filesystem "A set of read-only files to provision the system. Piensa en una capa como una instantánea de sólo lectura del sistema de archivos.")
 - Asigna una[interfaz de red/puente] (http://www.wikiwand.com/en/Bridging_%28networking%29 """)
 - Configura una[dirección IP] (http://www.wikiwand.com/en/IP_address "Una dirección de protocolo de Internet (dirección IP) es una etiqueta numérica asignada a cada dispositivo (por ejemplo, ordenador, impresora) que participa en una red informática que utiliza el protocolo de Internet para la comunicación").
 - Ejecuta un proceso que usted especifica (```` /bin/bash ```)
 - Captura y proporciona salida de la aplicación

---

#### The docker image

| | |
|-----|-----|
| Arquitectura Docker](img/arquitectura.small.png) | ![ubuntu:15.04 imagen](img/image-layers.jpg "Una capa de sólo lectura que es la base de su contenedor. Puede tener una imagen padre para abstraer la instantánea más básica del sistema de archivos. Cada imagen Docker hace referencia a una lista de capas de sólo lectura que representan las diferencias del sistema de archivos. Las capas se apilan una encima de otra para formar una base para el sistema de archivos raíz de un contenedor.) |

---

#### The docker container

| | |
|-----|-----|
| Arquitectura Docker](img/arquitectura.small.png) | ![contenedor usando imagen ubuntu:15.04](img/container-layers.jpg "Una instancia ejecutable de la imagen, básicamente es un proceso aislado por docker que se ejecuta sobre el sistema de archivos que proporciona una imagen. Para cada contenedor hay una capa nueva, delgada y grabable - capa de contenedor - en la parte superior de la pila subyacente (imagen)"). |

--

#### Union filesystem explained

![Explicación de UFS](img/ufs.png)

---

#### The Dockerfile

> Un Dockerfile es un documento de texto que contiene todos los comandos que un usuario puede llamar en la línea de comandos para crear una imagen.

 - [Esta presentación](Dockerfile)
 - [Dockerfile con comentarios en línea](http://github.com/cubantech/docker-presentation/blob/gh-pages/examples/dockerfile/Dockerfile) sólo para la educación
 - [Referencia del archivo del muelle] (http://docs.docker.com/engine/reference/builder/) en los muelles del muelle
 - Archivos portuarios oficiales ([rieles](http://github.com/docker-library/rails/blob/master/Dockerfile),[nodejs](http://github.com/ReadyTalk/nodejs-docker/blob/master/base/Dockerfile),[django](http://github.com/docker-library/django/blob/master/3.4/Dockerfile),[Drupal](http://github.com/docker-library/drupal/blob/master/8.1/fpm/Dockerfile))

--

#### Dockerfile for these slides

```
DE bitnami/apache
MAINTAINER Olemis Lang <olemis@cuban.tech>

# Añade todo el repositorio.
AGREGAR /opt/bitnami/apache/htdocs/

# Configure esta opción como ruta inicial cuando inicie sesión a través de ssh.
WORKDIR /opt/bitnami/apache/htdocs/
```

--

### Árboles de imágenes de Docker

Árbol de imágenes del muelle](img/docker_images.gif)

---

#### Common Docker Commands

```
// Información general
man docker // man docker-run
docker help // docker help run
información del muelle
versión portuaria
docker network ls

// Imágenes
docker images // docker[IMAGE_NAME]
docker pull[IMAGE] // docker push[IMAGE]

// Contenedores
carrera de muelle
docker ps // docker ps -a, docker ps -l
parada/arranque/rearranque de la base[CONTAINER].
estadísticas portuarias[CONTENEDOR]
docker top[CONTAINER]
puerto de atraque[CONTAINER]
inspección de muelle[CONTENEDOR]
docker inspect -f "{{.State.StartedAt }}" [CONTENEDOR]
docker rm[CONTENEDOR]

```

---

### Ejemplos de Docker

- SSH en un contenedor
- Construir una imagen
- Docker[Volumen](http://docs.docker.com/engine/userguide/containers/dockervolumes/)
- Contenedores[Linked](http://docs.docker.com/engine/userguide/networking/default_network/dockerlinks/)
- Utilizando[docker-compost] (http://docs.docker.com/compose/)
- Contenedores de báscula con docker-compost
- Compartir una imagen (compartir esta presentación)
- Empaquetar una aplicación con su entorno
- Pantalla y sonido dentro de los contenedores (x-forward)

--

#### Ejemplo: SSH en un contenedor

```
docker pull ubuntu
docker run -it --nombre ubuntu_ejemplo ubuntu /bin/bash
```

--

#### Ejemplo: Ejecute Jenkins de forma autónoma

Vamos a correr la[imagen oficial de Jenkins] (http://hub.docker.com)

```
docker pull jenkins

// Pruébalo
docker run -d -p 8098:8080 --nombre jenkins_example_1 jenkins
http://localhost:8098 DIFUNDE LA PALABRA-
```

--

#### Ejemplo: Construir una imagen

Construyamos una[imagen de Jenkins] (http://github.com/komljen/dockerfile-examples/blob/master/jenkins/Dockerfile)

```
cd ~/Docker-presentación
clon de git git@github.com:komljen/dockerfile-examples.git.git
cd dockerfile-ejemplos/jenkins
docker build -t jenkins-local.

// Pruébalo
docker run -d -p 8099:8080 --nombre jenkins_example_2 jenkins-local
Abierto http://localhost:8099
```

--

#### Ejemplo: Volumen del acoplador

Usemos[servidor Apache](http://bitbucket.org/EdBoraas/apache-docker/src/)

```
cd ~/Docker-presentación
mkdir apache-ejemplo
cd apache-ejemplo

docker pull bitnami/apache
docker run --nombre apache_volume_example \
           -p 8180:80 -p 443:443 \
           wWw.Subs-Team.Tv $(pwd):/opt/bitnami/apache/htdocs/ \
           -d bitnami/apache

// Crear localmente un archivo index.html
echo "Funciona usando mount." >> index.html

Abra http://localhost:8180 para ver el archivo html
```

--

### Ejemplo: Drupal + MariaDB con aislamiento de red

Bitnami ofrece contenedores preconfigurados y de cero confinamiento

```
docker pull bitnami/mariadb:latest bitnami/drupal:latest

red de acopladores crear drupal-tier
docker run -d --nombre mariadb --net drupal-tier bitnami/mariadb:más reciente
docker run -d -p 8081:80 -p 443:443 --nombre drupal --net drupal-tier bitnami/drupal:más reciente
```

--

#### Ejemplo: Contenedores Docker Link

Vamos a crear una aplicación[Drupal app](http://hub.docker.com/_/drupal/) (apache, php, mysql, drupal)

```
cd ~/Docker-presentación
ejemplo de drupal-link de mkdir
cd ejemplo de drupal-link

docker pull drupal:8.0.6-apache
docker pull mysql:5.5

// Poner en marcha un contenedor para mysql
docker run --nombre mysql_example \
           -e MYSQL_ROOT_PASSWORD=root \
           -...MYSQL_DATABASE=drupal.
           DIFUNDE LA PALABRA-
           -...MYSQL_PASSWORD=drupal.
           -d mysql:5.5

// Iniciar un contenedor de Drupal y enlazarlo con mysql
// Uso: --...enlace[nombre o id]:alias
docker run -d --nombre drupal_example \
           -p 8280:80 \
           --DIFUNDE LA PALABRA-
           drupal:8.0.6-apache

Abra http://localhost:8280 para continuar con la instalación.
// En el uso del host db: mysql

// Hay una conexión apropiada
docker inspect -f "{{.HostConfig.Links }}" drupal_example
```

--

#### Ejemplo: Uso de Docker Compose

Vamos a crear una aplicación Drupal con[docker-compos.yml](http://github.com/cubantech/docker-presentation/blob/gh-pages/examples/docker-compose/docker-compose.yml)

```
cd ~/Docker-presentación
git@github.com:cubantech/docker-presentation.git DIFUNDE LA PALABRA-
cd docker-presentación/ejemplos/docker-compuesto

// Ejecute docker-composition usando el docker-composition.yml
gato docker-composite.yml
docker-compone -d
```

--

#### Ejemplo: Compartir una imagen pública

```
cd ~/Docker-presentación
git@github.com:cubantech/docker-presentation.git DIFUNDE LA PALABRA-
cd docker-presentación

docker pull bitnami/apache
docker build -t olemis/docker-presentation .

// Pruébalo
docker run -itd --nombre docker_presentation \
           -p 8480:80 \
           olemis/docker-presentación

Abrir http://localhost:8480, deberías ver esta presentación

// Empújalo en el hub.docker.com
docker push olemis/docker-presentación
```

--

#### Ejemplo: Exportar/Guardar/Cargar, etc.

```
docker pull nimmis/alpine-apache
docker run -d --nombre apache_example \
           nimmis/alpine-apache

// Crear un archivo dentro del contenedor.
Ver http://github.com/nimmis/docker-alpine-apache para más detalles.
docker exec -ti apache_example \
            /bin/sh -c 'mkdir /test && echo "This is it." >> /test/test.txt'

// Pruébalo. Deberías ver el mensaje: "Esto es todo."
docker exec apache_example cat /test/test.txt

// Confirme el cambio.
docker commit apache_export_example myapache:latest

// Cree un nuevo contenedor con la nueva imagen.
docker run -d --nombre myapache_ejemplo myapache

// Debería ver la nueva carpeta/archivo dentro del contenedor myapache_example.
docker exec myapache_example cat /test/test.txt

// Exportar el contenedor como imagen
cd ~/Docker-presentación
docker exportar myapache_example > myapache_example.tar

// Importar una nueva imagen desde los archivos exportados
cd ~/Docker-presentación
docker importar myapache_example.tar myapache:nuevo

// Guardar una nueva imagen como tar
docker save -o ~/Docker-presentation/myapache_image.tar myapache:new

// Cargar una imagen desde el archivo tar
docker load < myapache_image.tar

```

--

#### Ejemplo: GUI con Docker

Ver ejemplos en[hub.docker.com/u/jess](http://hub.docker.com/u/jess/)

```
// Antes de empezar, debemos permitir el acceso a todos en el Servidor X (localmente)
// De lo contrario, los siguientes contenedores nunca arrancarán y no podrán utilizar x11
xhost +

// Libreoffice
docker run -d \
            wWw.Subs-Team.Tv /etc/localtime:/etc/localtime:ro \
            wWw.Subs-Team.Tv/.X11-unix:/tmp/.X11-unix \
            -e DISPLAY=unix$DISPLAY \
            -e GDK_SCALE \
            -e GDK_DPI_SCALE \
            --nombre libreoffice \
            jess/libreoffice

// SublimeTexto 3
docker run -it \
           wWw.Subs-Team.Tv $HOME/.config/sublime-text-3/:/root/.config/sublime-text-3 \\
           wWw.Subs-Team.Tv/.X11-unix:/tmp/.X11-unix \
           -e DISPLAY=$DISPLAY \
           --nombre sublime_text \
           jess/sublime-text-3

// Audacia (sonido en el contenedor de la rampa)
docker run -d \
            wWw.Subs-Team.Tv /etc/localtime:/etc/localtime:ro \
            wWw.Subs-Team.Tv/.X11-unix:/tmp/.X11-unix \
            -e DISPLAY=unix$DISPLAY \
            -e QT_DEVICE_PIXEL_RATIO \
            --...dispositivo /dev/snd.
            --group-add audio \
            --nombre audacia \
            jess/audacity

// Desactivar el acceso a x11
xhost -

```

---

### Las puntas de los muelles

Se conocen las mejores prácticas (véase una lista en[examples/tips](http://github.com/cubantech/docker-presentation/tree/gh-pages/examples/tips)])

- Optimice los contenedores (consulte[fromlatest.io](http://www.fromlatest.io/) y[imagelayers.io](http://imagelayers.io))
- Crea tu propia base diminuta
- Los contenedores no son máquinas virtuales
- Pila completa de Imágenes VS 1 proceso por Contenedor
- Crea tu registro privado
- Crear comandos de acceso directo
- Utilice plantillas docker-compos.yml (vea por qué en[lorry.io](http://lorry.io/))
- Ten en cuenta la versión del agente de la dársena hub.docker.com

---

### La guerra de los Dockers

| Tipo | Software | Software
|:----:|----------|
| Clustering/orchestration |[Swarm](http://docs.docker.com/swarm/),[Kubernetes](http://kubernetes.io/),[Marathon](http://mesosphere.github.io/marathon/),[MaestroNG](http://github.com/signalfx/maestro-ng),[decking](http://decking.io/),[shipyard](http://shipyard-project.com/),[Apache Mesos](http://mesos.apache.org) |
| Registros portuarios |[Portus](http://port.us.org/),[Docker Distribution](http://github.com/docker/distribution),[hub.docker.com](http://hub.docker.com),[quay.io](http://quay.io),[Google container registry](http://cloud.google.com/tools/container-registry/),[Artifactory](http://www.jfrog.com/artifactory/),[projectatomic.io](http://www.projectatomic.io/) |].
| PaaS con Docker |[Rancher](http://rancher.com/),[Tsuru](http://tsuru.io/),[dokku](http://github.com/dokku/dokku),[flynn](http://flynn.io/),[Octohost](http://octohost.io/),[DEIS](http://deis.io/) |
OS hecho de Contenedores |[RancherOS](http://rancher.com/rancher-os/) | | Containers |[RancherOS] (http://rancher.com/rancher-os/)

--

### Benchmarking y estadísticas

![Docker vs Kubernetes vs Amazon ECS](img/docker-orchestration-survey.png)

###### Ver los resultados de la[encuesta de 2016] (http://www.docker.com/survey-2016)

---

### Alternativas Docker

- [Rocket, rkt](http://github.com/coreos/rkt)
- [Contenedores Linux, LXC](http://linuxcontainers.org/)
- Hipervisor de contenedores Linux, LXD] (http://www.ubuntu.com/cloud/lxd)
- [Cárceles BSD] (http://www.freebsd.org/doc/handbook/jails.html)
- [Zonas Solaris](http://oracle.com/solaris)
- [puente levadizo] (http://research.microsoft.com/en-us/projects/drawbridge/)

---

#### En vez de recursos

![Usando Docker](img/using.docker.png)

 - [Awesome Docker](http://github.com/veggiemonk/awesome-docker) (lista de recursos y proyectos de Docker)
 - [Hoja de trucos de Docker](http://github.com/wsargent/docker-cheat-sheet)
 - [Docker in Practice](http://www.manning.com/books/docker-in-practice),[The Docker Book](http://www.dockerbook.com/),[Using Docker](http://bit.ly/using-docker)
 - [alias de Docker/abreviaturas] (http://github.com/cubantech/docker-presentation/tree/gh-pages/examples/shortcuts/docker-aliases.sh)
 - Docker[estudios de casos](http://www.docker.com/customers)

---

### Eventos futuros - Docker Cuba

| | |
|-----|-----|
| | [![Docker Cuba](img/dockercuba.logo.png)](http://docker.cuban.tech) | | [![Join us!](img/qr.volunteer.es.png)](http://forms.cuban.tech/volunteer/es) ||

####### Únete a nosotros -[forms.cuban.tech/volunteer/es](http://forms.cuban.tech/volunteer/es)

 - Encuentros en Cuba Docker[docker.cuban.tech](http://docker.cuban.tech)
   * Celebración del cumpleaños de Docker #4 en todas las provincias.

---

### Eventos futuros - SciPyLA 2017

| | |
|-----|-----|
| | [![SciPyLA 2017](img/scipyla.h.png)](http://scipyla.org/conf/2017) | | [![Emerging Computing Technologies](img/scipyla2017.tech.png)](http://scipyla.org/conf/2017/tracks/tech) |

 - [Taller de Tecnologías Informáticas Emergentes] (http://scipyla.org/conf/2017/tracks/tech)
   * Infraestructura para la investigación reproducible
   * .... con Docker! \o/

--

### Convocatoria de ponencias / revisores

Convocatoria de ponencias](img/scipyla2017.cfp.png)

- Fecha límite de presentación 30 de septiembre de 2017
- [Aplicar como árbitro](http://scipyla.org/conf/2017/forms/reviewers/)
- [Instrucciones para los autores] (http://scipyla.org/conf/2017/tracks/tech)

--

#### Participate

- Envía tus charlas / talleres[bit.ly/scipyla2017-actividades-tech](http://bit.ly/scipyla2017-actividades-tech)
- [Enviar carteles](http://scipyla.org/conf/2017/forms/poster)

---

### ¿Preguntas?

!Pythons sobre Docker!](img/docker_logo.png)

[Revisar esta presentación] (http://goo.gl/lkau9t)

> Siguiente: Docker en producción, Escalado, Registros privados, PaaS.

###### En esta presentación he utilizado[oh my zsh](http://ohmyz.sh/),[docker 17.03](http://github.com/docker/docker/releases/tag/v1.12.5),[wharfee](http://github.com/j-bennet/wharfee) y[dry](http://github.com/moncho/dry).

# Docker

## Construir, Distribuir y Ejecutar

“Docker te permite construir, distribuir y ejecutar cualquier aplicación en cualquier lado.”

Problemáticas del desarrollo de software

1. **Construir** - Escribir código en la máquina del desarrollador. (Compile, que no compile, arreglar el bug, compartir código, etc. )

Problemática:

- Entorno de desarrollo (paquetes)
- Dependencias (Frameworks, bibliotecas)
- Versiones de entornos de ejecución (runtime, versión Node)
- Equivalencia de entornos de desarrollo (compartir el código)
- Equivalencia con entornos productivos (pasar a producción)
- Servicios externos (integración con otros servicios ejem: base de datos)

2. **Distribuir** - Llevar la aplicación donde se va a desplegar (Transformarse en un artefacto)

Problemática:

- Output de build heterogeo (múltiples compilaciones)
- Acceso a servidores productivos (No tenemos acceso al servidor)
- Ejecución nativa vs virtualizada
- Entornos Serverless

3. **Ejecutar** - Implementar la solución en el ambiente de producción (Subir a producción)
El reto Hacer que funcione como debería funcionar

Problemática:

- Dependencia de aplicación (paquetes, runtime)
- Compatibilidad con el entorno productivo (sistema operativo poco amigable con la solución)
- Disponibilidad de servicios externos (Acceso a los servicios externos)
- Recursos de hardware (Capacidad de ejecución - Menos memoria, procesador más debil)

## Virtualización

Permite atacar en simultáneo los tres problemas del desarrollo de software profesional.

**Problemas de la virtualizacion**

- **PESO**: En el orden de los GBs. Repiten archivos en común. Inicio lento.
- **COSTO DE ADMINISTRACION**: Necesita mantenimiento igual que cualquier otra computadora.
- **MULTIPLES DE FORMATO**: VDI, VMDK, VHD, raw, etc.

**Containerización**
El empleo de contenedores para construir y desplegar software.

- Flexibles
- Livianos
- Portables
- Bajo acoplamiento
- Escalables
- Seguros

**Virtualizacion** vs **Containerización**

- **Virtualización**: A diferencia de un contenedor, las máquinas virtuales ejecutan un sistema operativo completo, incluido su propio kernel.

**Containerización**: Un contenedor es un silo aislado y ligero para ejecutar una aplicación en el sistema operativo host. Los contenedores se basan en el kernel del sistema operativo host (que puede considerarse la fontanería del sistema operativo), y solo puede contener aplicaciones y algunas API ligeras del sistema operativo y servicios que se ejecutan en modo de usuario.

## Preparando tu entorno de trabajo

En la pagina de [docker](https://www.docker.com/get-started) podemos descargar el programa.

Para instalar en kali-linux pueder ver como instalar docker por esta [pagina](https://computingforgeeks.com/install-docker-and-docker-compose-on-kali-linux/).

[docker Hub](https://hub.docker.com/signup) Es el repositorio publico de lo que construimos con docker.

## [Play with Docker](https://labs.play-with-docker.com/)

En play with docker puedes usar una maquina virtual con docker instalado por 4 horas.   

## Qué es y cómo funciona Docker

Componentes DENTRO del circulo de Docker:

- **Docker daemon**: Es el centro de docker, el corazón que gracias a el, podemos comunicarnos con los servicios de docker.Podemos exponer nuestro docker deamon y que una maquina que este en otra red se comunique con nuestro docker.

- **REST API**: Como cualquier otra API, es la que nos permite visualizar docker de forma “gráfica”.

- **Cliente de docker**: Gracias a este componente, podemos comunicarnos con el corazón de docker (Docker Daemon) que por defecto es la línea de comandos.


Dentro de la arquitectura de Docker encontramos:

- **Contenedores**: Es la razón de ser de Docker, es donde podemos encapsular nuestras imagenes para llevarlas a otra computadora, o servidor, etc.

- **Imagenes**: Son las encapsulaciones de x contenedor. Podemos correr nuestra aplicación en Java por medio de una imagen, podemos utilizar Ubuntu para correr nuestro proyecto, etc.

- **Volumenes de datos**: Podemos acceder con seguridad al sistema de archivos de nuestra máquina.

- **Redes**: Son las que permiten la comunicación entre contenedores.

## Iniciando con docker
Después de la instalación, configuramos nuestro usuario para que pueda utilizar docker sin permisos de root.
1. Creamos un grupo:
```
sudo groupadd docker
```
2. Añadimos nuestro usuario al grupo:
```
sudo usermod -aG docker name_user
```

3. Cerramos la terminal y la volvemos abrir
4. Activar los comandos del grupo
```
newgrp docker
```
5. Verificamos si todo funciona
```
docker run hello-world
```

## Conceptos fundamentales de Docker: contenedores

**Que es un contenedor ?**

- Es una agrupación de procesos.

- Es una entidad lógica, no tiene el limite estricto de las máquinas virtuales, emulación del sistema operativo simulado por otra más abajo.

- Ejecuta sus procesos de forma nativa.

- Los procesos que se ejecutan adentro de los contenedores ven su universo como el contenedor lo define, no pueden ver mas allá del contenedor, a pesar de estar corriendo en una maquina más grande.

- No tienen forma de consumir más recursos que los que se les permite. Si esta restringido en memoria ram por ejemplo, es la única que pueden usar.

- A fines prácticos los podemos imaginar cómo maquinas virtuales, pero NO lo son. Máquinas virtuales livianas.

- Docker corre de forma nativa solo en Linux.

- Sector del disco: Cuando un contenedor es ejecutado, el daemon de docker le dice, a partir de acá para arriba este disco es tuyo, pero no puedes subir mas arriba.

- Docker hace que los procesos adentro de un contenedor este aislados del resto del sistema, no le permite ver más allá.

- Cada contenedor tiene un ID único, también tiene un nombre.

## estado de Docker

- `docker ps` : permite ver los contenedores que tenemos en nuestro docker(los que estan encendidos)

- `docker ps -a`: permite ver los TODOS(encendidos o apagados) los contenedores que tenemos en nuestro docker junto con su **contenedor ID** y el **Names**.

- `docker run nombre_Del_contenedor`: crea un nuevo contenedor y lo ejecuta.

- `docker run --name nombreDelNames NombreContenedor` : permite crear un contenedor con un **Names** a nuestra eleccion.Docker no permite tener dos contenedores con el mismo **Names** en tu misma instalacion.

- `docker rename nombreDelNames nuevoNombreNames`: permite renombar el **Names** de un contenedor.

- `docker inspect contenedor-ID` : para ver mas informacion de algun contenedor como la configuracion del contenedor. Tambien podemos usar el **Names** en lugar del **contenedor ID** y tendremos el mismo resultado.

- `docker rm NamesOrID`: permite eliminar un contenedor con el **Names** o con el **contenedor ID**.

- `docker container prune`: permite eliminar todos los contenedores que estan apagados.

- `docker run --rm --name nombreDelNames NombreContenedor` : si este contenedor se detiene se borra automaticamente.

## El modo interactivo

- `docker run ubuntu` : correr un linux ubuntu entero en docker.

- `docker ps -a`:  Los **COMMAND** es el proceso que corre el contenedor al arrancar, **STATUS** indica el estatus del contenedor, en **STATUS** aparecera `Exited (0)` eso significa que todo salio bien. Todo proceso al terminar devuelve un codigo de salida, cero quiere decir que todo salio bien y cualquier numero distinto de cero quiere decir que hubo un error. 

- `docker run -it ubuntu`: `-it` es como interactivo, es como si correramos una maquina virtual de ubuntu en tu computadora.

- `exit` : si estamos dentro de un contenedor interactivo pododemos salir del el con este comando.

Si salimos del contenedor entonces este mismo se apaga.

## Ciclo de vida de un contenedor

Cada vez que un contendor se ejecuta, en realidad lo que ejecuta es un proceso del sistema operativo. Este proceso se le conoce como **Main process**.

**Main process**
Determina la vida del contenedor, un contendor corre siempre y cuando su proceso principal este corriendo.

**Sub process**
Un contenedor puede tener o lanzar procesos alternos al main process, si estos fallan el contenedor va a seguir encedido a menos que falle el main.
- Batch como Main process
- Agujero negro (/dev/null) como Main process

```
docker run --name   -d ubuntu tail -f /dev/null 
```
Lo que hace este comando es crear un contenedor que esta corriendo en un subproceso, va estar encendido aun que nosotros no estemos en modo interctivo.
 
`docker exec -it elNameDelContenedor bash` : En un contenedo que ya existe y esta corriendo ejecuta un comando o un proceso. Con esto entrariamos a dicho contenedor pero si salimos de nuevo de el con `exit` vemos que el contenedor aun sigue corriendo, esto es por que mientras el proceso principal de un contenedor este corriendo en contenedor va a estar corriendo.

- `docker inspect --format '{{.State.Pid}}' contenedorName` : permite obtener el **process ID**

- `kill -9 process-ID`: permite matar un proceso que este corriendo.

- `docker kill alwaysup` : tambien permite matar el proceso del contenedor.

## Exponiendo contenedores

```
docker run -d --name proxy nginx
```
si ejecutamos `docker ps` podemos ver al nuevo contenedor corriendo y en **POSTS** podemos ver un valor, eso quiere decir que el contenedor esta escuchando en el puerto indicado. Pero si tratamos de ir al navegador y ponemos `localhost:80` no arroja ningun resultado.

Cada contenedor tiene su propia interfaz de red virtual eso quiere decir que si el contenedor esta escuchando en el puerto 80 entonces no sera el mismo que el puerto de mi computador.

Si quieremos que el puerto de algun contenedor este expuesto en un puerto de nuestra maquina entonces:
1. Frenar y borrar el contenedor:
```
docker stop proxy
docker rm proxy
```
tambien se puede hacer con un solo comado:
```
docker rm -f alwaysp
```
Este comando permite borrar un contenedor aun que este encendido.

2. crear un nuevo contenedor con el comando:
```
docker run --name NameDelContenedor -p 8080:80 nginx
```
- `-p` : el primer parametro que pide es el puerto de la maquina anfitriona `:` en puerto del contenedor expuesto.

si pustamos en el teclado `CTRL + c` entonces matamos el proceso del contenedor.

3. si queremos que el contenedor corrar como un subproceso simplemente agregamos `-d`:
```
docker run --name NameDelContenedor -d -p 8080:80 nginx
```

- `docker logs NameContenedor` : para ver los logs de algun contenedors

- `doker logs -f NameCOntenedor` : permite ver los logs a medida que van llegando. si pustamos en el teclado `CTRL + c` entonces el contenedor va a seguir vivo pero dejamos de ver los logs.

- `doker logs --tail 10 -f NameCOntenedor` : permite ver solamente las ultimas 10 lineas de logs.

## Bind mounts

Queremos que lo que ocurra dentro del contenedor ocurra en nuestra maquina tambien.

lo primero que cesitamos es la ruta de la carpeta, la podemos saber con el comando `pwd`:
```
docker run -d --name db -v /home/sann/Documents/development/practicas/dockerData/mongoData:/data/db mongo
```
- `-v` : significa que vamos a hacer un bind mount. los parametros que pide son:
```
ruta_De_la_manina:ruta_dentro_Del_contenedor 
```

Ahora que el nuevo contedor esta corriendo vamos a gener cambios en el contenedor.
```
docker exex -it db bash
```
Ahora que estamos dentro intenemos dejar alguna informacion dentro
```
mongo
use dbMOngo
db.users.insert({"nombre": "diego"})
db.users.find()
exit
exit
```
Ahora matamos el contenedor:
```
docker rm -f db
``` 

ahora si vamos a la carpeta que creamos y que dimos la direccion ante `/home/sann/Documents/development/practicas/dockerData/mongoData` podemos ver que hay un monton. Cuando nostros generamos cambios en la base de datos de mongo dentro del contenedor, como este directorio esta montado en el contenedor y estaba despensajando un directorio que mongo usa, todos los archivos que se fueron generando ahi aparecieron en mi maquina tambien.

Ahora si creamos un nuevo contenedor con los datos de la misma carpeta lo que va a pasar es que los datos que guardamos en el contenedor anterios van a estar disponibles en el nuevo contenedor.

Esta es una manera simple de compartir datos de un contenedor hacia nuestro disco y entre contenedores.

## Volúmenes

Docker nos ofrece otras maneras de manejar datos distintas a los Bind mounts que se llama volumenes, que es la manera mas estandar de manejar datos en docker.

Lo que es importante entender es que la parte del disco que afectan a los volumenes en docker en manerajada por docker y nosotros no tenemos acceso amenos que seamos usuarios privilegiados. Es muy practico para disponer un lugar donde docker va almacenar datos y que nadie mas pueda tocar excepto docker.

Los **volumenes** los podemos ver con:
```
docker volume ls
```
Si ejecutamos dicho comando hay un monton de volumenes, estos son los que docker ha creado.

Para crear un volumen ejecutamos:
```
docker volume create nombre_Que_queramos
```
si volvemos a ejecutar `docker volume ls` aparecera el que hemos creado.

Ahora lo que vamos a hacer es crear un nuevo contenedor y montale este volumen en el directorio donde la base de datos escribe sus datos:
```
docker run -d --name db --mount src=dbdata,dst=/data/db mongo
``` 
- `--mount`: nos permite ser mas especificos que solamente poniendo la `-v`. Lo primero que especificamos es que queremos hacer que este disponible para el contenedor que vamos a tener.
- `src=` : seguido de src tenemos que poner el nombre el volumen que queremos usar(que ya creamos antes) 
- `dst=` : es el destino donde va a estar montado.

Todo lo que hagamos con un contenedor siempre se va a poder ver con un inspect
```
docker inspect db
```
Va a funcionar como un Bind mounts pero no sabemos que archivos hay y ningun otro usuario puede ir y ver que archivos hay amenos que entremos al contenedor.

## Insertar y extraer archivos de un contenedor

Lo que vamos aver ahora, independientemente que utilizemos bind mounts o volumenes o nada, podamos introducir archivos aun contenedor o extraer archivos de un contenedor.

crearemos un achivo para probar esta funcionalidad
```
touch prueba.txt
```
```
docker run -d --name copytest ubuntu tail -f /dev/null
```
```
docker exec -it copytest bash  
```

Dentro del contenedor creamos un archivo:
```
mkdir testing
exit
```

Para copiar nuestro archivo `prueba.txt` dentro del contenedor vamos a usar:
```
docker cp prueba.txt
```
- `cp`: los parametros de comando cp son el archivo despues el contenedor`:`la direccion dentro del contenedor, en este caso le ponemos otros nombre al archivo, esto funciona por que copea el contendo y lo pone dentro de un archivo con diferente nombre. 

Ahora entramos de nuevo al conteendor para verificar que se creo el archivo.
```
docker exec -it copytest bash
```

Asi es como introducimos archivos un contenedor, aun que el contenedor tenga volumen o bind mount no importa, no afectaria la operacion de `cp`.

Tambien es posible extraer el archivo con diferente nombre.
```
docker cp copytest:/testing localtesting
```
Con esto estariamos copiando un directorio completo del contenedor a nuestra maquina.

No es necesario que el contenedor este corriendo para que podamos usar `docker cp` el unico requerimento es que exista.

- **Host**: Donde Docker esta instalado.
- **Bind Mount**: Guarda los archivos en la maquina local persistiendo y visualizando estos datos (No seguro).
- **Volume**: Guarda los archivos en el area de Docker donde Docker los administra (Seguro).
- **TMPFS Mount**: Guarda los archivos temporalmente y persiste los datos en la memoria del contenedor, cuando muera sus datos mueren con el contenedor.

## Conceptos fundamentales de Docker: imágenes
Las imagenes son como docker intenta solucionar los problemas de construccion y de distribucion de software.

Las imagenes son moldes apartir de las que docker crea contenedores, una piza de software  empaquetada de foma liviana que contiene todo lo necesario para que un contenedor pueda ejecutarse exitosamente.

Para trabar con imagenes vamos a usar `image`:
```
docker image ls
```
nos mostrara las imagenes que hasta ahora hemos usado.
- `TAG`: Es como si fuera la version de la imagen, cuando no le especificamos ninguna entonces docker asume `latest`.

En [Docker Hub](https://hub.docker.com/) podemos buscar imagenes de docker.

```
docker pull ubuntu:20.04
```
Este comando `pull` trae una imagen sin correr un contenedor, por defecto va a utilizar docker hub que es un repositorio publico, pero podriamos especificar otro si asi quisieramos.

si ejecutamos denuevo `docker image ls` y nos aparecen dos imagenes o mas con el **IMAGE ID** igual significa que son imagenes exacatamente iguales, el **TAG** es solamente un puntero logico hacia los archivos reales que estan por debajo eso quiere decir que el solamente tenemos un ubuntu aun que muestren dos ubuntus.

## Construyendo una imagen propia
De una imagen podemos crear infinitos contenedores.
crearemos un nuevo archivo:
```
touch Dockerfile
code .
```
Todos los **Dockerfile** empiezan con la misma palabra
```
FROM ubuntu:latest
Run touch /usr/src/hola-mundo.txt
```
-  `FROM ubuntu:latest`: Todo Dockerfile va a estar basado en algo mas, vamos a partir de algo mas.

- `Run touch /usr/src/hola-mundo.txt` : Cuando to construya la imagen se va a ejecutar este comando, esto no quiere decir que despues de que inicie el contenedor se va a ejecutar este comando, no.

En la terminal de comando ejecutamos:
```
docker build -t ubuntu:world .
```
- `-t`: tag, demeos definir como nombrar a la imagen y despues le tenemos que da runa ruta, ruta del contexto de buld que vamos a utilizar, el contexto de build es a que parte del disco tiene acceso el proceso build mientras se esta ejecutando, cuando le ponemos `.` nos referimso al directorio en donde estamos en este momento.

Cuando lo ejecutemos vamos a ver que hizo varios `steps`.
Lo primero que hizo es mandarle el contexto de build al docker deamon, estos pasos que fue siguiente generaron `id` cada uno de esos id son las capas, cada instruccion que pongamos en un **Dockerfile** va a generar una nueva capa. Todas las imagenes son un conjunto de capas o de **layes**.

Si ejecutamos:
```
docker image ls
```
veremos la imagen que acabamos de construir.

Ahora correremos un nuevo contenedor con la imagen que acabamos de construir:
```
docker run -it ubuntu:world
```
si recoramos cuando creamos la imagen ingresamos este codigo `Run touch /usr/src/hola-mundo.txt` dentro del DOckerfile.

entonces si revamos en el contenedor:
```
ll /usr/src
```
Podremos ver que el archivo existe. Ese archivo fue creado durante el tiempo de build no cuando iniciamos el contenedor.

Para publicar la imagen usamos:
1. logiarte con tus credenciales de docker hub
```
docker login
```
2. retagear o cambiar el nombre de esta imagen a una que vaya a un repositorio que si nos pertenezca ya que si usamos el comando `docker image ls` vemos que la imagen que nosotros creamos en **REPOSITORY** dice ubuntu.
```
docker tag ubuntu:world usuarioDockerHub/ubuntu:world
```
si ejecutamos de nuevo el comadno `docker image ls` vemos que el nombre de **REPOSITORY** de nuestra imagen cambio.
3. empujamos la imagen 
```
docker push usuarioDockerHub/ubuntu:world
```

Las imagenes que publicamos son publicas, cualquier persona la puede descargar.

## El sistema de capas

para ver las capas:
```
docker history nombreDeImagen
```
- `nombreDeImagen` :     ubuntu:world 
Hay otra manera de ver esto mejor, es la herramienta [dive](https://github.com/wagoodman/dive).

Una vez que tengas instalada la herramienta dive ejecutamos:
```
dive nombreImagen
```
y con `CTRL + c` podemos salir de dive.

Es muy importante entender la relacion que tiene con git, entendamos que las capas son inmutables y por eso cuando con una capa borramos un archivo que se creo en la capa anterior en realidad esas dos capas existen y simplemente lo que hicimos fue desperdiciar espacio por que cada una de esas capas genera una diferencia con la anterior.

Las capas de la imagen no pueden ser cambiadas ni por el contenedor ni por nosotros una vez que las hayamos creado. Es interesante que investiges sobre el comando `docker commit`.

## comandos de Dockerfile
Dentro del archivo podemos usar los comando como:
- `COPY`: puede copiar archivos y pegarlos en otra ruta.Ejemplo:
```
COPY [".", "/usr/src/"]
```

- `WORKDIR`: especificar un directorio de trabajo como un `cd`. Ejemplo:
```
WORKDIR /usr/src
```

- `RUN`:  permite ejecutar comando como en una terminal, en este caso lo usaremos para instalar dependecias.Ejemplo:
```
RUN npm install
```

- `EXPOSE`: los que hace es permitir que un puerto sea vinculable a la maquina. Ejemplo:
```
EXPOSE 3000
```

- `CMD` : define el comando por defecto que va a ejecutarse cuando corramos este contenedor. Ejemplo:
```
CMD ["node","index.js"]
```

## Aprovechando el caché de capas para estructurar correctamente tus imágenes

Una de las herramientas que nos da docker para agilizar nuestro tiempo de trabajo es que considera cada uno de los layers(Capas) cada vez que intentamos construir una nueva, eso se llama **layer cache**, si nosotros estamos queriendo construir una capa que ya existe en el sistma, docker se da cuenta y no la construye y entonces nos ahorra tiempo.

Si queremos cambiar la version de node de una imagen ya creada entonces como es la capa base de toda la imagen va invalidar todos los layers(y se invalida el cache).Entonces se va a tardar mas por que tiene que instalar todo de nuevo, en cambio si no hacermos ninguna modificacion sera mas rapida la creacion de algun contenedor.

En desarrollo una de las cosas que queremos hacer es cambiar codigo de manera frecuente, si cambiamos una linea de codigo el cambiar el nombre de la imagen va a volver a instalar todo por que hubo una mdoificacion en el codigo y se invalida. No es algo que queramos, solamente cambiamos una linea de codigo que node puede interpretar sin necesidad de reiterar todas las dependencias.

**Por que pasa eso?**
Esto pasa por que nuestro **Dockerfile** no esta bien estructurado. Nuestro Dockerfie es:
```
FROM ubuntu:latest

COPY [".", "usr/src"]

WORKDIR /usr/src

RUN npm install

EXPOSE 3000

CMD ["node", "index.js"]
```

En este caso la instalacion de dependencias es lo que mas tarda entonces tenemos que copiar los archivos indispensables como librerias primero y dejar abajo la estructura de codigo para que si se cambia el codigo de una aplicacion no tenga que estar reinstalando las dependencias una y otra vez.

```
FROM ubuntu:latest

COPY ["package.json","package-lock.json" , "usr/src"] //en esta linea vamos acopiar el archivo donde indica las dependencias que vamos a descargar

WORKDIR /usr/src

RUN npm install // aqui da la orden para instalar las dependencias

COPY ["." , "usr/src"] // aqui copiamos la carpeta donde viene el codigo de la app, en este caso como copiamos y pasamos antes "package.json","package-lock.json" entonces docker no los copiara de nuevo, asi de eficiente es. Si cambiamos el codigo de la app entonces el cache se invalidara apartir de este punto si necesidad de reinstalar las librerias.

EXPOSE 3000

CMD ["node", "index.js"]

```

Siempre y cuando modidifiquemos cosas que no sean de "package.json","package-lock.json" todo eso se va a reutilizar y no vamos a tener que rebuildiar cada vez y ahorra mucho tiempo.

**Que pasa no queremos rebuidiar cada vez que cambiamos algo?**

Lo que podemos hacer es que esta apliaccion utilice otra herramienta para que cuando cambiemos algo en el codigo eso este disponible devuelta.

Nostros queremos que nuestro contenedor este actualizandose cada vez que cambiamos algo de codigo sin rebuildiar toda la imagen.

La herramienta se llama [nodemon] y lo que hace es mirar archivos de node y corre node y si alguno de esos archivo cambia vuelve a acargar esoa archivos.

```
FROM ubuntu:latest

COPY [".", "usr/src"]

WORKDIR /usr/src

RUN npm install

EXPOSE 3000

CMD ["npx", "nodemon", "index.js"] //al correr este comando va a estar monitoriando el archivo index.js
```
```
docker run --rm -p 3000:3000 -v /home/sann/Documents/development/practicas/dockerData/imagenes/index.js:/usr/src/index.js nombreImagen
```

ahora si vamos al navegador y entramos el `localhost:3000` y luego cambiamos el codigo de `index.js` vemos el cabio en el navegador sin tener que rebuidiar. Asi podemos tener cargado en el cotenedor un archivo que esta monitoriando los cambios de la maquina sin tener que hacer un rebuild aun que no es muy practico hacerlo con un solo archivo.

## Docker networking: colaboración entre contenedores

La manera de conectar contenedores, la manera que nos da docker para hacer eso es con redes virtuales:
```
docker network ls
```
docker ya viene con unas redes ya prehechas, por un lado tenemos las red `bridge`, `host` la cual es una representacion en docker de la red real de mi maquina, es decir que si quisieramos que un contenedor tuviera acceso a las interfaces reales de la maquina entonces tendriamos que permitir que usara `host`, `none` es una red especial que la podemos usar si queremos que un contenedor no tenga ningun tipo de acceso a la red.

Tambien podemos crear nuestra propia red:
```
docker network create warcraft
```
Ademas de crear una red y que exista queremos que otros contenedores se puedan conectar a ella cuando quieran :
```
docker network create --attachable warcraft
```
Con la opcion `--attachable` le estamos diciendo a al red que permita que otros contenedores se conecten a ella.

Si usamos denuevo `docker network ls` aparecera la red que creamos.

Para inspeccionarla mas detalladamente usamos el comando:
```
docker network inspect nombreRed
```

Ahora crearemos los contenedores que queramos conectar 
```
docker run -d --name db mongo
```
Ahora tenemos que conectar nuestro contenedor nuevo de base de datos a esa red:
```
docker network connect nombreRed nombreContenedor
```

ahora en el codigo de la aplicacion:
```
const mongoUrl = process.env.MONGO_URL || "mongodb://localhost:27017/test"
```
El codigo esta preaprado para recibir una variable de entrorno `MONGO_URL`. Lo que vamos a ahcer ahora en el momento de creacion del contenedor le vamos a asignar una nueva variable de entrono.

```
docker run -d --name app -p 3000:3000 --env MONGO_URL=mongo://db:27017/test nombreImagen
``` 
- `db:27017/test` : es el hostname de la maquina donde va a estar mongo y lo que teien de bueno docker es que si dos contenedores estan en la misma red pueden encontrarse por hostname usando sus nombres.

ahora solamente querdaria conectar el contenedor a la red:
```
docker network connect warcraft app
```
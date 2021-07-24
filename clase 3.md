clase 3
===
 **imagenes**
 la imágenes es una plantilla de solo lectura con instrucciones para crear un contenedero docker
y también las imágenes también pueden basarse en otras o tener alguna funcionalidad que dependa de otra imagen docker tiene un docker registry la cual podemos encontrar en el siguiente link https://hub.docker.com/_/registry

para crear la propia imagen se debe crear un archivo Dockerfile cada instrucción de un Dockerfile es una capa en la imagen ,cuando se cambia el dockerfile y se reconstruye la imagen solo se recostruyen las capas que han cambiado, esto es parte de lo que hace que las imágenes sean tan livianas pequeñas y rapidas,en comparación con otras tecnologías de virtualización.

Para crear una imagen debe partir de una imagen base 
Ejemplo se va a partir de nginx
Creamos una carpeta que se va a llamar
 static-html-directory
y dentro creamos un archivo index.html que contiene
“hola semillero ejemplo”
Salimos a la carpeta padre con cd ..
Dentro de la carpeta padre tenemos que tener el archivo
Que se va a llamar Dockerfile  y este archivo va a contener las siguientes operaciones
**FROM nginx
COPY static-html-directory /usr/share/nginx/html**
Después salimos hacia la carpeta donde esta nuestro archivo Dockerfile con cd ..
Luego utilizamos el siguiente comando para construir la imagen.
> Docker image build –t some-content-nginx .

Para eliminar alguna imagen tenemos que eliminar las imagen partiendo de su jerarquía y lo hacemos con el siguiente comando.
primero listamos las imagenes 
> Docker image ls 

luego lo borramos con
> Docker image rm nombreImagen

Si se esta utilizando lo detemos y después eliminamos el contenedor
Cada instrucción del archivo Dockerfile es una capa


----
**Creación de contenedor** 
Usamos la siguiente línea de comando 
 >  docker run –name some-nginx –d –p 8080:80 some-content-nginx


para correr el contenedor usamos la siguiente línea de comando
> curl –k localhost:8080

y después deberá aparecer el mensaje que le indicamos

----
# para subir la imagen al docker hub
usamos el siguiente comando para logearnos 
> docker login

luego usamos el siguiente comando
> docker tag local-image:tagname new-repo:tagname

quedaría asi
> docker tag some-content-nginx cristhiancz/fedesoft-web

y para subirlo hacemos el push
>  docker push cristhiancz/fedesoft-web

Para eliminar el tag de una imagen usamos el siguiente comando 
>  docker image rm cristhiancz:fedesoft-web2

Y para descargar seleccionamos see all y luego vemos el comando docker pull
> docker pull cristhiancz/fedesoft-web:latest

para ejecutarla cuando descargamos la imagen usamos el siguiente código en este caso del usuario > para ejecutarla cuando descargamos la imagen usamos el siguiente código en este caso del usuario 
*jsgiraldoh*

> docker pull jsgiraldoh/fedesoft-web:latest
> docker run --name fedesoft-web -d -p 8081:80 jsgiraldoh/fedesoft-web

Lo ejecutamos para ver que funcione
Con el siguiente comando
> Curl –k localhost:8081

Link de la imagen 
https://hub.docker.com/repository/docker/cristhiancz/fedesoft-web
pull
> docker pull cristhiancz/fedesoft-web:latest
# clase 4 
scratch es una palabra reservada que usa docker
docker compose funciona atravez de un archivo

creamos la carpeta con el siguiente comando
> mkdir proxy

entramos a la carpeta proxy
creamos el archivo yamel
> vim docker-compose.yml

y dentro del archivo vim colocamos las siguientes lineas
> version: '3'
> services:
>   web:
>     image: dockercloud/hello-world
>   lb:
>     image: dockercloud/haproxy
>     links:
>       - web
>     volumes:
>       - /var/run/docker.sock:/var/run/docker.sock
>     ports:
>       - 80:80

Usamos el siguiente comando levantando el servicio
> docker-compose up -d

luego lo visualizamos con el siguiente comando
> docker-compose ps

Docker log es para ver los logs de los servicios
Escalamiento horizontal
Docker nos permite escalar de manera horizontal que es para aporovechar los recursos que tenemos en nuestra maquina
> docker compose up scale web=5

Intalacion de Jenkins
----

Descargamos el repositorio del siguiente enlace
https://github.com/jsgiraldoh/Jenkins.git

podemos ver el archivo yml
> cat docker-compose-jenkins.yml

Cambiamos el propietario de la carpeta Jenkins_home/
> sudo chown cristhian:cristhian jenkins_home/

Le damos permisos con el siguiente comando
> sudo chmod 2777 jenkins_home/

le damos el siguiente comando para ver el logs y la contraseña

> docker logs -f Jenkins

e0b98e51f7604e5892bb53d757dd9441 
luego damos en continuar y también configurar los plugins necesarios
y luego lo configuramos
con el **nombre contraseña correo**   
guardamos y enviamos
y despues ingresamos a la url
http://192.168.0.22:8090/


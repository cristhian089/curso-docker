# Ctisthian alexander zambrano





clase 2
===
Instalación de docker
Entramos a la siguiente pagina de la documentación de docker
https://docs.docker.com/engine/install/ubuntu/
lo primero que hacemos es actulizar los paquetes de Ubuntu
con el siguiente comando

> sudo apt-get update

Luego instalamos los paquetes necesarios para instalar docker con el siguiente comando
>  sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
    
Luego ejecutamos el siguiente comando Agrega una llave al repositorio oficial de docker
>  curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
>  
luego ejecutamos el siguiente comando
> echo \
  "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
  
Luego usamos nuevamente la siguiente línea de comando para acturlizar
>  sudo apt-get update

luego ejecutamos el siguiente comando para instalar docker
>  sudo apt-get install docker-ce docker-ce-cli containerd.io

luego corremos el comando  para ejecutar la línea de hello world
>  sudo docker run hello-world

luego usamos este comando para ver la versión de docker
> sudo docker versión


----

luego procedemos a instalar docker compose

https://docs.docker.com/compose/install/
ingresamos a la pestaña Linux

Ejecutamos el siguiente comando
> sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

luego ejecutamos para darles permisos al archivo 
> sudo chmod +x /usr/local/bin/docker-compose

luego usamos el comando para ver la versión del docker compose
> docker-compose versión

----
**para descargar de un repositorio de git** 
copiamos el enlace del repositorio
y ejecutamos el 
> git clone direcciondelrepositorio

luego entramos a la carpeta con 
cd nombrecarpeta
luego usamos 
> sudo docker-compose up -d

para ver los contenedores que estamos corriendo es con el siguiente comando
> sudo docker container ls

para apagar el servicio usamos el siguiente comando
> sudo systemctl stop docker
> 
para dejar persisitente el servicio se utiliza el siguiente comando

> sudo systemctl enable docker
> 
para confirmar que este habilitado le damos con el siguiente comando
> sudo systemctl status docker

el siguiente comando va a modificar el usuario lo va a agregar al grupo de docker al grupo secundario
> sudo usermod –aG docker cristhian

luego de este comando le damos el siguiente 
> sudo systemctl restart docker

después cuando se reinicie la maquina dejara de pedirnos ejecutar los  comandos con sudo


----
**estructura de comandos**
podemos usar el comando de la ayuda 
> docker --help

también podemos listar las imágenes que tenemos 
> docker image ls 

tambien tenemos las redes de los contenedores
> docker network ls

para detener un contenedor con el nombre usamos el comando o por id también se puede

> docker container stop nombreContenedor

iniciar el contenedor 
> docker container start nombreContenedor


para reiniciar el contenedor usamos 
> docker container restart nombreContenedor

para ver los log de los contenedores usamos
> docker logs –f docker nombreContenedor




# Curso de Docker en Platzi

Esta es una aplicación de ejemplo para el curso de Docker de Platzi

### Administrando tu ambiente de Docker

#### Hola mundo con docker
$ docker run hello-world
#### Ver contenedores corriendo
$ docker ps
#### Ver todos los contenedores
$ docker ps -a
#### Inspecionar la config un contenedor
$ docker inspect <container_id or container_name>
#### Crear un contenedor con un nombre personalizado
$ docker run --name <custom_name> <image_name>
#### Renombrar un contenedor
$ docker rename --name <old_name> <new_name>
#### Eliminar un contenedor
$ docker rm <container_id or container_name>
#### Eliminar todos los contenedores apagados
$ docker container prune
#### Eliminar TODOS los contenedores
$ docker rm -f $(docker ps -aq)
#### Eliminar todas las imágenes de docker
$ docker rmi $(docker images -q)

#### El modo interactivo docker -it ubuntu (lo corre y entra al shell de ubuntu)
-i: interactivo
-t: abre la consola

#### Con un contenedor existente
docker exec -it id-container bash

#### Remove All
sudo docker rm -vf $(sudo docker ps -a -q)
sudo docker rmi -f $(sudo docker images -a -q)
sudo docker system prune -f
sudo docker volume prune -f

#### Remove # Remove volumens and images
docker-compose -f production.yml down --volumes --rmi all

#### Eliminar todos los contenedores que no estan corriendo o apagados
docker container prune

#### Eliminar todos los contenedores incluyendo los que estan corriendo (-q: muestra ID, -a: todos, -f: fuerza bruta)
docker rm -f $(docker ps -aq)

#### Listar redes
docker network ls

#### Eliminar las redes que no estamos usando
docker network prune

#### Listar volumenes
docker volume ls

#### Eliminar los volumenes que no estamos usando
docker volume prune

#### Eliminar todos los contenedores, imagenes, redes y cache
docker system prune

#### Limito el uso de memoria
docker run -d --name app --memory 1g platziapp

#### Ver cuantos recursos consume docker en mi sistema
docker stats

#### Ver si el proceso muere por falta de recursos
docker inspect app

### Docker networking: colaboración entre contenedores

DockerNetwork
Comandos:
#### Listar las redes
docker network ls

#### Crear una red
docker network create --atachable <network_name>

docker network create --atachable plazinet 

#### Inspeccionar una red
docker network inspect <network_name>

#### Conectar un contenedor a la red
docker network connect  <network_name> <container_name> 

docker network connect plazinet db 

#### Correr un contenedor usando variables de entorno
docker run --env MY_VAR='' <image_name>

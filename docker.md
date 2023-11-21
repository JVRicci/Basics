## Comandos basicos 

Verificar versão do Docker

    docker --version ou docker -v

Infos sobre docker

    docker info

Baixar imagem do docker hub

    docker pull <image_name>

Listar imagens locais do docker

    docker images ou docker image ls

Listar containers

    docker ps 
    docker container ls

Listar todos os containers (incluindo parados)

    docker ps -a 
    docker container ls -a

Criar e iniciar um novo container a partir de uma imagem

    docker run <option> <image_name>

# Ciclo de vida do container

Iniciar um container parado.

    docker start <container_name/id>

Parar um container em execução.

    docker stop <container_name/id>

Parar um container em execução de maneira forçada

    docker kill <container_name/id>

Reiniciar um container

    docker restart <container_name/id>

Remover um container parado.

    docker rm <container_name/id>

## Images

Construir uma imagem Docker a partir de um Dockerfile

    docker build -t <image_name> <path_to_dockerfile>

Remover uma imagem

    docker rmi <image_name>

Remover todas as imagens não utilizados

    docker image prune

## Docker Compose

Iniciar os serviços definidos em um arquivo Docker Compose

    docker-compose up

Parar e remover os serviços definidos em um arquivo Docker Compose

    docker-compose down

Listar os serviços em um arquivo Compose e seu Status

    docker-compose ps

Visualizar os logs de um serviço especifico

    docker-compose logs <service_name>

Executar um comando em um container de serviço em execução

    docker-compose exec <service_name> <command>

## Volumes 

Criar um volume com nome

    docker volume create <volume_name>

Montar um volume em um container

    docker run -v <volume_name>:<container_path>

Listar volumes

    docker volume ls

Remover um volume 

    docker volume rm <volume_name>

## Docker Registro e Hub

Login do Docker Hub ou em outro registro Docker privado

    docker login

Enviar uma imagem Docker para um registro de containers, como o Docker Hub ou um registro privado

    docker push <image_name>

baixar uma imagem de um registro

    docker pull <image_name>

## Networks

Criar uma nova rede (network) e no docker

    docker network create <network_name>

Listar redes

    docker network ls

Conectar um container a uma rede (network)

    docker network connect <network_name> <container_name/id>

Desconectar um container de uma rede (network)

    docker network disconnect <network_name> <container_name/id>

## Logs e Debugging

Visualizar logs do container

    docker logs <container_name/id>

Iniciar um shell interativo em um container em execução

    docker exec -it <container_name/id> /bin/bashdocker exec -it <container_name/id> /bin/bash

Exibir o uso de recursos em tempo real de um container

    docker stats <container_name/id>

## Cleanup 

Remover todos os containers parados, redes, e imagens não utilizadas

    docker system prune

Remover todos os containersk imagens ou volumes parados

    docker container prune
    docker image prune
    docker volume prune


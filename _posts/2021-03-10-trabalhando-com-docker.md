---
title: "Docker CLI"
date: 2021-03-10
excerpt: ""
permalink: /posts/2021/03/docker-cli
tags:
  - cli
  - linux
  - iniciante
  - bash
  - docker
---

Abaixo listo algumas instruções do Docker

## docker --version

Mostra a versão do Docker instalado

## docker image ls [REPOSITORY[:TAG]]

Lista imagens instaladas na maquina

## docker image ls --all [REPOSITORY[:TAG]]

Lista imagens sem marca instaladas na maquina

## docker image rm IMAGE [IMAGE...]

Remove uma imagem instalada na maquina

## docker container ls

Lista os container em execução

## docker container ls --all

Lista os container em execução e os parados

## docker container create IMAGE

Cria um novo container a partir de uma imagem

## docker container start CONTAINER [CONTAINER...]

Inicia um container a partir de uma imagem

## docker container start -ia CONTAINER [CONTAINER...]

Inicia um container de modo interativo a partir de uma imagem

## docker container stop CONTAINER [CONTAINER...]

Finaliza a execução de um container

## docker container run IMAGE [COMMAND] [ARG...]

Cria e excuta um container a partir de uma imagem

## docker container run -it IMAGE [COMMAND] [ARG...]

Cria e excuta um container em modo interativo a partir de uma imagem

## docker container run -v path:path:ro IMAGE [COMMAND] [ARG...]

Cria e executa um container a partir de uma imagem compartilhando com o container um arquivo para somente leitura

## docker container run -p port:port -it <imagem>

Cria e executa um container a partir de uma imagem compartilhando uma porta da maquina com o container

## docker container rename CONTAINER NEW_NAME

Renomeia um container

## docker container attach CONTAINER

Anexa o terminal a um container em execução que foi criado com interatividade

## docker container rm CONTAINER [CONTAINER...]

Apaga um container

## docker container exec CONTAINER COMMAND [ARG...]

Executa um comando dentro de um container

## docker container cp SRC_PATH CONTAINER:DEST_PATH

Copia um arquivo da maquina para um container

## docker container cp CONTAINER:SRC_PATH DEST_PATH 

Copia um arquivo de um container para uma maquina

## docker container logs CONTAINER

Mostra os registros (logs) do container

## docker container inspect CONTAINER [CONTAINER...]

Descreve detalhes de um container

## docker container commit CONTAINER REPOSITORY[:TAG]

Cria uma nova imagem a partir de um container

## docker image save -o FILE IMAGE

Exporta uma image para um arquivo TAR

## docker image load -i FILE

Carrega uma imagem a partir de um arquivo TAR

## docker image history IMAGE

Mostra o histórico de uma imagem

## docker image history --human=false IMAGE

Mostra o histórico de uma imagem com informações de maquina

## docker container export -o FILE CONTAINER

Exporta um container para um arquivo TAR

## docker image import FILE [REPOSITORY[:TAG]]

Importa o conteúdo de um arquivo TAR para criar uma nova imagem

## docker image pull NAME[:TAG]

Baixa uma imagem de um repositório

## docker login [SERVER]

Faz login no repositório de imagens do Docker.
Se o servidor nao for especificado, o padrão é definido pelo serviço em execução.

## docker image push NAME[:TAG]

Envia uma imagem para o repositório de imagens

## docker image tag SOURCE_IMAGE[:TAG] TARGET_IMAGE[:TAG]

Cria uma tag TARGET_IMAGE para referenciar a imagem SOURCE_IMAGE

## docker image build PATH

Constroi uma imagem a partir de um Dockerfile

## docker volume ls

Lista os volumes

## docker volume inspect VOLUME [VOLUME...]

Mostra as informações detalhadas de um ou mais volumes

## docker volume create [VOLUME]

Cria um volume

## docker volume rm VOLUME [VOLUME...]

Remove um ou mais volumes. Não é possível remover a volume que está sendo usado por um container.

## docker system df -v

Mostra o uso de disco do Docker

## docker system info [OPTIONS]

Mostra informações de todo o ecossistema do Docker

##  docker system prune --all

Remove dados inúteis do Docker

<!--

## network, node, plugin, secret, service, stack, 

## network     Manage networks
## node        Manage Swarm nodes
## plugin      Manage plugins
## secret      Manage Docker secrets
## service     Manage services
## stack       Manage Docker stacks

## builder, config, context, manifest, swarm, trust

## builder     Manage builds
## config      Manage Docker configs
## context     Manage contexts
## manifest    Manage Docker image manifests and manifest lists
## swarm       Manage Swarm
## trust       Manage trust on Docker images

-->
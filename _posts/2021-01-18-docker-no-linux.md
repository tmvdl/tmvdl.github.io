---
title: 'Docker no Linux'
date: 2021-01-18
excerpt: ""
permalink: /posts/2021/01/docker-no-linux
tags:
  - in portuguese
  - docker
  - linux
  - debian
  - ubuntu
  - installation
---

<img src="/images/install-docker.png" alt="docker-no-linux">

# Instalando o Docker no Linux

O Docker torna simples a criação e o gerenciamento de contêiner e integra com muitos projetos open source.

As principais vantagens do Docker são:

* Utilização leve de recursos: Em vez da virtualização de um sistema operacional inteiro, os contêineres isolam no nível de processos e utilizan o kernel do host.
* Portabilidade: Todas as dependências para uma aplicação conteinerizada são empacotadas dentro do contêiner, permitindo-a executar em qualquer host Docker.
* Previsibilidade: O host não se importa com o que está sendo executado dentro do contêiner e o contêiner não se importa em qual host ele está executando. As interfaces são padronizadas e as interações são previsíveis.

## Como Instalar e Utilizar o Docker no Ubuntu

Neste tutorial, você irá instalar e usar a Edição Community (CE) do Docker no Ubuntu 20.04. Você instalará o Docker.

### Passo-a-passo

Primeiro, atualize sua lista existente de pacotes:

```sh
sudo apt update -y
```

Em seguida, instale alguns pacotes pré-requisito que deixam o apt usar pacotes pelo HTTPS:

```sh
sudo apt install -y apt-transport-https ca-certificates curl software-properties-common
```

Então, adicione a chave GPG para o repositório oficial do Docker no seu sistema:

```sh
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

Adicione o repositório do Docker às fontes do APT:

```sh
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
```

Em seguida, atualize o banco de dados do pacote com os pacotes do Docker do recém adicionado repositório:

```sh
sudo apt update -y
```

Certifique-se de que você está prestes a instalar do repositório do Docker ao invés do repositório padrão do Ubuntu:

```sh
apt-cache policy docker-ce
```

Finalmente, instale o Docker:

```sh
sudo apt install -y docker-ce
```

O Docker deve agora ser instalado, o daemon iniciado e o processo habilitado a iniciar no boot. Verifique se ele está funcionando:

```sh
sudo systemctl status docker
```

Instalando o Docker agora não dá apenas o serviço do Docker (daemon), mas também o utilitário de linha de comando docker, ou o cliente do Docker. Vamos explorar como usar o comando docker mais tarde em outro tutorial.

Até.

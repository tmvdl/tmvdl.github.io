---
title: 'Automatizei a configuração do meu computador'
date: 2021-03-01
excerpt: ""
permalink: /posts/2021/03/automatizei-a-configuracao-do-meu-computador
tags:
  - automação
  - instalação
  - scripts
  - bash
---

Eu acabei de instalar esse sistema operacional aqui, o Neon, que é uma extensão do Ubuntu.
E pra instalar os aplicativos que eu sempre uso ono Linux, eu escrevi um script pra fazer tudo pra mim.
Esse script tem os comandos exatos pra fazer a instalação dos aplicativos que eu preciso
Sempre que eu preciso instalar esses aplicativos em um computador novo eu uso esse script.

<img src="/images/neon-install.png" alt="neon-install" />

É só digitar esses dois comandos no terminal para instalar os aplicativos.
O primeiro comando é pra atualizar o repositório de pacotes do Linux para que eu consigo instalar novos pacotes de aplicativos no computador.
O segundo comando é pra instalar os aplicativos.
Ele demora um pouco pra terminar mas, no final, está tudo instalado.

Nesse script eu coloquei a instalação do navegador Brave, do Node na versão atual, do Visual Studio Code e do Git.
Ele remove, também, alguns aplicativos que vem instalados por padrão e que eu não uso como o Firefox, KDE Connect, o Discover do Plasma e alguns outros.

Além de instalar e desintalar os aplicativos que eu preciso, o script também configura algumas coisinhas pra mim, como parar o serviço do Journald e aumentar o limite de observação de arquivos do usuário.

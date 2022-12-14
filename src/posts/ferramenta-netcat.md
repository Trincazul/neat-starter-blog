---
title: Ferramenta Netcat
description: Funcionamento da ferramenta
author: Endriw Villa
date: 2022-12-14T17:38:45.217Z
tags:
  - Tags
---
O netcat é uma ferramenta que pode ser usada para realizar diversas tarefas relacionadas a rede, como criar conexões de rede, transferir arquivos e executar port scanning. Para usar o netcat, primeiro você precisa instalá-lo em seu sistema. Isso geralmente pode ser feito executando o seguinte comando em um terminal:

```
sudo apt-get install netcat
```

Uma vez instalado, você pode usar o netcat com diversos parâmetros diferentes para realizar diferentes tarefas. Por exemplo, para criar um servidor TCP simples que escuta em uma porta específica, você pode usar o seguinte comando:

```
nc -l 1234
``
Isso fará com que o netcat crie um servidor que escuta na porta 1234. Para se conectar a esse servidor como um cliente, você pode usar o seguinte comando:

```
nc localhost 1234
```

Isso fará com que o netcat se conecte ao servidor local na porta 1234. Você pode então enviar e receber dados através da conexão de rede criada.

Existem diversos comandos básicos que você pode usar com o netcat. Alguns exemplos incluem:

    **nc -l 1234:** cria um servidor que escuta na porta 1234
    **nc localhost 1234:** se conecta ao servidor local na porta 1234
    **nc -z localhost 1234-1240:** realiza um port scanning nos endereços e portas especificados, procurando por portas abertas
    **nc -w 3 localhost 1234 < arquivo.txt:** envia o conteúdo do arquivo arquivo.txt para o servidor local na porta 1234
    **nc localhost 1234 > arquivo.txt:** recebe dados do servidor local na porta 1234 e salva-os no arquivo arquivo.txt

Esses são apenas alguns exemplos de comandos básicos do netcat. Existem muitos outros comandos e opções disponíveis, que podem ser consultados na documentação do netcat ou em tutoriais e exemplos online.

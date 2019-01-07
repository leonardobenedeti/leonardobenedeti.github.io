---
layout: post
title: "Aplicativo Premier Pet"
little_desc: "Ajuste de versão para publicação"
excerpt_separator: ""
categories:
  - Próprios / Freelas
  - Vision Comunicação
tags:
  - android
  - google play
last_modified_at: 2017-10-26T14:00:00-05:00
---


<img src="assets/img/vision/premier-pet.png" style="margin:40px auto;" alt="">

Este projeto foi bem curto, levou 12h no total para resolver o problema inicial e alguns outros erros.

**Problema inicial:**
> "Não conseguimos publicar o app na loja, o painel reclama que o version code está errado, mas não está."
>
> <cite>Vision Comunicação</cite>

Ao iniciar a analise do porque o GooglePlay não aceitou o apk, solicitei acesso ao painel e o APK em questão que foi recusado.

Refiz o processo confirmando que o Play não aceitava o apk, fui analisar mais a fundo o binário.

Existe um processo para verificar detalhes de qualquer apk, chamado `aapt`. Ao executar o comando ele retorna todas as informações que o Play extrai para realizar a publicação. 

Como utilizar o aapt: 
``` terminal
$ANDROID_HOME/buid-tools/[android-version]/aapt dump badging <path-to-apk>
```

No meu caso, precisava confirmar o `version code`, que de acordo com o painel estava incorreto.

Para contextualizar um pouco mais, o projeto foi construido com Ionic 1. O framework utiliza um arquivo para suas configurações chamado config.xml, onde abriga todas as configs básicas do app, incluindo a versão do app.

Quando o projeto Android é criado se baseando nesse arquivo, o script utiliza a versão do app 1.0.0 e converte `.` em `0`, transformando assim a versão 1.0.0 em 10000.


Ao verificar o arquivo, já tendo em mente o version code necessário para subida do apk, reparei que apenas o número estava errado, parte por falta de atenção da Vision parte pelo Ionic transformar `.` em `0` no version code.

Com isso aconteceu uma confusão com as versões.

O config.xml ficou com o mesmo 1.0.0(10000) e as alterações foram feitas direto no Android Studio(prática não recomendada já que o Ionic gera os arquivos automaticamente), alterando o Manifest de 10000(1.0.0) para 100001(1.0.01), aumentando assim o version code de 10000(dez mill) para 100001(cem mil e um). 

Em um nova alteração, ajustaram o config.xml como recomendam as docs a cada subida e seguindo a ordem foi alterado de 1.0.0 para 1.0.1, convertendo para o version code 10001(dez mil e um). Ao tentar subir um apk com version code 10001 o GooglePlay reclamou, e com razão, afinal 100001 > 10001. 

A solução então foi incrementar mais um .2 no version code, 1.0.1.2, convertendo para 100002. 

Demorou tanto para encontrar este detalhe pois os commits estavam de acordo, config.xml certinho. 

Mas ao comparar os apks gerados cheguei a essa conclusão, com isso, passei a analise para a Vision e tudo correu normalmente. O app foi publicado com as alterações que precisavam e continua sendo mantido. 


<a href="https://stackoverflow.com/questions/4470139/how-to-get-application-or-package-info-from-the-apk-file-in-the-android-applicat" target="_blank">https://stackoverflow....e-in-the-android-applicat</a>
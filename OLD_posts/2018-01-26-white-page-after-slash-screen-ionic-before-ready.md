---
layout: post
title: "White page after splash screen on ionic before ready"
little_desc: "Ao iniciar um projeto ionic, eu reparei que a splash tinha um comportamento estranho..."
excerpt_separator: "<!--more-->"
comments: true
categories:
  - Dev Ionic
tags:
  - ionic
last_modified_at: 2018-01-26T12:32:16-05:00
---

Ao iniciar um projeto ionic, eu reparei que a splash tinha um comportamento estranho. 
Ao finalizar o fade de saída, a tela do app ainda não tinha carregado, mostrando assim uma tela branca antes do conteúdo. 
Fui investigar o porque e descobri algumas `preferences` que corrigem esse comportamento.
Normalmente as splash screens servem para preparar o app, e ao finalizar o carregamento dos arquivos ela faz o fade dando foco ao conteúdo da tela inicial do seu aplicativo.

Neste post vamos alterar apenas dois arquivos pra que isso de fato aconteça. O config.xml e o app.js

Para previnir que a splash execute o fade automaticamente antes do conteúdo estar pronto, você precisa da preference: `AutoHideSplashScreen`, que é quem previne isso, se estiver com valor `false`.
As demais preferences são para melhorar a experiência da splash, os nomes já se auto explicam né. =D


config.xml:
``` xml
    <preference name="AutoHideSplashScreen" value="false" />
    <preference name="FadeSplashScreenDuration" value="1000" />
    <preference name="ShowSplashScreenSpinner" value="false" />
    <preference name="SplashMaintainAspectRatio" value="true" />
```

Com os valores do config.xml definidos basta incluir este trecho de código no arquivo app.js para a magia acontecer.

Atenção: para ele funcionar como combinado, ele precisa estar dentro do ready, para que assim que de fato ele esteja pronto e a splash pode ser esmaecida. =D

app.js:
``` js
    setTimeout(function() {
      navigator.splashscreen.hide();
    }, 100);
```


fontes: <br/>[Doc Cordova](https://cordova.apache.org/docs/en/2.6.0/cordova/splashscreen/splashscreen.hide.html)<br/>
[Forum Ionic](https://forum.ionicframework.com/t/white-page-showing-after-splash-screen-before-app-load/2908/9)

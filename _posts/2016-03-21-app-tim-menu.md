---
layout: post
title: "App TIM Menu"
little_desc: "App criado para abrigar todos os apps, redes sociais e promoções da TIM"
excerpt_separator: ""
categories:
  - Conception
tags:
  - Android
  - iOS
  - PHP
last_modified_at: 2016-07-01T14:00:00-05:00
---

<img src="assets/img/conception/app-tim-menu.png" style="margin:40px auto;" alt="">

Neste projeto atuei em duas frentes com pequenos ajustes, visto que era desenvolvedor WEB na época. =D

* API
* APP

### API

A api é construida com PHP puro e ela retorna se o app está ou não com o conteúdo desatualizado. Estando desatualizado ele retorna um link de um .zip com as informações e imagens para tal atualização.

Constantemente precisavamos incrementar informações no .zip e consequentemente o código da versão para o app se atualizar.


### APP

No aplicativo atuei também muito pouco mas atuei em ambas plataformas: iOS e Android.

##### iOS - Obj-C

No iOS eu ajustei feed de informações do twitter, usando a propria api da rede social, adaptando apenas o layout dos twits a identidade do app. E os clicks dos posts do facebook direcionando para os posts na página.


#### Android - Java

O app precisa mostrar varios apps em grids. Em uma determinada resolução mostravam apenas 3 e não 4 como deveria ser. 
Para resolver incluí um novo dimens.xml para a resolução tvdpi, não lembro agora qual device era. Mas era o clássico problema que algum gerente tinha o device e precisava ser ajustado rsrsrs


Infelizmente não tenho prints desses ajustes. Imagino que o app ainda seja mantido pela Conception e esteja funcionando. =D
---
layout: post
title: "[POC] - SmartApp"
little_desc: "Criado para exemplificar o conceito de SmartApps API Based"
excerpt_separator: ""
categories:
  - Everis
tags:
  - ionic
  - python
  - ios
  - android
  - heroku
last_modified_at: 2018-06-08T14:00:00-05:00
---


<img src="assets/img/everis/smartapp/img-post.png" style="margin:40px auto 10px;" alt="">
<p style="text-align:center;">** Acredite, no canto direito superior é um cerebro pra simbolizar a inteligencia da api</p>

Este projeto foi criado utilizando uma arquitetura básica de um app feito em Ionic consumindo uma API python utilizando Flask e um algoritmo de recomendações baseado em inteligencia artificial.

Vamos separar em tópicos para explicar a POC.

1. Conceito de smart apps
2. Necessidade e contexto 
3. App final


#### 1. Conceito de smart apps
Para explicar o conceito de smart apps a melhor maneira é exemplificar alguns casos.
Um smart app bem conhecido e muito utilizado é o Waze.
O app altera o fundo do app quando atinge o horário 17:59, antes deste horário é cinza com rotas em roxo, quando o dia vira noite, o app faz um cross-fading de cor de fundo para um cinza bem escuro e com rotas em azul claro para contrastar com o fundo.

<div class="images-grid two">
  <img src="assets/img/everis/smartapp/waze-dia.png" alt="">
  <img src="assets/img/everis/smartapp/waze-noite.png" alt="">
</div>

Com isso podemos classificar smart apps, os apps que conseguem de alguma forma interagir com o ambiente do usuário. Seja com horário, como o Waze faz, com localização recomendando de lugares e outros exemplos. 

Existem tipos de smart app, a grande maioria utiliza recursos do device que esta instalado, mas existem apps que são baseados em API. Que é o caso do post.


#### 2. Necessidade e contexto 

A POC foi pensada para ser apresentada em um evento onde a Everis tem boa participação e sempre aborda as novas tendências de mercado em varias frentes. 

Neste caso estavamos a pouco tempo do evento e existia um app nativo iOS que ainda não consumia nenhuma api e tinha alguns exemplos de cards, mas tudo offline e sem nenhuma recomendação. 

Para conseguir criar tudo que precisava, chegamos a um consenso que Ionic seria a melhor pedida devido sua facilidade e menor barreira de entrada.

Também existia um algoritmo feito em Python que ao inputar dados, ele recomenda algumas informações baseadas no treino previamente feito.

Com o algoritmo em mãos precisavamos criar uma API na mesma linguagem para não gerar retrabalho no algoritmo, com isso escolhemos o Flask para expor em uma API e disponibilizamos no Heroku. 

Escrevi um outro <a href="/heroku-python-mysql" target="_blank">post</a> que mostra como subir uma aplicação python com mysql no heroku. 


#### 3. App final

Após criar o app e a api, conectamos os dois e ao enviar os dados preenchidos no formulário a API baseada no treino feito posteriormente, recomenda as informações que o app mostra em formato de cards.

<div class="images-grid three">
  <img class="a" src="assets/img/everis/smartapp/smartapp-1.png" alt="">
  <img class="b" src="assets/img/everis/smartapp/smartapp-2.png" alt="">
  <img class="c" src="assets/img/everis/smartapp/smartapp-3.png" alt="">
</div>

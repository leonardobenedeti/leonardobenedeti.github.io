---
layout: post
title: "ng-bind-html on ionic 1"
little_desc: "Trabalhando em um projeto mobile, precisei dinamizar uma página inteira..."
excerpt_separator: "<!--more-->"
comments: true
categories:
  - Dev Ionic
tags:
  - ionic
last_modified_at: 2018-01-11T12:32:16-05:00
---

Trabalhando em um projeto mobile, precisei dinamizar uma página inteira, com isso busquei como fazer tal coisa. Foi ai que encontrei o ng-bind-html.
<br/>Como ele funciona: você basicamente monta todo o html no controller da aplicação e passa para a view como uma variável de escopo, sim, só isso.

Abaixo criei uma variável dentro do escopo e passei uma string já com o html que queria utilizar. 

Controller:
``` js
$scope.data_body = '\
    <h1 class="text-center">'+variavel_qualquer_que_queira_utilizar+'</h1>\
';
```

Já na view, basta passar a variável como valor para a diretiva ng-bind-html e ver a mágica acontecer. 

View:
``` html
<div class="padding" ng-bind-html="data_body">
```

Infelizmente não tenho as fontes pra isso. Mas não precisa, basta fazer como mostrei acima que vai dar certo. =D
---
layout: post
title: "Deploy flask API on Heroku"
little_desc: "Em um happy hour com o pessoal do trabalho, rolou um papo de api em python..."
excerpt_separator: "<!--more-->"
comments: true
categories:
  - Dev Python
tags:
  - python
  - flash
  - heroku
last_modified_at: 2018-05-25T12:32:16-05:00
---

Em um happy hour com o pessoal do trabalho, rolou um papo de api em python e a curiosidade para criar isso se iniciou. 
Não sou tão bom assim com python, mas decidi iniciar os estudos sobre o papo direto com a lib Flask, focada em apis.

Após alguns minutos de busca e vídeos assistidos, tinha uma api rodando localmente na minha máquina. Com pouco mais de 10 linhas e alguns imports uma api já estava pronta, é claro, apenas com uma resposta de 'hello world', mas ainda sim já estava funcional.

Outra necessidade era expor essa api em algum lugar, foi ai que pensamos no [Heroku](https://www.heroku.com/), gratuito e fácil de usar. Abaixo, vou mostrar como fazer o deploy de uma api, que você pode baixar e ver como foi feita meu [GitHub](https://github.com/leonardobenedeti/api-flask).

Levando em consideração que os arquivos já estejam prontos e rodando localmente, temos duas opções após criar o app no Heroku:
1 - vincular com algum repositório do github e criar um pipeline, onde você commita na branch escolhida no github e o Heroku faz o deploy a partir dela.
2 - vincular com o própio heroku, que é baseado em git também. 

Mas antes de criar a api precisamos criar o app no Heroku.
Pra isso vamos seguir alguns passos.

#### 0.0 - Criar app sem definição de plataforma
<img src="assets/img/heroku-deploy/create-app.png" style="margin:20px auto;" alt="">

#### 0.1 - Escolher nome e região 
<img src="assets/img/heroku-deploy/nome-e-regiao.png" style="margin:20px auto;" alt="">


Com estes dois itens já criados, vamos vincular com o GitHub e Heroku.

#### 1.0 - Vincular com o github

No print eu já estava vinculado com o github, mas basta clicar em conctar e colocar usuário e senha do github pra buscar seus repositorios e escolher o que abriga a sua api, no meu caso, api-flask.

<img src="assets/img/heroku-deploy/vinculo-com-github.png" style="margin:20px auto;" alt="">

#### 1.1 - Configurar os deploys

No meu caso como é uma api aberta e de exemplo, escolhi o deploy automático. Pois a cada commit que eu faça na api, em questão de segundos já posso visualizar o que foi alterado.

<img src="assets/img/heroku-deploy/deploy-auto-manual.png" style="margin:20px auto;" alt="">

E pronto. A partir daqui basta commitar na branch escolhida no momento do vínculo com o GitHub e pronto, seu deploy vai ser feito automaticamente, caso tenha habilitado a opção.


#### 2.0 - Vincular com o próprio heroku

Neste caso precisei criar outro app para printar, não ia apagar e criar outro rsrs.


Para este vínculo, você não é preciso ter login no github, precisa apenas seguir os commandos que ele recomenda. Simples assim.

<img src="assets/img/heroku-deploy/vinculo-com-heroku.png" style="margin:20px auto;" alt="">


Agora, basta você customizar sua api como quiser, commitar onde escolheu subir o código e aproveitar a facilidade do Flask + Heroku.

Pra visualizar o exemplo criado no repositório citado acima basta ir para: [https://api-flask-leonardobenedeti.herokuapp.com/](https://api-flask-leonardobenedeti.herokuapp.com/)


Fonte: [https://progblog...k-App-to-Heroku/](https://progblog.io/How-to-deploy-a-Flask-App-to-Heroku/)
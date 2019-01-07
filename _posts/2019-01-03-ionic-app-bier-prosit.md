---
layout: post
title: "Aplicativo Bier Prosit"
little_desc: "Criado com intuito de substituir o cardápio da loja"
excerpt_separator: ""
categories:
  - Próprios / Freelas
  - Bier Prosit
tags:
  - ionic
  - php
  - ios
  - android
  - cloud
  - google play
  - app store
last_modified_at: 2019-01-03T14:00:00-05:00
---


<img src="assets/img/bierprosit/imagem-post.png" style="margin:40px auto;" alt="">

Projeto criado em conjunto ao Bier Prosit focado em resolver alguns problemas em lojas e empórios focados em cervejas especiais. 
Principal dor: Apesar do atendimento focado na informação do produto, os clientes da loja ainda sim não questionavam tudo o que precisavam saber sobre o produto.

Inicialmente o MVP foi pensado para apenas ler o código de barras da cerveja e mostrar ao usuário sua informação mais detalhada. 

Com essa base, o app foi ganhando novas funcionalidades como: Cardápio completo, Dicas, Cupons, Lista de desejos, Avaliações dos produtos e Foto personalizada do Bier!

Para explicar melhor o projeto vamos separar em tópicos

1. Arquitetura básica
2. Painel administrativo / API
3. Aplicativo
4. Publicação
5. Sustentação

>Vale ressaltar que o projeto foi idealizado e iniciado pela empresa All Most, que foi constituida por 4 amigos, Leonardo Benedeti(este que vos escreve), Mateus Diniz, Marcus Paulo e Michael Almeida. Atualmente não integro mais o time da All Most e como era o único desenvolvedor mobile, segui com o desenvolvimento sozinho, fora da All Most.

#### 1. Arquitetura básica
<img src="assets/img/bierprosit/arq-bier.jpeg" style="margin:40px auto 5px;" alt="">
<p style="text-align:center;">** Sim, desenhei num flipchart e tirei foto =D</p>

#### 2. Painel administrativo / API
Criado utilizando `PHP`, sem utilização de nenhum framework. O painel é responsável por gerenciar todos os produtos, sendo efetuando o cadastro, alteração ou exclusão de algum produto e emitir push notifications para o app, seja a cada produto cadastrado ou alguma mensagem customizada, de acordo com a vontade do Bier Prosit.

Os produtos são salvos em uma base de dados `MySQL` e toda conexão com ele é feita pelo painel. #phpraiz

Em breve o painel será atualizado para a linguagem `Python` e será `API Based` utilizando `Flask`, provavelmente com front-end em `Angular` ou `React`.

#### 3. Aplicativo
A primeira versão foi criada utilizando `Android Nativo` e com o lançamento do `Ionic 1` migrei para o framework, com a atualização foi feito o upgrade para a versão 3 do framework.

**Funcionalidades**
* Consulta de produtos na API
* Criação de listas de desejo
* Avaliação de produtos baseado na lista de desejos
* Leitura de QR Code
* Captura de imagens e ao finalizar a captura, inclusão da logo do Bier na foto
* Compartilhamento de fotos nas redes sociais que o usuário utilizar
* Push Notification
* DeepLink, ao clicar em um push de um produto específico, o usuário é direcionado para a página de detalhes do produto
* Rotas até o Bier, ao clicar para exibir a rota o app sugere todos os apps que são capazes de criar uma rota. ex.: Uber, 99, Google Maps...
* Novidades podem vir por ai... =D

#### 4. Publicação
Finalizado o desenvolvimento do app, o mesmo foi submetido para a AppStore e Google Play, todas as telas são diferentes por conta do framework Ionic, ele consegue diferenciar ambas plataformas e tornar a UX mais fluida possível para o usuário ter a sensação que está utilizando um app nativo. 

Para baixar o app ou visualizar as telas você pode acessar os links abaixo ou ler o QR Code.

* <a href="https://itunes.apple.com/br/app/bier-prosit/id1211795341" target="_blank">AppStore</a>
* <a href="https://play.google.com/store/apps/details?id=br.com.leonardobenedeti.bierprosit" target="_blank">GooglePlay</a>

<img src="assets/img/bierprosit/qr-post.png" style="margin:40px auto 5px;" alt="">


#### 5. Sustentação
Após a publicação do app, bugs e melhorias serão ajustados para manter o app funcionando normalmente.

Caso tenha encontrado algum bug ou melhoria reporte e ajude o app a ficar mais completo.

* <a href="https://goo.gl/forms/7pgNxSLakCyOVgiy1" target="_blank">Melhorias e Sugestões</a>
* <a href="https://goo.gl/forms/99WNF42lMfq1UmOJ2" target="_blank">Bugs</a>
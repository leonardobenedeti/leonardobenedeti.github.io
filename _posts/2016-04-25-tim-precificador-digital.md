---
layout: post
title: "TIM - Precificador Digital"
little_desc: "Projeto criado para evitar preços de papel nas lojas da TIM"
excerpt_separator: ""
categories:
  - Conception
tags:
  - Android
  - PHP
last_modified_at: 2016-04-25T14:00:00-05:00
---

<img src="assets/img/conception/tim-precificador-digital.png" style="margin:40px auto;" alt="">

Aplicativo criado com o intuito de substituir as plaquinhas de preço das lojas, que constantemente estão desatualizadas. 
O App funciona junto a uma api que envia para os devices os preços atualizados no momento e o cliente da loja que possui o app está sempre atualizada.

Também atuei em duas frentes nesse projeto, API e APP. 


* API
* APP

### API
Criada utilizando PHP com o framework CakePhp e para atualizar os apps, emitia uma carga de informação de acordo com a demanda do gerente de vendas da região. 

Atuei em ajustes simples de conteúdo e versionamento de pacotes para atualização dos devices.


### APP
Criado utilizando Java, tendo como funcionalidade básica a busca de informações de preço relativo ao device. 

Ex.: ao abrir o app em um Motorola One, a promoção vigente referente ao aparelho seria mostrada.

Atuei em bugs e melhorias de layout do app, na maior parte das vezes bem simples como tamanho de fonte e posicionamento. Mas em um caso específico precisamos investigar e testar muito a fundo um problema relatado pelo cliente: Telas dos devices queimando pelo layout ser estático. Efeito Burn-In comum em androids devido a barra fixa de ação, botão voltar, home e lista de apps. No caso do nosso app como o layout era estático como a barra comentada, queimava a tela com a promoção do device. Não era legal mesmo.

ex.:
<img src="assets/img/conception/pd-tim-burn-in.png" style="margin:20px auto;" alt="">

A solução para isso foi tornar o conteúdo da promoção móvel, assim como proteções de telas de televisões e computadores. 
A equipe de criação e design criou um novo layout mantendo a tela sempre alterando os valores de cores dos pixels da tela.

> O desenho pode não estar 100% mas vai fazer sentido com a explicação abaixo rsrs

O app tinha um espaço para o conteúdo da promoção bater nos cantos. Dinamicamente ele traçava uma reta para cada próximo canto. Assim o conteúdo alternava a posição constantemente. Nunca batendo no mesmo ponto da tela.

Já o fundo precisavamos alternar as cores pra garantir que a tela mantivesse sua vida útil intacta. 
Foi pensado 5 imagens usando um gradiente entre cores escuras e claras para sempre manter o pixel alternando o estado.

ex.: 
<img src="assets/img/conception/pd-tim-bg-example.png" style="margin:20px auto;" alt="">

O app alternava entre essas imagens e o fundo girava no próprio eixo, assim mantendo o pixel sempre trabalhando e evitando que o mesmo queimasse em uma cor específica marcando a tela. 


Infelizmente pouco tempo após esses ajustes para a tela não queimar mais a tim descontinuou o projeto e não é mais utilizado.
A Apple é uma loja que utiliza algo parecido. 


---
layout: post
title: "#2 Meta Minha - Design"
little_desc: "Aqui ferrou. Dev pagando de UI/UX ... vamos ver o que sai"
excerpt_separator: ""
categories:
  - Próprios / Freelas
tags:
  - flutter
  - android
  - ios
  - agil
  - ux
  - devops
  - jenkins
last_modified_at: 2020-02-18T14:00:00-05:00
---

Neste post vou entrar em um terreno desconhecido, nem tanto, mas não conheço tantos detalhes então talvez deixe algo passar.

Vou estruturar a escrita para fazer sentido, pois fui criando meio sem ter noção de como fazer componentes e coisas assim.

Vou mostrar primeiro os componentes que criei e como estou utilizando no protótipo.

### Componentes

<img src="assets/img/metaminha/2-componentes.png" alt="">

Explicando no geral, quis deixar a ideia mais estruturada possível, para quando for escrever o código, já ter noção de todos os estados de componentes, como botões, toggles e listas.

Vou explicar alguns apenas, para estender tanto o post sobre design, até para não me perder na explicação. rsrs


### Botões - Primary/Clear

<div class="grid">
    <div class="a img">
        <img src="assets/img/metaminha/3-componente-botao-primary.png" alt="">
    </div>
    <div class="b img">
        <img src="assets/img/metaminha/3.2-componente-botao-clear.png" alt="">
    </div>
</div>

**Primary** - Este botão é responsável por ações principais no app, ações que faria o usuário percorrer todo o app baseado no que desenhei como fluxo feliz. 

**Clear** - Este botão é responsável por ações secundárias do app, ações como Skip do login e sair da aplicação, não são coisas que quero chamar atenção do usuário. Portanto utilizei este estado do botão.


### Toggle - Ativado/Desativado

<div class="grid">
    <div class="a img">
        <img src="assets/img/metaminha/4-componente-toggle-ativado.png" alt="">
    </div>
    <div class="b img">
        <img src="assets/img/metaminha/4.1-componente-toggle-desativado.png" alt="">
    </div>
</div>

Aqui não temos mistério, um toggle para ativar ou desativar algo, portanto temos os dois estados para o componente.


### Item detalhe meta - Não Executado/Executado/Remover

<div class="grid">
    <div class="a img">
        <img src="assets/img/metaminha/5-componente-item-detalhe-meta.png" alt="">
    </div>
    <div class="b img">
        <img src="assets/img/metaminha/5.1-componente-item-detalhe-meta-selecionado.png" alt="">
    </div>
</div>

<div class="grid">
    <div class="a img">
        <img src="assets/img/metaminha/5.2-componente-item-detalhe-meta-remover.png" alt="">
    </div>
    <div class="b img"></div>
</div>

Os estados aqui são 3 e controlam mais que um estado, controla também um comportamento. Além de selecionado e não selecionado também criei o estado para mostrar como seria caso o usuário quisesse remover o item.

Bom... chega de componentes, para não estender tanto o post.


### Protótipo

Tentei seguir o máximo do desenho mas alterei algumas coisas e incluí outras que não desenhei por ser bem padrão como o Onboarding do app.

<img src="assets/img/metaminha/6-prototipo-final.png" alt="">

> Disclaimer: Não fiz nenhum curso nem nada relacionado ao assunto, portanto não me julguem rsrs

Com o protótipo montado precisei ver com um pouco mais de vida antes de validar alguns pontos para partir para o desenvolvimento.

Vamos então para a navegação deste protótipo. Até então temos um protótipo estático. Vamos dar vida a ele.

### Protótipo navegável

Linkei todo cenário possível que enxerguei para os casos de uso que imaginei no app. Vendo de cima fica um emaranhado de links impossível de entender. 

<img src="assets/img/metaminha/6.1-prototipo-navegavel.png" alt="">

<div class="grid">
    <div class="a img">
        <img src="assets/img/metaminha/fluxo.gif" alt="">
    </div>
    <div class="b text">
        Para facilitar o entendimento do fluxo do app e não precisar explicar um a um com prints aqui, fiz o seguinte: Gravei a navegação e na sequência segue o gif do fluxo completo. 
    </div>
</div>

Caso queira validar o protótipo com a visão de desenvolvedor e com mais detalhes clique no link abaixo.
* <a href="https://xd.adobe.com/view/06b9671d-61a3-4f79-4e44-78921d4c12e3-7088/" target="_blank">https://xd.adobe.com/view/06b9671d-61a3-4f79-4e44-78921d4c12e3-7088/</a>

Caso tenha algum problema para acessar, provavelmente estou usando o link para outro projeto. Mas assim que receber a mensagem retorno para o link. 

Infelizmente não tenho a versão paga do Adobe XD. #AdobePagaNois rsrs

Próximo post: Organização e priorização...
---
layout: post
title: "[Github PR] - Twitter UI Clone Bug fix"
little_desc: "A titulo de curiosidade baixei um repo para entender mais sobre flutter..."
excerpt_separator: ""
categories:
  - Próprios / Freelas
tags:
  - flutter
  - github
  - pull requests
last_modified_at: 2019-09-06T14:00:00-05:00
---

## Minha "primeira" aventura Flutter

A título de curiosidade baixei um repo para entender mais sobre Flutter. 

Navegando encontrei esse post no medium<br>
<a href="https://medium.com/@diegoveloper/flutter-lets-know-the-scrollcontroller-and-scrollnotification-652b2685a4ac" target="_blank">Flutter: let’s know the ScrollController and ScrollNotification</a>


Estava procurando especificamente sobre como controlar a scrollview para emitir eventos enquanto o usuário estivesse scrollando a tela.

Para minha grata surpresa, o repo além de ter o que eu procurava, encontrei um clone do Twitter, especificamente a UI da page de perfil, com efeitos e tudo.

Ao tentar incluir em um projeto notei um bug ao scrollar as tabs do projeto original. 

Quando eu scrollava as tabs o avatar iniciava a animação, porém, não deveria acontecer isso.

Problema:
<img src="assets/videos/bug-scrolling-tabs.gif" alt="">

Esse bug me fez quase desistir da UI que antes considerei perfeita para o que estava criando para estudos.

Mas como o Flutter é um toolkit desafiador e o Dart é intuitivo e simples, pensei: Porque não tentar arrumar isso?!

Com algum tempo procurando o problema e imprimindo tudo que poderia de logs, identifiquei que a animação do avatar estava sendo iniciado com QUALQUER scroll na tela, mais especificamente falando do header.

Encontrei a propriedade `scrollNotification.metrics.axisDirection` que identificava se o scroll era vertical`(top->bottom or bottom->top)` ou horizontal`(left->right or right->left)` e com isso consegui controlar quando a animação iniciaria ou não.

Solução:
<img src="assets/videos/bug-fixed-scroll-tabs.gif" alt="">

O pull request desse ajuste foi enviado para o repo original e espero que ajude outras pessoas.<br>
<a href="https://github.com/diegoveloper/flutter-samples/pull/11" target="_blank">Link para o pull request</a>


Obs.: essa foi a minha primeira contribuição com a comunidade open source. =D

---

Informações importantes para quem quer entrar para o mundo Flutter:

Temos uma mega comunidade no Brasil que fez agora no fim de agosto o evento Flutter Talks, onde conheci o git em questão, comentado acima. O Diego Velasquez mostrou as diferenças entre Provider e Bloc, além dele tiveram muitas outras talks sobre todos os assuntos possíveis de Flutter.

A comunidade tem muito conteúdo de flutter. Recomendo acesso ao grupo e todo conteúdo oferecido por eles. Vale a pena!

<a href="https://t.me/flutterando" target="_blank">Telegram da Comunidade Flutterando</a>

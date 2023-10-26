---
layout: post
title: "Costa Coffee"
little_desc: "Aplicação web usada como interface de uma máquina de café"
excerpt_separator: ""
categories:
  - Dextra / CI&T
tags:
  - flutter
  - web
last_modified_at: 2023-10-26T14:00:00-05:00
---


### Contexto geral e história

Aplicação web usada como interface de uma máquina de café da marca Costa Coffee, marca internacional comprada recentemente pela CocaCola na época e com a CI&T tento uma boa posição dentro do projeto cuidando de várias frentes.

O projeto consistia basicamente em criar aplicações que beberiam da mesma fonte de dados, exibindo em 4 formatos:
- Pedidos: Tela que mostrava todos os itens disponíveis para realizar o pedido, no caso deste formato, pouco depois da minha chegada também passamos a adaptar o código para rodar em browsers para os usuários pedirem dos seus próprios devices e não apenas do totem de pedidos.

- Acompanhamento: Uma tela sem interação do usuário. Básicamente uma tela de status mostrando a fila de pedidos e o status de cada um deles.

- Retirada: Uma tela bem específica, tanto em dimensões quanto em design por conta do tamanho, tinha o foco de receber a intenção de retirada do pedido do usuário e validar as informações para emitir a ação pra máquina. 


### Tecniquês

O projeto foi criado utilizando uma base mais focada em apps mobile por ter uma navegação bem restrita e totalmente controlada pelo próprio app, não dependendo assim de interações externas ao app como um voltar do browser por exemplo ou botão voltar do android. Tudo era controlado 100% pelos botões desenvolvidos pelo time.

Utilizavamos uma arquitetura muito específica do projeto e estavamos caminhando pra implementar algo como o Clean mas ainda não estava nesse ponto quando deixei o projeto. 

Para a gestão de estado da aplicação utilizavamos Bloc e também próximo a minha saída do projeto estavamos começando a migrar para Cubit.
Injeção e inversão de dependência, utilizando GetIt para injeção.


### Fim da história

Este foi meu último projeto na CI&T, onde decidi abrir asas e experimentar um mundo mais arriscado lançando um app independente chamado GearApp que é focado no setor automotivo, mas aqui a história é do Costa e não do Gear... com essa decisão acabei deixando a CI&T em junho de 2023, uma das melhores consultorias que já passei. 

Obrigado CI&T. Tamo junto
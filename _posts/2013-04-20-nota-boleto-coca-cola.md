---
layout: post
title: "Nota Boleto - Coca Cola"
little_desc: "Integração SAP x AS400 para unificação de documentos de nota e boletos"
excerpt_separator: ""
categories:
  - CiaFlu - CocaCola
tags:
  - SAP
  - AS400
  - Java
last_modified_at: 2016-08-17T14:00:00-05:00
---


<img src="assets/img/coca/coca-porto-real.jpg" style="margin:40px auto;" alt="">

Motivo do projeto: Com boleto e notas fiscais sendo gerado em ambientes diferentes, o setor de conferência de pedidos precisava, toda manhã antes de liberar as entregas, imprimir todos os boletos em um servidor, notas fiscais em outro, folhear as duas pilhas e unir boleto com a nota fiscal do pedido do Bar do Zé, grampear e liberar para entrega. 

>**Um processo manual e trabalhoso demais.**

O projeto consistiu em buscar numa base de dados em um AS400, informações de notas fiscais e no SAP, boletos referentes a pedidos efetuados pelos clientes da unidade CiaFlu.

Para auxiliar o projeto, foi comprada uma nova impressora que ao finalizar a impressão de um documento com mais de uma página, ela grampeava as páginas. **WOW**

Com as duas informações em mãos e a impressora esperando, bastava unir tudo em um único arquivo e enviar para impressão.

>**Moleza rsrsrs**

A integração foi feita em Java buscando as informações e enviando para o SAP mostrando em um report customizado mostrando a lista a ser impressa.

Com esse processo todo automatizado, o analista agora podia apenas conferir as notas e boletos, já impressos e grampeados, e direcionar para o fluxo de entrega de um modo mais garantido, evitando erros manuais que aconteciam com frequência. 

**Outras informações**

Com a compra da CiaFlu pela FEMSA, o ABAP foi descontinuado, por eles utilizarem o SAP sem customizações. 

Com essa rescisão precisei decidir o que fazer e depois de pensar muito, comprei um MacBook e migrei para o desenvolvimento mobile. A outra opção seria fazer a Academia SAP, mas o mundo mobile estava crescendo e tomei a direção que achei mais interessante. =D
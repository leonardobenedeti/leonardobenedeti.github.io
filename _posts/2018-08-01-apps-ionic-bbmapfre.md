---
layout: post
title: "Apps Ionic BB e MAPFRE"
little_desc: "Projeto de unificação e migração de apps kony para ionic"
excerpt_separator: ""
categories:
  - Everis
tags:
  - ionic
  - ios
  - android
  - google play
  - app store
  - devops
  - jenkins
  - azure devops
last_modified_at: 2018-08-01T14:00:00-05:00
---

> Antes de começar a falar sobre este projeto, vale a pena relembrar o período que atuei apenas na sustentação dos aplicativos que foram migrados. <a href="/apps-kony-bbmapfre" target="_blank">Confira aqui</a>

Vamos separar o post em alguns tópicos para organizar:

1. Estudos sobre melhores tecnologias mobile
2. PoC com a tecnologia escolhida
3. Definição do projeto/estimativa
4. Início do projeto
5. Desenvolvimento
6. Entrega


Vamos lá...



### 1. Estudos sobre melhores tecnologias mobile

Ainda durante a sustentação, atuando pela Entelgy, fizemos um estudo sobre as tecnologias mobile que estavam em alta no momento.
Esse estudo veio acompanhado com uma estimativa comparando entre: Kony(atual), Ionic, React Native e Nativas.
Comparamos os seguintes pontos: Curva de aprendizado, velocidade de desenvolvimento, performance e custo.

Com esses pontos na mesa, após alguns dias de papo entre todos que prestavam serviço, chegamos a conclusão que Ionic seria a melhor opção dado o cenário atual do Grupo Segurador.

Corta a cena vamos para o próximo item.


### 2. PoC com a tecnologia escolhida

Voltando dos comerciais, já atuando pela everis, ainda na sustentação dos apps, surgiu o assunto que migraríamos os apps para o Ionic.
Com isso a equipe de sustentação, mesmo sem nada confirmado, decidiu usar o tempo livre para replicar a home do app principal dos apps em ionic para mensurar o tempo que precisariam para a migração.

Com isso fizemos em duas maneiras.

* Layout exatamente igual ao app atual também com ionic
* Layout aos moldes do ionic com poucos ajustes


Com isso vamos aos prints

#### Original - Prints do app em produção
<img src="assets/img/everis/bbmapfre-unificacao/0-app-kony.png" alt="">

#### Ionic Idêntico - Muitos ajustes para o layout ficar idêntico ao app de produção
<div class="grid">
    <div class="a img">
        <img src="assets/img/everis/bbmapfre-unificacao/1.0-home-identico-ionic.png" alt="">
    </div>
    <div class="b img">
        <img src="assets/img/everis/bbmapfre-unificacao/1.1-menu-identico-ionic.png" alt="">
    </div>
</div>

> Porque criamos este exatamente igual: No início do projeto foi dito que seria apenas uma troca de tecnologia sem alterar nada de regra de negócio nem layout. Dai fizemos exatamente igual para respeitar essa decisão.


#### Ionic Way - Layout básico sem muitos ajustes
<div class="grid">
    <div class="a img">
        <img src="assets/img/everis/bbmapfre-unificacao/2.0-home-ajustes-pequenos-ionic.png" alt="">
    </div>
    <div class="b img">
        <img src="assets/img/everis/bbmapfre-unificacao/2.1-menu-ajustes-pequenos-ionic.png" alt="">
    </div>
</div>

> Mas como todo consultor deve se comportar, fizemos uma versão mais simples, usando tudo que o Ionic podia oferecer e mostramos as vantagens.

A PoC foi apresentada para os gerentes e foi muito elogiada. Mas infelizmente não foi utilizada porque o projeto teve uma surpresa, que vou citar abaixo. rsrs



### 3. Definição do projeto/estimativa

Com o cenário posto, com PoC e noção de tempo para migrar, estimamos em 3 meses o projeto para 4 pessoas. Maravilha.

Porém como nada pode estar tão perfeito, veio a surpresa que comentei acima. O app mudaria o escopo, como?

#### De: 
4 apps Kony: 
* MAPFRE Seguros ( institucional )
* BB Seguros ( institucional )
* MAPFRE Auto ( auto )
* BB Seguro Auto ( auto )

Sim, existia um app apenas para o conteúdo institucional da empresa e outro para as ações transacionais referentes ao segmento auto.
E o projeto inicial seria manter esse escopo, porém com a tecnologia Ionic.

#### Para: 
2 apps Ionic:
* MAPFRE Seguros
* BB Seguros

Mantivemos o nome do app institucional por ser mais abrangente e unificamos o conteúdo dos apps para facilitar a vida do usuário.
e agora com a unificação não fazia mais sentido manter a mesma UX do app, com isso foi preciso um trabalho massivo da equipe de UI/UX da everis para conseguir criar um app com todo conteúdo e ainda sim fazer sentido.

#### Novo layout
Prints de produção, não achei as especificações rsrs
<img src="assets/img/everis/bbmapfre-unificacao/novo-layout.png" alt="">

### 4. Início do projeto

Com novo layout definido para algumas telas e time se formando. Fomos criando o app e agora como a estimativa já havia sido definida, precisávamos replanejar ou assumir que caberia nos 3 meses que já havíamos passado para o cliente.

Aceitamos o desafio e topamos manter os 3 meses, visto que o novo layout melhoraria a usabilidade e com isso removeria algumas telas desnecessárias.


### 5. Desenvolvimento

Apesar de a estimativa ter sido feita como escopo fechado, controlamos o desenvolvimento com métodos ágeis e tivemos poucos problemas em relação a isso.

O desenvolvimento teve poucos problemas na parte do ionic. Não acho tão relevante falar das outras frentes que tiveram. rsrs

Pontos interessantes que podemos citar sobre o desenvolvimento são:
* Criamos cerca de 95+ telas, algumas sendo reutilizadas como componentes;
* Criamos um fluxo de telas para o usuário voltar onde parou, mesmo após a morte do app, depois de um tempo em segundo plano;
* Criamos um plugin específico para o projeto que não existia na doc do ionic. Plugin para enviar o ticket carteirinha para a Apple Wallet <a href="https://github.com/everis-br/cordova-apple-wallet-tickets" target="_blank">Repo</a>
* Usamos o plugin do maps para mostrar o guincho solicitado chegando em tempo real
* e muito mais ...

Também utilizamos uma boa prática em apps componentizáveis para melhoria de performance chamada `Lazy Loading`. Em um app com quase 100 telas faz uma diferença e tanto. Pensa, se a splash do app precisasse esperar carregar as 100 telas, demoraria muito. 
Com esse recurso, carregamos apenas a home e o que mais o usuário for clicando para utilizar.

Por último, mas não menos importante, criamos, duas vezes, todo pipeline de build utilizando a primeira vez, Jenkins e após o cliente adotar, utilizamos o Azure DevOps. 
O pipeline não fazia todo papel DevOps de fato por políticas do cliente, mas conseguimos otimizar boa parte do desenvolvimento/homologação. 

A cada commit feito nas branchs escolhidas como trigger, tanto jenkins quanto azure, faziam o build e entregavam o `apk` e `ipa` em uma enterprise store chamada <a href="https://appinstaller.com.br" target="_blank">AppInstaller</a>. Com isso passávamos o link para a equipe de homologação do cliente. 

Infelizmente o processo de publicação ainda continua manual pelas políticas já mencionadas.

### 6. Entrega

O prazo para entrega do projeto, código desenvolvido, era para dia 02/02. Fizemos algumas correrias para atingir essa data e conseguimos entregar perto disso. Atrasado? Não. Entregamos dia 01/02 com uma ressalva, não entregamos apenas o código desenvolvido, mas sim o app PUBLICADO nas lojas. =D


### Resumo

Hoje o app continua nas lojas e a sustentação do app está bem estabilizada, sem incidentes graves e problemas que demandem muita energia. =D

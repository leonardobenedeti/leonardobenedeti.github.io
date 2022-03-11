---
layout: post
title: "iFood Benefícios"
little_desc: "App criado do zero atuando pela CI&T/Dextra "
excerpt_separator: ""
categories:
  - Dextra / CI&T
tags:
  - flutter
  - android
  - ios
  - ux
  - ui
  - branding
last_modified_at: 2022-03-04T14:00:00-05:00
---


### Contexto geral e história

Minha história relacionando iFood Benefícios e Dextra iniciou dia 01/12/2020, fui contratado ainda em outubro/2020 pela Dextra para iniciar dia 01/12. Com isso minha integração foi interrompida já por uma das primeiras reuniões do projeto. 

Fiquei muito empolgado ao iniciar o projeto com uma gigante chamada iFood, mesmo não sendo o aplicativo principal, tínhamos uma responsabilidade imensa de criar o app de benefícios do ZERO.

Inicialmente o time do projeto contava apenas com pessoas da Dextra e definimos todos os primeiros passos do projeto, que no momento ainda era tratado como um MVP, por conta do produto já existir dentro do app principal do ifood. 

O contexto inicial do projeto era esse: Remover o produto benefícios do app iFood Delivery, até para o próprio produto iFood Benefícios ter mais autonomia, e com isso iniciamos. 

Antes de me despedir do projeto(spoiler alert), fiz um `git log` buscando os primeiros commits para levantar essa informação. 

Fui o autor do 4 commit do projeto, ainda definindo os primeiros widgets e uso de themeData e design tokens.
> (claramente ofusquei informações para não expor meus colegas)

``` console
commit 0599c1****************7a2cf
Author: Leonardo Benedeti <leonardobenedeti@gmail.com>
Date:   Fri Dec 4 16:46:21 2020 -0300

    Inclusão de themeData e designTokens

commit acc0a0****************909eb
Author: Leonardo Benedeti <leonardobenedeti@gmail.com>
Date:   Wed Dec 2 20:26:08 2020 -0300

    Criação do widget button com as suas variações e adição dele no dashbook

commit b544c5****************22508
Author: ****************
Date:   Tue Dec 1 09:44:41 2020 -0300

    Removing web folder

commit 83af1****************450ca
Author: ****************
Date:   Mon Nov 30 17:59:27 2020 -0300

    vscode on gitignore

commit 9285c****************5c4b4
Author: ****************
Date:   Mon Nov 30 17:55:47 2020 -0300

    Initial commit
```



### Tecniquês

O projeto já passou por algumas alterações de arquitetura e gestão de estado, porém ele iniciou com o seguinte setup: Arquitetura próxima ao MVVM e utilizando MobX como gestão de estado. Este primeiro setup foi decidido por conta do contexto inicial do produto, que era muito pequeno, não existindo a necessidade de algo mais robusto. 

O MVP cresceu, virou produto e esse produto cresce todos os dias cada vez mais.

Com isso, atualmente o app com um contexto MUITO maior e já com uma escala e time gigante, optamos em migrar para um novo setup: Clean Arch e Cubit. 

Infelizmente não posso abrir muita coisa por se tratar de um projeto privado, mas o que posso afirmar é: Foi muito gratificante atuar num projeto onde foi possível migrar código, refatorar quando necessário e coisas do tipo. 


### Presença na loja

O app sempre teve uma nota proporcionalmente baixa em relação aos concorrentes, mas à medida que evoluímos o app conseguimos chegar num patamar de avaliações bem compatível e sempre crescendo. 

![Imagem do app na loja appstore](./assets/img/dextra-ciandt/ifood-beneficios/appstore.png)



### Fim da história

Em março, completei 1 ano e 4 meses de projeto. Projeto que no início foi bem conturbado e tortuoso por conta de estarmos descobrindo como o produto seria. Passamos por marés muito agitadas e atualmente o projeto se encontra em águas bem mansas, e como diz o ditado: maré calma nunca fez bom marinheiro, decidi sair do projeto para buscar novos desafios. Mas calma, tudo isso ainda atuando pela CI&T, apenas vou trocar de projeto e antes de iniciar no novo desafio, também optei por tirar umas férias para descansar. 

Com isso, hoje dia 04/03, último dia antes das férias, encerro minha participação no projeto iFood Benefícios mas mantenho o carinho pelo projeto, que vi crescer literalmente do zero. #vaiFilhão
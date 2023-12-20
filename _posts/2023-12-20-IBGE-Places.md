---
layout: post
title: "IBGE - Places"
little_desc: "App criado com Ionic para relembrar o framework"
excerpt_separator: ""
categories:
  - Próprios / Freelas
tags:
  - Ionic
  - scss
  - typescript
last_modified_at: 2023-12-20T14:00:00-05:00
---

### Relembrar é viver... edição Ionic Framework

![Resumo da usabilidade do app em GIF](./assets/img/ibge/video-device-browser.gif)


### Porque reviver uma tech que não atuo mais ?

Por conta de uma possível oportunidade, que precisava estabilizar um app criado em Ionic, fui abordado por um amigo/ex-colega de trabalho sobre a possibilidade de ajudar no projeto.

Porém... mesmo topando ajudar inicialmente, surgiu uma incerteza de que de fato eu daria conta do trabalho, afinal, faz muito tempo que não atuo com Ionic. 

Daí decidi criar esse projeto pra ir relembrando a documentação, navegação e chamadas de APIs abertas.


### Porque estados e cidades do brasil?

Queria criar algo usando uma api aberta como os testes padrões que normalmente utilizam as APIs de heróis da marvel e muitas outras apis abertas, porém não queria ser contaminado com testes já existentes e nessa brincadeira encontrei a api do IBGE que tem muitas outras opções muito legais pra serem exploradas. 

No caso deste app, optei por utilizar estas opções:

`https://servicodados.ibge.gov.br/api/v1/localidades`

Lista as localidades do brasil em vários formatos, aqui no app usamos apenas estados e cidades pra montar a lista e capturar o id da cidade pra utilizar nas próximas.

---

`https://servicodados.ibge.gov.br/api/v2/censos/nomes/leonardo?localidade=[ID_CIDADE]`

Fornece a quantidade de Leonardos nascidos em um determinado período na localidade, que no caso utilizei o id da cidade pra buscar o número por cidade.

---


`https://servicodados.ibge.gov.br/api/v3/malhas/municipios/[ID_CIDADE] `

Também com o id da cidade, neste caso aqui é possível buscar a silhueta da cidade. 
 

e com toda essa informação vamos pro layout...

### Layout da ideia

Como era algo apenas pra relembrar a mecânica do Ionic e não um projeto de fato, não tinha muita intenção de criar algo muito complexo em layout, muito também por conta de que o layout no Ionic é feito com html e css, duas tecnologias que já tenho uma ótima experiência.

Daí pra relembrar apenas a mecânica, um layout simples bastaria e pensei justamente em duas listas simples com ChoiceChips e depois uma tela com mais detalhes da cidade escolhida.

1. Listagens de estados e cidades
![Imagem das listas](./assets/img/ibge/listagens.png)

2. Detalhes da cidade e quantos Leonardos
![Imagem das listas](./assets/img/ibge/detalhes.png)


Vale comentar, em um projeto mais elaborado, normalmente faço um protótipo antes, aqui eu fui me guiando apenas pelo código. 

### Sobre o projeto e código

Confesso que quando a oportunidade chegou eu não aceitei tão bem a ideia de retornar a uma tecnologia que não utilizo há algum tempo... mas sinceramente a realidade é que não achei tão ruim, de fato me encontrei muito mais rápido do que imaginava e o resultado foi bem interessante, principalmente pelo tempo, demorei cerca de 3~4h pra realizar a base do projeto e antes de escrever este post, fiz uns ajustes de layout apenas e tudo pode ser conferido nos timestamps dos commits. =D

Sobre o código, vocês podem conferir tudo como foi feito no repo do projeto que está aberto. 

Repo do projeto: 
<a href="https://github.com/leonardobenedeti/ibge-places" target="_blank">https://github.com/leonardobenedeti/ibge-places</a>


obs.: tenho outro projeto parecido com este, feito também para uma oportunidade porém bem mais elaborado e feito em Flutter que é o 
<a href="https://leonardobenedeti.github.io/pruuu-app" target="_blank">Pruuu App</a> criado pra ser uma réplica do twitter, ficou bem daora e vale a leitura. =D
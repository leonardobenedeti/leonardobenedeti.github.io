---
layout: post
title: "Github Actions - Flutter Web"
little_desc: "Pipeline criada pra exemplificar uso no AppInstaller"
excerpt_separator: ""
categories:
  - Próprios / Freelas
tags:
  - Flutter
  - Web
  - CI/CD
  - Github Actions
last_modified_at: 2023-12-24T14:00:00-05:00
---

### Como publicar flutter web utilizando Github Actions + webhook + hostinger

Recentemente atuei com o Github Actions em um projeto mas não tive oportunidade de criar um do zero pra ver como funcionava, dai veio a ideia de criar algo simples e que pudesse postar por aqui, dai como o repositório do GearApp é privado não poderia servir de case pra mostrar publicamente, dai lembrei de um projeto que estava meio jogado e caberia um testes como esse.

A ideia era:
1. Criar o layout mais básico possível com flutter
2. Sincronizar os hooks pra assim que publicar em uma branch já publicar no hostinger
3. Automatizar tudo isso com o Github actions

O resumo da ideia em um rabisco seria algo nesse sentido. 

![Desenho do fluxo de código](./assets/img/github-actions/code-flow.jpeg)


### Layout

O App installer é um projeto que acabou morrendo e decidi manter o domínio por ser um nome bem bom, mas também disponibilizar a possibilidade para negociação do domínio e não apenas mostrar que o site não existe. Inicialmente fiz com um construtor da própria hostinger e tava ok, mas pra exemplificar o uso do Github Actions vi um bom candidato pra isso.

![Layout do site](./assets/img/github-actions/layout.png)

Além do layout adicionei também o copiar para área de transferência. 

No final vou disponibilizar o link do repo completo.


### Githooks no hostinger

Aqui não existe muito mistério, mas pra não deixar de mostrar, vamos aos prints

No painel de hospedagem da hostinger você pode cadastrar um repo e apontar para um diretório, assim que o repo for atualizado, você pode implantar e com isso ele pega tudo que tem na branch e adiciona no diretório indicado, mas nesse passo, ainda manualmente. 

![Implantação manual dos arquivos do repo](./assets/img/github-actions/repo-to-directory.png)


E pra facilitar mais ainda, ao clicar em implantação automática, é mostrado um link do hook que o hostinger irá escutar caso esteja vinculado ao github. Feito isso, todo push na branch production é feito todo o processo de substituir os arquivos do diretório pelos arquivos da branch, assim, atualizando o site ou projeto.

![Implantação automática](./assets/img/github-actions/implantacao-automatica.png)


### Estrela do show

Agora, com tudo já montado, faltou apenas o próprio build utilizando os workflows do github actions e o meu ficou assim: 

``` yaml
name: Publish Web

on:
  workflow_dispatch:
  push:
    branches:
      - main

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout
        uses: actions/checkout@v1

      - name: Setup Flutter
        uses: subosito/flutter-action@v1
        with:
          channel: "stable"

      - name: Install dependencies
        run: flutter pub get

      - name: Build Web
        run: flutter build web --release

      - name: Deploy
        run: |
          cd build/web
          git init
          git config --global user.email leonardobenedeti@gmail.com
          git config --global user.name leonardobenedeti
          git status
          git remote add origin https://${{secrets.TOKEN_FOR_BUILD}}@github.com/leonardobenedeti/appinstaller.git
          git checkout -b production
          git add --all
          git commit -m "Publish by Actions"
          git push origin production -f
```

Mas aqui temos mais detalhes pra funcionar como o `secrets.TOKEN_FOR_BUILD`. Pela internet tem vários artigos que mostram como criar o token pra utilizar aqui só que gostaria de indicar e também deixar o crédito de onde tirei essa dúvida que foi neste <a href="https://blog.flutterando.com.br/publicando-suas-paginas-flutter-no-github-pages-utilizando-github-action-ab2701cd1f52" target="_blank">post</a> do Toshi Ossada no blog do Flutterando. 


E com isso tudo pronto, só fazer seus commits que tudo vai acontecer automágicamente... =D

![Implantação automática](./assets/img/github-actions/workflows.png)

e claro, quando for utilizar algo mais automatiado assim, cuidado com o fluxo pra não sobrepor códigos que não poderiam ser alterados.

E como prometido, aqui vai o <a href="https://github.com/leonardobenedeti/appinstaller" target="_blank">Repo do AppInstaller</a> pra vocês conferirem as execuções e tudo além que não foi explicado aqui. 


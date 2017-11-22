---
layout: post
title: "Jekyll - Criação de blog e sites"
excerpt_separator: "<!--more-->"
comments: true
categories:
  - Dev Web
tags:
  - web
  - jekyll
last_modified_at: 2017-11-21T12:32:16-05:00
---

Todo desenvolvedor tem a necessidade pessoal de montar seu próprio site ou blog para mostrar seus trabalhos <!--more-->de uma maneira mais amigável, né?!
Comigo não foi diferente, porém no meu caso, precisava de algo mais simples e que não me demandasse tanto tempo para criar um site, precisava que fosse rápido, simples e funcional. Com isso iniciei as buscas e encontrei uma magia chamada Jekyll, basicamente um criador de páginas estáticas a partir de arquivos Markdown. 

Este site que você navega, foi criado com esta ferramenta. O intuito era ter uma base de conhecimento muito simples com um acesso mais fácil e melhor indexada, porém com a facilidade de montar e alterar templates e conteúdo, também incrementei com minhas informações profissionais, assim tentando substituir o tão formal currículo de papel. Que ainda tenho se precisar rsrs. 

Pra utilizar o a criação de um site básico e já totalmente indexado basta rodar os comandos abaixo:
``` terminal
# Install Jekyll and Bundler gems through RubyGems
gem install jekyll bundler

# Create a new Jekyll site at ./myblog
jekyll new myblog

# Change into your new directory
cd myblog

# Build the site on the preview server
bundle exec jekyll serve
```

Com esses comandos ~~e muitos outros pra configurar o ambiente que não vem ao caso por cada máquina ter suas particularidades~~ você consegue criar um blog ou site estático de maneira muito simples. A maior vantagem pra mim é que já tinha costume em escrever os `*.md` para repositórios onde contribuo, assim atingindo a meta de conseguir criar uma página do jeito que precisava em pouco tempo.

Enfim... 


Pra conhecer mais detalhes da plataforma, segue abaixo links para documentação oficial e um curso gratuito no Udemy, curso este que assisti enquanto criava este site. 

[Documentação oficial](https://jekyllrb.com/)<br/>
[Curso no Udemy](https://www.udemy.com/criando-sites-estaticos-com-jekyll/)
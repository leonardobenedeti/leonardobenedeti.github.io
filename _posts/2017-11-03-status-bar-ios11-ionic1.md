---
layout: post
title: "Status bar ionic1 rodando no iOS 11"
little_desc: "Em uma alteração de um aplicativo que eu mantenho, me deparei com o problema"
excerpt_separator: "<!--more-->"
comments: true
categories:
  - Dev Ionic
tags:
  - ionic
  - ios
last_modified_at: 2017-11-03T12:32:16-05:00
---

Em uma alteração de um aplicativo que eu mantenho, me deparei com o problema relacionado a status bar do iOS 11.
O app ficou com o header maior por não utilizar setar a cor de background da status bar, com isso ocorreram quebras de layout e a própria status bar ficou sem cor. 

Depois de uma boa busca pelo assunto, encontrei o plugin que resolvia isso e logo adicionei ao projeto
``` 
ionic plugin add cordova-plugin-disable-ios11-statusbar
```

Após a inclusão do plugin, bastou gerar um novo build e tudo se resolveu. Apenas para o iOS 11, para o iPhone X ainda não consegui testar, mas a solução deve ser bem próxima. 

fonte: [Issues Apache](https://issues.apache.org/jira/browse/CB-12886)
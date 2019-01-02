---
layout: post
title: "Override keys configs do info.plist para Ionic 3"
little_desc: "Ao atualizar um projeto ionic, do 1 para o 3, precisei rever alguns..."
excerpt_separator: "<!--more-->"
comments: true
categories:
  - Dev Ionic
tags:
  - ionic
  - ios
  - info-plist
last_modified_at: 2018-05-16T12:32:16-05:00
---

Ao atualizar um projeto ionic, do 1 para o 3, precisei rever alguns guides da Apple referente a permissões de uso de recursos nativos.
Neste caso precisei utilizar a câmera e a configuração básica deste plugin não estava criando a chave de descrição para o info.plist, com isso ao executar a chamada para a câmera o aplicativo crashava. 
Ao procurar o motivo encontrei a key `NSCameraUsageDescription` sem valor algum. Ao incluir um valor de teste, tudo voltou a funcionar. 
Porém o projeto XCode é sempre refeito quando se faz um novo build, alterar a cada build não seria algo prático e busquei a solução abaixo.

No arquivo config.xml é onde ficam todas as configurações básicas do ionic para gerar o projeto de cada plataforma.

Como é algo focado em iOS, precisamos definir essas tags dentro da tag 'Mãe' `<platform name="ios">`, onde obviamente são definidas as propriedades do build para o XCode. 

config.xml:
``` xml
<platform name="ios">
...
    <config-file parent="NSCameraUsageDescription" platform="ios" target="*-Info.plist">
        <string>Texto explicando o porque você quer usar a câmera</string>
    </config-file>
...    
</platform>
```

Com isso ele altera a key e inclui o valor que você escreveu na tag `<string>`, com isso você consegue utilizar a câmera com a devida permissão.

Vale ressaltar que basta trocar a key e o valor para ser alterada no info.plist, ou seja, quer trocar a de localização por exemplo ?
Basta descobrir o nome da key, que sendo de localização é `NSLocationWhenInUseUsageDescription` e criar a mesma tag pra ele, incluir um texto explicando o porque e pronto. Ao fazer o build do aplicativo você vai conseguir utilizar o recurso desejado.


Fonte: [https://stackove...-10-builds/40466511](https://stackoverflow.com/questions/39980700/usage-description-issue-in-ionic-and-ios-10-builds/40466511)
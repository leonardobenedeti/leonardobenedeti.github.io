---
layout: post
title: "AAPT - Como verificar detalhes de um APK"
excerpt_separator: "<!--more-->"
comments: true
categories:
  - Dev Android
tags:
  - android
  - apk
  - appt
last_modified_at: 2017-10-24T12:32:16-05:00
---

Recentemente em um freela, precisei verificar o version code de um apk, porém não queria subir na loja para que a mesma verificasse, queria algo mais simples, <!--more-->do nível de terminal. 
Dai iniciei uma busca e encontrei o binário `aapt` que com algumas flags adicionais, fazem toda essa mágica, e mostram as informações do apk.

Como utilizar: 
``` terminal
$ANDROID_HOME/buid-tools/[android-version]/aapt dump badging <path-to-apk>
```

Utilizando este comando, consegui o que precisava, que era saber o version code do apk de um modo bem simples. 
E pra variar, encontrei essa solução no [Stack Overflow](https://stackoverflow.com/), nos links abaixo:

[https://stackoverflow....e-in-the-android-applicat](https://stackoverflow.com/questions/4470139/how-to-get-application-or-package-info-from-the-apk-file-in-the-android-applicat)

[https://stackoverflow...can-not-be-found-on-mac](https://stackoverflow.com/questions/11330165/android-aapt-can-not-be-found-on-mac)
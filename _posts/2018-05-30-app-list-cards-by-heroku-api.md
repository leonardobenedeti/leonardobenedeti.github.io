---
layout: post
title: "Ionic app to list cards by heroky api"
little_desc: "No mesmo happy hour do último post, além da API, houve a necessidade de um APP..."
excerpt_separator: "<!--more-->"
comments: true
categories:
  - Dev Ionic
tags:
  - ionic
  - rest
  - api
  - heroku
last_modified_at: 2018-05-30T12:32:16-05:00
---

No mesmo happy hour do [último post](./deploy-flask-api-on-heroku), além da API, houve a necessidade de um APP que pudesse entender essa API de maneira simples. 

Escopo: Rápido e básico, fazer um request em uma API que vai retornar uma lista e mostrar isso como cards. 

No papo também definimos que fazer isso com [Ionic](http://ionicframework.com/) seria bem tranquilo.


Com tudo definido vamos a criação do app.


```
ionic start listCardsByHerokuApi blank
```

~ A partir deste momento é preciso estar dentro da pasta do projeto, de preferência usando o Visual Studio Code. 

Vamos alterar o arquivo `[path-to-your-project]/src/app/app.module.ts` para incluir um import.

``` javascript
//incluir o import do HttpClientModule
import { HttpClientModule } from '@angular/common/http'; 
...
imports: [
    ...
    //incluir na lista de imports que o app precisa
    HttpClientModule, 
    ...
  ],
```

Próximo passo - Vamos precisar criar um provider com o seguinte comando 

```
ionic g provider ListRest
```

Após criar seu provider precisamos alterar algumas coisas nele. 


Vamos até ele então `[path-to-your-project]/src/providers/list-rest/list-rest.ts`

``` javascript
  // precisamos incluir o endpoint da api
  endpoint = 'https://api-flask-leonardobenedeti.herokuapp.com';
  ...
  // e criar um metodo que retorna uma promise simples
  // vamos tratar esta promise mais pra frente no home.ts
  getList(api) {
    return new Promise((resolve, reject) => {
      this.http.get(this.endpoint+api)
      .subscribe(data => {
        resolve(data);
      }, err => {
        reject(err)
      });
    });
  }
```

Provider devidamente escrito, vamos alterar agora a tela que vai chamar essa lista. 



Como criamos um projeto baseado no template `blank` do Ionic, temos apenas uma página, que é a `[path-to-your-project]/src/pages/home/`.
Dentro da pasta dessa página temos 3 arquivos, mas vamos alterar apenas 2, `home.html` e `home.ts`, o `home.scss` fica pra um próximo post.

Vamos ao `.ts`, que é quem vai buscar a lista utilizando o provider que criamos acima.

``` javascript
import { Component } from '@angular/core';
import { NavController, LoadingController } from 'ionic-angular';
import { ListRestProvider } from '../../providers/list-rest/list-rest';

@Component({
  selector: 'page-home',
  templateUrl: 'home.html'
})
export class HomePage {

  // incluir o list rest para podermos buscar a lista
  // incluir o loadingControler para não deixar o usuário esperando sem informar
  // Ambos precisam do import, se estiver utilizando o VSCode provavelmente ele já importou pra você.
  // Caso contrário, copie os imports acima.
  constructor(
    public navCtrl: NavController,
    public listRest: ListRestProvider, 
    public loadingCtrl: LoadingController 
  ) {}

  // definição de uma variável tipo any para abrigar os cards
  cards: any;

  ionViewDidLoad() {
    this.getCards(); 
  }

  getCards(){
    // quando iniciarmos a request já vamos ter um loading na tela, informando o usuário que algo está acontecendo
    let loading = this.loadingCtrl.create({
      content: ''
    });
    loading.present();

    // chamada para o provider que criamos anteriormente passando a api que vamos utilizar, / no caso.
    // com o retorno da promise, basta tratar o then ou catch
    this.listRest.getList('/')
    .then(data => {
      this.cards = data['cards'];
      loading.dismiss();
    })
    .catch(err => {
      loading.dismiss();
      // evite usar alerts comuns como utilizei, ele bloqueia o resto da execução, pode deixar seu app atrapalhado
      // Dica para este caso é utilizar o AlertController do próprio Ionic
      alert("Algo de errado não está certo. Tente novamente!")
    });
  }
}
```

Agora para mostrar o que foi feito no `.ts` vamos alterar o `.html`.

``` html
<ion-header>
  <ion-navbar>
    <ion-title>
      Ionic Blank
    </ion-title>
  </ion-navbar>
</ion-header>

<ion-content padding>
  <!-- usando o template basico, removemos tudo dentro de ion-content e incluimos o card abaixo -->
  <!-- repare o *ngFor que estamos fazendo, a variável cards é a mesma do home.ts que alimentamos com a lista que o provider devolveu, elas devem ter o mesmo nome  -->
  <ion-card *ngFor="let card of cards"> 
    <!-- agora para cada item da lista ele vai escrever um card -->
    <ion-card-header [innerHTML]="card.title"></ion-card-header>
    <ion-card-content [innerHTML]="card.desc"></ion-card-content>
  </ion-card>
</ion-content>
```
~ Ignorem os erros do arquivo, é algo do jekyll, em breve ajeito isso. =D


Neste ponto estamos prontos para executar nosso app, como estamos fazendo uma requisição com loading e tudo mais, vamos testar em um device para ver como se comporta.
Para isso precisamos incluir a plataforma necessária para o teste. 

```
ionic cordova platform add android
```

Utilizei a plataforma Android por ser mais simples e não precisar configurar certificados e tudo que a Apple demanda. 


Após adicionar a plataforma, basta executar este comando com o device conectado ao computador. Ao finalizar o build, ele vai instalar no device o app que foi criado.

```
ionic cordova run android --device
```

E pronto. Aqui temos um aplicativo que é capaz de buscar uma lista de uma API e transformar em Cards. 

<div style="display:flex;">
    <img src="assets/img/list-cards-by-heroku/loading.png" style="margin:20px auto;border: 1px solid #000;padding: 5px;" alt="">
    <img src="assets/img/list-cards-by-heroku/cards.png" style="margin:20px auto;border: 1px solid #000;padding: 5px;" alt="">
</div>


--------

Pra visualizar a API citada neste post basta ir para: [https://api-flask-leonardobenedeti.herokuapp.com/](https://api-flask-leonardobenedeti.herokuapp.com/)

Para baixar os códigos mostrados acima basta acessar:
[https://github.com/leonardobenedeti/ionic-app-list-cards-by-heroku-api](https://github.com/leonardobenedeti/ionic-app-list-cards-by-heroku-api)

Para baixar o apk criado neste exemplo basta [clicar aqui](./assets/files/app-list-cards-by-heroku-api.apk)

--------

Fonte: [https://www.djamwa...43-httpclient](https://www.djamware.com/post/59924f9080aca768e4d2b12e/ionic-3-consuming-rest-api-using-new-angular-43-httpclient)
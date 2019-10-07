---
layout: post
title: "[Tutorial] - Email sender with Sendgrid on Heroku"
little_desc: "Pensando como melhorar algumas plataformas que tenho online encontrei o sendgrid"
excerpt_separator: ""
categories:
  - Próprios / Freelas
tags:
  - heroku
  - node.js
  - sendgrid
last_modified_at: 2019-10-07T14:00:00-05:00
---

Pensando como melhorar algumas plataformas que tenho online encontrei o Sendgrid dentro do nosso velho amigo Heroku.

A Sendgrid é uma plataforma de envio de emails transacionais e de marketing. 

Abaixo vão dois links explicando melhor os detalhes:

* <a href="http://sendgrid.com/" target="_blank">Site oficial</a>
* <a href="https://elements.heroku.com/addons/sendgrid" target="_blank">Link para o add-on dentro do heroku</a>(recomendo vir por aqui)

Agora já conhecendo melhor a plataforma, vamos configurar tudo para criar nossos emails transacionais.

O primeiro passo é provisionar o add-on do Sendgrid dentro do Heroku.

<img src="assets/img/sendgrid/1.0-provision-heroku.png" alt="">

Com o add-on configurado essa é o dashboard da plataforma.

<img src="assets/img/sendgrid/2.0-dashboard.png" alt="">

Dentro do dashboard precisamos realizar duas configurações básicas são:

* 1 - Criar uma api key no dashboard 
<br/><a href="https://app.sendgrid.com/settings/api_keys" target="_blank">Settings > API KEY</a>
<img src="assets/img/sendgrid/3.0-config-api-key.png" alt="">

* 2 - Configurar a api key como variável no heroku
<img src="assets/img/sendgrid/4.0-config-api-on-heroku.png" alt="">

Após as configurações básicas precisamos criar e testar um template ainda pelo dashboard

* Menu de templates
<img src="assets/img/sendgrid/5.0-menu-templates.png" alt="">

Aqui basta criar o template como preferir, usando a interface de arrasta e solta ou usando HTML

Após criar o template precisamos testar e pra isso na própria plataforma temos um sandbox para enviar o email.
<img src="assets/img/sendgrid/6.0-preview-and-test-template.png" alt="">

Ao enviar o email via sandbox, podemos conferir a caixa de entrada do email escolhido para receber o teste.
<img src="assets/img/sendgrid/7.0-first-test-by-preview.png" alt="">

Podemos perceber que a variável user ainda está sem preenchimento. Vamos agora criar o backend para enviar o email de forma transacional.


### NodeJs

Para exemplificar o uso da plataforma criei um projeto e estou mantendo no meu github. 

<a href="https://github.com/leonardobenedeti/heroku-mail-sender" target="_blank">
  Link do repo
</a>

Ou você pode 'deployar' direto no heroku clicando abaixo

<a href="https://heroku.com/deploy?template=https://github.com/leonardobenedeti/heroku-mail-sender" target="_blank">
  <img src="https://www.herokucdn.com/deploy/button.svg" alt="Deploy">
</a>


A base do código é o que busquei na doc oficial do Sendgrid para nodejs.


Import e configuração da API KEY que criamos anteriormente.

``` javascript
const sgMail = require('@sendgrid/mail');
sgMail.setApiKey(process.env.SENDGRID_APIKEY);
```

Código base utilizando o template que criamos enviando todos os parametros no request.
``` javascript
app.post("/sendmail/template", function(req, res){
    const {to, from, template_data} = req.body;
    const msg = {
        to: to,
        from: from,
        templateId: 'd-ee4c43022cc74cec802e5398cb54a31f',
        dynamic_template_data: template_data,
    };
    sgMail.send(msg)
    .then((success)=>{
      res.status(200).send({success: "Email enviado com sucesso"});
    }).catch(err=>res.status(400).send({error:"Algo de errado não está certo no envio de emails."})); 
});
```

Com todo código configurado e rodando localmente vamos aos testes via postman.

<img src="assets/img/sendgrid/8.0-request-postman.png" alt="">

Após o teste, podemos perceber que o parametro de usuário foi preenchido de acordo com o request via postman.

<img src="assets/img/sendgrid/9.0-result-postman.png" alt="">

Dai pra frente, precisamos criar um template customizado para cada caso e transacionar como preferir. =D

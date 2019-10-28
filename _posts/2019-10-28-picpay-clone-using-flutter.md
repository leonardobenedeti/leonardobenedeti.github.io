---
layout: post
title: "Clone do app PicPay usando Flutter"
little_desc: "Um belo dia resolvi mudar e fazer tudo o que eu queria fazer..."
excerpt_separator: ""
categories:
  - Próprios / Freelas
tags:
  - flutter
  - android
  - ios
last_modified_at: 2019-10-28T14:00:00-05:00
---

"Um belo dia resolvi mudar e fazer tudo o que eu queria fazer"

Sim. Em um dia, não tão belo como na música, decidi me aventurar e criar algo bacana usando Flutter.

Participo de alguns grupos que fazem apps de exemplo, para mostrar arquiteturas e boas práticas, criando clones de apps já existentes.

Com essa ideia em mente procurei algum app que ainda não tivesse sido clonado e não vi nenhum clone do PicPay, o canivete suíço dos pagamentos.

Uso muito o app no meu dia a dia e foi uma motivação maior ainda replicar um app tão bom, que imagino que seja nativo, utilizando o Flutter.

Como ponto de partida, tirei um print do meu celular e decidi recriar apenas a home do app, que mostra:
* Saldo
* Lista de pessoas
* Tabs de transações, minhas e das pessoas que sigo
* A lista referente as tabs

Print do app original. 
<img src="assets/img/picpay/original.png" alt="">

Seguindo para o desenvolvimento. 

Iniciei o projeto em um horário vago no período de trabalho, mas só consegui dar continuidade a noite em casa, devido a tarefas do trabalho.

Seguindo assim, podemos analisar os ajustes a cada commit que fiz. Os detalhes dos commits vocês podem ver no repo. =D

Primeiro ajuste: Apenas ajustes no app que o flutter te entrega pronto, inclusão de cores e ícones na title bar.
<img src="assets/img/picpay/commits/1.png" alt="">

Segundo ajuste: Aqui tivemos uma mudança mais considerável, ajustei o header para sliver e customizei o title para fazer o 'Meu Saldo' e já adicionei os containers para os próximos ajustes.
<img src="assets/img/picpay/commits/2.png" alt="">


Terceiro ajuste: Aqui iniciei a criação das listas de atividades e dos cards. Dei uma boeira na cor da tab também. era pra alterar a cor do indicator apenas mas alterei do container. #mybad
<img src="assets/img/picpay/commits/3.png" alt="">


Quarto Ajuste: Cores devidamente ajustadas e card construido.
<img src="assets/img/picpay/commits/4.png" alt="">

Quinto ajuste: Inclusão da lista de sugestões de contato para efetuar um pagamento.
<img src="assets/img/picpay/commits/5.png" alt="">

Sexto ajuste: Inclusão de mais itens na lista e inclusão de icones printados do app original
<img src="assets/img/picpay/commits/6.png" alt="">

Sétimo ajuste: Remover a necessidade da safe area na parte de baixo do layout. 
<img src="assets/img/picpay/commits/7.png" alt="">


E para comparar com o layout original vamos com uma imagem lado a lado.
<div class="grid">
    <div class="a img">
        <img src="assets/img/picpay/original.png" alt="">
    </div>
    <div class="b img">
        <img src="assets/img/picpay/clone.png" alt="">
    </div>
</div>



Vale ressaltar. Criei aqui apenas a UI da home do PicPay, não me importei com algumas coisas, como arquitetura, boas práticas, BLoC e affins...

Queria deixar a UI mais próxima possível do app original para me testar neste quesito. 

Quando tiver um pouco mais de tempo, pretendo plugar uma consulta a algum backend, que provavelmente eu vou criar também, e ai sim, plugar tudo que tiver de boas práticas, loadings e tudo mais pra deixar o app dinâmico.

E pra quem não conhece o PicPay, da uma olhada ai que vale a pena usar. 

Aqui vai um convite pra você: <a href="http://www.picpay.com/convite?@331X" target="_blank">http://www.picpay.com/convite?@331X</a>

O código completo do app você pode conferir no meu repositório com todos os detalhes.  
<a href="https://github.com/leonardobenedeti/picpay_clone_flutter" target="_blank">https://github.com/leonardobenedeti/picpay_clone_flutter</a>

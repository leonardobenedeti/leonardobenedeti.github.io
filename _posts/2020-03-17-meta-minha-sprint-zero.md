---
layout: post
title: "#5 Meta Minha - Preparação do Ambiente"
little_desc: "Vamos botar a mão na massa com algumas configurações e ajustes para iniciar do jeito certo"
excerpt_separator: ""
categories:
  - Meta Minha
tags:
  - flutter
  - android
  - ios
  - agil
  - ux
  - ui
  - branding
  - devops
  - jenkins
last_modified_at: 2020-03-17T14:00:00-05:00
---

Uma imagem é melhor do que mil palavras.... pois bem! (sim já tinha iniciado rsrs)


<img src="assets/img/metaminha/sprint-zero/1-sprint-zero.png" alt="">

Este será, talvez, o menor post da série. Aqui darei início aos trabalhos mais técnicos do que conceituais. 

Mas de onde surgiu a ideia de fazer uma **Sprint Zero** neste app tão pequeno. Precisamos disso ???

Vamos tentar pintar um cenário: Para uma casa ser construída é necessário uma fundação bem sólida para que a casa se mantenha firme, certo ?!

A Sprint Zero funciona da mesma maneira. É um período onde todas as frentes podem atuar sem impactar nada, preparando tudo para o projeto iniciar.

Exemplos que acontecem durante a Sprint Zero, por frente:

* **Product Owner**: Escreve as histórias na ordem de prioridade para a primeira sprint do projeto.
* **Scrum Master**: Orienta o time, sugerindo como utilizar o cockpit da maneira mais otimizada.
* **Quality & Assurance**: Escreve os cenários de testes básicos e configura um ambiente automatizado de testes ( Tema não abordado por aqui, AINDA!).
* **Developers**: Criam essa base para que todo o app seja criado de maneira sustentável e sólida.

Neste app, vamos abordar apenas duas frentes, **Product Owner** e **Developers**. Dado o contexto, não tem porque simular as outras frentes. Faria sentido caso estipulasse um prazo para conclusão, mas como não faremos isso... =D

Separando as responsabilidades por frente:

**Product Owner**

<img src="assets/img/metaminha/agil/6-descricao-historias.png" alt="">
Com o boné de **PO**, tenho muito trabalho pela frente mas não vou descrevê-lo na Sprint-zero. Vou mostrar as histórias escritas a cada sprint que for evoluindo o aplicativo. #aindaNãoEscrevi

**Developer**

Finalmente na minha zona de conforto. Na frente de desenvolvimento, na Sprint-zero, vou configurar muita coisa. Como puderam ver na primeira imagem do post, em algumas tasks que criei. 

Estou utilizando uma técnica que pratiquei em um dos projetos que atuei. 

Eu sou um só, certo ? (Adoraria ter um clone rsrs)

Eu, sendo um só, LOGICAMENTE, só consigo fazer uma coisa por vez. Com isso fiz o seguinte:

<div class="grid">
    <div class="a text">
        <span>
            Limitei, mentalmente, o Work In Progress do projeto. <br>
            <b>Porque?</b> <br>
            Com este limite de uma task por vez, não vou me afogar com 3, 4, 5 tasks por vez. O que normalmente acontece na maioria dos projetos.
        </span>
    </div>
    <div class="b img">
        <img src="assets/img/metaminha/sprint-zero/2-WIP.png" alt="">
    </div>
</div> 

Outro detalhe que a limitação de execução de tasks ocasiona, é que uma task mal "quebrada", vai ter dependência de outra task e com isso o dev é meio que OBRIGADO a fazer duas tasks ao mesmo tempo. Esse limite na sprint seguinte, vai educar o dev a quebrar a task sem dependência na próxima sprint.

Ex.: Uma história que tenha uma chamada de api e que liste o resultado na tela. 

A quebra de tasks pode ser assim:
* Criar modelo de dados de itens da lista
* Criar widget para repetir após o retorno da api
* Criar API e printar o retorno no console
* Conectar o widget com a API criando a lista baseado no modelo

Aqui criei 3 tasks independentes e uma para fechar todas elas. Eventualmente as tasks vão ter dependência, mas o ideal é evitar esse tipo de coisa para que mais de uma pessoa consiga atuar na mesma história. =D


Outro item interessante é tentar criar uma base de widgets, componentes ou o que for reutilizar no projeto. 

No decorrer do projeto pretendo conseguir entregar um design system com o que estou criando. 

Para isso, ainda na sprint-zero estou criando alguns widgets que serão a base do meu app.

<img src="assets/img/metaminha/sprint-zero/3-design-system.png" alt="">
Para validar melhor este item com todo app junto, vale dar uma revisitada no post de <a href="/meta-minha-design" target="_blank">#2 - Design da ideia</a>

Aqui então finalizo o post, mas a Sprint-zero ainda vai continuar correndo até conseguir fechar todos os itens, UM A UM, sem pressa e sem correria, para manter sempre a qualidade. 

Em breve a #sprint-01 começa e aí sim vamos codar. =D


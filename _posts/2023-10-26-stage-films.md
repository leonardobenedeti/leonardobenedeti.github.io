---
layout: post
title: "Site StageFilms"
little_desc: "Site criado a mão, com todos efeitos feitos na pontinha dos dedos."
excerpt_separator: ""
categories:
  - GearLabs
tags:
  - html
  - css
  - javascript
last_modified_at: 2023-10-12T14:00:00-05:00
---

### Inicio da ideia e proposta

Por ser seguidor do canal onde o Pedro Spina atuava anteriormente à fundação da StageFilms, sempre acompanhei o trabalho dele e na primeira oportunidade de criar um site pra empresa dele, pulei na bomba e ofereci meus trabalhos então pra Stage, composta pelo Pedro Spina e sua esposa Luana Spina. 

Após todo papo pra entender o que eles queriam e pegar exemplos, iniciei uma analise que acabou sendo bem controversa, julguei ser possível fazer 100% do que eles pedira, mas ao iniciar o código, tudo conflitou e acabou ficando muito bagunçado e não funcionou. 

Com isso, fizemos uma nova reunião e fomos por um caminho de criar algo mais simples mas que ainda sim evidenciasse o trabalho da Stage Films e acabamos criando algo muito daora.


### Desenvolvimento

Inicialmente utilizariamos uma serie de libs para o site todo ser animado, mas com os conflitos citados anteiormente, acabei optando por seguir uma linha mais "raiz" e criar muita coisa na mão. 

Caso não queira ler todo processo mas esteja curioso com o site, basta abrir o link: <a href="https://stagefilms.com.br" target="_blank">stagefilms.com.br</a>

#### Section: Header / Logo animada

Um dos itens principais pedidos por eles era uma logo que tinha uma animação bem específica, onde todas as letras da logo iriam mudando o tamanho e posicionamento, meio que desconstruindo a logo. 

Nesse caso, isolei cada letra da logo e apliquei uma regra de scale e padding específica para gerar o efeito de desconstrução. Inicialmente queriamos algo disforme, mas acabou que a padronização de algumas reduzindo e outras aumentando agradou e seguimos assim.

![Imagem da section head pré scroll](./assets/img/stagefilms/logo-pre-scroll.png)
![Imagem da section head pós scroll](./assets/img/stagefilms/logo-pos-scroll.png)


No asset mostrando o comportamento da logo, vocês também puderam reparar um video rolando no fundo, isso foi apenas uma cereja que decidimos fazer nos últimos ajustes e é apenas um embedded do youtube rolando com um estilo aplicado para não esbarrar nos aspect ratios. =D


---

#### Todo o site

Inserimos um efeito de cursor bem conhecido que é um highlight em itens específicos do site. 

Utilizamos a lib <a href="https://magicmousejs.web.app/" target="_blank">Magic Mouse</a> pra realizar esse efeito e o uso dela é bem simples. 

Após importar os arquivos necessários pra ela funcionar, basta rodar esse código para configurar as opções do highlight do cursor.


Como foi feito: 

``` javascript
options = {
  "outerStyle": "circle",
  "hoverEffect": "circle-move",
  "hoverItemMove": false,
  "defaultCursor": false,
  "outerWidth": 30,
  "outerHeight": 30
}
magicMouse(options);
```

Resultado:

![Imagem do efeito do cursor com o Magic Mouse](./assets/img/stagefilms/efeito-magic-mouse.png)

---

### Section: Grade de cases

Esta sessão foi bem tranquila, embora trabalhosa pois criar um grid desigual assim é um bom de um trabalho de formiguinha pra encaixar todos eles. 

Para replicar não existe muito mistério, é basicamente um display grid com uma grade específica onde nos itens maiores vc precisa aumentar o tamanho dele e pular alguns espaços da grade.

``` css
.classe-pai{
    display: grid;
    grid-template-rows: repeat(5, 1fr);
    grid-template-columns: repeat(8, 1fr);
}

.classe-maior-horizontalmente{
    grid-column-end: span 2;
}

.classe-maior-verticalmente{
    grid-row-end: span 2;
}
```

Feito isso, você só precisa alinhar o conteúdo do que vc fez dentro de cada item, expandido ou não e pronto. =D

![Imagem da grade de cases](./assets/img/stagefilms/grid-cases.png)


---

### Section: Carrossel de marcas

Talvez a sessão do site mais simples de execução por utilizar um lib também, chamada <a href="https://owlcarousel2.github.io/OwlCarousel2/" target="_blank">OwnCarousel</a>. Bem simples de utilizar mas aqui no projeto fizemos algo além de só utilizar a lib. 

Para ativar o carrossel com a lib basta você importar tudo que ela demanda e rodar este trecho

``` javascript
$('.brand-carousel').owlCarousel({
    loop: true,
    margin: 20,
    autoplay: true,
    center: true,
    slideTransition: 'ease-in-out',
    autoplayHoverPause: true,
    smartSpeed: 600,
    autoWidth: true,
    responsive: {
      0: {
        items: 1,
      },
      600: {
        items: 2,
      },
      1000: {
        items: 4,
      }
    }
});
```

Depois de ativarmos a lib, fizemos com o `hover`, um efeito de troca de imagens 100% preenchidas em branco para as logos originais com as cores das empresas. 

![Imagem do carrossel de marcas](./assets/img/stagefilms/carrossel-marcas.png)


---

### Section: Contato

E pra fechar, seguindo o conceito minimalista do site, a sessão de contato foi a mais simples e sem uso de nenhuma lib. Apenas os contatos e o magic mouse que já tinha sido aplicado em todo o site. 

Direto e reto. Clicou falou com eles direto nos links. =D

![Imagem do contato](./assets/img/stagefilms/contato.png)


---

### Considerações finais

O site foi publicado recentemente e está passando por uma avaliação dos clientes da StageFilms. Até então ele fica como está, mas estamos estudando a viabilidade de mais uma atualização pra trazer mais componentes para o site. =D
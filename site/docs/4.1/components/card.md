---
layout: docs
title: Cards
description: Os cards Bootstrap proporcionam um container de conteúdo flexível e extensível com múltiplos variantes e opções.
group: components
toc: true
---

## Sobre

Um **card** é um container de conteúdo flexível e extensível. Ele tem opções para cabeçalhos e rodapés, uma larga variedade de conteúdo, cores de background contextuais e opções de display poderosas. Se você é familiarizado com Bootstrap 3, saiba que os cards substituem nossos antigos panels, wells e thumbnails. Uma funcionalidade similar a destes componentes está disponível, usando classes modificadoras para cards.

## Exemplo

Cards são feitos com menos marcação HTML e estilos possível, mas ainda assim conseguem entregar bastante controle e personalização. Feitos com flexbox, oferecem fácil alinhamento e combinação com outros componentes. Por padrão, não possuem `margin`, então, use [utilitários de espaçamento]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/spacing/), se necessário.

Abaixo, tem um exemplo de um card básico com conteúdo misto e largura fixa. Cards não possuem largura fixa, inicialmente, então, eles vão preencher toda a largura de seu elemento pai, naturalmente. Isso é fácilmente personalizado com nossas várias [opções de tamanhos](#sizing).

{% capture example %}
<div class="card" style="width: 18rem;">
  <img class="card-img-top" data-src="holder.js/100px180/" alt="Imagem de capa do card">
  <div class="card-body">
    <h5 class="card-title">Título do card</h5>
    <p class="card-text">Um exemplo de texto rápido para construir o título do card e fazer preencher o conteúdo do card.</p>
    <a href="#" class="btn btn-primary">Visitar</a>
  </div>
</div>
{% endcapture %}
{% include example.html content=example %}

## Tipos de conteúdo

Cards suportam uma larga variedade de conteúdos, incluindo imagens, texto, grupo de listas, links e muito mais. Abaixo, temos oquê é suportado.

### Body

A base de um card é o `.card-body`. Use ele, sempre que precisar de um espaço dentro do card.

{% capture example %}
<div class="card">
  <div class="card-body">
    Isto é um texto dentro de um card.
  </div>
</div>
{% endcapture %}
{% include example.html content=example %}

### Títulos, textos e cards.

Os títulos dos card são usados adicionando a classe `.card-title` em uma tag `<h*>`. Da mesma maneira, links são adicionados e posicionados próximos um dos outros, colocando `.card-link` em um elemento `<a>`.

Subtitulos são criadas usando uma `.card-subtitle` em uma tag `<h*>`. Se os itens `.card-title` e `.card-subtitle` são colocados em um `.card-body`, os títulos e subtitulos serão alinhados, adequadamente.

{% capture example %}
<div class="card" style="width: 18rem;">
  <div class="card-body">
    <h5 class="card-title">Título do card</h5>
    <h6 class="card-subtitle mb-2 text-muted">Subtitulo do card</h6>
    <p class="card-text">Um exemplo de texto rápido para construir o título do card e fazer preencher o conteúdo do card.</p>
    <a href="#" class="card-link">Link do card</a>
    <a href="#" class="card-link">Outro link</a>
  </div>
</div>
{% endcapture %}
{% include example.html content=example %}

### Imagens

A `.card-img-top` posiciona uma imagem no topo do card. Com `.card-text`, textos podem ser adicionados ao card. O texto dentro do `.card-text` também pode ser estilizado com as tags HTML padrões.

{% capture example %}
<div class="card" style="width: 18rem;">
  <img class="card-img-top" data-src="holder.js/100px180/?text=Image cap" alt="Imagem de capa do card">
  <div class="card-body">
    <p class="card-text">Um exemplo de texto rápido para construir o título do card e fazer preencher o conteúdo do card.</p>
  </div>
</div>
{% endcapture %}
{% include example.html content=example %}

### Grupo e listas

Crie listas de conteúdo em um card, usando um grupo de listas.


{% capture example %}
<div class="card" style="width: 18rem;">
  <ul class="list-group list-group-flush">
    <li class="list-group-item">Cras justo odio</li>
    <li class="list-group-item">Dapibus ac facilisis in</li>
    <li class="list-group-item">Vestibulum at eros</li>
  </ul>
</div>
{% endcapture %}
{% include example.html content=example %}

{% capture example %}
<div class="card" style="width: 18rem;">
  <div class="card-header">
    Destaque
  </div>
  <ul class="list-group list-group-flush">
    <li class="list-group-item">Cras justo odio</li>
    <li class="list-group-item">Dapibus ac facilisis in</li>
    <li class="list-group-item">Vestibulum at eros</li>
  </ul>
</div>
{% endcapture %}
{% include example.html content=example %}

### Baguncinha

Misture e combine vários tipos de conteúdos para ter o card que precisa. Mostrando abaixo, estão estilos de imagens, blocos, estilos de textos e grupo de listas, todos dentro de um card com largura fixa.

{% capture example %}
<div class="card" style="width: 18rem;">
  <img class="card-img-top" data-src="holder.js/100px180/?text=Image cap" alt="Imagem de capa do card">
  <div class="card-body">
    <h5 class="card-title">Título do card</h5>
    <p class="card-text">Um exemplo de texto rápido para construir o título do card e fazer preencher o conteúdo do card.</p>
  </div>
  <ul class="list-group list-group-flush">
    <li class="list-group-item">Cras justo odio</li>
    <li class="list-group-item">Dapibus ac facilisis in</li>
    <li class="list-group-item">Vestibulum at eros</li>
  </ul>
  <div class="card-body">
    <a href="#" class="card-link">Link do card</a>
    <a href="#" class="card-link">Outro link</a>
  </div>
</div>
{% endcapture %}
{% include example.html content=example %}

### Cabeçalho e rodapé

Coloque um cabeçalho e/ou rodapé opcional, dentro de um card.

{% capture example %}
<div class="card">
  <div class="card-header">
    Destaque
  </div>
  <div class="card-body">
    <h5 class="card-title">Título especial</h5>
    <p class="card-text">Com suporte a texto embaixo, que funciona como uma introdução a um conteúdo adicional.</p>
    <a href="#" class="btn btn-primary">Visitar</a>
  </div>
</div>
{% endcapture %}
{% include example.html content=example %}

Cabeçalhos de cards podem ser estilizados usando `.card-header` em elementos `<h*>`.

{% capture example %}
<div class="card">
  <h5 class="card-header">Destaque</h5>
  <div class="card-body">
    <h5 class="card-title">Título especial</h5>
    <p class="card-text">Com suporte a texto embaixo, que funciona como uma introdução a um conteúdo adicional.</p>
    <a href="#" class="btn btn-primary">Visitar</a>
  </div>
</div>
{% endcapture %}
{% include example.html content=example %}

{% capture example %}
<div class="card">
  <div class="card-header">
    Citação
  </div>
  <div class="card-body">
    <blockquote class="blockquote mb-0">
      <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer posuere erat a ante.</p>
      <footer class="blockquote-footer">Alguém famoso em <cite title="Título da fonte">Título da fonte</cite></footer>
    </blockquote>
  </div>
</div>
{% endcapture %}
{% include example.html content=example %}

{% capture example %}
<div class="card text-center">
  <div class="card-header">
    Destaque
  </div>
  <div class="card-body">
    <h5 class="card-title">Título especial</h5>
    <p class="card-text">Com suporte a texto embaixo, que funciona como uma introdução a um conteúdo adicional.</p>
    <a href="#" class="btn btn-primary">Visitar</a>
  </div>
  <div class="card-footer text-muted">
    2 dias atrás
  </div>
</div>
{% endcapture %}
{% include example.html content=example %}

## Tamanhos

Os cards não recebem nenhuma largura inicial específica, então, eles vão ter 100% da largura do pai, se não for declarado. Você pode mudar isso, se necessário, usando CSS personalizado, classes grid, mixins grid Sass ou utilitários.

### Usando a marcação do grid

Usando o grid, envolva cards em colunas e rows, o quanto quiser.

{% capture example %}
<div class="row">
  <div class="col-sm-6">
    <div class="card">
      <div class="card-body">
        <h5 class="card-title">Título especial</h5>
        <p class="card-text">Com suporte a texto embaixo, que funciona como uma introdução a um conteúdo adicional.</p>
        <a href="#" class="btn btn-primary">Visitar</a>
      </div>
    </div>
  </div>
  <div class="col-sm-6">
    <div class="card">
      <div class="card-body">
        <h5 class="card-title">Título especial</h5>
        <p class="card-text">Com suporte a texto embaixo, que funciona como uma introdução a um conteúdo adicional.</p>
        <a href="#" class="btn btn-primary">Visitar</a>
      </div>
    </div>
  </div>
</div>
{% endcapture %}
{% include example.html content=example %}

### Usando utilitários

Use nosso punhado de [utilitários para dimensionamento]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/sizing/) e defina a largura de um card, rapidamente.

{% capture example %}
<div class="card w-75">
  <div class="card-body">
    <h5 class="card-title">Título do card</h5>
    <p class="card-text">Com suporte a texto embaixo, que funciona como uma introdução a um conteúdo adicional.</p>
    <a href="#" class="btn btn-primary">Botão</a>
  </div>
</div>

<div class="card w-50">
  <div class="card-body">
    <h5 class="card-title">Título do card</h5>
    <p class="card-text">Com suporte a texto embaixo, que funciona como uma introdução a um conteúdo adicional.</p>
    <a href="#" class="btn btn-primary">Botão</a>
  </div>
</div>
{% endcapture %}
{% include example.html content=example %}

### Usando CSS personalizado

Use CSS personalizado em suas folhas de estilos ou estilos inline para definir a largura.

{% capture example %}
<div class="card" style="width: 18rem;">
  <div class="card-body">
    <h5 class="card-title">Título especial</h5>
    <p class="card-text">Com suporte a texto embaixo, que funciona como uma introdução a um conteúdo adicional.</p>
    <a href="#" class="btn btn-primary">Visitar</a>
  </div>
</div>
{% endcapture %}
{% include example.html content=example %}

## Alinhamento de texto

Você pode alterar o alinhamento de texto de qualquer card, rapidamente, em seu todo ou partes específicas, com nossas [classes de alinhamento]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/text/#text-alignment).

{% capture example %}
<div class="card" style="width: 18rem;">
  <div class="card-body">
    <h5 class="card-title">Título especial</h5>
    <p class="card-text">Com suporte a texto embaixo, que funciona como uma introdução a um conteúdo adicional.</p>
    <a href="#" class="btn btn-primary">Visitar</a>
  </div>
</div>

<div class="card text-center" style="width: 18rem;">
  <div class="card-body">
    <h5 class="card-title">Título especial</h5>
    <p class="card-text">Com suporte a texto embaixo, que funciona como uma introdução a um conteúdo adicional.</p>
    <a href="#" class="btn btn-primary">Visitar</a>
  </div>
</div>

<div class="card text-right" style="width: 18rem;">
  <div class="card-body">
    <h5 class="card-title">Título especial</h5>
    <p class="card-text">Com suporte a texto embaixo, que funciona como uma introdução a um conteúdo adicional.</p>
    <a href="#" class="btn btn-primary">Visitar</a>
  </div>
</div>
{% endcapture %}
{% include example.html content=example %}

## Navegação

Adicione alguma navegação no cabeçalho do card com os [componentes nav]({{ site.baseurl }}/docs/{{ site.docs_version }}/components/navs/) do Bootstrap.

{% capture example %}
<div class="card text-center">
  <div class="card-header">
    <ul class="nav nav-tabs card-header-tabs">
      <li class="nav-item">
        <a class="nav-link active" href="#">Ativo</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#">Link</a>
      </li>
      <li class="nav-item">
        <a class="nav-link disabled" href="#">Desativado</a>
      </li>
    </ul>
  </div>
  <div class="card-body">
    <h5 class="card-title">Título especial</h5>
    <p class="card-text">Com suporte a texto embaixo, que funciona como uma introdução a um conteúdo adicional.</p>
    <a href="#" class="btn btn-primary">Visitar</a>
  </div>
</div>
{% endcapture %}
{% include example.html content=example %}

{% capture example %}
<div class="card text-center">
  <div class="card-header">
    <ul class="nav nav-pills card-header-pills">
      <li class="nav-item">
        <a class="nav-link active" href="#">Ativo</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#">Link</a>
      </li>
      <li class="nav-item">
        <a class="nav-link disabled" href="#">Desativado</a>
      </li>
    </ul>
  </div>
  <div class="card-body">
    <h5 class="card-title">Título especial</h5>
    <p class="card-text">Com suporte a texto embaixo, que funciona como uma introdução a um conteúdo adicional.</p>
    <a href="#" class="btn btn-primary">Visitar</a>
  </div>
</div>
{% endcapture %}
{% include example.html content=example %}

## Imagens

Cards possuem algumas opções para trabalharmos com imagens. Escolha entre anexar "capas com imagens" no final do card, sobrepor ela com o conteúdo ou, simplesmente, embutir a imagem no card.

### Capas com imagens

Semelhante aos cabeçalhos e rodapés, cards podem ter capas com imagens na parte inferior ou superior.

{% capture example %}
<div class="card mb-3">
  <img class="card-img-top" data-src="holder.js/100px180/" alt="Imagem de capa do card">
  <div class="card-body">
    <h5 class="card-title">Título do card</h5>
    <p class="card-text">Este é um card maior com suporte a texto embaixo, que funciona como uma introdução a um conteúdo adicional. Este conteúdo é um pouco maior, para demonstração.</p>
    <p class="card-text"><small class="text-muted">Atualizados 3 minutos atrás</small></p>
  </div>
</div>
<div class="card">
  <div class="card-body">
    <h5 class="card-title">Título do card</h5>
    <p class="card-text">Este é um card maior com suporte a texto embaixo, que funciona como uma introdução a um conteúdo adicional. Este conteúdo é um pouco maior, para demonstração.</p>
    <p class="card-text"><small class="text-muted">Atualizados 3 minutos atrás</small></p>
  </div>
  <img class="card-img-bottom" data-src="holder.js/100px180/" alt="Imagem de capa do card">
</div>
{% endcapture %}
{% include example.html content=example %}

### Sobreposição de imagens

Transforme uma imagem em background de card, sobrepondo o texto do seu card. Dependendo da imagem, você pode precisar de estilos ou utilitários adicionais.

{% capture example %}
<div class="card bg-dark text-white">
  <img class="card-img" data-src="holder.js/100px270/#55595c:#373a3c/text:Card image" alt="Imagem do card">
  <div class="card-img-overlay">
    <h5 class="card-title">Título do card</h5>
    <p class="card-text">Este é um card maior com suporte a texto embaixo, que funciona como uma introdução a um conteúdo adicional. Este conteúdo é um pouco maior, para demonstração.</p>
    <p class="card-text">Atualizados 3 minutos atrás</p>
  </div>
</div>
{% endcapture %}
{% include example.html content=example %}

## Estilos de card

Cards possuem várias opções para customizar seus backgrounds, bordas e cores.

### Background e cor

Use [utilitários de texto e background]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/colors/) para mudar a aparência do card.

{% capture example %}
{% for color in site.data.theme-colors %}
<div class="card{% unless color.name == "light" %} text-white{% endunless %} bg-{{ color.name }} mb-3" style="max-width: 18rem;">
  <div class="card-header">Cabeçalho</div>
  <div class="card-body">
    <h5 class="card-title">Título de Card {{ color.name | capitalize }}</h5>
    <p class="card-text">Um exemplo de texto rápido para construir o título do card e fazer preencher o conteúdo do card.</p>
  </div>
</div>{% endfor %}
{% endcapture %}
{% include example.html content=example %}

{% include callout-warning-color-assistive-technologies.md %}

### Bordas

Use [utilitários de bordas]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/borders/) para mudar só a cor das bordas de um card. Perceba que você pode usar as classes `.text-{color}` no `.card` pai ou um subconjunto de cards, como mostrado abaixo.

{% capture example %}
{% for color in site.data.theme-colors %}
<div class="card border-{{ color.name }} mb-3" style="max-width: 18rem;">
  <div class="card-header">Cabeçalho</div>
  <div class="card-body{% unless color.name == "light" %} text-{{ color.name }}{% endunless %}">
    <h5 class="card-title">Título de Card {{ color.name | capitalize }}</h5>
    <p class="card-text">Um exemplo de texto rápido para construir o título do card e fazer preencher o conteúdo do card.</p>
  </div>
</div>{% endfor %}
{% endcapture %}
{% include example.html content=example %}

### Utilitários mixins

Você também pode mudar as bordas no cabeçalho e rodapé do card, como quiser. Ainda pior: pode remover suas `background-color` com `.bg-transparent`.

{% capture example %}
<div class="card border-success mb-3" style="max-width: 18rem;">
  <div class="card-header bg-transparent border-success">Cabeçalho</div>
  <div class="card-body text-success">
    <h5 class="card-title">Título de Card Success</h5>
    <p class="card-text">Um exemplo de texto rápido para construir o título do card e fazer preencher o conteúdo do card.</p>
  </div>
  <div class="card-footer bg-transparent border-success">Rodapé</div>
</div>
{% endcapture %}
{% include example.html content=example %}

## Layout do card

Além da estilização do conteúdo dentro dos cards, Bootstrap possui algumas opções para a criação de vários cards. No momento, **estas opções de layout ainda não são responsivas**.

### Grupo de cards

Use grupo de cards para renderizá-los como um único elemento anexado com largura e altura igual. Grupo de cards usam `display: flex;` para conseguir seus tamanhos adequados.

{% capture example %}
<div class="card-group">
  <div class="card">
    <img class="card-img-top" data-src="holder.js/100px180/" alt="Imagem de capa do card">
    <div class="card-body">
      <h5 class="card-title">Título do card</h5>
      <p class="card-text">Este é um card maior com suporte a texto embaixo, que funciona como uma introdução a um conteúdo adicional. Este conteúdo é um pouco maior, para demonstração.</p>
      <p class="card-text"><small class="text-muted">Atualizados 3 minutos atrás</small></p>
    </div>
  </div>
  <div class="card">
    <img class="card-img-top" data-src="holder.js/100px180/" alt="Imagem de capa do card">
    <div class="card-body">
      <h5 class="card-title">Título do card</h5>
      <p class="card-text">Este é um card com suporte a texto embaixo, que funciona como uma introdução a um conteúdo adicional.</p>
      <p class="card-text"><small class="text-muted">Atualizados 3 minutos atrás</small></p>
    </div>
  </div>
  <div class="card">
    <img class="card-img-top" data-src="holder.js/100px180/" alt="Imagem de capa do card">
    <div class="card-body">
      <h5 class="card-title">Título do card</h5>
      <p class="card-text">Este é um card maior com suporte a texto embaixo, que funciona como uma introdução a um conteúdo adicional. Este card tem o conteúdo ainda maior que o primeiro, para mostrar a altura igual, em ação.</p>
      <p class="card-text"><small class="text-muted">Atualizados 3 minutos atrás</small></p>
    </div>
  </div>
</div>
{% endcapture %}
{% include example.html content=example %}

Quando usar grupo de cards com rodapé, seus conteúdos vão se alinhar automaticamente.

{% capture example %}
<div class="card-group">
  <div class="card">
    <img class="card-img-top" data-src="holder.js/100px180/" alt="Imagem de capa do card">
    <div class="card-body">
      <h5 class="card-title">Título do card</h5>
      <p class="card-text">Este é um card maior com suporte a texto embaixo, que funciona como uma introdução a um conteúdo adicional. Este conteúdo é um pouco maior, para demonstração.</p>
    </div>
    <div class="card-footer">
      <small class="text-muted">Atualizados 3 minutos atrás</small>
    </div>
  </div>
  <div class="card">
    <img class="card-img-top" data-src="holder.js/100px180/" alt="Imagem de capa do card">
    <div class="card-body">
      <h5 class="card-title">Título do card</h5>
      <p class="card-text">Este é um card com suporte a texto embaixo, que funciona como uma introdução a um conteúdo adicional.</p>
    </div>
    <div class="card-footer">
      <small class="text-muted">Atualizados 3 minutos atrás</small>
    </div>
  </div>
  <div class="card">
    <img class="card-img-top" data-src="holder.js/100px180/" alt="Imagem de capa do card">
    <div class="card-body">
      <h5 class="card-title">Título do card</h5>
      <p class="card-text">Este é um card maior com suporte a texto embaixo, que funciona como uma introdução a um conteúdo adicional. Este card tem o conteúdo ainda maior que o primeiro, para mostrar a altura igual, em ação.</p>
    </div>
    <div class="card-footer">
      <small class="text-muted">Atualizados 3 minutos atrás</small>
    </div>
  </div>
</div>
{% endcapture %}
{% include example.html content=example %}

### Card decks

Precisa de um conjunto de cards com larguras e alturas iguais, mas sem que estejam interligados? Use os card decks.

{% capture example %}
<div class="card-deck">
  <div class="card">
    <img class="card-img-top" data-src="holder.js/100px200/" alt="Imagem de capa do card">
    <div class="card-body">
      <h5 class="card-title">Título do card</h5>
      <p class="card-text">Este é um card mais longo com suporte a texto embaixo, que funciona como uma introdução a um conteúdo adicional. Este conteúdo é um pouco maior.</p>
      <p class="card-text"><small class="text-muted">Atualizados 3 minutos atrás</small></p>
    </div>
  </div>
  <div class="card">
    <img class="card-img-top" data-src="holder.js/100px200/" alt="Imagem de capa do card">
    <div class="card-body">
      <h5 class="card-title">Título do card</h5>
      <p class="card-text">Este é um card com suporte a texto embaixo, que funciona como uma introdução a um conteúdo adicional.</p>
      <p class="card-text"><small class="text-muted">Atualizados 3 minutos atrás</small></p>
    </div>
  </div>
  <div class="card">
    <img class="card-img-top" data-src="holder.js/100px200/" alt="Imagem de capa do card">
    <div class="card-body">
      <h5 class="card-title">Título do card</h5>
      <p class="card-text">Este é um card maior com suporte a texto embaixo, que funciona como uma introdução a um conteúdo adicional. Este card tem o conteúdo ainda maior que o primeiro, para mostrar a altura igual, em ação.</p>
      <p class="card-text"><small class="text-muted">Atualizados 3 minutos atrás</small></p>
    </div>
  </div>
</div>
{% endcapture %}
{% include example.html content=example %}

Assim como os grupos de cards, rodapés de cards nos decks vão se alinhar, automaticamente.

{% capture example %}
<div class="card-deck">
  <div class="card">
    <img class="card-img-top" data-src="holder.js/100px180/" alt="Imagem de capa do card">
    <div class="card-body">
      <h5 class="card-title">Título do card</h5>
      <p class="card-text">Este é um card maior com suporte a texto embaixo, que funciona como uma introdução a um conteúdo adicional. Este conteúdo é um pouco maior, para demonstração.</p>
    </div>
    <div class="card-footer">
      <small class="text-muted">Atualizados 3 minutos atrás</small>
    </div>
  </div>
  <div class="card">
    <img class="card-img-top" data-src="holder.js/100px180/" alt="Imagem de capa do card">
    <div class="card-body">
      <h5 class="card-title">Título do card</h5>
      <p class="card-text">Este é um card com suporte a texto embaixo, que funciona como uma introdução a um conteúdo adicional.</p>
    </div>
    <div class="card-footer">
      <small class="text-muted">Atualizados 3 minutos atrás</small>
    </div>
  </div>
  <div class="card">
    <img class="card-img-top" data-src="holder.js/100px180/" alt="Imagem de capa do card">
    <div class="card-body">
      <h5 class="card-title">Título do card</h5>
      <p class="card-text">Este é um card maior com suporte a texto embaixo, que funciona como uma introdução a um conteúdo adicional. Este card tem o conteúdo ainda maior que o primeiro, para mostrar a altura igual, em ação.</p>
    </div>
    <div class="card-footer">
      <small class="text-muted">Atualizados 3 minutos atrás</small>
    </div>
  </div>
</div>
{% endcapture %}
{% include example.html content=example %}

### Colunas de cards

Cards podem ser organizados de uma maneira parecida com as colunas [Masonry](https://masonry.desandro.com/), apenas com CSS e envoltos em uma `.card-column`. Eles são feitos com propriedades CSS `column`, invés de flexbox, para fácil alinhamento. Além do mais, são orientados de cima para baixo, da esquerda para direita.

**Atenção!** Sua experiência com colunas de cards pode variar. Para evitar cards bugando nas colunas, devemos defini-los como `display: inline-block`, já que `column-break-inside: avoid` ainda não é uma solução infalível.

{% capture example %}
<div class="card-columns">
  <div class="card">
    <img class="card-img-top" data-src="holder.js/100px160/" alt="Imagem de capa do card">
    <div class="card-body">
      <h5 class="card-title">Título do card que quebra em uma nova linha</h5>
      <p class="card-text">Este é um card mais longo com suporte a texto embaixo, que funciona como uma introdução a um conteúdo adicional. Este conteúdo é um pouco maior.</p>
    </div>
  </div>
  <div class="card p-3">
    <blockquote class="blockquote mb-0 card-body">
      <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer posuere erat a ante.</p>
      <footer class="blockquote-footer">
        <small class="text-muted">
          Alguém famoso em <cite title="Título da fonte">Título da fonte</cite>
        </small>
      </footer>
    </blockquote>
  </div>
  <div class="card">
    <img class="card-img-top" data-src="holder.js/100px160/" alt="Imagem de capa do card">
    <div class="card-body">
      <h5 class="card-title">Título do card</h5>
      <p class="card-text">Este é um card com suporte a texto embaixo, que funciona como uma introdução a um conteúdo adicional.</p>
      <p class="card-text"><small class="text-muted">Atualizados 3 minutos atrás</small></p>
    </div>
  </div>
  <div class="card bg-primary text-white text-center p-3">
    <blockquote class="blockquote mb-0">
      <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer posuere erat.</p>
      <footer class="blockquote-footer">
        <small>
          Alguém famoso em <cite title="Título da fonte">Título da fonte</cite>
        </small>
      </footer>
    </blockquote>
  </div>
  <div class="card text-center">
    <div class="card-body">
      <h5 class="card-title">Título do card</h5>
      <p class="card-text">Este é um card com suporte a texto embaixo, que funciona como uma introdução a um conteúdo adicional.</p>
      <p class="card-text"><small class="text-muted">Atualizados 3 minutos atrás</small></p>
    </div>
  </div>
  <div class="card">
    <img class="card-img" data-src="holder.js/100px260/" alt="Imagem do card">
  </div>
  <div class="card p-3 text-right">
    <blockquote class="blockquote mb-0">
      <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer posuere erat a ante.</p>
      <footer class="blockquote-footer">
        <small class="text-muted">
          Alguém famoso em <cite title="Título da fonte">Título da fonte</cite>
        </small>
      </footer>
    </blockquote>
  </div>
  <div class="card">
    <div class="card-body">
      <h5 class="card-title">Título do card</h5>
      <p class="card-text">Este é um card maior com suporte a texto embaixo, que funciona como uma introdução a um conteúdo adicional. Este card tem o conteúdo ainda maior que o primeiro, para mostrar a altura igual, em ação.</p>
      <p class="card-text"><small class="text-muted">Atualizados 3 minutos atrás</small></p>
    </div>
  </div>
</div>
{% endcapture %}
{% include example.html content=example %}

Colunas de cards também podem ser extendidas e customizadas com algum código personalizado. Abaixo, vemos uma extensão da classe `.card-columns` usando o mesmo CSS que usamos para gerar uma graduação responsiva de alteração do número de colunas.

{% highlight scss %}
.card-columns {
  @include media-breakpoint-only(lg) {
    column-count: 4;
  }
  @include media-breakpoint-only(xl) {
    column-count: 5;
  }
}
{% endhighlight %}

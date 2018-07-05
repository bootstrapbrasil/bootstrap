---
layout: docs
title: Objeto de mídia
description: Documentação e exemplos para o objeto de mídia Bootstrap, construído para componentes repetitivos como comentários de blog, tweets, etc.
group: layout
toc: true
---

## Exemplo

O [objeto de mídia](http://www.stubbornella.org/content/2010/06/25/the-media-object-saves-hundreds-of-lines-of-code/) ajuda construir componentes complexos e repetitivos, onde alguma mídia é posicionada ao lado do conteúdo. Além do mais, isso é possível só com duas classes, graças ao flexbox.

Abaixo, temos um exemplo de um objeto de mídia. Apenas duas classes são necessárias (o elemento pai `.media` e o corpo `.media-body`), em volta de seus conteúdos. Margem e padding adicionais podem ser usados com [utilitários de espaçamento]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/spacing/).

{% capture example %}
<div class="media">
  <img class="mr-3" data-src="holder.js/64x64" alt="Imagem de exemplo genérica">
  <div class="media-body">
    <h5 class="mt-0">Cabeçalho da mídia</h5>
    Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio, vestibulum in vulputate at, tempus viverra turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia congue felis in faucibus.
  </div>
</div>
{% endcapture %}
{% include example.html content=example %}

{% capture callout %}
##### Flexbug #12: Elementos inline não são tratados como flex items

Internet Explorer 10-11 não renderiza elementos inline, como links ou imagens (ou pseudo-elementos `::before` e `::after`), como flex items. A única solução é definir um valor não-inline `display` (`block`, `inline-block` ou `flex`). Nós sugerimos usar `.d-flex`, um de nossos [utilitários display]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/display/), como uma solução fácil.

**Fonte:** [Flexbugs no GitHub](https://github.com/philipwalton/flexbugs#flexbug-12)
{% endcapture %}
{% include callout.html content=callout type="warning" %}

## Aninhamento

Objetos de mídia podem ser aninhados infinitamente, apesar de sugerirmos que você pare, em algum ponto. Coloque `.media` aninhado dentro do `.media-body` de um objeto mídia pai aninhado.

{% capture example %}
<div class="media">
  <img class="mr-3" data-src="holder.js/64x64" alt="Imagem de exemplo genérica">
  <div class="media-body">
    <h5 class="mt-0">Cabeçalho da mídia</h5>
    Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio, vestibulum in vulputate at, tempus viverra turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia congue felis in faucibus.

    <div class="media mt-3">
      <a class="pr-3" href="#">
        <img data-src="holder.js/64x64" alt="Imagem de exemplo genérica">
      </a>
      <div class="media-body">
        <h5 class="mt-0">Cabeçalho da mídia</h5>
        Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio, vestibulum in vulputate at, tempus viverra turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia congue felis in faucibus.
      </div>
    </div>
  </div>
</div>
{% endcapture %}
{% include example.html content=example %}

## Alinhamento

A mídia, em um objeto de mídia, pode ser alinhada com utilitários flexbox na parte superior, meio ou fim do conteúdo do `.media-body`.

{% capture example %}
<div class="media">
  <img class="align-self-start mr-3" data-src="holder.js/64x64" alt="Imagem de exemplo genérica">
  <div class="media-body">
    <h5 class="mt-0">Mídia alinhada ao topo</h5>
    <p>Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio, vestibulum in vulputate at, tempus viverra turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia congue felis in faucibus.</p>
    <p>Donec sed odio dui. Nullam quis risus eget urna mollis ornare vel eu leo. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus.</p>
  </div>
</div>
{% endcapture %}
{% include example.html content=example %}

{% capture example %}
<div class="media">
  <img class="align-self-center mr-3" data-src="holder.js/64x64" alt="Imagem de exemplo genérica">
  <div class="media-body">
    <h5 class="mt-0">Mídia centralizada</h5>
    <p>Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio, vestibulum in vulputate at, tempus viverra turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia congue felis in faucibus.</p>
    <p class="mb-0">Donec sed odio dui. Nullam quis risus eget urna mollis ornare vel eu leo. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus.</p>
  </div>
</div>
{% endcapture %}
{% include example.html content=example %}

{% capture example %}
<div class="media">
  <img class="align-self-end mr-3" data-src="holder.js/64x64" alt="Imagem de exemplo genérica">
  <div class="media-body">
    <h5 class="mt-0">Mídia alinhada na parte inferior</h5>
    <p>Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio, vestibulum in vulputate at, tempus viverra turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia congue felis in faucibus.</p>
    <p class="mb-0">Donec sed odio dui. Nullam quis risus eget urna mollis ornare vel eu leo. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus.</p>
  </div>
</div>
{% endcapture %}
{% include example.html content=example %}

## Ordem

Altere a ordem do conteúdo, em objetos de mídia, modificando o próprio HTML ou usando algum CSS flexbox customizado para definir o valor da propriedade `order` em um número inteiro de sua escolha.

{% capture example %}
<div class="media">
  <div class="media-body">
    <h5 class="mt-0 mb-1">Objeto mídia</h5>
    Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio, vestibulum in vulputate at, tempus viverra turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia congue felis in faucibus.
  </div>
  <img class="ml-3" data-src="holder.js/64x64" alt="Imagem de exemplo genérica">
</div>
{% endcapture %}
{% include example.html content=example %}

## Lista de mídia

Devido as poucas exigências do objeto de mídia, você também pode usar estas classes em elementos HTML de lista. Em seu `<ul>` ou `<ol>`, use a classe `.list-unstyled` para remover qualquer estilo de lista padrão e, então, aplique `.media` no seu `<li>`. Como sempre: use utilitários de espaçamento, onde quer que precise.

{% capture example %}
<ul class="list-unstyled">
  <li class="media">
    <img class="mr-3" data-src="holder.js/64x64" alt="Imagem de exemplo genérica">
    <div class="media-body">
      <h5 class="mt-0 mb-1">Objeto de mídia baseado em lista</h5>
      Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio, vestibulum in vulputate at, tempus viverra turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia congue felis in faucibus.
    </div>
  </li>
  <li class="media my-4">
    <img class="mr-3" data-src="holder.js/64x64" alt="Imagem de exemplo genérica">
    <div class="media-body">
      <h5 class="mt-0 mb-1">Objeto de mídia baseado em lista</h5>
      Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio, vestibulum in vulputate at, tempus viverra turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia congue felis in faucibus.
    </div>
  </li>
  <li class="media">
    <img class="mr-3" data-src="holder.js/64x64" alt="Imagem de exemplo genérica">
    <div class="media-body">
      <h5 class="mt-0 mb-1">Objeto de mídia baseado em lista</h5>
      Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio, vestibulum in vulputate at, tempus viverra turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia congue felis in faucibus.
    </div>
  </li>
</ul>
{% endcapture %}
{% include example.html content=example %}

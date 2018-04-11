---
layout: docs
title: Imagens
description: Documentação e exemplos para tornar imagens responsivas (nunca crescem mais que os elementos pais) e adicionar estilos leves a elas, através de classes.
group: content
toc: true
---

## Imagens responsivas

Imagens no Bootstrap são feitas responsivas com a classe `.img-fluid`. As declarações `max-width: 100%;` e `height: auto;` são aplicadas a imagem, de modo que ela escale junto ao elemento pai.

<div class="bd-example">
  <img data-src="holder.js/100px250" class="img-fluid" alt="Imagem responsiva genérica">
</div>

{% highlight html %}
<img src="..." class="img-fluid" alt="Imagem responsiva">
{% endhighlight %}

{% callout warning %}
##### Imagens SVG e o IE10

No Internet Explorer 10, imagens SVG com `.img-fluid` são dimensionadas desproporcionalmente. Para consertar isso, adicione `width: 100% \9;` quando necessário. Isso conserta dimensões impróprias para outros formatos de imagens, então, o Bootstrap não aplica isso automaticamente.

## Thumbnails

Além de nossos [utilitários border-radius]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/borders/), você pode usar `.img-thumbnail` para dar uma borda arredondada de 1px a uma imagem.

<div class="bd-example bd-example-images">
  <img data-src="holder.js/200x200" class="img-thumbnail" alt="Uma imagem de um quadrado genérico com uma borda branca ao redor, fazendo ela parecer uma fotografia tirada com uma polaroide antiga.">
</div>

{% highlight html %}
<img src="..." alt="..." class="img-thumbnail">
{% endhighlight %}

## Alinhando imagens

Alinhe imagens com as [classes utilitárias de float]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/float) ou [classes para alinhamento de texto]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/text/#text-alignment). Imagens de `block`-level podem ser centralizadas usando a [classe utilitária de margem `.mx-auto`]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/spacing/#horizontal-centering).

<div class="bd-example bd-example-images">
  <img data-src="holder.js/200x200" class="rounded float-left" alt="Uma imagem genérica de um quadrado com cantos arredondados.">
  <img data-src="holder.js/200x200" class="rounded float-right" alt="Uma imagem genérica de um quadrado com cantos arredondados.">
</div>

{% highlight html %}
<img src="..." class="rounded float-left" alt="...">
<img src="..." class="rounded float-right" alt="...">
{% endhighlight %}

<div class="bd-example bd-example-images">
  <img data-src="holder.js/200x200" class="rounded mx-auto d-block" alt="Uma imagem genérica de um quadrado com cantos arredondados.">
</div>

{% highlight html %}
<img src="..." class="rounded mx-auto d-block" alt="...">
{% endhighlight %}

<div class="bd-example bd-example-images">
  <div class="text-center">
    <img data-src="holder.js/200x200" class="rounded" alt="Uma imagem genérica de um quadrado com cantos arredondados.">
  </div>
</div>

{% highlight html %}
<div class="text-center">
  <img src="..." class="rounded" alt="...">
</div>
{% endhighlight %}


## Elemento <picture>

Se você está usando o elemento `<picture>` para especificar várias fontes (`<source>`) para uma imagem específica, se assegure de adicionar as classes `.img-` para as `<img>` e não para as tags `<picture>`.

{% highlight html %}
​<picture>
  <source srcset="..." type="image/svg+xml">
  <img src="..." class="img-fluid img-thumbnail" alt="...">
</picture>
{% endhighlight %}

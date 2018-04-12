---
layout: docs
title: Bordas
description: Use os utilitários de borda para estilizar rapidamente a borda e o raio da borda de um elemento. Ótimo para imagens, botões ou qualquer outro elemento.
group: utilities
redirect_from: "/docs/4.1/utilities/"
toc: true
---

## Borda

Use os utilitários de borda para adicionar ou remover as bordas de um elemento. Escolha entre um dos lados ou todos de uma vez.

### Adicione

<div class="bd-example-border-utils">
{% capture example %}
<span class="border"></span>
<span class="border-top"></span>
<span class="border-right"></span>
<span class="border-bottom"></span>
<span class="border-left"></span>
{% endcapture %}
{% include example.html content=example %}
</div>

### Remova

<div class="bd-example-border-utils bd-example-border-utils-0">
{% capture example %}
<span class="border-0"></span>
<span class="border-top-0"></span>
<span class="border-right-0"></span>
<span class="border-bottom-0"></span>
<span class="border-left-0"></span>
{% endcapture %}
{% include example.html content=example %}
</div>

## Cor da borda

Altere a cor da borda usando utilitários criados a partir das nossas cores de tema.

<div class="bd-example-border-utils">
{% capture example %}
{% for color in site.data.theme-colors %}
<span class="border border-{{ color.name }}"></span>{% endfor %}
<span class="border border-white"></span>
{% endcapture %}
{% include example.html content=example %}
</div>

## Raio da borda

Adicione classes a um elemento para arredondar facilmente seus cantos.

<div class="bd-example bd-example-images">
  <img data-src="holder.js/75x75" class="rounded" alt="Example rounded image">
  <img data-src="holder.js/75x75" class="rounded-top" alt="Example top rounded image">
  <img data-src="holder.js/75x75" class="rounded-right" alt="Example right rounded image">
  <img data-src="holder.js/75x75" class="rounded-bottom" alt="Example bottom rounded image">
  <img data-src="holder.js/75x75" class="rounded-left" alt="Example left rounded image">
  <img data-src="holder.js/75x75" class="rounded-circle" alt="Completely round image">
  <img data-src="holder.js/75x75" class="rounded-0" alt="Example non-rounded image (overrides rounding applied elsewhere)">
</div>

{% highlight html %}
<img src="..." alt="..." class="rounded">
<img src="..." alt="..." class="rounded-top">
<img src="..." alt="..." class="rounded-right">
<img src="..." alt="..." class="rounded-bottom">
<img src="..." alt="..." class="rounded-left">
<img src="..." alt="..." class="rounded-circle">
<img src="..." alt="..." class="rounded-0">
{% endhighlight %}

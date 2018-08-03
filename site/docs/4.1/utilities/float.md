---
layout: docs
title: Float
description: Utilize float em qualquer elemento, em quaquer breakpoint, usando nossos utilitários responsivos.
group: utilities
toc: true
---

## Sobre

Estas classes utilitárias flutuam um elemento à esquerda e direita ou desativa a flutuação, baseando-se no tamanho da atual viewport e usando a [propriedade CSS `float`](https://developer.mozilla.org/en-US/docs/Web/CSS/float). Além do mais, a *flag* `!important` é utilizada para evitar problemas de especificidade. 

Também, não esqueça que essas classes usam os mesmos breakpoints que nosso sistema de grid e que não afetam flex items.

## Classes

Alterne entre flutuação ou não, usando as seguintes classes:

{% capture example %}
<div class="float-left">Flutua à esquerda em todos os tamanhos de viewport.</div><br>
<div class="float-right">Flutua à direita em todos os tamanhos de viewport.</div><br>
<div class="float-none">Nunca flutua, independente do tamanho da viewport.</div>
{% endcapture %}
{% include example.html content=example %}

## Mixins

Também é possível utilizar os mixins Sass:

{% highlight scss %}
.elemento {
  @include float-left;
}
.outro-elemento {
  @include float-right;
}
.mais-outro {
  @include float-none;
}
{% endhighlight %}

## Responsividade

Cada valor da propriedade `float` possui variantes responsivas:

{% capture example %}
<div class="float-sm-left">Flutua à esquerda, em viewports de tamanho SM (pequena) ou maior.</div><br>
<div class="float-md-left">Flutua à esquerda, em viewports de tamanho MD (média) ou maior.</div><br>
<div class="float-lg-left">Flutua à esquerda, em viewports de tamanho LG (grande) ou maior.</div><br>
<div class="float-xl-left">Flutua à esquerda, em viewports de tamanho XL (extra-grande) ou maior.</div><br>
{% endcapture %}
{% include example.html content=example %}

Aqui, estão todas as classes suportadas:

{% for bp in site.data.breakpoints %}
- `.float{{ bp.abbr }}-left`
- `.float{{ bp.abbr }}-right`
- `.float{{ bp.abbr }}-none`{% endfor %}

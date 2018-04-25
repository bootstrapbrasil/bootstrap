---
layout: docs
title: Visão Geral
description: Componentes e opções para o layout do seu projeto Bootstrap, incluindo wrapping containers, um poderoso sistema de grid, um objeto de mídia flexível e classes responsivas.
group: layout
redirect_from: "/docs/4.1/layout/"
toc: true
---

## Containers

Containers são os elementos de layout mais básico do Bootstrap e são **necessários quando usamos o sistema de grid padrão**. Escolha entre um container responsivo de largura fixa (ou seja, com alterações de `max-width` em cada ponto de interrupção) ou por um responsivo de largura fluida (ou seja, `100%` de largura o tempo todo).


Embora os containers possam ser aninhados, a maioria dos layouts não exige um container aninhado.

<div class="bd-example">
  <div class="bd-example-container">
    <div class="bd-example-container-header"></div>
    <div class="bd-example-container-sidebar"></div>
    <div class="bd-example-container-body"></div>
  </div>
</div>

{% highlight html %}
<div class="container">
  <!-- Content here -->
</div>
{% endhighlight %}

Use `.container-fluid` para um container com de largura total, abrangindo toda a largura da sua área de visualização.

<div class="bd-example">
  <div class="bd-example-container bd-example-container-fluid">
    <div class="bd-example-container-header"></div>
    <div class="bd-example-container-sidebar"></div>
    <div class="bd-example-container-body"></div>
  </div>
</div>

{% highlight html %}
<div class="container-fluid">
  ...
</div>
{% endhighlight %}


## Pontos de parada reponsivos

Como o bootstrap é desenvolvido para ser "mobile first" usamos varias [media queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries) para criar sensíveis pontos de parada para nossos layouts e interfaces. Esses pontos são baseadas em larguras de área de visualização miníma e nos permitem dimensionar conforme muda o tamanho da área de visualização.

Bootstrap usa principalmente os seguintes intervalos de media queries, ou pontos de paradas, em nossos arquivos de origem do SASS para os layouts, sistemas de grid e componentes.

{% highlight scss %}
// Extra small devices (portrait phones, less than 576px)
// No media query since this is the default in Bootstrap

// Small devices (landscape phones, 576px and up)
@media (min-width: 576px) { ... }

// Medium devices (tablets, 768px and up)
@media (min-width: 768px) { ... }

// Large devices (desktops, 992px and up)
@media (min-width: 992px) { ... }

// Extra large devices (large desktops, 1200px and up)
@media (min-width: 1200px) { ... }
{% endhighlight %}

Como escrevemos nosso CSS de origem no Sass, todas as nossas consultas de mídia estão disponíveis via mixins do Sass:

{% highlight scss %}
@include media-breakpoint-up(xs) { ... }
@include media-breakpoint-up(sm) { ... }
@include media-breakpoint-up(md) { ... }
@include media-breakpoint-up(lg) { ... }
@include media-breakpoint-up(xl) { ... }

// Example usage:
@include media-breakpoint-up(sm) {
  .some-class {
    display: block;
  }
}
{% endhighlight %}

Ocasionalmente, usamos media queries que seguem na outra direção (no tamanho da tela fornecida *ou menor*):

{% highlight scss %}
// Extra small devices (portrait phones, less than 576px)
@media (max-width: 575.98px) { ... }

// Small devices (landscape phones, less than 768px)
@media (max-width: 767.98px) { ... }

// Medium devices (tablets, less than 992px)
@media (max-width: 991.98px) { ... }

// Large devices (desktops, less than 1200px)
@media (max-width: 1199.98px) { ... }

// Extra large devices (large desktops)
// No media query since the extra-large breakpoint has no upper bound on its width
{% endhighlight %}

{% include callout-info-mediaqueries-breakpoints.md %}

Mais uma vez, essas media queries também estão disponíveis via mixins Sass:

{% highlight scss %}
@include media-breakpoint-down(xs) { ... }
@include media-breakpoint-down(sm) { ... }
@include media-breakpoint-down(md) { ... }
@include media-breakpoint-down(lg) { ... }
{% endhighlight %}

Há também media queries e mixins para selecionar um único segmento com o tamanho da tela separado pelo tamanho minímo e tamanho máximo.

{% highlight scss %}
// Extra small devices (portrait phones, less than 576px)
@media (max-width: 575.98px) { ... }

// Small devices (landscape phones, 576px and up)
@media (min-width: 576px) and (max-width: 767.98px) { ... }

// Medium devices (tablets, 768px and up)
@media (min-width: 768px) and (max-width: 991.98px) { ... }

// Large devices (desktops, 992px and up)
@media (min-width: 992px) and (max-width: 1199.98px) { ... }

// Extra large devices (large desktops, 1200px and up)
@media (min-width: 1200px) { ... }
{% endhighlight %}

Essas media queries também estão disponíveis via Sass mixins: 

{% highlight scss %}
@include media-breakpoint-only(xs) { ... }
@include media-breakpoint-only(sm) { ... }
@include media-breakpoint-only(md) { ... }
@include media-breakpoint-only(lg) { ... }
@include media-breakpoint-only(xl) { ... }
{% endhighlight %}

Da mesma forma, as media querias podem abranger várias larguras de pontos de parada.

{% highlight scss %}
// Example
// Apply styles starting from medium devices and up to extra large devices
@media (min-width: 768px) and (max-width: 1199.98px) { ... }
{% endhighlight %}

O Sass mixin para selecionar o mesmo tamanho de tela seria:

{% highlight scss %}
@include media-breakpoint-between(md, xl) { ... }
{% endhighlight %}

## Z-index

Several Bootstrap components utilize `z-index`, the CSS property that helps control layout by providing a third axis to arrange content. We utilize a default z-index scale in Bootstrap that's been designed to properly layer navigation, tooltips and popovers, modals, and more.

These higher values start at an arbitrary number, high and specific enough to ideally avoid conflicts. We need a standard set of these across our layered components—tooltips, popovers, navbars, dropdowns, modals—so we can be reasonably consistent in the behaviors. There's no reason we couldn't have used `100`+ or `500`+.

We don't encourage customization of these individual values; should you change one, you likely need to change them all.

{% highlight scss %}
$zindex-dropdown:          1000 !default;
$zindex-sticky:            1020 !default;
$zindex-fixed:             1030 !default;
$zindex-modal-backdrop:    1040 !default;
$zindex-modal:             1050 !default;
$zindex-popover:           1060 !default;
$zindex-tooltip:           1070 !default;
{% endhighlight %}

To handle overlapping borders within components (e.g., buttons and inputs in input groups), we use low single digit `z-index` values of `1`, `2`, and `3` for default, hover, and active states. On hover/focus/active, we bring a particular element to the forefront with a higher `z-index` value to show their border over the sibling elements.

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
  <!-- Conteúdo aqui -->
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


## Breakpoints reponsivos

Como o bootstrap é desenvolvido para ser "mobile first" usamos varias [media queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries) para criar sensíveis breakpoints para nossos layouts e interfaces. Esses pontos são baseadas em larguras de área de visualização miníma e nos permitem dimensionar conforme muda o tamanho da área de visualização.

Bootstrap usa principalmente os seguintes intervalos de media queries, ou breakpoints, em nossos arquivos de origem do SASS para os layouts, sistemas de grid e componentes.

{% highlight scss %}
// Dispositivos extra small (telefones em modo retrato, com menos de 576px)
// Sem media query para `xs`, já que este é o padrão, no Bootstrap.

// Dispositivos small (telefones em modo paisagem, com 576px ou mais)
@media (min-width: 576px) { ... }

// Dispositivos médios (tablets com 768px ou mais)
@media (min-width: 768px) { ... }

// Dispositivos large (desktops com 992px ou mais)
@media (min-width: 992px) { ... }

// Dispositivos extra large (desktops grandes com 1200px ou mais)
@media (min-width: 1200px) { ... }
{% endhighlight %}

Como escrevemos nosso CSS fonte no Sass, todas as nossas consultas de mídia estão disponíveis via mixins do Sass:

{% highlight scss %}
// No media query necessary for xs breakpoint as it's effectively `@media (min-width: 0) { ... }`
@include media-breakpoint-up(sm) { ... }
@include media-breakpoint-up(md) { ... }
@include media-breakpoint-up(lg) { ... }
@include media-breakpoint-up(xl) { ... }

// Exemplo: Começe ocultando em  `min-width: 0`, e então mostre em no breakpoint `sm`
.custom-class {
  display: none;
}
@include media-breakpoint-up(sm) {
  .custom-class {
    display: block;
  }
}
{% endhighlight %}

Ocasionalmente, usamos media queries que seguem na outra direção (no tamanho da tela fornecida *ou menor*):

{% highlight scss %}
// Dispositivos extra small (telefones em modo retrato, com menos de 576px)
@media (max-width: 575.98px) { ... }

// Dispositivos small (telefones em modo paisagem, com menos de 768px)
@media (max-width: 767.98px) { ... }

// Dispositivos médios (tablets com menos de 992px)
@media (max-width: 991.98px) { ... }

// Dispositivos large (desktops com menos de 1200px)
@media (max-width: 1199.98px) { ... }

// Dispositivos extra large (desktops grandes)
// Nenhuma media query, já que o breakpoint extra large não possui nenhum limite acima.
{% endhighlight %}

{% include callout-info-mediaqueries-breakpoints.md %}

Mais uma vez, essas media queries também estão disponíveis via mixins Sass:

{% highlight scss %}
@include media-breakpoint-down(xs) { ... }
@include media-breakpoint-down(sm) { ... }
@include media-breakpoint-down(md) { ... }
@include media-breakpoint-down(lg) { ... }
// No media query necessary for xl breakpoint as it has no upper bound on its width

// Example: Style from medium breakpoint and down
@include media-breakpoint-down(md) {
  .custom-class {
    display: block;
  }
}
{% endhighlight %}

Há também media queries e mixins para selecionar um único segmento com o tamanho da tela separado pelo tamanho minímo e tamanho máximo.

{% highlight scss %}
// Dispositivos extra small (telefones em modo retrato, com menos de 576px)
@media (max-width: 575.98px) { ... }

// Dispositivos small (telefones em modo paisagem, com 576px ou mais)
@media (min-width: 576px) and (max-width: 767.98px) { ... }

// Dispositivos médios (tablets com 768px ou mais)
@media (min-width: 768px) and (max-width: 991.98px) { ... }

// Dispositivos large (desktops com 992px ou mais)
@media (min-width: 992px) and (max-width: 1199.98px) { ... }

// Dispositivos extra large (desktops grandes com 1200px ou mais)
@media (min-width: 1200px) { ... }
{% endhighlight %}

Essas media queries também estão disponíveis via mixins Sass: 

{% highlight scss %}
@include media-breakpoint-only(xs) { ... }
@include media-breakpoint-only(sm) { ... }
@include media-breakpoint-only(md) { ... }
@include media-breakpoint-only(lg) { ... }
@include media-breakpoint-only(xl) { ... }
{% endhighlight %}

Da mesma forma, as media querias podem abranger várias larguras de breakpoints.

{% highlight scss %}
// Exemplo
// Aplica estilos, começando de dispositivos médios até os extra larges
@media (min-width: 768px) and (max-width: 1199.98px) { ... }
{% endhighlight %}

O mixin Sass para selecionar o mesmo tamanho de tela seria:

{% highlight scss %}
@include media-breakpoint-between(md, xl) { ... }
{% endhighlight %}

## Z-index

Vários componentes Bootstrap usam `z-index`, a propriedade CSS que ajuda controlar layout, provendo um terceiro eixo para mover o conteúdo. Nós usamos uma escala z-index padrão, no Bootstrap. Ela foi desenhada para dispor nvegações, tooltips, popovers, modals e etc, adequadamente.

Estes valores maiores começam em um número arbitrário, grande e específico o suficiente para, com sorte, evitar conflitos. Nós precisamos de um conjunto de valores padrões desse para que nossos componentes dispostos em camadas (tooltips, popovers, navbars, dropdowns e modals) sejam, razoavelmente, consistentes em seus comportamentos. Não há motivos para não termos usado valores maiores que `100` ou `500`, ou não.

Nós não encorajamos a personalização desses valores, individualmente. Se precisar alterar um deles, provavelmente, vai precisar mudar todos eles.

{% highlight scss %}
$zindex-dropdown:          1000 !default;
$zindex-sticky:            1020 !default;
$zindex-fixed:             1030 !default;
$zindex-modal-backdrop:    1040 !default;
$zindex-modal:             1050 !default;
$zindex-popover:           1060 !default;
$zindex-tooltip:           1070 !default;
{% endhighlight %}

Para lidar com sobreposição de bordas dentro de componentes (ex: botões em grupos de inputs), nós usamos os baixos valores `z-index` de `1`, `2` e `3` para estados padrões, hover e active. Em hover, focus e active, nós trazemos um elemento específico à frente, usando um valor `z-index` maior para mostrar suas bordas, invés de seus elementos.

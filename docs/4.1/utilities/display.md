---
layout: docs
title: Propriedade display
description: Rapido e responsivamente, alterne a visibilidade e outras coisas, com nossos utilitários de display. Além do mais, tenha suporte para alguns dos valores mais comuns, assim como alguns extras para controle do display durante impressões.
group: utilities
toc: true
---

## Como funciona

Altere o valor da [propriedade `display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display) com nossas classes utilitárias e responsivas display. Propositalmente, nós só suportamos alguns de todos os possíveis valores para a propriedade `display`. No entanto, as classes podem ser combinadas para atingirmos os diferentes efeitos que queremos.

## Notação

Classes utilitárias de display que afetam todos os [breakpoints]({{ site.baseurl }}/docs/{{ site.docs_version }}/layout/overview/#responsive-breakpoints) (do `xs` ao `xl`) não possuem abreviações, em si. Isto se deve ao fato destas classes serem definidas à partir de uma declaração `min-width: 0;` e, portanto, não são limitadas por media queries. Contudo, as demais classes possuem abreviação de breakpoint.

De tal maneira, classes são nomeadas de tal modo:

* `.d-{valor}` para o breakpoint `xs`;
* `.d-{breakpoint}-{valor}` para os breakpoints `sm`, `md`, `lg` e `xl`.

Onde a parte *{valor}* deve ser substituída por:

* `none`;
* `inline`;
* `inline-block`;
* `block`;
* `table`;
* `table-cell`;
* `table-row`;
* `flex`;
* `inline-flex`.

As media queries afetam as laguras das telas com o dado ou maior breakpoint. Por exemplo, `.d-lg-none` define `display: none;` tanto em telas de tamanho `lg`, quanto `xl`.

## Exemplos

{% capture example %}
<div class="d-inline p-2 bg-primary text-white">d-inline</div>
<div class="d-inline p-2 bg-dark text-white">d-inline</div>
{% endcapture %}
{% include example.html content=example %}

{% capture example %}
<span class="d-block p-2 bg-primary text-white">d-block</span>
<span class="d-block p-2 bg-dark text-white">d-block</span>
{% endcapture %}
{% include example.html content=example %}

## Escondendo elementos

Para um desenvolvimento rápido e *mobile-friendly*, use classes display responsivas para exibir ou esconder elementos, de acordo o tamanho do dispositivo. Com isso, evite criar versões inteiramente diferentes, mas esconda elementos em certos tamanhos de telas.

Para esconder elementos, simplesmente, use a classe `.d-none` ou uma das classes `.d-{sm, md, lg ou xl}-none`.

Para mostrar um elemento somente em uma escala de tamanho de telas, você pode combinar uma classe `.d-*-none` com uma `.d-*-*`. Por exemplo: `.d-none .d-md-block .d-xl-none` vai esconder o elemento em todas as telas, exceto em dispositivos médios e grandes.

| Tamanho da tela        | Classe |
| ---                    | --- |
| Esconde em todos       | `.d-none` |
| Esconde apenas em telas xs   | `.d-none .d-sm-block` |
| Esconde apenas em telas sm   | `.d-sm-none .d-md-block` |
| Esconde apenas em telas md   | `.d-md-none .d-lg-block` |
| Esconde apenas em telas lg   | `.d-lg-none .d-xl-block` |
| Esconde apenas em telas xl   | `.d-xl-none` |
| Visível em todas             | `.d-block` |
| Visível apenas em telas xs   | `.d-block .d-sm-none` |
| Visível apenas em telas sm   | `.d-none .d-sm-block .d-md-none` |
| Visível apenas em telas md   | `.d-none .d-md-block .d-lg-none` |
| Visível apenas em telas lg   | `.d-none .d-lg-block .d-xl-none` |
| Visível apenas em telas xl   | `.d-none .d-xl-block` |

{% capture example %}
<div class="d-lg-none">Esconde em telas maiores que lg</div>
<div class="d-none d-lg-block">Esconde em telas menores que lg</div>
{% endcapture %}
{% include example.html content=example %}

## Display durante impressão

Altere o valor `display` dos elementos, quando for imprimir, usando nossas classes utilitárias display. Você também terá suporte para os mesmos valores de `display` que nossos utilitários responsivos `.d-*` possuem.

- `.d-print-none`;
- `.d-print-inline`;
- `.d-print-inline-block`;
- `.d-print-block`;
- `.d-print-table`;
- `.d-print-table-row`;
- `.d-print-table-cell`;
- `.d-print-flex`;
- `.d-print-inline-flex`.

Não esqueça: as classes print e display podem ser combinadas!

{% capture example %}
<div class="d-print-none">Exibe apenas em telas (esconde em impressões).</div>
<div class="d-none d-print-block">Exibe apenas em impressões (Esconde em telas).</div>
<div class="d-none d-lg-block d-print-block">Esconde em telas grandes, mas sempre mostra nas impressões.</div>
{% endcapture %}
{% include example.html content=example %}

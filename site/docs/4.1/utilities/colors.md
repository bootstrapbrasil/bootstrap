---
layout: docs
title: Cores
description: Transmita mensagens através de cores, usando um punhado de cores utilitárias. Inclui suporte para estilização de links em estados de hover, também.
group: utilities
toc: true
---

## Cores

{% capture example %}
{% for color in site.data.theme-colors %}
<p class="text-{{ color.name }}{% if color.name == "light" %} bg-dark{% endif %}">.text-{{ color.name }}</p>{% endfor %}
<p class="text-body">.text-body</p>
<p class="text-muted">.text-muted</p>
<p class="text-white bg-dark">.text-white</p>
<p class="text-black-50">.text-black-50</p>
<p class="text-white-50 bg-dark">.text-white-50</p>
{% endcapture %}
{% include example.html content=example %}

Classes de texto contextuais também funcionam bem em âncoras, usando os estados hover e focus providos. **No entanto, perceba que as classes `.text-white` e `.text-muted` não possuem estilização para links.**

{% capture example %}
{% for color in site.data.theme-colors %}
<p><a href="#" class="text-{{ color.name }}{% if color.name == "light" %} bg-dark{% endif %}">{{ color.name | capitalize }} link</a></p>{% endfor %}
<p><a href="#" class="text-muted">Link esmaecido</a></p>
<p><a href="#" class="text-white bg-dark">Link branco</a></p>
{% endcapture %}
{% include example.html content=example %}

## Cores de fundo

Similar as classes de textos contextuais, você também pode definir o background de um elemento, com classes contextuais. Componentes de âncoras vão escurecer no hover, assim como quando usando classes de texto. Utilitários de background **não definem propriedades `color`**, então, em alguns casos, você precisará de utilitários de texto.

{% capture example %}
{% for color in site.data.theme-colors %}
<div class="p-3 mb-2 bg-{{ color.name }} {% if color.name == "light" or color.name == "warning" %}text-dark{% else %}text-white{% endif %}">.bg-{{ color.name }}</div>{% endfor %}
<div class="p-3 mb-2 bg-white text-dark">.bg-white</div>
<div class="p-3 mb-2 bg-transparent text-dark">.bg-transparent</div>
{% endcapture %}
{% include example.html content=example %}

## Gradientes de fundo

Quando a variável `$enable-gradients` está definida com valor "true", as variantes do utilitário `.bg-gradient` poderão ser utilizadas. **Por padrão, `$enable-gradients` está definida com "false" e o exemplo abaixo está, intencionalmente, quebrado.** Isso é para fácil customização, assim que você começa a usar o Bootstrap. 

[Aprenda mais sobre nossas configurações Sass]({{ site.baseurl }}/docs/{{ site.docs_version }}/getting-started/theming/#sass-options), para ativiar estas classes e outras coisas.

{% capture example %}
{% for color in site.data.theme-colors %}
<div class="p-3 mb-2 bg-gradient-{{ color.name }} {% if color.name == "light" or color.name == "warning" %}text-dark{% else %}text-white{% endif %}">.bg-gradient-{{ color.name }}</div>{% endfor %}
{% endcapture %}
{% include example.html content=example %}

{% capture callout %}
#### Lidando com especificidade

As vezes, classes contextuais não podem ser utilizadas, devido a especificidade de um outro seletor. Em alguns casos, envolver seu elemento em uma nova `<div>` com a classe, é suficiente.

{% endcapture %}
{% include callout.html content=callout type="info" %}

{% include callout-warning-color-assistive-technologies.md %}

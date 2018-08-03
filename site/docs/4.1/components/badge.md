---
layout: docs
title: Badges
description: Documentação e exemplos sobre os badges, nosso pequeno componente para contagem e rótulos.
group: components
toc: true
---

## Exemplo

Os badges escalam para combinar com o tamanho do elemento pai imediato, usando font-size relativa e unidade `em`.

<div class="bd-example">
<div class="h1">Cabeçalho exemplo <span class="badge badge-secondary">Novo</span></div>
<div class="h2">Cabeçalho exemplo <span class="badge badge-secondary">Novo</span></div>
<div class="h3">Cabeçalho exemplo <span class="badge badge-secondary">Novo</span></div>
<div class="h4">Cabeçalho exemplo <span class="badge badge-secondary">Novo</span></div>
<div class="h5">Cabeçalho exemplo <span class="badge badge-secondary">Novo</span></div>
<div class="h6">Cabeçalho exemplo <span class="badge badge-secondary">Novo</span></div>
</div>

{% highlight html %}
<h1>Cabeçalho exemplo <span class="badge badge-secondary">Novo</span></h1>
<h2>Cabeçalho exemplo <span class="badge badge-secondary">Novo</span></h2>
<h3>Cabeçalho exemplo <span class="badge badge-secondary">Novo</span></h3>
<h4>Cabeçalho exemplo <span class="badge badge-secondary">Novo</span></h4>
<h5>Cabeçalho exemplo <span class="badge badge-secondary">Novo</span></h5>
<h6>Cabeçalho exemplo <span class="badge badge-secondary">Novo</span></h6>
{% endhighlight %}

Badges podem ser usados como parte de links ou botões para realizar contagem.

{% capture example %}
<button type="button" class="btn btn-primary">
  Notificações <span class="badge badge-light">4</span>
</button>
{% endcapture %}
{% include example.html content=example %}

Perceba que dependendo do uso, badges podem ser confusos para usuários de leitores de telas e tecnologias assistivas similares. Apesar do estilo dos badges serem intuitivos, esses usuários vão ser apresentados só ao conteúdo contido neles. Por isso, dependendo da situação, esses badges podem parecer palavras ou números quaisquer ao final da frase, link ou botão.

A não ser que o contexto esteja claro (como no exemplo "Notificações", onde é entendido que o 4 é o número de notificações), considere criar contexto com um texto adicional escondido visualmente.

{% capture example %}
<button type="button" class="btn btn-primary">
  Perfil <span class="badge badge-light">9</span>
  <span class="sr-only">Mensagens não lidas</span>
</button>
{% endcapture %}
{% include example.html content=example %}

## Variações contextuais

Adicione qualquer uma das classes modificadoras mencionadas abaixo para mudar a aparência de um badge.

{% capture example %}
{% for color in site.data.theme-colors %}
<span class="badge badge-{{ color.name }}">{{ color.name | capitalize }}</span>{% endfor %}
{% endcapture %}
{% include example.html content=example %}

{% include callout-warning-color-assistive-technologies.md %}

## Badges em pílulas

Use a classe modificadora `.badge-pill` para fazer com que os badges fiquem mais arredondados (`border-radius` maior e `padding` horizontal adicional). É útil se você precisa dos badges da v3.

{% capture example %}
{% for color in site.data.theme-colors %}
<span class="badge badge-pill badge-{{ color.name }}">{{ color.name | capitalize }}</span>{% endfor %}
{% endcapture %}
{% include example.html content=example %}

## Links

Usando as classes contextuais `.badge-*`, em um elemento `<a>`, rapidamente, consiga badges _acionáveis_ com estados hover e focus.

{% capture example %}
{% for color in site.data.theme-colors %}
<a href="#" class="badge badge-{{ color.name }}">{{ color.name | capitalize }}</a>{% endfor %}
{% endcapture %}
{% include example.html content=example %}

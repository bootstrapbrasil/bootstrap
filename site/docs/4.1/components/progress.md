---
layout: docs
title: Progress
description: Documentação e exemplos de uso das barras de progresso Bootstrap, além de barras empilhadas, backgrounds animados e rótulos.
group: components
toc: true
---

## Como funciona

Componentes de progresso são feitos com dois elementos HTML, um pouco de CSS para a largura e outros atributos. Não usamos [o elemento HTML5 `<progress>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/progress) para garantir que você possa empilhar barras de progresso e colocar textos sobre elas.

- Nós usamos o elemento com `.progress` como um envolto para indicar o valor máximo da barra de progresso;
- Nós usamos o elemento interno com `.progress-bar` para indicar o progresso da barra, até então;
- A `.progress-bar` exige um CSS inline, classe utilitária ou CSS personalizado, para definir sua largura;
- A classe `.progress-bar` também exige o uso de alguns atributos `role` e `aria` para fazê-lo acessível.

Junte tudo isso e consiga o seguinte:

{% capture example %}
<div class="progress">
  <div class="progress-bar" role="progressbar" aria-valuenow="0" aria-valuemin="0" aria-valuemax="100"></div>
</div>
<div class="progress">
  <div class="progress-bar" role="progressbar" style="width: 25%" aria-valuenow="25" aria-valuemin="0" aria-valuemax="100"></div>
</div>
<div class="progress">
  <div class="progress-bar" role="progressbar" style="width: 50%" aria-valuenow="50" aria-valuemin="0" aria-valuemax="100"></div>
</div>
<div class="progress">
  <div class="progress-bar" role="progressbar" style="width: 75%" aria-valuenow="75" aria-valuemin="0" aria-valuemax="100"></div>
</div>
<div class="progress">
  <div class="progress-bar" role="progressbar" style="width: 100%" aria-valuenow="100" aria-valuemin="0" aria-valuemax="100"></div>
</div>
{% endcapture %}
{% include example.html content=example %}

Bootstrap provê um punhado de [utilitários para definir largura]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/sizing/). Dependendo de suas necessidades, elas podem ajudar a configurar seu progresso, rapidamente.

{% capture example %}
<div class="progress">
  <div class="progress-bar w-75" role="progressbar" aria-valuenow="75" aria-valuemin="0" aria-valuemax="100"></div>
</div>
{% endcapture %}
{% include example.html content=example %}

## Rótulos

Use rótulos em suas barras de progressos, colocando texto dentro do elemento com `.progress-bar`.

{% capture example %}
<div class="progress">
  <div class="progress-bar" role="progressbar" style="width: 25%;" aria-valuenow="25" aria-valuemin="0" aria-valuemax="100">25%</div>
</div>
{% endcapture %}
{% include example.html content=example %}

## Altura

Nós só definimos um valor para altura no `.progress`, então, se você alterar o valor, o elemento interno `.progress-bar` vai se redimensionar propocionalmente, automaticamente.

{% capture example %}
<div class="progress" style="height: 1px;">
  <div class="progress-bar" role="progressbar" style="width: 25%;" aria-valuenow="25" aria-valuemin="0" aria-valuemax="100"></div>
</div>
<div class="progress" style="height: 20px;">
  <div class="progress-bar" role="progressbar" style="width: 25%;" aria-valuenow="25" aria-valuemin="0" aria-valuemax="100"></div>
</div>
{% endcapture %}
{% include example.html content=example %}

## Backgrounds

Use classes utilitárias de background para mudar a aparência das barras de progresso.

{% capture example %}
<div class="progress">
  <div class="progress-bar bg-success" role="progressbar" style="width: 25%" aria-valuenow="25" aria-valuemin="0" aria-valuemax="100"></div>
</div>
<div class="progress">
  <div class="progress-bar bg-info" role="progressbar" style="width: 50%" aria-valuenow="50" aria-valuemin="0" aria-valuemax="100"></div>
</div>
<div class="progress">
  <div class="progress-bar bg-warning" role="progressbar" style="width: 75%" aria-valuenow="75" aria-valuemin="0" aria-valuemax="100"></div>
</div>
<div class="progress">
  <div class="progress-bar bg-danger" role="progressbar" style="width: 100%" aria-valuenow="100" aria-valuemin="0" aria-valuemax="100"></div>
</div>
{% endcapture %}
{% include example.html content=example %}

## Múltiplas barrras

Crie várias barras de progresso, dentro de um único componente de progresso, se precisar.

{% capture example %}
<div class="progress">
  <div class="progress-bar" role="progressbar" style="width: 15%" aria-valuenow="15" aria-valuemin="0" aria-valuemax="100"></div>
  <div class="progress-bar bg-success" role="progressbar" style="width: 30%" aria-valuenow="30" aria-valuemin="0" aria-valuemax="100"></div>
  <div class="progress-bar bg-info" role="progressbar" style="width: 20%" aria-valuenow="20" aria-valuemin="0" aria-valuemax="100"></div>
</div>
{% endcapture %}
{% include example.html content=example %}

## Listrada

Adicione `.progress-bar-striped` em qualquer `.progress-bar` para aplicar uma listra sobre a cor de fundo, via gradiente CSS.

{% capture example %}
<div class="progress">
  <div class="progress-bar progress-bar-striped" role="progressbar" style="width: 10%" aria-valuenow="10" aria-valuemin="0" aria-valuemax="100"></div>
</div>
<div class="progress">
  <div class="progress-bar progress-bar-striped bg-success" role="progressbar" style="width: 25%" aria-valuenow="25" aria-valuemin="0" aria-valuemax="100"></div>
</div>
<div class="progress">
  <div class="progress-bar progress-bar-striped bg-info" role="progressbar" style="width: 50%" aria-valuenow="50" aria-valuemin="0" aria-valuemax="100"></div>
</div>
<div class="progress">
  <div class="progress-bar progress-bar-striped bg-warning" role="progressbar" style="width: 75%" aria-valuenow="75" aria-valuemin="0" aria-valuemax="100"></div>
</div>
<div class="progress">
  <div class="progress-bar progress-bar-striped bg-danger" role="progressbar" style="width: 100%" aria-valuenow="100" aria-valuemin="0" aria-valuemax="100"></div>
</div>
{% endcapture %}
{% include example.html content=example %}

## Listras animadas

O gradiente listrado também pode ser animado. Use `.progress-bar-animated` no `.progress-bar` para animar as listras, da direita para esquerda, via animações CSS3.

<div class="bd-example">
  <div class="progress">
    <div class="progress-bar progress-bar-striped" role="progressbar" aria-valuenow="75" aria-valuemin="0" aria-valuemax="100" style="width: 75%"></div>
  </div>
  <button type="button" class="btn btn-secondary bd-toggle-animated-progress" data-toggle="button" aria-pressed="false" autocomplete="off">
    Ligar animação
  </button>
</div>

{% highlight html %}
<div class="progress">
  <div class="progress-bar progress-bar-striped progress-bar-animated" role="progressbar" aria-valuenow="75" aria-valuemin="0" aria-valuemax="100" style="width: 75%"></div>
</div>
{% endhighlight %}

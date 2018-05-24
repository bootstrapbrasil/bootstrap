---
layout: docs
title: Clearfix
description: Rapido e facilmente usar a propriedade clear em elementos flutuando, usando o utilitário clearfix.
group: utilities
toc: true
---

Facilmente limpa a `float`, usando a classe `.clearfix`, no **elemento pai**. Além do mais, também pode ser usado como um mixin.

{% highlight html %}
<div class="clearfix">...</div>
{% endhighlight %}

{% highlight scss %}
// O mixin, em si.
@mixin clearfix() {
  &::after {
    display: block;
    content: "";
    clear: both;
  }
}

// Como usar o mixin.
.element {
  @include clearfix;
}
{% endhighlight %}

O exemplo a seguir mostra como o clearfix pode ser usado. Sem ele, a div envoltando não se expandiria ao redor dos botões, oquê causaria um layout quebrado.

{% capture example %}
<div class="bg-info clearfix">
  <button type="button" class="btn btn-secondary float-left">Exemplo de botão flutuando à esquerda</button>
  <button type="button" class="btn btn-secondary float-right">Exemplo de botão flutuando à direita</button>
</div>
{% endcapture %}
{% include example.html content=example %}

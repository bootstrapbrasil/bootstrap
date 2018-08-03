---
layout: docs
title: Substituição por imagens
description: Troque textos por imagens em background, com nossa classe para esconder textos.
group: utilities
toc: true
---

{% capture callout %}
##### Aviso
A classe `text-hide()` foi descontinuada na versão v4.1. E será removida por completo na v5.
{% endcapture %}
{% include callout.html content=callout type="warning" %}

Utilize a classe `.text-hide` ou o mixin para ajudar a substituir o texto de um elemento por uma imagem em background.

{% highlight html %}
<h1 class="text-hide">Cabeçalho personalizado</h1>
{% endhighlight %}

{% highlight scss %}
// Exemplo de uso do mixin
.heading {
  @include text-hide;
}
{% endhighlight %}

A classe `.text-hide` é usada para esconder o texto e manter os benefícios de acessibilidade e SEO das tags de cabeçalho, enquanto utiliza-se uma imagem de background.

{% capture example %}
<h1 class="text-hide" style="background-image: url('/docs/{{ site.docs_version }}/assets/brand/bootstrap-solid.svg'); width: 50px; height: 50px;">Bootstrap</h1>
{% endcapture %}
{% include example.html content=example %}

---
layout: docs
title: Posicionamento
description: Use estes utilitários de atalho, para definir o tipo de posicionamento de um elemento, rapidamente.
group: utilities
toc: true
---

## Valores comuns

Apesar de termos classes para definir o tipo de posicionamento, elas não são responsivas.

{% highlight html %}
<div class="position-static">...</div>
<div class="position-relative">...</div>
<div class="position-absolute">...</div>
<div class="position-fixed">...</div>
<div class="position-sticky">...</div>
{% endhighlight %}

## Fixed top

Posicione um elemento no topo da viewport, de ponta a ponta, usando a seguinte classe:

{% highlight html %}
<div class="fixed-top">...</div>
{% endhighlight %}

_Ps: certifique-se de entender a influência de elementos posicionados de tal forma, em seu projeto, pois, você pode precisar de CSS adicional._

## Fixed bottom

Posicione um elemento na parte inferior da viewport, de ponta a ponta, usando a seguinte classe:

{% highlight html %}
<div class="fixed-bottom">...</div>
{% endhighlight %}

_Ps: certifique-se de entender a influência de elementos posicionados de tal forma, em seu projeto, pois, você pode precisar de CSS adicional._

## Sticky top

Posicione um elemento no topo da viewport, de ponta a ponta, mas só depois que o usuário rolar sobre ele. O utilitário `.sticky-top` usa a declaração `position: sticky`, a qual não é suportada em todos browsers, completamente.

**IE11 e IE10 vão renderizar `position: sticky` como se fosse `position: relative`**. Devido a isso, precisamos usar uma query `@supports`, para usar tal comportamento só em browsers que suportam isso, adequadamente.

{% highlight html %}
<div class="sticky-top">...</div>
{% endhighlight %}

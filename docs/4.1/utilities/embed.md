---
layout: docs
title: Incorporações
description: Crie incorporações de vídeos ou slideshows, baseando-se na largura do pai, criando uma proporção que escala em qualquer dispositivo.
group: utilities
toc: true
---

## Sobre

Regras são, diretamente, aplicadas a elementos `<iframe>`, `<embed>`, `<video>` e `<object>`. Opcionalmente, use uma classe descendente explícita `.embed-responsive-item`, quando quiser combinar o estilo em outros atributos.

**Dica PROFISSA!** Não é necessário usar `frameborder="0"` em seus `<iframe>`s, dado que já fazemos isso por você.

## Exemplo

Envolte qualquer elemento (como um `<iframe>`) em um elemento pai com a classe `.embed-responsive` e uma proporção de tela. Já a classe `.embed-responsive-item` não obrigatória, mas encorajamos utilizá-la.

{% capture example %}
<div class="embed-responsive embed-responsive-16by9">
  <iframe class="embed-responsive-item" src="https://www.youtube.com/embed/zpOULjyy-n8?rel=0" allowfullscreen></iframe>
</div>
{% endcapture %}
{% include example.html content=example %}

## Proporções de telas

Proporções de telas podem ser personalizadas com classes modificadoras.

{% highlight html %}
<!-- Proporção 21:9 -->
<div class="embed-responsive embed-responsive-21by9">
  <iframe class="embed-responsive-item" src="..."></iframe>
</div>

<!-- Proporção 16:9 -->
<div class="embed-responsive embed-responsive-16by9">
  <iframe class="embed-responsive-item" src="..."></iframe>
</div>

<!--Proporção 4:3 -->
<div class="embed-responsive embed-responsive-4by3">
  <iframe class="embed-responsive-item" src="..."></iframe>
</div>

<!--Proporção 1:1 -->
<div class="embed-responsive embed-responsive-1by1">
  <iframe class="embed-responsive-item" src="..."></iframe>
</div>
{% endhighlight %}

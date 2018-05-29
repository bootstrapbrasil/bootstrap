---
layout: docs
title: Leitores de tela
description: Use estes utilitários para esconder elementos em todos os dispositivos, com exceção dos próprios leitores de tela.
group: utilities
toc: true
---

Com os utilitários você poderá esconder um elemento em todos os dispositivos, **exceto em leitores de tela**. Também, combinando as classes `.sr-only` e `.sr-only-focusable`, é possível mostrar um elemento, novamente, quando ele recebe foco. Isso tudo é possível usando mixins, também.

{%- comment -%}
É necessário para seguir as [melhores práticas de acessibilidade]({{ site.baseurl }}/docs/{{ site.docs_version }}/getting-started/#accessibility).
{%- endcomment -%}

{% capture example %}
<a class="sr-only sr-only-focusable" href="#content">Pular para o conteúdo principal</a>
{% endcapture %}
{% include example.html content=example %}

{% highlight scss %}
// Exemplo de uso com mixin
.pula-navegacao {
  @include sr-only;
  @include sr-only-focusable;
}
{% endhighlight %}

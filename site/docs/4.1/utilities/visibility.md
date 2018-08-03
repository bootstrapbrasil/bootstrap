---
layout: docs
title: Visibilidade
description: Controle a visibilidade de elementos, sem modificar a propriedade display, usando os utilitários de visibilidade.
group: utilities
---

Altere o valor da propriedade `visibility` dos elementos usando as classes utilitárias de visibilidade. Elas não modificam o valor da propriedade `display` para não impactar no layout - elementos `.invisible` ainda deixam o espaço na página. São úteis para esconder o conteúdo da maioria dos usuários, com excessão dos usuários com leitores de telas.

Use as classes `.visible` ou `.invisible`, como quiser.

{% highlight html %}
<div class="visible">...</div>
<div class="invisible">...</div>
{% endhighlight %}

{% highlight scss %}
// Como são as classes
.visible {
  visibility: visible;
}
.invisible {
  visibility: hidden;
}

// Modo de uso com mixins
.elemento {
  @include invisible(visible);
}
.outro-elemento {
  @include invisible(hidden);
}
{% endhighlight %}

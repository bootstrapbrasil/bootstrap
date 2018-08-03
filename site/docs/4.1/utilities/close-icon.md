---
layout: docs
title: Ícone de dispensa
description: Use um botão genérico, para dispensar conteúdos como modais e alertas.
group: utilities
toc: true
---

**Certifique-se de incluir texto para os leitores de telas**, como fizemos no atributo `aria-label`.

{% capture example %}
<button type="button" class="close" aria-label="Fechar">
  <span aria-hidden="true">&times;</span>
</button>
{% endcapture %}
{% include example.html content=example %}

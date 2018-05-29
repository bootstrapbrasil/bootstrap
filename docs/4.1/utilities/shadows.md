---
layout: docs
title: Sombras
description: Adicione ou remova sombras de elementos, usando os utilitários box-shadows.
group: utilities
toc: false
---

## Exemplos

Apesar de sombras em componentes estarem desativadas por padrão, no Bootstrap, e poderem ser ativadas alterando o valor da variável `$enable-shadows`, também é possível adicionar e remover sombras, rapidamente, usando nossas classes utilitárias `box-shadow`. Essas classes são `.shadow-none` e três outras, para diferentes tamanhos de sombras.

{% capture example %}
<div class="shadow-none p-3 mb-5 bg-light rounded">Sem sombra</div>
<div class="shadow-sm p-3 mb-5 bg-white rounded">Sombra pequena</div>
<div class="shadow p-3 mb-5 bg-white rounded">Sombra média</div>
<div class="shadow-lg p-3 mb-5 bg-white rounded">Sombra grande</div>
{% endcapture %}
{% include example.html content=example %}

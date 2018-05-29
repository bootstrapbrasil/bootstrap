---
layout: docs
title: Alinhamento vertical
description: Facilmente, altere o alinhamento vertical de elementos inline, inline-block, inline-table ou células de tabelas.
group: utilities
---

Altere o alinhamento de elementos com os utilitários de [alinhamento vertical](https://developer.mozilla.org/pt-BR/docs/Web/CSS/vertical-align). No entanto, se lembre: alinhamento vertical só afeta elementos inline, inline-block, inline-table e células de tabelas.

É possível escolher entre `.align-baseline`, `.align-top`, `.align-middle`, `.align-bottom`, `.align-text-bottom` e `.align-text-top`.

Uso em elementos inline:

{% capture example %}
<span class="align-baseline">baseline</span>
<span class="align-top">top</span>
<span class="align-middle">middle</span>
<span class="align-bottom">bottom</span>
<span class="align-text-top">text-top</span>
<span class="align-text-bottom">text-bottom</span>
{% endcapture %}
{% include example.html content=example %}

Uso em células de tabelas:

{% capture example %}
<table style="height: 100px;">
  <tbody>
    <tr>
      <td class="align-baseline">baseline</td>
      <td class="align-top">top</td>
      <td class="align-middle">middle</td>
      <td class="align-bottom">bottom</td>
      <td class="align-text-top">text-top</td>
      <td class="align-text-bottom">text-bottom</td>
    </tr>
  </tbody>
</table>
{% endcapture %}
{% include example.html content=example %}

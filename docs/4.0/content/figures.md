---
layout: docs
title: Figuras
description: Documentação e exemplos para mostrar imagens e textos relacionados usando o componente figure, no Bootstrap.
group: content
---

Sempre que você precisar mostrar algum tipo de conteúdo como uma imagem com legenda, considere usar o `<figure>`.

Use as classes `.figure`, `.figure-img` e `.figure-caption` para conseguir alguns estilos bases para os elementos HTML5 `<figure>` e `<figcaption>`. Imagens na tag `<figure>` não possuem tamanhos explícitos, por isso, tenha certeza de colocar a classe `.img-fluid` no elemento `<img>`, para fazer com que ela seja responsiva.

{% example html %}
<figure class="figure">
  <img data-src="holder.js/400x300" class="figure-img img-fluid rounded" alt="Imagem de um quadrado genérico com bordas arredondadas, em uma figure.">
  <figcaption class="figure-caption">Uma legenda para a imagem acima.</figcaption>
</figure>
{% endexample %}

Alinhar a legenda de uma figura é fácil com nossos [utilitários de textos]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/text/#text-alignment).

{% example html %}
<figure class="figure">
  <img data-src="holder.js/400x300" class="figure-img img-fluid rounded" alt="Imagem de um quadrado genérico com bordas arredondadas, em uma figure.">
  <figcaption class="figure-caption text-right">Uma legenda para a imagem acima.</figcaption>
</figure>
{% endexample %}

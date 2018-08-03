---
layout: docs
title: Texto
description: Documentação e exemplos de utilitários de texto comuns para controle de alinhamento, quebra de linha, espessura, etc.
group: utilities
toc: true
---

## Alinhamento de texto

Facilmente, alinhe texto de componentes com as classes de alinhamento.

{% capture example %}
<p class="text-justify">Ambitioni dedisse scripsisse iudicaretur. Cras mattis iudicium purus sit amet fermentum. Donec sed odio operae, eu vulputate felis rhoncus. Praeterea iter est quasdam res quas ex communi. At nos hinc posthac, sitientis piros Afros. Petierunt uti sibi concilium totius Galliae in diem certam indicere. Cras mattis iudicium purus sit amet fermentum.</p>
{% endcapture %}
{% include example.html content=example %}

Para alinhamento à esquerda, direita e centralizado, existem classes responsivas que usam os mesmos breakpoints que o sistema de grid.

{% capture example %}
<p class="text-left">Alinhado à esquerda, em todos tamanhos de viewport.</p>
<p class="text-center">Centralizado, em todos tamanhos de viewport.</p>
<p class="text-right">Alinhado à direita, em todos tamanhos de viewport.</p>

<p class="text-sm-left">Alinhado à esquerda, em viewports com tamanho SM (pequenas) ou maior.</p>
<p class="text-md-left">Alinhado à esquerda, em viewports com tamanho MD (médias) ou maior.</p>
<p class="text-lg-left">Alinhado à esquerda, em viewports com tamanho LG (grandes) ou maior.</p>
<p class="text-xl-left">Alinhado à esquerda, em viewports com tamanho XL (extra-grandes) ou maior.</p>
{% endcapture %}
{% include example.html content=example %}

## Quebra e transbordamento de texto

Evite que o texto quebre, usando a classe `.text-nowrap`.

{% capture example %}
<div class="text-nowrap bd-highlight" style="width: 8rem;">
  Este texto está transbordando o elemento pai.
</div>
{% endcapture %}
{% include example.html content=example %}

Para conteúdos longos demais, você pode usar a classe `.text-truncate` para reduzir o texto com reticências. **Requer o uso de `display: inline-block` ou `display: block`.**

{% capture example %}
<!-- Elemento com `diplay: block;` -->
<div class="row">
  <div class="col-2 text-truncate">
    Praeterea iter est quasdam res quas ex communi.
  </div>
</div>

<!-- Elemento com `diplay: inline;` -->
<span class="d-inline-block text-truncate" style="max-width: 150px;">
  Praeterea iter est quasdam res quas ex communi.
</span>
{% endcapture %}
{% include example.html content=example %}

## Text transform

Tranforme textos com as seguintes classes:

{% capture example %}
<p class="text-lowercase">TEXTO EM LETRAS MINÚSCULAS.</p>
<p class="text-uppercase">Texto em letras maiúsculas.</p>
<p class="text-capitalize">texto capitalizado.</p>
{% endcapture %}
{% include example.html content=example %}

Perceba que `text-capitalize` apenas altera a primeira letra de cada palavra.

## Espessura e italização de fontes

Rapidamente, modifique a espessura do texto ou italicize-o.

{% capture example %}
<p class="font-weight-bold">Texto grosso.</p>
<p class="font-weight-normal">Texto de espessura comum.</p>
<p class="font-weight-light">Texto de espessura leve.</p>
<p class="font-italic">Texto itálico.</p>
{% endcapture %}
{% include example.html content=example %}

## Monospace

Use nossa fonte monospace, usando a classe `.text-monospace`.

{% capture example %}
<p class="text-monospace">Este é um texto com fonte monospace.</p>
{% endcapture %}
{% include example.html content=example %}

---
layout: docs
title: Dimensionamento
description: Facilmente, é possível fazer um elemento ser tão largo e alto quanto seu pai, usando nossos utilitários de largura e altura.
group: utilities
toc: true
---

Utilitáiros de largura e altura são gerados a partir do mapa Sass `$sizes`, no arquivo `_variables.scss`. Por padrão, as classes dão suporte para valores de `25%`, `50%`, `75%`, `100%` e `auto`. Também é possível modificar esses valores, se for necessário gerar novos utilitários com novos valores.

{% capture example %}
<div class="w-25 p-3" style="background-color: #eee;">Largura de 25%</div>
<div class="w-50 p-3" style="background-color: #eee;">Largura de 50%</div>
<div class="w-75 p-3" style="background-color: #eee;">Largura de 75%</div>
<div class="w-100 p-3" style="background-color: #eee;">Largura de 100%</div>
<div class="w-auto p-3" style="background-color: #eee;">Largura automática</div>
{% endcapture %}
{% include example.html content=example %}

{% capture example %}
<div style="height: 100px; background-color: rgba(255,0,0,0.1);">
  <div class="h-25 d-inline-block" style="width: 120px; background-color: rgba(0,0,255,.1)">Altura de 25%</div>
  <div class="h-50 d-inline-block" style="width: 120px; background-color: rgba(0,0,255,.1)">Altura de 50%</div>
  <div class="h-75 d-inline-block" style="width: 120px; background-color: rgba(0,0,255,.1)">Altura de 75%</div>
  <div class="h-100 d-inline-block" style="width: 120px; background-color: rgba(0,0,255,.1)">Altura de 100%</div>
  <div class="h-auto d-inline-block" style="width: 120px; background-color: rgba(0,0,255,.1)">Altura automática</div>
</div>
{% endcapture %}
{% include example.html content=example %}

Você também pode usar os utilitários de largura e altura máxima.
{% capture example %}
<img class="mw-100" data-src="holder.js/1000px100?text=Max-width%20%3D%20100%25" alt="Max-width 100%">
{% endcapture %}
{% include example.html content=example %}

{% capture example %}
<div style="height: 100px; background-color: rgba(255,0,0,0.1);">
  <div class="mh-100" style="width: 100px; height: 200px; background-color: rgba(0,0,255,0.1);">Max-height 100%</div>
</div>
{% endcapture %}
{% include example.html content=example %}

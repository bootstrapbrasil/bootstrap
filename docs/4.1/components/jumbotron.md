---
layout: docs
title: Jumbotron
description: Componente leve e flexível para exibir conteúdo.
group: components
---

Um componente leve e flexível que pode se extender pela viewport inteira para exibir mensagens de market, em seu site.

{% capture example %}
<div class="jumbotron">
  <h1 class="display-4">Olá, mundo!</h1>
  <p class="lead">Este é um simples componente jumbotron para chamar mais atenção a um determinado conteúdo ou informação.</p>
  <hr class="my-4">
  <p>Ele usa classes utilitárias para tipografia e espaçamento de conteúdo, dentro do maior container.</p>
  <a class="btn btn-primary btn-lg" href="#" role="button">Leia mais</a>
</div>
{% endcapture %}
{% include example.html content=example %}

Para um jumbotron com largura total e sem cantos arredondados, use a classe modificadora `.jumbotron-fluid` e adicione um `.container` ou `.container-fluid` dentro do jumbotron.

{% capture example %}
<div class="jumbotron jumbotron-fluid">
  <div class="container">
    <h1 class="display-4">Fluid jumbotron</h1>
    <p class="lead">Este é um jumbotron modificado que ocupa todo o espaço horizontal de seu elemento pai.</p>
  </div>
</div>
{% endcapture %}
{% include example.html content=example %}

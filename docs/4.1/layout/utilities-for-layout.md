---
layout: docs
title: Utilitários para layout
description: Para um desenvolvimento responsivo, mobile-friendly, mais rápido, Bootstrap possui uma dúzia de classes utilitárias para exibir, esconder, alinha e espaçar conteúdo.
group: layout
toc: true
---

## Alterando `display`

Use nossos [utilitários de display]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/display/) para, responsivamente, alternar valores comuns da propriedade `display`. Misture-os com nosso sistema grid, conteúdo e componentes a serem exibidos ou ocultos, em viewports específicos.

## Opções flexbox

Bootstrap 4 é feito com flexbox, mas nem todo `display` de elementos foram altreados para `display: flex`, já que isso faria muitas sobrescrições desnecessárias e mudanças inesperadas em comportamentos chaves de browsers. A maior parte de [nossos componentes]({{ site.baseurl }}/docs/{{ site.docs_version }}/components/alerts/) são feitos com flexbox ativado.

Se precisar ativar `display: flex` em um elemento, faça colocando `.d-flex` ou uma das variações responsivas (ex: `.-sm-flex`). Você precisará desta classe ou valor `display` para conseguir usar o resto de nossos [utilitários flexbox]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/flex/) para dimensionamento, alinhamento, espaçamento, etc.

## Margem e padding

Use os [utilitários de espaçamento]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/spacing/) de `margin` e `padding` para controlar como elementos e componentes são espaçados e dimensionados. Bootstrap 4 possui uma escala de cinco níveis para utilitários de espaçamento, baseado no valor padrão `1rem` da variável `$spacer`. Escolha valores para todas viewports (`.mr-3`, no caso `margin-right: 1rem`) ou variações responsivas para mirar em viewports específicas (`.mr-md-3` para `margin-right: 1rem` em viewports do breakpoint `md`).

## Alternar `visibility`

Quando alternar o valor da `display` não é necessário, você pode alternar o valor da `visibility` de algum elemento, usando nossos [utilitários de visibilidade]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/visibility/). Elementos invisíveis vão continuar a afetar o layout da página, mas são ocultos dos usuários, visualmente.

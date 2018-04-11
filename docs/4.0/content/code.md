---
layout: docs
title: Código
description: Documentação e exemplos para mostrar blocos de código em linha ou multi-linhas, usando o Bootstrap.
group: content
toc: true
---

## Código em linha

Envolte pedaços de códigos (aqueles com única linha), usando o elemento `<code>`. Se assegure de usar escape, nos colchetes do HTML.

{% example html %}
Por exemplo, isso deve ser envolto em uma linha: <code>&lt;section&gt;</code>.
{% endexample %}

## Bloco de códigos

Use tags `<pre>` para diversas linhas de código. Mais uma vez: tenha certeza de usar escape em qualquer colchete HTML, para que tudo seja renderizado adequadamente. Opcionalmente, você pode adicionar a classe `.pre-scrollable`, a qual vai usar `max-height` com valor de `340px` e criar uma barra de rolagem vertical.

{% example html %}
<pre><code>&lt;p&gt;Exemplo de texto aqui...&lt;/p&gt;
&lt;p&gt;Outro exemplo de texto aqui...&lt;/p&gt;
</code></pre>
{% endexample %}

## Variáveis

Para indicar variáveis, use a tag `<var>`.

{% example html %}
<var>y</var> = <var>m</var><var>x</var> + <var>b</var>
{% endexample %}

## Input do usuário

Use o `<kbd>` para indicar um input típico de entrada via teclado.

{% example html %}
Para trocar diretórios, digite <kbd>cd</kbd> seguido pelo nome do diretório.<br>
Para editar configurações, pressione <kbd><kbd>ctrl</kbd> + <kbd>,</kbd></kbd>
{% endexample %}

## Amostra de output

Para indicar uma amostra output de um programa, use a tag `<samp>`.

{% example html %}
<samp>Este texto deve ser tratado como uma amostra output de um programa de computadores.</samp>
{% endexample %}

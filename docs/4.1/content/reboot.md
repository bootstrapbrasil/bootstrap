---
layout: docs
title: Reboot
description: Reboot, uma série de customizações para elementos em único arquivo CSS, ajuda o Bootstrap prover uma base elegante, consistente e simples de se construir em cima.
group: content
redirect_from: "/docs/4.1/content/"
toc: true
---

## Abordagem

O Reboot é construído baseado no Normalize, possibilitando muitos elementos HTML sem estilos baseados em opiniões e usando apenas seletores de elementos. Por exemplo, nós customizamos alguns estilos do `<table>` para uma base mais simples e, então, te damos a oportunidade de usar `.table`, `.table-bordered` e outras classes.

Aqui estão nossas diretrizes e razões para termos escolhidos oquê sobrescrever, no Reboot:

- Atualizar alguns valores padrões de navegadores para usar `rem`s, invés de `em`s para espaçamento de componentes escaláveis;
- Evitar `margin-top`. Margens verticais podem colapsar, resultando em resultados inesperados. Mais importante ainda: uma única direção de margem é mentalmente mais simples;
- Para escalar facilmente através de diferentes tamanhos de dispositivos, elementos `block` devem usar `rem`s em suas margens;
- Manter o mínimo de declarações relacionadas a propriedade `font`, usando o valor `inherit` sempre que possível.

## Padrões de páginas

Os elementos `<html>` e `<body>` são atualizados para possibilitarem melhores padrões, em toda a página. Mais especificamente:

- `box-sizing` é configurado globalmente em todos elementos, incluindo `*::before` e `*::after`. Isso assegura que a largura declarada do elemento nunca exceda, devido a padding ou borda;
  - Nenhum tamanho de fonte base é declarado no `<html>`, mas assumimos o padrão do navegador (`16px`). É declarado `font-size: 1rem` no `<body>` para escalar o texto fácil e responsivamente usando media queries, enquanto é respeitado as preferências do usuário e garantindo uma abordagem mais acessível.
- O `<body>` também configura `font-family`, `line-height` e `text-align`, globalmente. Isso é herdado mais tarde por alguns elementos de formulário, para previnir inconsistência em fontes.
- Por segurança, o `<body>` tem `background-color` padrão de `#fff` declarado.

## Pilha de fontes nativas

As fontes web padrões (Helvetica Neue, Helvetica e Arial) foram descartadas no Bootstrap 4 e substituídas com uma "pilha de fontes nativas" para otimizar rederização de texto em todo dispositivo e SO. Leia mais sobre [pilhas de fontes nativas, nesse artigo da *Smashing Magazine*](https://www.smashingmagazine.com/2015/11/using-system-ui-fonts-practical-guide/).

{% highlight sass %}
$font-family-sans-serif:
  // Safari para OS X e iOS (San Francisco)
  -apple-system,
  // Chrome < 56 para OS X (San Francisco)
  BlinkMacSystemFont,
  // Windows
  "Segoe UI",
  // Android
  "Roboto",
  // Fallback de fonts web básicas
  "Helvetica Neue", Arial, sans-serif,
  // Fonts de Emoji
  "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol" !default;
{% endhighlight %}

Esta `font-family` é aplicada ao `<body>` e herdada Bootstrap adentro, global e automaticamente. Para trocar a `font-family` global, basta atualizar a variável `$font-family-base` e recompilar o Bootstrap.

## Cabeçalhos e parágrafos

Todos elementos de cabeçalho e parágrafo são resetados para terem `margin-top` removido. Cabeçalhos possuem `margin-bottom: .5rem` e parágrafos `margin-bottom: 1rem` para espaçamento mais fácil.

<table>
  <thead>
    <tr>
      <th>Cabeçalho</th>
      <th>Exemplo</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        {{ "`<h1></h1>`" | markdownify }}
      </td>
      <td><span class="h1">h1. Cabeçalho Bootstrap</span></td>
    </tr>
    <tr>
      <td>
        {{ "`<h2></h2>`" | markdownify }}
      </td>
      <td><span class="h2">h2. Cabeçalho Bootstrap</span></td>
    </tr>
    <tr>
      <td>
        {{ "`<h3></h3>`" | markdownify }}
      </td>
      <td><span class="h3">h3. Cabeçalho Bootstrap</span></td>
    </tr>
    <tr>
      <td>
        {{ "`<h4></h4>`" | markdownify }}
      </td>
      <td><span class="h4">h4. Cabeçalho Bootstrap</span></td>
    </tr>
    <tr>
      <td>
        {{ "`<h5></h5>`" | markdownify }}
      </td>
      <td><span class="h5">h5. Cabeçalho Bootstrap</span></td>
    </tr>
    <tr>
      <td>
        {{ "`<h6></h6>`" | markdownify }}
      </td>
      <td><span class="h6">h6. Cabeçalho Bootstrap</span></td>
    </tr>
  </tbody>
</table>

## Listas

Todas listas (`<ul>`, `<ol>` e `<dl>`) possuem seus valores para `margin-top` removidos e uma `margin-bottom: 1rem`. Listas aninhadas não possuem nenhuma `margin-bottom.`

<div class="bd-example">
{% capture markdown %}
* Lorem ipsum dolor sit amet
* Consectetur adipiscing elit
* Integer molestie lorem at massa
* Facilisis in pretium nisl aliquet
* Nulla volutpat aliquam velit
  * Phasellus iaculis neque
  * Purus sodales ultricies
  * Vestibulum laoreet porttitor sem
  * Ac tristique libero volutpat at
* Faucibus porta lacus fringilla vel
* Aenean sit amet erat nunc
* Eget porttitor lorem

1. Lorem ipsum dolor sit amet
2. Consectetur adipiscing elit
3. Integer molestie lorem at massa
4. Facilisis in pretium nisl aliquet
5. Nulla volutpat aliquam velit
6. Faucibus porta lacus fringilla vel
7. Aenean sit amet erat nunc
8. Eget porttitor lorem
{% endcapture %}
{{ markdown | markdownify }}
</div>

Para estilização mais simples, hierarquia mais limpa e melhor espaçamento, listas de descrição possuem margens customizadas. `<dd>`s possuem `margin-left` com valor `0` e adicionam `margin-bottom: .5rem`. `<dt>`s estão formatadas em **negrito**.

<div class="bd-example">
  <dl>
    <dt>Lista de descrições</dt>
    <dd>Uma lista de descrições é perfeita para definir termos.</dd>
    <dt>Euismod</dt>
    <dd>Vestibulum id ligula porta felis euismod semper eget lacinia odio sem.</dd>
    <dd>Donec id elit non mi porta gravida at eget metus.</dd>
    <dt>Malesuada porta</dt>
    <dd>Etiam porta sem malesuada magna mollis euismod.</dd>
  </dl>
</div>

## Textos pré-formatados

O elemento `<pre>` é configurado para remover sua `margin-top` e usar `rem` em sua `margin-bottom`.

<div class="bd-example">
<pre>
.example-element {
  margin-bottom: 1rem;
}
</pre>
</div>

## Tabelas

Tabelas são ajustadas sutilmente para estilizar elementos `<caption>`, colapsar bordas e garantir que o `text-align` seja consistente. Mudanças adicionais para bordas, paddings e outras propriedades são adicionadas com [a classe `.table`]({{ site.baseurl }}/docs/{{ site.docs_version }}/content/tables/).

<div class="bd-example">
  <table>
    <caption>
      Este é um exemplo de tabela e isso é um exemplo de legenda para descrever conteúdos.
    </caption>
    <thead>
      <tr>
        <th>Cabeçalho da tabela</th>
        <th>Cabeçalho da tabela</th>
        <th>Cabeçalho da tabela</th>
        <th>Cabeçalho da tabela</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>Célula da tabela</td>
        <td>Célula da tabela</td>
        <td>Célula da tabela</td>
        <td>Célula da tabela</td>
      </tr>
      <tr>
        <td>Célula da tabela</td>
        <td>Célula da tabela</td>
        <td>Célula da tabela</td>
        <td>Célula da tabela</td>
      </tr>
      <tr>
        <td>Célula da tabela</td>
        <td>Célula da tabela</td>
        <td>Célula da tabela</td>
        <td>Célula da tabela</td>
      </tr>
    </tbody>
  </table>
</div>

## Formulários

Vários elementos de formulário são resetados para estilos mais básicos. Aqui vai algumas das mudanças mais notáveis:

- Os `<fieldset>`s não possuem bordas, padding ou margem, então, eles podem ser usados facilmente como _wrappers_ para grupos ou inputs individuais;
- A tag `<legend>`, como os fieldsets, também foram re-estilizados para serem mostrados como um tipo de cabeçalho;
- As `<label>`s são configuradas para terem `display: inline-block` e permitir que margens sejam aplicadas;
- Os `<input>`s, `<select>`s, `<textarea>`s e `<button>`s são mais estilizados pelo Normalize, mas o Reboot remove suas margens e configura `line-height: inherit`, também;
- Tags `<textarea>` são modificadas para apenas serem redimensionáveis verticalmente, já que horizontalmente costuma quebrar o layout da página.

Essas mudanças e outras, são mostradas abaixo.

<form class="bd-example">
  <fieldset>
    <legend>Exemplo de legendas</legend>

    <p>
      <label for="input">Exemplo de input</label>
      <input type="text" id="input" placeholder="Exemplo de input">
    </p>

    <p>
      <label for="select">Exemplo de select</label>
      <select id="select">
        <option value="">Escolha...</option>
        <optgroup label="Grupo de opções 1">
          <option value="">Opção 1</option>
          <option value="">Opção 2</option>
          <option value="">Opção 3</option>
        </optgroup>
        <optgroup label="Grupo de opções 2">
          <option value="">Opção 4</option>
          <option value="">Opção 5</option>
          <option value="">Opção 6</option>
        </optgroup>
      </select>
    </p>

    <p>
      <label>
        <input type="checkbox" value="">
        Confira esta checkbox
      </label>
    </p>

    <p>
      <label>
        <input type="radio" name="optionsRadios" id="optionsRadios1" value="option1" checked>
        Essa é a opção um.
      </label>
      <label>
        <input type="radio" name="optionsRadios" id="optionsRadios2" value="option2">
        A opção dois é algo diferente e é super longa para demonstrar o _wrapping_ desses controles de formulários chiques.
      </label>
      <label>
        <input type="radio" name="optionsRadios" id="optionsRadios3" value="option3" disabled>
        Opção três está desativada.
      </label>
    </p>

    <p>
      <label for="textarea">Exemplo de input textarea</label>
      <textarea id="textarea" rows="3"></textarea>
    </p>

    <p>
      <label for="date">Exemplo de input date</label>
      <input type="date" id="date">
    </p>

    <p>
      <label for="time">Exemplo de input time</label>
      <input type="time" id="time">
    </p>

    <p>
      <label for="output">Example de output</label>
      <output name="result" id="output">100</output>
    </p>

    <p>
      <button type="submit">Botão submit</button>
      <input type="submit" value="Botão de input submit">
      <input type="button" value="Botão input">
    </p>

    <p>
      <button type="submit" disabled>Botão submit</button>
      <input type="submit" value="Botão de input submit" disabled>
      <input type="button" value="Botão input" disabled>
    </p>
  </fieldset>
</form>

## Elementos variados

### Address

O elemento `<address>` é atualizado para resetar os padrões da `font-style` de itálico para normal. A `line-height` é herdada e a `margin-bottom: 1rem` foi acrescentada. As tags `<address>` são para apresentar informações de contato para o ancestral mais próximo ou um determinado trabalho. Preserve sua formatação, colocando `<br>` no final de suas linhas.

<div class="bd-example">
  <address>
    <strong>Twitter, Inc.</strong><br>
    Rua Market, 1355, Suíte 900<br>
    São Francisco, CA 94103<br>
    <abbr title="Telefone">Tel:</abbr> (123) 456-7890
  </address>

  <address>
    <strong>Nome completo</strong><br>
    <a href="mailto:#">fulano.ciclano@exemplo.com</a>
  </address>
</div>

### Blockquote

O valor padrão das margens no `<blockquote>` é `1em 40px`, então, nós resetamos para `0 0 1rem` e conseguimos algo mais consistente em outros elementos.

<div class="bd-example">
  <blockquote class="blockquote">
    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer posuere erat a ante.</p>
    <footer>Alguém famoso em <cite title="Título da fonte">Título da fonte</cite></footer>
  </blockquote>
</div>

### Elementos inline

O elemento `<abbr>` recebe estilos básicos para se destacar dentro do texto do parágrafo.

<div class="bd-example">
  Nulla <abbr title="atributo">attr</abbr> vitae elit libero, a pharetra augue.
</div>

### Summary

O valor padrão da propriedade `cursor` é `text`, então, nós resetamos para `pointer` para dar a impressão que é possível interagir com elemento, clicando nele.

<div class="bd-example">
  <details>
    <summary>Alguns detalhes</summary>
    <p>Mais informações sobre os detalhes</p>
  </details>

  <details open>
    <summary>Mais detalhes</summary>
    <p>Mais informações ainda sobre os detalhes.</p>
  </details>
</div>

## Atributo HTML5 `[hidden]`

HTML5 acrescentou um [novo atributo global denominado `[hidden]`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/hidden), o qual é estilizado como `display: none`, por padrão. Pegando uma ideia emprestada do [PureCSS](https://purecss.io/), nós aprimoramos esse valor padrão fazendo com que tenha a _flag_ `!important`, previnindo que sua propriedade display seja sobrescrita, acidentalmente. Além do mais, o atributo `[hidden]` não é suportado nativamente no IE10 e esta declaração no nosso CSS contorna esse problema.

{% highlight html %}
<input type="text" hidden>
{% endhighlight %}

{% capture callout %}
##### Incompatibilidade jQuery

O atributo `[hidden]` não é compatível com os métodos JQuery `$(...).hide()` e `$(...).show()`. Portanto, atualmente, nós não usamos `[hidden]` no lugar de outras técnicas para gerenciar o `display` de elementos.
{% endcapture %}
{% include callout.html content=callout type="warning" %}

Para a simples troca de visibilidade de um elemento, sem modificar o valor do `display` e continuar permitindo que o elemento tenha efeito no fluxo do documento, use a class [`.invisible`]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/visibility/).

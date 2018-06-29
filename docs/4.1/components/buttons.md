---
layout: docs
title: Botões
description: Use os botões Bootstrap personalizados para ações em formulários, diálogos e outras coisas. Lembrando que esse componente tem suporte a escolha de tamanhos, estados e muito mais.
group: components
redirect_from: "/docs/4.1/components/"
toc: true
---

## Exemplos

Bootstrap possui vários estilos de botões pré-definidos, cada um com seu próprosito semântico e outros recursos extras para mais controle.

{% capture example %}
{% for color in site.data.theme-colors %}
<button type="button" class="btn btn-{{ color.name }}">{{ color.name | capitalize }}</button>{% endfor %}

<button type="button" class="btn btn-link">Link</button>
{% endcapture %}
{% include example.html content=example %}

{% include callout-warning-color-assistive-technologies.md %}

## Button tags

A classe `.btn` foi desenhada para ser usada com o elemento `<button>`. No entanto, você também pode usar esta classe nos elementos `<a>` ou `<input>`, apesar de alguns browser aplicarem um visual um pouco diferente.

Quando usando classes de botão em elementos `<a>` que funcionam como gatilhos in-page (igual aos conteúdos colapsáveis), invés de link para novas páginas ou seções dentro da página atual, estas âncoras devem receber `role="button"` para expliciar seu propósito a tecnologias assistivas, como leitores de telas.

{% capture example %}
<a class="btn btn-primary" href="#" role="button">Link</a>
<button class="btn btn-primary" type="submit">Botão</button>
<input class="btn btn-primary" type="button" value="Input">
<input class="btn btn-primary" type="submit" value="Submit">
<input class="btn btn-primary" type="reset" value="Reset">
{% endcapture %}
{% include example.html content=example %}

## Botões outline

Precisa de um botão, mas sem cor de backround? Substitua as classes modificadoras padrões pelas `.btn-outline-*` que removem todas as imagens de background e cores, em qualquer botão.

{% capture example %}
{% for color in site.data.theme-colors %}
<button type="button" class="btn btn-outline-{{ color.name }}">{{ color.name | capitalize }}</button>{% endfor %}
{% endcapture %}
{% include example.html content=example %}

## Tamanhos

Botões grandes ou pequenos? Use `.btn-lg` ou `.btn-sm` para tamanhos alternativos ao padrão.

{% capture example %}
<button type="button" class="btn btn-primary btn-lg">Botão grande</button>
<button type="button" class="btn btn-secondary btn-lg">Botão grande</button>
{% endcapture %}
{% include example.html content=example %}

{% capture example %}
<button type="button" class="btn btn-primary btn-sm">Botão pequeno</button>
<button type="button" class="btn btn-secondary btn-sm">Botão pequeno</button>
{% endcapture %}
{% include example.html content=example %}

Crie botões block-level (ocupam toda a largura do elemento pai), usando a classe `.btn-block`.

{% capture example %}
<button type="button" class="btn btn-primary btn-lg btn-block">Botão block-level</button>
<button type="button" class="btn btn-secondary btn-lg btn-block">Botão block-level</button>
{% endcapture %}
{% include example.html content=example %}

## Estado ativo

Os botões parecem pressionados (background, borda e sombra internas mais escuras), quando estão em estado ativo. **Não há necessidade de usar a classe no `<button>`, porque eles usam uma pseudo-classe.** No entanto, você ainda pode forçar a aparência de estado ativo com a classe `.active` e incuir o atributo <code>aria-pressed="true"</code>, se precisar.

{% capture example %}
<a href="#" class="btn btn-primary btn-lg active" role="button" aria-pressed="true">Link primário</a>
<a href="#" class="btn btn-secondary btn-lg active" role="button" aria-pressed="true">Link</a>
{% endcapture %}
{% include example.html content=example %}

## Estado desativado

Faça botões parecerem inativos, usando o atributo booleano `disabled` em qualquer elemento `<button>`.

{% capture example %}
<button type="button" class="btn btn-lg btn-primary" disabled>Botão primário</button>
<button type="button" class="btn btn-secondary btn-lg" disabled>Botão</button>
{% endcapture %}
{% include example.html content=example %}

Botões desativados usando o elemento `<a>` se comportam um pouco diferente:

- O elemento `<a>` não suport o atributo `disabled`, então, você deve usar a classe `.disabled` para fazê-lo parecer desativado, visualmente;
- Alguns estilos (que ainda não são bem suportados) são usados para desativarem todos os `pointer-events`, em botões âncora;
  - Em browsers que suportam essa propriedade, você não verá o cursor desativado.
- Botões desativados devem ter o atributo `aria-disabled="true"` para indicar o estado do elemento para tecnologias assistivas.

{% capture example %}
<a href="#" class="btn btn-primary btn-lg disabled" tabindex="-1" role="button" aria-disabled="true">Link primário</a>
<a href="#" class="btn btn-secondary btn-lg disabled" tabindex="-1" role="button" aria-disabled="true">Link</a>
{% endcapture %}
{% include example.html content=example %}

{% capture callout %}
##### Problemas com a funcionalidade de link

A class `.disabled` usa `pointer-events: none` para tentar desativar a funcionalidade de link do `<a>`, mas esta propriedade CSS ainda não foi padronizada. Além disso, até em navegadores que suportam `pointer-events: none`, a navegação por teclado continua inatingida, significando que tanto usuários com ou sem tecnologias assistivas ainda conseguirão ativar estes links. Portanto, para evitar isso, use o atributo `tabindex="-1"` (evita que tenham foco) nestes links e use seu próprio JavaScript  para desativar as funcionalidades.

{% endcapture %}
{% include callout.html content=callout type="warning" %}

## Plugin de botão

Faça mais com botões. Controle estados ou crie grupos de botões, para mais componentes como toolbars.

### Alternar estados

Use `data-toggle="button"` para alternar o estado `ativo` do botão. Se você pré-ativar o botão, deve usar a classe `.active` **e** o atributo `aria-pressed="true"`, no `<button>`.

{% capture example %}
<button type="button" class="btn btn-primary" data-toggle="button" aria-pressed="false" autocomplete="off">
  Única alternância
</button>
{% endcapture %}
{% include example.html content=example %}

### Botões checkbox e radio

Os estilos do `.button` Bootstrap podem seren usado em outros elementos, como `<label>` para se ter um botão no estilo checkbox ou radio com alternância. Use `data-toggle="buttons"` em um `.btn-group` para estilizar o os `inputs` dentro de seus botões. **Perceba que você pode criar botões com apenas um input ou grupos deles**.

O estado checado destes botões **só é atualizado através do evento de clique**, no botão. Se você usar outro método para atualizar o input (ex: `<input type="reset">` ou aplicando a propriedade `checked`, manualmente), vai precisar anternar a classe `.active` da `<label>`, manualmente.

Note que botões pré-checados requerem que você coloque a classe `.active`, manualmente, no input do `<label>`.

{% capture example %}
<div class="btn-group-toggle" data-toggle="buttons">
  <label class="btn btn-secondary active">
    <input type="checkbox" checked autocomplete="off"> Checado
  </label>
</div>
{% endcapture %}
{% include example.html content=example %}

{% capture example %}
<div class="btn-group btn-group-toggle" data-toggle="buttons">
  <label class="btn btn-secondary active">
    <input type="radio" name="options" id="option1" autocomplete="off" checked> Ativo
  </label>
  <label class="btn btn-secondary">
    <input type="radio" name="options" id="option2" autocomplete="off"> Radio
  </label>
  <label class="btn btn-secondary">
    <input type="radio" name="options" id="option3" autocomplete="off"> Radio
  </label>
</div>
{% endcapture %}
{% include example.html content=example %}

### Métodos

| Método | Descrição |
| --- | --- |
| `$().button('toggle')` | Alterna o estado. Dá ao botão uma aparência como se estivesse ativado. |
| `$().button('dispose')` | Destroi o botão de um elemento. |

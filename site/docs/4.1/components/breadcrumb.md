---
layout: docs
title: Breadcrumb
description: Indica a localização da página atual, dentro de uma hierarquia de navegação e, automaticamente, coloca separadores usando CSS.
group: components
---

## Exemplo

{% capture example %}
<nav aria-label="breadcrumb">
  <ol class="breadcrumb">
    <li class="breadcrumb-item active" aria-current="page">Home</li>
  </ol>
</nav>

<nav aria-label="breadcrumb">
  <ol class="breadcrumb">
    <li class="breadcrumb-item"><a href="#">Home</a></li>
    <li class="breadcrumb-item active" aria-current="page">Biblioteca</li>
  </ol>
</nav>

<nav aria-label="breadcrumb">
  <ol class="breadcrumb">
    <li class="breadcrumb-item"><a href="#">Home</a></li>
    <li class="breadcrumb-item"><a href="#">Biblioteca</a></li>
    <li class="breadcrumb-item active" aria-current="page">Dados</li>
  </ol>
</nav>
{% endcapture %}
{% include example.html content=example %}

## Como escolher o separador

Separadores são, automaticamente, adicionados com CSS usando [`::before`](https://developer.mozilla.org/en-US/docs/Web/CSS/::before) e [`content`](https://developer.mozilla.org/en-US/docs/Web/CSS/content). Você pode escolhê-los, alterando a variável `$breadcrumb-divider`. A função [quote](https://sass-lang.com/documentation/Sass/Script/Functions.html#quote-instance_method) é necessária para gerar as aspas ao redor de uma string, então, se você quer `>` como um separador, pode usar isso:
 
```scss
$breadcrumb-divider: quote(">");
```

Também é possível usar um **ícone SVG base64 embutido**:

```scss
$breadcrumb-divider: url(Dados:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSI4IiBoZWlnaHQ9IjgiPjxwYXRoIGQ9Ik0yLjUgMEwxIDEuNSAzLjUgNCAxIDYuNSAyLjUgOGw0LTQtNC00eiIgZmlsbD0iY3VycmVudENvbG9yIi8+PC9zdmc+);
```

O separador pode ser removido definindo o valor de `$breadcrumb-divider` como `none`:

```scss
$breadcrumb-divider: none;
```

## Acessibilidade

Já que breadcrumbs provém uma navegação, é uma boa ideia adicionar um atributo significativo como `aria-label="breadcrumb"` para descrever o tipo de navegação provida no elemento `<nav>`, assim como aplicar um `aria-current="page"` ao último item para indicar que ele representa a atual página.

Para mais informações, veja: [WAI-ARIA Authoring Practices for the breadcrumb pattern](https://www.w3.org/TR/wai-aria-practices/#breadcrumb).

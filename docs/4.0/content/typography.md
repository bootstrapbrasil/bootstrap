---
layout: docs
title: Tipografia
description: Documentação e exemplos para a tipografia Bootstrap, incluindo configurações globais, cabeçalhos, listas, texto do `<body>` e outros.
group: content
toc: true
---

## Configurações globais

O Bootstrap configura estilos básicos para display, tipografia e links, globalmente. Quando precisar de mais controle, confira as [classes utilitárias de texto]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/text/).

- Usa-se uma [pilha de fontes nativas]({{ site.baseurl }}/docs/{{ site.docs_version }}/content/reboot/#native-font-stack) que seleciona a melhor `font-family` para cada SO e dispositivo;
- Para tipografia mais inclusiva e acessível em escala, nós usamos as `font-size`s padrões dos navegadores (tipicamente 16px), então, visitantes podem customizar os padrões de seus browser, sempre que necessário;
- Usamos as variáveis `$font-family-base`, `$font-size-base` e `$line-height-base` como nossa base tipografica aplicada ao `<body>`;
- Configuramos as cores de links globalmente, através da `$link-color` e aplicamos _underlines_ só em estado `:hover`;
- Utilizamos a variável `$body-bg` para colocar `background-color` no `<body>` (`#fff` é o valor padrão).

Estes estilos podem ser encontrados dentro do arquivo `_reboot.scss` e a variáveis globais são declaradas em `_variables.scss`. Tenha certeza de configurar `$font-size-base` usando `rem`.

## Cabeçalhos

Todos cabeçalhos HTML (`<h1>` até `<h6>`) estão disponíveis.

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

{% highlight html %}
<h1>h1. Cabeçalho Bootstrap</h1>
<h2>h2. Cabeçalho Bootstrap</h2>
<h3>h3. Cabeçalho Bootstrap</h3>
<h4>h4. Cabeçalho Bootstrap</h4>
<h5>h5. Cabeçalho Bootstrap</h5>
<h6>h6. Cabeçalho Bootstrap</h6>
{% endhighlight %}

As classes de `.h1` até `.h6` também estão disponíveis, para quando você quiser usar os estilos de um cabeçalho mas não pode usar os elementos em si.

{% example html %}
<p class="h1">h1. Cabeçalho Bootstrap</p>
<p class="h2">h2. Cabeçalho Bootstrap</p>
<p class="h3">h3. Cabeçalho Bootstrap</p>
<p class="h4">h4. Cabeçalho Bootstrap</p>
<p class="h5">h5. Cabeçalho Bootstrap</p>
<p class="h6">h6. Cabeçalho Bootstrap</p>
{% endexample %}

### Customizando cabeçalhos

Use as classes utilitárias para recriar aquele cabeçalho secundário do Bootstrap 3.

<div class="bd-Exemplo">
  <span class="h3">
    Exemplo de cabeçalho chique
    <small class="text-muted">Com texto secundário e mais apagado</small>
  </span>
</div>

{% highlight html %}
<h3>
  Exemplo de cabeçalho chique
  <small class="text-muted">Com texto secundário e mais apagado</small>
</h3>
{% endhighlight %}

## Classes display para cabeçalhos

Elementos de cabeçalhos tradicionais são desenvolvidos para funcionar melhor no miolo do conteúdo da página. Quando você precisa que um cabeçalho se destaque, considere usar uma **classe display** (provê cabeçalhos maiores e levemente mais estilizados).

<div class="bd-exemple bd-exemple-type">
  <table class="table">
    <tbody>
      <tr>
        <td><span class="display-1">Display 1</span></td>
      </tr>
      <tr>
      <td><span class="display-2">Display 2</span></td>
      </tr>
      <tr>
      <td><span class="display-3">Display 3</span></td>
      </tr>
      <tr>
      <td><span class="display-4">Display 4</span></td>
      </tr>
    </tbody>
  </table>
</div>

{% highlight html %}
<h1 class="display-1">Display 1</h1>
<h1 class="display-2">Display 2</h1>
<h1 class="display-3">Display 3</h1>
<h1 class="display-4">Display 4</h1>
{% endhighlight %}

## Parágrafo destaque

Faça um parágrafo se destacar, adicionando a classe `.lead`.

{% example html %}
<p class="lead">
  Vivamus sagittis lacus vel augue laoreet rutrum faucibus dolor auctor. Duis mollis, est non commodo luctus.
</p>
{% endexample %}

## Elementos de texto inline

Estilos para elementos inline HTML5, mais comuns.

{% example html %}
<p>Você pode usar a tag _mark_ para <mark>destacar</mark> textos.</p>
<p><del>Esta linha de texto deve ser tratada com um texto deletado.</del></p>
<p><s>Esta linha de texto deve ser tratada como algo impreciso.</s></p>
<p><ins>Esta linha de texto deve ser tratada como uma adição ao documento.</ins></p>
<p><u>Esta linha de texto vai ser renderizada com underline.</u></p>
<p><small>Esta linha deve ser usada para letras com tamanhos menores.</small></p>
<p><strong>Esta linha renderiza em negrito.</strong></p>
<p><em>Esta linha renderiza em itálico.</em></p>
{% endexample %}

As classes `.mark` e `.small` também são úteis para aplicar os mesmos estilos que os elementos `<mark>` e `<small>`, sem precisar usar implicações semânticas que viriam com as tags.

Apesar de não ter sido demonstrado, sinta-se livre para usar as tags `<b>` e `<i>`, no HTML. O `<b>` é suposto a destacar palavras ou frases sem importância adicional, enquanto o `<i>` é mais para vozes, termos técnicos e etc.

## Utilitários de texto

Altere alinhamento de texto, `transform`, estilos, espessura e cor com nossos [utilitários de texto]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/text/) e [utilitários de cores]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/colors/).

## Abreviações

Implementação customizada do elemento HTML `<abbr>` (para abreviações e acrônimos), o qual mostra versões expandidas no estado _hover_. Abreviações tem uma _underline_ padrão e cursor de ajuda, para criar um contexto mais rico em estado _hover_ e para usuários de tecnologias assistivas.

Use `.initialism` em uma abreviação, para uma `font-size` um pouquinho menor.

{% example html %}
<p><abbr title="attribute">attr</abbr></p>
<p><abbr title="HyperText Markup Language" class="initialism">HTML</abbr></p>
{% endexample %}

## Bloco de citação

Para citar blocos de conteúdos de outras fontes, dentro do seu documento, use `<blockquote class="blockquote">` em volta de qualquer conteúdo <abbr title="HyperText Markup Language">HTML</abbr>.

{% example html %}
<blockquote class="blockquote">
  <p class="mb-0">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer posuere erat a ante.</p>
</blockquote>
{% endexample %}

### Declarando a fonte

Use `<footer class="blockquote-footer">` para identificar uma fonte. Envolva o nome da fonte do trabalho usando `<cite>`.

{% example html %}
<blockquote class="blockquote">
  <p class="mb-0">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer posuere erat a ante.</p>
  <footer class="blockquote-footer">Alguém famoso na <cite title="Título da fonte">Título da fonte</cite></footer>
</blockquote>
{% endexample %}

### Alinhamento

Use utilitários de texto o quanto seja necessário, para alterar o alinhamento de seu bloco de citação.

{% example html %}
<blockquote class="blockquote text-center">
  <p class="mb-0">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer posuere erat a ante.</p>
  <footer class="blockquote-footer">Alguém famoso na <cite title="Título da fonte">Título da fonte</cite></footer>
</blockquote>
{% endexample %}

{% example html %}
<blockquote class="blockquote text-right">
  <p class="mb-0">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer posuere erat a ante.</p>
  <footer class="blockquote-footer">Alguém famoso na <cite title="Título da fonte">Título da fonte</cite></footer>
</blockquote>
{% endexample %}

## Listas

### Sem estilos

Remova o `list-style` padrão e margem à esquerda, nos itens da lista (apenas funciona em filhos imediatos). **Isso só se aplica a itens que são filhos imediatos**, significando que você irá precisar usar a classe em outras listas aninhadas.

{% example html %}
<ul class="list-unstyled">
  <li>Lorem ipsum dolor sit amet</li>
  <li>Consectetur adipiscing elit</li>
  <li>Integer molestie lorem at massa</li>
  <li>Facilisis in pretium nisl aliquet</li>
  <li>Nulla volutpat aliquam velit
    <ul>
      <li>Phasellus iaculis neque</li>
      <li>Purus sodales ultricies</li>
      <li>Vestibulum laoreet porttitor sem</li>
      <li>Ac tristique libero volutpat at</li>
    </ul>
  </li>
  <li>Faucibus porta lacus fringilla vel</li>
  <li>Aenean sit amet erat nunc</li>
  <li>Eget porttitor lorem</li>
</ul>
{% endexample %}

### Inline

Remova as marcações de uma lista e adicione uma leve margem com uma combinação de duas classes: `.list-inline` e `.list-inline-item`.

{% example html %}
<ul class="list-inline">
  <li class="list-inline-item">Lorem ipsum</li>
  <li class="list-inline-item">Phasellus iaculis</li>
  <li class="list-inline-item">Nulla volutpat</li>
</ul>
{% endexample %}

### Alinhamento de listas de descrições

Alinhe termos e descrições, horizontalmente, usando nossas classes do nosso sistema de _grid_ (ou mixins semânticos). Para termos mais longos, você pode usar a classe `.text-truncate` para truncar o texto em elipse, opcionalmente.

{% example html %}
<dl class="row">
  <dt class="col-sm-3">Listas de descrições</dt>
  <dd class="col-sm-9">Uma lista de descrições é perfeita para definir termos.</dd>

  <dt class="col-sm-3">Euismod</dt>
  <dd class="col-sm-9">
    <p>Vestibulum id ligula porta felis euismod semper eget lacinia odio sem nec elit.</p>
    <p>Donec id elit non mi porta gravida at eget metus.</p>
  </dd>

  <dt class="col-sm-3">Malesuada porta</dt>
  <dd class="col-sm-9">Etiam porta sem malesuada magna mollis euismod.</dd>

  <dt class="col-sm-3 text-truncate">Truncated term is truncated</dt>
  <dd class="col-sm-9">Fusce dapibus, tellus ac cursus commodo, tortor mauris condimentum nibh, ut fermentum massa justo sit amet risus.</dd>

  <dt class="col-sm-3">Aninhamento</dt>
  <dd class="col-sm-9">
    <dl class="row">
      <dt class="col-sm-4">Lista de defiinições aninhada</dt>
      <dd class="col-sm-8">Aenean posuere, tortor sed cursus feugiat, nunc augue blandit nunc.</dd>
    </dl>
  </dd>
</dl>
{% endexample %}

## Tipografia responsiva

*Tipografia responsiva* se refere a escala de textos e componentes, simplesmente ajustando a `font-size` dos elementos raizes, usando várias media queries. Bootstrap não faz isso por você, mas é muito fácil se você quiser.

Abaixo vai um exemplo disso, na prática. Escolha qualquer `font-size` e media querie que quiser.

{% highlight scss %}
html {
  font-size: 1rem;
}

@include media-breakpoint-up(sm) {
  html {
    font-size: 1.2rem;
  }
}

@include media-breakpoint-up(md) {
  html {
    font-size: 1.4rem;
  }
}

@include media-breakpoint-up(lg) {
  html {
    font-size: 1.6rem;
  }
}
{% endhighlight %}

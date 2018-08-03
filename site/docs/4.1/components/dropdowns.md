---
layout: docs
title: Dropdowns
description: Clique em botões para ver um lista de links e outras coisas, usando o plugin Bootstrap dropdown.
group: components
toc: true
---

## Visão Geral

Dropdowns são botões com alternância de visibilidade de listas de links e outras coisas. Conseguem ser interativos graças a sua construção que foi feita com o plugin JavaScript dropdown. A visibilidade do conteúdo é alternada com cliques e nunca só ao passar o mouse em cima do botão ([uma decisão de design intencional](http://markdotto.com/2012/02/27/bootstrap-explained-dropdowns/)).

Dropdowns são feitos em cima de uma biblioteca de terceiros, [Popper.js](https://popper.js.org/), a qual permite posicionamento dinâmico e detecção de viewport. Se assegure de invocar [popper.min.js]({{ site.cdn.popper }}), antes do JavaScript Bootstrap ou use `bootstrap.bundle.min.js` / `bootstrap.bundle.js`, os quais já possuem o Popper.js. No entanto, Popper.js não é usada para posicionar dropdowns em navbars, já que posicionamento dinâmico não é necessário.

Se você está construindo nosso JavaScript a partir da fonte, vai precisar do [`util.js`]({{ site.baseurl }}/docs/{{ site.docs_version }}/getting-started/javascript/#util).

## Acessibilidade

O padrões [<abbr title="Web Accessibility Initiative">WAI</abbr> <abbr title="Accessible Rich Internet Applications">ARIA</abbr>](https://www.w3.org/TR/wai-aria/) pedem o uso do atributo `role="menu"`, mas ele é específico para menus de aplicações que ativam ações ou funções. Menus <abbr title="Accessible Rich Internet Applications">ARIA</abbr> só podem conter itens de menu, checkbox, grupos e botões radio, além de sub-menus.

Os dropdowns Bootstrap, por outro lado, são desenhados para serem genéricos e aplicáveis em várias situações e estruturas de marcação. Por exemplo, é possível criar dropdowns que possuem inputs e form controls adicionais, como campos de pesquisa ou formulários de login. Por essa razão, Bootstrap não espera (nem adiciona automaticamente) a presença dos atributos `role` e `aria`, exigidos nos reais menus <abbr title="Accessible Rich Internet Applications">ARIA</abbr>. Os autores terão que incluí-los, por si só.

No entanto, Bootstrap tem suporte para a maioria das interações padrões de teclado, como a habilidade de mover-se através de elementos individuais `dropdown-item` (usando o as setinhas do teclado) ou fechar o menu com a tecla <kbd>ESC</kbd>.

## Exemplos

Envolte os itens ou menu dropdown dentro da classe `.dropdown` ou qualquer outro elemento que tenha `position: relative;` declarado. Dropdowns podem ser acionados de um elemento `<a>` ou `<button>`, te dando mais flexibilidade.

### Único botão

Qualquer `.btn` pode se transformar em um dropdown, com algumas adições na marcação HTML. 

Aqui está como você pode fazê-los funcionar, usando `<button>`:

{% capture example %}
<div class="dropdown">
  <button class="btn btn-secondary dropdown-toggle" type="button" id="dropdownMenuButton" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
    Botão dropdown
  </button>
  <div class="dropdown-menu" aria-labelledby="dropdownMenuButton">
    <a class="dropdown-item" href="#">Alguma ação</a>
    <a class="dropdown-item" href="#">Outra ação</a>
    <a class="dropdown-item" href="#">Alguma coisa aqui</a>
  </div>
</div>
{% endcapture %}
{% include example.html content=example %}

Já aqui, temos um exemplo de uso com o elemento `<a>`:

{% capture example %}
<div class="dropdown">
  <a class="btn btn-secondary dropdown-toggle" href="#" role="button" id="dropdownMenuLink" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
    Link dropdown
  </a>

  <div class="dropdown-menu" aria-labelledby="dropdownMenuLink">
    <a class="dropdown-item" href="#">Alguma ação</a>
    <a class="dropdown-item" href="#">Outra ação</a>
    <a class="dropdown-item" href="#">Alguma coisa aqui</a>
  </div>
</div>
{% endcapture %}
{% include example.html content=example %}

O melhor é que você pode fazer isso com qualquer variante de botão, também:

<div class="bd-example">
  <div class="btn-group">
    <button type="button" class="btn btn-primary dropdown-toggle" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">Primary</button>
    <div class="dropdown-menu">
      <a class="dropdown-item" href="#">Alguma ação</a>
      <a class="dropdown-item" href="#">Outra ação</a>
      <a class="dropdown-item" href="#">Alguma coisa aqui</a>
      <div class="dropdown-divider"></div>
      <a class="dropdown-item" href="#">Link separado</a>
    </div>
  </div><!-- /btn-group -->
  <div class="btn-group">
    <button type="button" class="btn btn-secondary dropdown-toggle" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">Secondary</button>
    <div class="dropdown-menu">
      <a class="dropdown-item" href="#">Alguma ação</a>
      <a class="dropdown-item" href="#">Outra ação</a>
      <a class="dropdown-item" href="#">Alguma coisa aqui</a>
      <div class="dropdown-divider"></div>
      <a class="dropdown-item" href="#">Link separado</a>
    </div>
  </div><!-- /btn-group -->
  <div class="btn-group">
    <button type="button" class="btn btn-success dropdown-toggle" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">Success</button>
    <div class="dropdown-menu">
      <a class="dropdown-item" href="#">Alguma ação</a>
      <a class="dropdown-item" href="#">Outra ação</a>
      <a class="dropdown-item" href="#">Alguma coisa aqui</a>
      <div class="dropdown-divider"></div>
      <a class="dropdown-item" href="#">Link separado</a>
    </div>
  </div><!-- /btn-group -->
  <div class="btn-group">
    <button type="button" class="btn btn-info dropdown-toggle" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">Info</button>
    <div class="dropdown-menu">
      <a class="dropdown-item" href="#">Alguma ação</a>
      <a class="dropdown-item" href="#">Outra ação</a>
      <a class="dropdown-item" href="#">Alguma coisa aqui</a>
      <div class="dropdown-divider"></div>
      <a class="dropdown-item" href="#">Link separado</a>
    </div>
  </div><!-- /btn-group -->
  <div class="btn-group">
    <button type="button" class="btn btn-warning dropdown-toggle" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">Warning</button>
    <div class="dropdown-menu">
      <a class="dropdown-item" href="#">Alguma ação</a>
      <a class="dropdown-item" href="#">Outra ação</a>
      <a class="dropdown-item" href="#">Alguma coisa aqui</a>
      <div class="dropdown-divider"></div>
      <a class="dropdown-item" href="#">Link separado</a>
    </div>
  </div><!-- /btn-group -->
  <div class="btn-group">
    <button type="button" class="btn btn-danger dropdown-toggle" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">Danger</button>
    <div class="dropdown-menu">
      <a class="dropdown-item" href="#">Alguma ação</a>
      <a class="dropdown-item" href="#">Outra ação</a>
      <a class="dropdown-item" href="#">Alguma coisa aqui</a>
      <div class="dropdown-divider"></div>
      <a class="dropdown-item" href="#">Link separado</a>
    </div>
  </div><!-- /btn-group -->
</div>

{% highlight html %}
<!-- Exemplo de único botão danger -->
<div class="btn-group">
  <button type="button" class="btn btn-danger dropdown-toggle" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
    Ação
  </button>
  <div class="dropdown-menu">
    <a class="dropdown-item" href="#">Alguma ação</a>
    <a class="dropdown-item" href="#">Outra ação</a>
    <a class="dropdown-item" href="#">Alguma coisa aqui</a>
    <div class="dropdown-divider"></div>
    <a class="dropdown-item" href="#">Link separado</a>
  </div>
</div>
{% endhighlight %}

### Botão dividido

Similarmente, crie botões divididos com a mesma marcação HTML de botões dropdowns, mas com a adição da classe `.dropdown-toggle-split` para espaçamento apropriado, ao redor da setinha.

Nós usamos esta classe extra para reduzir o `padding` horizontal, em 25% dos lados da setinha e remover a `margin-left` que é adicionada em botões dropdowns comuns. Estas mudanças extras mantém a setinha centralizada e dá uma área de clique maior, no botão principal.

<div class="bd-example">
  <div class="btn-group">
    <button type="button" class="btn btn-primary">Primary</button>
    <button type="button" class="btn btn-primary dropdown-toggle dropdown-toggle-split" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
      <span class="sr-only">Dropdown</span>
    </button>
    <div class="dropdown-menu">
      <a class="dropdown-item" href="#">Alguma ação</a>
      <a class="dropdown-item" href="#">Outra ação</a>
      <a class="dropdown-item" href="#">Alguma coisa aqui</a>
      <div class="dropdown-divider"></div>
      <a class="dropdown-item" href="#">Link separado</a>
    </div>
  </div><!-- /btn-group -->
  <div class="btn-group">
    <button type="button" class="btn btn-secondary">Secondary</button>
    <button type="button" class="btn btn-secondary dropdown-toggle dropdown-toggle-split" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
      <span class="sr-only">Dropdown</span>
    </button>
    <div class="dropdown-menu">
      <a class="dropdown-item" href="#">Alguma ação</a>
      <a class="dropdown-item" href="#">Outra ação</a>
      <a class="dropdown-item" href="#">Alguma coisa aqui</a>
      <div class="dropdown-divider"></div>
      <a class="dropdown-item" href="#">Link separado</a>
    </div>
  </div><!-- /btn-group -->
  <div class="btn-group">
    <button type="button" class="btn btn-success">Success</button>
    <button type="button" class="btn btn-success dropdown-toggle dropdown-toggle-split" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
      <span class="sr-only">Dropdown</span>
    </button>
    <div class="dropdown-menu">
      <a class="dropdown-item" href="#">Alguma ação</a>
      <a class="dropdown-item" href="#">Outra ação</a>
      <a class="dropdown-item" href="#">Alguma coisa aqui</a>
      <div class="dropdown-divider"></div>
      <a class="dropdown-item" href="#">Link separado</a>
    </div>
  </div><!-- /btn-group -->
  <div class="btn-group">
    <button type="button" class="btn btn-info">Info</button>
    <button type="button" class="btn btn-info dropdown-toggle dropdown-toggle-split" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
      <span class="sr-only">Dropdown</span>
    </button>
    <div class="dropdown-menu">
      <a class="dropdown-item" href="#">Alguma ação</a>
      <a class="dropdown-item" href="#">Outra ação</a>
      <a class="dropdown-item" href="#">Alguma coisa aqui</a>
      <div class="dropdown-divider"></div>
      <a class="dropdown-item" href="#">Link separado</a>
    </div>
  </div><!-- /btn-group -->
  <div class="btn-group">
    <button type="button" class="btn btn-warning">Warning</button>
    <button type="button" class="btn btn-warning dropdown-toggle dropdown-toggle-split" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
      <span class="sr-only">Dropdown</span>
    </button>
    <div class="dropdown-menu">
      <a class="dropdown-item" href="#">Alguma ação</a>
      <a class="dropdown-item" href="#">Outra ação</a>
      <a class="dropdown-item" href="#">Alguma coisa aqui</a>
      <div class="dropdown-divider"></div>
      <a class="dropdown-item" href="#">Link separado</a>
    </div>
  </div><!-- /btn-group -->
  <div class="btn-group">
    <button type="button" class="btn btn-danger">Danger</button>
    <button type="button" class="btn btn-danger dropdown-toggle dropdown-toggle-split" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
      <span class="sr-only">Dropdown</span>
    </button>
    <div class="dropdown-menu">
      <a class="dropdown-item" href="#">Alguma ação</a>
      <a class="dropdown-item" href="#">Outra ação</a>
      <a class="dropdown-item" href="#">Alguma coisa aqui</a>
      <div class="dropdown-divider"></div>
      <a class="dropdown-item" href="#">Link separado</a>
    </div>
  </div><!-- /btn-group -->
</div>

{% highlight html %}
<!-- Exemplo de botão danger dividido -->
<div class="btn-group">
  <button type="button" class="btn btn-danger">Ação</button>
  <button type="button" class="btn btn-danger dropdown-toggle dropdown-toggle-split" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
    <span class="sr-only">Dropdown</span>
  </button>
  <div class="dropdown-menu">
    <a class="dropdown-item" href="#">Alguma ação</a>
    <a class="dropdown-item" href="#">Outra ação</a>
    <a class="dropdown-item" href="#">Alguma coisa aqui</a>
    <div class="dropdown-divider"></div>
    <a class="dropdown-item" href="#">Link separado</a>
  </div>
</div>
{% endhighlight %}

## Tamanhos

Tanto os dropdowns padrões, quanto os divididos, funcionam em todos os tamanhos.

<div class="bd-example">
  <div class="btn-toolbar" role="toolbar">
    <div class="btn-group">
      <button class="btn btn-secondary btn-lg dropdown-toggle" type="button" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
        Botão grande
      </button>
      <div class="dropdown-menu">
        <a class="dropdown-item" href="#">Alguma ação</a>
        <a class="dropdown-item" href="#">Outra ação</a>
        <a class="dropdown-item" href="#">Alguma coisa aqui</a>
        <div class="dropdown-divider"></div>
        <a class="dropdown-item" href="#">Link separado</a>
      </div>
    </div><!-- /btn-group -->
    <div class="btn-group ml-2">
      <button type="button" class="btn btn-lg btn-secondary">Botão dividido grande</button>
      <button type="button" class="btn btn-lg btn-secondary dropdown-toggle dropdown-toggle-split" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
        <span class="sr-only">Dropdown</span>
      </button>
      <div class="dropdown-menu">
        <a class="dropdown-item" href="#">Alguma ação</a>
        <a class="dropdown-item" href="#">Outra ação</a>
        <a class="dropdown-item" href="#">Alguma coisa aqui</a>
        <div class="dropdown-divider"></div>
        <a class="dropdown-item" href="#">Link separado</a>
      </div>
    </div><!-- /btn-group -->
  </div><!-- /btn-toolbar -->
  <div class="btn-toolbar" role="toolbar">
    <div class="btn-group">
      <button class="btn btn-secondary btn-sm dropdown-toggle" type="button" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
        Botão pequeno
      </button>
      <div class="dropdown-menu">
        <a class="dropdown-item" href="#">Alguma ação</a>
        <a class="dropdown-item" href="#">Outra ação</a>
        <a class="dropdown-item" href="#">Alguma coisa aqui</a>
        <div class="dropdown-divider"></div>
        <a class="dropdown-item" href="#">Link separado</a>
      </div>
    </div><!-- /btn-group -->
    <div class="btn-group ml-2">
      <button type="button" class="btn btn-sm btn-secondary">Botão dividido pequeno</button>
      <button type="button" class="btn btn-sm btn-secondary dropdown-toggle dropdown-toggle-split" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
        <span class="sr-only">Dropdown</span>
      </button>
      <div class="dropdown-menu">
        <a class="dropdown-item" href="#">Alguma ação</a>
        <a class="dropdown-item" href="#">Outra ação</a>
        <a class="dropdown-item" href="#">Alguma coisa aqui</a>
        <div class="dropdown-divider"></div>
        <a class="dropdown-item" href="#">Link separado</a>
      </div>
    </div><!-- /btn-group -->
  </div><!-- /btn-toolbar -->
</div><!-- /example -->

{% highlight html %}
<!-- Grupo de botões grandes (padrões e divididos) -->
<div class="btn-group">
  <button class="btn btn-secondary btn-lg dropdown-toggle" type="button" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
    Botão grande
  </button>
  <div class="dropdown-menu">
    ...
  </div>
</div>
<div class="btn-group">
  <button class="btn btn-secondary btn-lg" type="button">
    Botão grande dividido
  </button>
  <button type="button" class="btn btn-lg btn-secondary dropdown-toggle dropdown-toggle-split" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
    <span class="sr-only">Dropdown</span>
  </button>
  <div class="dropdown-menu">
    ...
  </div>
</div>

<!-- Grupo de botões pequenos (padrão e dividido) -->
<div class="btn-group">
  <button class="btn btn-secondary btn-sm dropdown-toggle" type="button" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
    Botão pequeno
  </button>
  <div class="dropdown-menu">
    ...
  </div>
</div>
<div class="btn-group">
  <button class="btn btn-secondary btn-sm" type="button">
    Botão pequeno dividido
  </button>
  <button type="button" class="btn btn-sm btn-secondary dropdown-toggle dropdown-toggle-split" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
    <span class="sr-only">Dropdown</span>
  </button>
  <div class="dropdown-menu">
    ...
  </div>
</div>
{% endhighlight %}

## Direções

### Dropup

Acione menus para cima, usando a classe `.dropup` no elemento pai.

<div class="bd-example">
  <div class="btn-group dropup">
    <button type="button" class="btn btn-secondary dropdown-toggle" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
      Dropup
    </button>
    <div class="dropdown-menu">
      <a class="dropdown-item" href="#">Alguma ação</a>
      <a class="dropdown-item" href="#">Outra ação</a>
      <a class="dropdown-item" href="#">Alguma coisa aqui</a>
      <div class="dropdown-divider"></div>
      <a class="dropdown-item" href="#">Link separado</a>
    </div>
  </div>

  <div class="btn-group dropup">
    <button type="button" class="btn btn-secondary">
      Dropup dividido
    </button>
    <button type="button" class="btn btn-secondary dropdown-toggle dropdown-toggle-split" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
      <span class="sr-only">Dropdown</span>
    </button>
    <div class="dropdown-menu">
      <a class="dropdown-item" href="#">Alguma ação</a>
      <a class="dropdown-item" href="#">Outra ação</a>
      <a class="dropdown-item" href="#">Alguma coisa aqui</a>
      <div class="dropdown-divider"></div>
      <a class="dropdown-item" href="#">Link separado</a>
    </div>
  </div>
</div>

{% highlight html %}
<!-- Botão dropup padrão -->
<div class="btn-group dropup">
  <button type="button" class="btn btn-secondary dropdown-toggle" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
    Dropup
  </button>
  <div class="dropdown-menu">
    <!-- Links do menu dropup -->
  </div>
</div>

<!-- Botão dropup dividido -->
<div class="btn-group dropup">
  <button type="button" class="btn btn-secondary">
    Dropup dividido
  </button>
  <button type="button" class="btn btn-secondary dropdown-toggle dropdown-toggle-split" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
    <span class="sr-only">Dropdown</span>
  </button>
  <div class="dropdown-menu">
    <!-- Dropdown menu links -->
  </div>
</div>
{% endhighlight %}

### Dropright

Acione menus para a direita, usando `.dropright` no elemento pai.

<div class="bd-example">
  <div class="btn-group dropright">
    <button type="button" class="btn btn-secondary dropdown-toggle" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
      Dropright
    </button>
    <div class="dropdown-menu">
      <a class="dropdown-item" href="#">Alguma ação</a>
      <a class="dropdown-item" href="#">Outra ação</a>
      <a class="dropdown-item" href="#">Alguma coisa aqui</a>
      <div class="dropdown-divider"></div>
      <a class="dropdown-item" href="#">Link separado</a>
    </div>
  </div>

  <div class="btn-group dropright">
    <button type="button" class="btn btn-secondary">
      Dropright dividido
    </button>
    <button type="button" class="btn btn-secondary dropdown-toggle dropdown-toggle-split" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
      <span class="sr-only">Toggle Dropright</span>
    </button>
    <div class="dropdown-menu">
      <a class="dropdown-item" href="#">Alguma ação</a>
      <a class="dropdown-item" href="#">Outra ação</a>
      <a class="dropdown-item" href="#">Alguma coisa aqui</a>
      <div class="dropdown-divider"></div>
      <a class="dropdown-item" href="#">Link separado</a>
    </div>
  </div>
</div>

{% highlight html %}
<!-- Botão dropright padrão -->
<div class="btn-group dropright">
  <button type="button" class="btn btn-secondary dropdown-toggle" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
    Dropright
  </button>
  <div class="dropdown-menu">
    <!-- Links do menu dropright -->
  </div>
</div>

<!-- Botão dropright dividido -->
<div class="btn-group dropright">
  <button type="button" class="btn btn-secondary">
    Dropright dividido
  </button>
  <button type="button" class="btn btn-secondary dropdown-toggle dropdown-toggle-split" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
    <span class="sr-only">Dropright</span>
  </button>
  <div class="dropdown-menu">
    <!-- Links do menu dropright -->
  </div>
</div>
{% endhighlight %}

### Dropleft

Acione menus a esquerda, usando a classe `.dropleft` no elemento pai.

<div class="bd-example">
  <div class="btn-group dropleft">
    <button type="button" class="btn btn-secondary dropdown-toggle" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
      Dropleft
    </button>
    <div class="dropdown-menu">
      <a class="dropdown-item" href="#">Alguma ação</a>
      <a class="dropdown-item" href="#">Outra ação</a>
      <a class="dropdown-item" href="#">Alguma coisa aqui</a>
      <div class="dropdown-divider"></div>
      <a class="dropdown-item" href="#">Link separado</a>
    </div>
  </div>

  <div class="btn-group">
    <div class="btn-group dropleft" role="group">
      <button type="button" class="btn btn-secondary dropdown-toggle dropdown-toggle-split" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
        <span class="sr-only">Dropleft</span>
      </button>
      <div class="dropdown-menu">
        <a class="dropdown-item" href="#">Alguma ação</a>
        <a class="dropdown-item" href="#">Outra ação</a>
        <a class="dropdown-item" href="#">Alguma coisa aqui</a>
        <div class="dropdown-divider"></div>
        <a class="dropdown-item" href="#">Link separado</a>
      </div>
    </div>
    <button type="button" class="btn btn-secondary">
      Dropleft dividido
    </button>
  </div>
</div>

{% highlight html %}
<!-- Botão dropleft padrão -->
<div class="btn-group dropleft">
  <button type="button" class="btn btn-secondary dropdown-toggle" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
    Dropleft
  </button>
  <div class="dropdown-menu">
    <!-- Links do menu dropleft -->
  </div>
</div>

<!-- Botão dropleft dividido -->
<div class="btn-group">
  <div class="btn-group dropleft" role="group">
    <button type="button" class="btn btn-secondary dropdown-toggle dropdown-toggle-split" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
      <span class="sr-only">Dropleft</span>
    </button>
    <div class="dropdown-menu">
      <!-- Links do menu dropleft -->
    </div>
  </div>
  <button type="button" class="btn btn-secondary">
    Dropleft dividido
  </button>
</div>
{% endhighlight %}

## Itens do menu

Historicamente, o conteúdo dos dropdowns *tinham* que ser links, mas isso não é mais o caso, na v4. Agora, você pode usar elementos `<button>` em seus dropdowns, invés de `<a>`.

{% capture example %}
<div class="dropdown">
  <button class="btn btn-secondary dropdown-toggle" type="button" id="dropdownMenu2" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
    Dropdown
  </button>
  <div class="dropdown-menu" aria-labelledby="dropdownMenu2">
    <button class="dropdown-item" type="button">Ação</button>
    <button class="dropdown-item" type="button">Another Ação</button>
    <button class="dropdown-item" type="button">Something else here</button>
  </div>
</div>
{% endcapture %}
{% include example.html content=example %}

Você também pode criar dropdowns com itens não interativos, usando `.dropdown-item-text`. Sinta-se livre para fazer mais estilizações com CSS ou utilitários de texto.

{% capture example %}
<div class="dropdown-menu">
  <span class="dropdown-item-text">Texto do item dropdown</span>
  <a class="dropdown-item" href="#">Alguma ação</a>
  <a class="dropdown-item" href="#">Outra ação</a>
  <a class="dropdown-item" href="#">Alguma coisa aqui</a>
</div>
{% endcapture %}
{% include example.html content=example %}

### Ativo

Use `.active` nos itens do dropdown para **estilizar eles como ativos**.

{% capture example %}
<div class="dropdown-menu">
  <a class="dropdown-item" href="#">Link comum</a>
  <a class="dropdown-item active" href="#">Link ativo</a>
  <a class="dropdown-item" href="#">Outro link</a>
</div>
{% endcapture %}
{% include example.html content=example %}

### Desativado

Coloque `.disabled` nos itens do dropdown para **estilizar eles como desativados**.

{% capture example %}
<div class="dropdown-menu">
  <a class="dropdown-item" href="#">Link comum</a>
  <a class="dropdown-item disabled" href="#">Link desativado</a>
  <a class="dropdown-item" href="#">Outro link</a>
</div>
{% endcapture %}
{% include example.html content=example %}

## Alinhamento de menu

Por padrão, o menu dropdown é, automaticamente, posicionado 100% a partir do topo e esquerda do elemento pai. Use `.dropdown-menu-right` em um `.dropdown-menu` para alinhar o menu dropdown a direita.

{% capture callout %}
**Atenção!** Dropdowns são posicionados com ajuda do Popper.js (exceto quando estão dentro de uma navbar).

{% endcapture %}
{% include callout.html content=callout type="info" %}

{% capture example %}
<div class="btn-group">
  <button type="button" class="btn btn-secondary dropdown-toggle" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
    Menu alinhado a direita
  </button>
  <div class="dropdown-menu dropdown-menu-right">
    <button class="dropdown-item" type="button">Ação</button>
    <button class="dropdown-item" type="button">Another Ação</button>
    <button class="dropdown-item" type="button">Algo mais aqui</button>
  </div>
</div>
{% endcapture %}
{% include example.html content=example %}

## Conteúdo do menu

### Cabeçalho

Coloque um cabeçalho para rotular seções, no menu dropdown.

{% capture example %}
<div class="dropdown-menu">
  <h6 class="dropdown-header">Cabeçalho dropdown</h6>
  <a class="dropdown-item" href="#">Alguma ação</a>
  <a class="dropdown-item" href="#">Outra ação</a>
</div>
{% endcapture %}
{% include example.html content=example %}

### Divisórias

Separe grupos de itens, usando uma divisória.

{% capture example %}
<div class="dropdown-menu">
  <a class="dropdown-item" href="#">Alguma ação</a>
  <a class="dropdown-item" href="#">Outra ação</a>
  <a class="dropdown-item" href="#">Alguma coisa aqui</a>
  <div class="dropdown-divider"></div>
  <a class="dropdown-item" href="#">Link separado</a>
</div>
{% endcapture %}
{% include example.html content=example %}

### Texto

Coloque qualquer texto dentro do menu dropdown e use [utilitários de espaçamentos]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/spacing/). Perceba que você pode precisar estilizar o tamanho da fonte para se adequar a largura do menu.

{% capture example %}
<div class="dropdown-menu p-4 text-muted" style="max-width: 200px;">
  <p>
    Algum exemplo de texto, aqui dentro do menu.
  </p>
  <p class="mb-0">
    Mais um exemplo de texto.
  </p>
</div>
{% endcapture %}
{% include example.html content=example %}

### Formulários

Coloque um formulário dentro do menu dropdown ou transforme-o em um menu dropdown. Use [utilitários de margem ou padding]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/spacing/) para conseguir o espaço negativo necessário.

{% capture example %}
<div class="dropdown-menu">
  <form class="px-4 py-3">
    <div class="form-group">
      <label for="exampleDropdownFormEmail1">Endereço de email</label>
      <input type="email" class="form-control" id="exampleDropdownFormEmail1" placeholder="email@exemplo.com">
    </div>
    <div class="form-group">
      <label for="exampleDropdownFormPassword1">Senha</label>
      <input type="password" class="form-control" id="exampleDropdownFormPassword1" placeholder="Senha">
    </div>
    <div class="form-check">
      <input type="checkbox" class="form-check-input" id="dropdownCheck">
      <label class="form-check-label" for="dropdownCheck">
        Remember me
      </label>
    </div>
    <button type="submit" class="btn btn-primary">Entrar</button>
  </form>
  <div class="dropdown-divider"></div>
  <a class="dropdown-item" href="#">Novo, por aqui? Regitre-se.</a>
  <a class="dropdown-item" href="#">Esqueceu a senha?</a>
</div>
{% endcapture %}
{% include example.html content=example %}

{% capture example %}
<form class="dropdown-menu p-4">
  <div class="form-group">
    <label for="exampleDropdownFormEmail2">Endereço de email</label>
    <input type="email" class="form-control" id="exampleDropdownFormEmail2" placeholder="email@exemplo.com">
  </div>
  <div class="form-group">
    <label for="exampleDropdownFormPassword2">Senha</label>
    <input type="password" class="form-control" id="exampleDropdownFormPassword2" placeholder="Senha">
  </div>
  <div class="form-check">
    <input type="checkbox" class="form-check-input" id="dropdownCheck2">
    <label class="form-check-label" for="dropdownCheck2">
      Lembrar de mim
    </label>
  </div>
  <button type="submit" class="btn btn-primary">Entrar</button>
</form>
{% endcapture %}
{% include example.html content=example %}

## Prâmetros do dropdown

Use `data-offset` ou `data-reference` para mudar a localização do dropdown.

{% capture example %}
<div class="d-flex">
  <div class="dropdown mr-1">
    <button type="button" class="btn btn-secondary dropdown-toggle" id="dropdownMenuOffset" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false" data-offset="10,20">
      Offset
    </button>
    <div class="dropdown-menu" aria-labelledby="dropdownMenuOffset">
      <a class="dropdown-item" href="#">Alguma ação</a>
      <a class="dropdown-item" href="#">Outra ação</a>
      <a class="dropdown-item" href="#">Alguma coisa aqui</a>
    </div>
  </div>
  <div class="btn-group">
    <button type="button" class="btn btn-secondary">Referência</button>
    <button type="button" class="btn btn-secondary dropdown-toggle dropdown-toggle-split" id="dropdownMenuReference" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false" data-reference="parent">
      <span class="sr-only">Dropdown</span>
    </button>
    <div class="dropdown-menu" aria-labelledby="dropdownMenuReference">
      <a class="dropdown-item" href="#">Alguma ação</a>
      <a class="dropdown-item" href="#">Outra ação</a>
      <a class="dropdown-item" href="#">Alguma coisa aqui</a>
      <div class="dropdown-divider"></div>
      <a class="dropdown-item" href="#">Link separado</a>
    </div>
  </div>
</div>
{% endcapture %}
{% include example.html content=example %}

## Modo de uso

Usando JavaScript ou atributos data, o plugin dropdown alterna a visibilidade de conteúdo invisível (menus dropdown) trocando a classe `.show`, no elemento pai da lista. O atributo `data-toggle="dropdown"` é acreditado para fechar os menus dropdown em level de aplicação, então, é uma boa ideia sempre usá-lo.

{% capture callout %}
Em dispositivos touch, abrir um menu adiciona manipuladores (`$.noop`) `mouseover` vazios em filhos imediatos do elemento `<body>`. Essa gambiarra feia é necessária para contornar um [problema na delegação de eventos do iOS](https://www.quirksmode.org/blog/archives/2014/02/mouse_event_bub.html), o qual poderia evitar que toques fora do dropdown acionassem o código que fecha o próprio dropdown. Uma vez que o dropdown é fechado, esses manipuladores `mouseover` adicionais vazios são removidos.
{% endcapture %}
{% include callout.html content=callout type="info" %}

### Via atributos data

Use `data-toggle="dropdown"` em um link ou botão para alternar a visibilidade do menu dropdown.

{% highlight html %}
<div class="dropdown">
  <button id="dLabel" type="button" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
    Gatilho dropdown
  </button>
  <div class="dropdown-menu" aria-labelledby="dLabel">
    ...
  </div>
</div>
{% endhighlight %}

### Via JavaScript

Invoque os dropdowns, usando JavaScript:

{% highlight js %}
$('.dropdown-toggle').dropdown()
{% endhighlight %}

{% capture callout %}
##### `data-toggle="dropdown"` é obrigatório

Independente se você invoca seu dropdown com JavaScript ou com a data-api, o uso de `data-toggle="dropdown"` sempre é obrigatório no gatilho dropdown.
{% endcapture %}
{% include callout.html content=callout type="info" %}

### Parâmetros

Parâmetros sempre podem ser passados usando atributos ou JavaScript. Para atributos, anexe o parâmetro no prefixo `data-`, como em `data-offset=""`.

<table class="table table-bordered table-striped">
  <thead>
    <tr>
      <th style="width: 100px;">Nome</th>
      <th style="width: 100px;">Tipo</th>
      <th style="width: 50px;">Padrão</th>
      <th>Descrição</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>offset</td>
      <td>number | string | função</td>
      <td>0</td>
      <td>Deslocamento do dropdown, em relação ao seu alvo. Para mais informações, veja a <a href="https://popper.js.org/popper-documentation.html#modifiers..offset.offset">documentação do offset</a> Popper.js.</td>
    </tr>
    <tr>
      <td>flip</td>
      <td>boolean</td>
      <td>true</td>
      <td>Permite o dropdown virar, em caso de sobreposição no elemento de referência. Para mais informações, veja a <a href="https://popper.js.org/popper-documentation.html#modifiers..flip.enabled">documentação do flip</a> Popper.js.</td>
    </tr>
    <tr>
      <td>boundary</td>
      <td>string | elemento</td>
      <td>'scrollParent'</td>
      <td>Limite de transbordamento do menu dropdown. Aceita os valores <code>'viewport'</code>, <code>'window'</code>, <code>'scrollParent'</code> ou uma referência HTMLElement (JavaScript, apenas). Para mias informações, veja a <a href="https://popper.js.org/popper-documentation.html#modifiers..preventOverflow.boundariesElement">documentação preventOverflow</a> Popper.js.</td>
    </tr>
    <tr>
      <td>reference</td>
      <td>string | elemento</td>
      <td>'toggle'</td>
      <td>Elemento de referência do menu dropdown. Aceita os valores <code>'toggle'</code>, <code>'parent'</code> ou uma referência HTMLElement. Para mais informações, veja a <a href="https://popper.js.org/popper-documentation.html#referenceObject">documentação referenceObject</a> Popper.js.</td>
    </tr>
    <tr>
      <td>display</td>
      <td>string</td>
      <td>'dynamic'</td>
      <td>Por padrão, nós usamos o posicionamento dinâmico do Popper.js. Desative isso, usando o valor <code>static</code>.</td>
    </tr>
  </tbody>
</table>

**Nota:** quando `boundary` tem como valor definido qualquer coisa, que não `'scrollParent'`, o estilo `position: static` é aplicado no container `.dropdown`.

### Métodos

| Método | Descrição |
| --- | --- |
| `$().dropdown('toggle')` | Alterna a visibilidade do menu dropdown em uma dada navbar ou navegação por abas. |
| `$().dropdown('update')` | Atualiza a posição do dropdown de um elemento. |
| `$().dropdown('dispose')` | Destroi o dropdown de um elemento. |

### Eventos

Todos eventos dropdown são acionados no elemento pai do `.dropdown-menu` e possuem uma propriedade `relatedTarget`, a qual tem o valor referente ao elemento âncora de alternância.
`hide.bs.dropdown` and `hidden.bs.dropdown` events have a `clickEvent` property (only when the original event type is `click`) that contains an Event Object for the click event.

| Evento | Descrição |
| --- | --- |
| `show.bs.dropdown` | Este evento é acionado, imediatamente, quando o método show é invocado. |
| `shown.bs.dropdown` | Este evento é acionado quando o dropdown se torna visível ao usuário (espera as transições CSS finalizarem) |
| `hide.bs.dropdown` | Este evento é acionado, imediatamente, quando o método hide foi invocado. |
| `hidden.bs.dropdown`| Este evento é acionado quando o dropdown acaba de se esconder do usuário (espera as transições CSS finalizarem). |

{% highlight js %}
$('#myDropdown').on('show.bs.dropdown', function () {
  // Faça algo, aqui…
})
{% endhighlight %}

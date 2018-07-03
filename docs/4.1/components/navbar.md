---
layout: docs
title: Navbar
description: Documentação e exemplos para o poderoso e responsivo cabeçalho de navegação, o navbar. Inclui suporte para logo, navegação, plugin collapse e muito mais.
group: components
toc: true
---

## Como funciona

Aqui está oquê você precisa saber, antes de começar a usar o navbar:

- Navbars precisam de um `.navbar` com `.navbar-expand{-sm|-md|-lg|-xl}` (para responsividade) e classes do [esquema de cores](#color-schemes);
- Navbars e seus conteúdos são fluidos, por padrão;
  - Use [containers alternativos](#containers) para limitar suas larguras.
- Use nossas classes utilitárias de [espaçamento]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/spacing/) e [flex]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/flex/) para controlar o espaço e alinhamento, dentro das navbars;
- Navbars são responsivos, por padrão, mas você pode modificar isso, facilmente;
  - Comportamento responsivo depende do nosso plugin JavaScript Collapse.
- Navbars são escondidos, por padrão, quando imprimindo. Forçe-os a serem imprimidos, usando a classe `.d-print` no `.navbar`;
  - Leia sobre a classe utilitária [display]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/display/).
- Garanta acessibilidade com o elemento `<nav>` ou, se estiver usando um elemento mais genérico (como `<div>`), coloque `role="navigation"` em cada navbar para identificá-lo como tal, em tecnologias assistivas.

Continue lendo para ver um exemplo e lista de sub-componentes suportados.

## Conteúdo suportado

Navbars vem com suporte integrado para um punhado de sub-componentes. Escolha entre os seguintes, sempre que precisar:

- `.navbar-brand` para o nome de seu projeto, produto ou companhia;
- `.navbar-nav` para obter uma leve navegação com suporte a dropdowns;
- `.navbar-toggler` para usar com nosso plugin collapse e outros comportamentos;
- `.form-inline` para qualquer campo de formulário e ações;
- `.navbar-text` para adicionar texto centralizado verticalmente;
- `.collapse.navbar-collapse` para agrupar e esconder conteúdos navbar, de acordo com o breakpoint do pai.

Aqui está um exemplo de todos os sub-componentes incluídos em um navbar light responsivo, o qual colapsa no breakpoint `lg` (large, em português: grande), automaticamente.

{% capture example %}
<nav class="navbar navbar-expand-lg navbar-light bg-light">
  <a class="navbar-brand" href="#">Navbar</a>
  <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#conteudoNavbarSuportado" aria-controls="conteudoNavbarSuportado" aria-expanded="false" aria-label="Alterna navegação">
    <span class="navbar-toggler-icon"></span>
  </button>

  <div class="collapse navbar-collapse" id="conteudoNavbarSuportado">
    <ul class="navbar-nav mr-auto">
      <li class="nav-item active">
        <a class="nav-link" href="#">Home <span class="sr-only">(página atual)</span></a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#">Link</a>
      </li>
      <li class="nav-item dropdown">
        <a class="nav-link dropdown-toggle" href="#" id="navbarDropdown" role="button" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
          Dropdown
        </a>
        <div class="dropdown-menu" aria-labelledby="navbarDropdown">
          <a class="dropdown-item" href="#">Ação</a>
          <a class="dropdown-item" href="#">Outra ação</a>
          <div class="dropdown-divider"></div>
          <a class="dropdown-item" href="#">Algo mais aqui</a>
        </div>
      </li>
      <li class="nav-item">
        <a class="nav-link disabled" href="#">Desativado</a>
      </li>
    </ul>
    <form class="form-inline my-2 my-lg-0">
      <input class="form-control mr-sm-2" type="search" placeholder="Pesquisar" aria-label="Pesquisar">
      <button class="btn btn-outline-success my-2 my-sm-0" type="submit">Pesquisar</button>
    </form>
  </div>
</nav>
{% endcapture %}
{% include example.html content=example %}

Este exemplo usa utilitários de [cor]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/colors/) (`bg-light`) e [espaçamento]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/spacing/) (`my-2`, `my-lg-0`, `mr-sm-0` e `my-sm-0`).

### Marca

A classe `.navbar-brand` pode ser aplicada na maioria dos elementos, mas uma âncora funciona melhor, já que alguns elementos precisam de classes utilitárias ou estilos customizados.

{% capture example %}
<!-- Como um link -->
<nav class="navbar navbar-light bg-light">
  <a class="navbar-brand" href="#">Navbar</a>
</nav>

<!-- Como um span -->
<nav class="navbar navbar-light bg-light">
  <span class="navbar-brand mb-0 h1">Navbar</span>
</nav>
{% endcapture %}
{% include example.html content=example %}

Colocar imagens no `.navbar-brand` vai, provavelmente, sempre precisar de estilos customizados ou utilitários para dimensionamento, adequado. Aqui estão alguns exemplos para demonstrar.

{% capture example %}
<!-- Só uma imagem -->
<nav class="navbar navbar-light bg-light">
  <a class="navbar-brand" href="#">
    <img src="{{ site.baseurl }}/assets/brand/bootstrap-solid.svg" width="30" height="30" alt="">
  </a>
</nav>
{% endcapture %}
{% include example.html content=example %}

{% capture example %}
<!-- Imagem e texto -->
<nav class="navbar navbar-light bg-light">
  <a class="navbar-brand" href="#">
    <img src="{{ site.baseurl }}/assets/brand/bootstrap-solid.svg" width="30" height="30" class="d-inline-block align-top" alt="">
    Bootstrap
  </a>
</nav>
{% endcapture %}
{% include example.html content=example %}

### Nav

Links de navegação navbar são feitos com nossas opções `.nav`, suas próprias classes modificadoras e precisam usar [classes togglers](#toggler), para estilização responsiva apropriada. **Navegação em navbars também vão crescer para ocupar o maior espaço horizontal possível**, mantendo os conteúdos do seu navbar alinhados.

Estados ativos (classe `.active`) para indicar a página atual podem ser aplicados, diretamente, no `.nav-link` ou seus pais imediatos `.nav-item`.

{% capture example %}
<nav class="navbar navbar-expand-lg navbar-light bg-light">
  <a class="navbar-brand" href="#">Navbar</a>
  <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Alterna navegação">
    <span class="navbar-toggler-icon"></span>
  </button>
  <div class="collapse navbar-collapse" id="navbarNav">
    <ul class="navbar-nav">
      <li class="nav-item active">
        <a class="nav-link" href="#">Home <span class="sr-only">(Página atual)</span></a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#">Destaques</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#">Preços</a>
      </li>
      <li class="nav-item">
        <a class="nav-link disabled" href="#">Desativado</a>
      </li>
    </ul>
  </div>
</nav>
{% endcapture %}
{% include example.html content=example %}

E porque nós usamos classes em nossos navs, você pode evitar a abordagem baseada em lista, se quiser.

{% capture example %}
<nav class="navbar navbar-expand-lg navbar-light bg-light">
  <a class="navbar-brand" href="#">Navbar</a>
  <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNavAltMarkup" aria-controls="navbarNavAltMarkup" aria-expanded="false" aria-label="Alterna navegação">
    <span class="navbar-toggler-icon"></span>
  </button>
  <div class="collapse navbar-collapse" id="navbarNavAltMarkup">
    <div class="navbar-nav">
      <a class="nav-item nav-link active" href="#">Home <span class="sr-only">(Página atual)</span></a>
      <a class="nav-item nav-link" href="#">Destaques</a>
      <a class="nav-item nav-link" href="#">Preços</a>
      <a class="nav-item nav-link disabled" href="#">Desativado</a>
    </div>
  </div>
</nav>
{% endcapture %}
{% include example.html content=example %}

Você também pode usar dropdowns em seu nav da navbar. Menus dropdown precisam de um elemento envolto para posicionamento, então, se assegure de usar elementos aninhados e separados para `.nav-item` e `.nav-link`, como mostrado abaixo.

{% capture example %}
<nav class="navbar navbar-expand-lg navbar-light bg-light">
  <a class="navbar-brand" href="#">Navbar</a>
  <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNavDropdown" aria-controls="navbarNavDropdown" aria-expanded="false" aria-label="Alterna navegação">
    <span class="navbar-toggler-icon"></span>
  </button>
  <div class="collapse navbar-collapse" id="navbarNavDropdown">
    <ul class="navbar-nav">
      <li class="nav-item active">
        <a class="nav-link" href="#">Home <span class="sr-only">(Página atual)</span></a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#">Destaques</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#">Preços</a>
      </li>
      <li class="nav-item dropdown">
        <a class="nav-link dropdown-toggle" href="#" id="navbarDropdownMenuLink" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
          Link dropdown
        </a>
        <div class="dropdown-menu" aria-labelledby="navbarDropdownMenuLink">
          <a class="dropdown-item" href="#">Ação</a>
          <a class="dropdown-item" href="#">Outra ação</a>
          <a class="dropdown-item" href="#">Algo mais aqui</a>
        </div>
      </li>
    </ul>
  </div>
</nav>
{% endcapture %}
{% include example.html content=example %}

### Formulários

Coloque vários campos de formulário e componentes, dentro de um navbar com `.form-inline`.

{% capture example %}
<nav class="navbar navbar-light bg-light">
  <form class="form-inline">
    <input class="form-control mr-sm-2" type="search" placeholder="Pesquisar" aria-label="Pesquisar">
    <button class="btn btn-outline-success my-2 my-sm-0" type="submit">Pesquisar</button>
  </form>
</nav>
{% endcapture %}
{% include example.html content=example %}

Elementos filhos imediatos no `.navbar` usam layout flex e vão ter `justify-content: between`, por padrão. Use [utilitários flex ]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/flex/) sempre que precisar, para ajustar este comportamento.

{% capture example %}
<nav class="navbar navbar-light bg-light">
  <a class="navbar-brand">Navbar</a>
  <form class="form-inline">
    <input class="form-control mr-sm-2" type="search" placeholder="Pesquisar" aria-label="Pesquisar">
    <button class="btn btn-outline-success my-2 my-sm-0" type="submit">Pesquisar</button>
  </form>
</nav>
{% endcapture %}
{% include example.html content=example %}

Grupos de input também funcionam:

{% capture example %}
<nav class="navbar navbar-light bg-light">
  <form class="form-inline">
    <div class="input-group">
      <div class="input-group-prepend">
        <span class="input-group-text" id="basic-addon1">@</span>
      </div>
      <input type="text" class="form-control" placeholder="Usuário" aria-label="Usuário" aria-describedby="basic-addon1">
    </div>
  </form>
</nav>
{% endcapture %}
{% include example.html content=example %}

Vários botões dentro dos formulários navbar também são suportados. Isso é um bom lembrete que utilitários de alinhamento vertical podem ser usados para linhar elementos de diferentes tamanhos.

{% capture example %}
<nav class="navbar navbar-light bg-light">
  <form class="form-inline">
    <button class="btn btn-outline-success" type="button">Botão principal</button>
    <button class="btn btn-sm btn-outline-secondary" type="button">Botão menor</button>
  </form>
</nav>
{% endcapture %}
{% include example.html content=example %}

### Texto

Navbars podem conter pedaços de textos, com ajuda do `.navbar-text`. Esta classe configura o alinhamento vertical e espaçamento horizontal, em linhas de textos.

{% capture example %}
<nav class="navbar navbar-light bg-light">
  <span class="navbar-text">
    Texto navbar com um elemento inline
  </span>
</nav>
{% endcapture %}
{% include example.html content=example %}

Misture e combine com outros componentes e utilitários, se precisar.

{% capture example %}
<nav class="navbar navbar-expand-lg navbar-light bg-light">
  <a class="navbar-brand" href="#">Navbar com texto</a>
  <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#textoNavbar" aria-controls="textoNavbar" aria-expanded="false" aria-label="Alterna navegação">
    <span class="navbar-toggler-icon"></span>
  </button>
  <div class="collapse navbar-collapse" id="textoNavbar">
    <ul class="navbar-nav mr-auto">
      <li class="nav-item active">
        <a class="nav-link" href="#">Home <span class="sr-only">(Página atual)</span></a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#">Destaques</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#">Preços</a>
      </li>
    </ul>
    <span class="navbar-text">
      Texto navbar com um elemento inline
    </span>
  </div>
</nav>
{% endcapture %}
{% include example.html content=example %}

## Esquema de cores

Tematizar o navbar nunca foi tão fácil, graças a combinação de classes temas e utilitários `background-color`. Escolha de `.navbar-light` (cores de fundo leves) até `.navbar-dark` (cores de fundo escuras). Depois, personalize o resto com utilitários `.bg-*`.

<div class="bd-example">
  <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
    <a class="navbar-brand" href="#">Navbar</a>
    <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#corNavbar01" aria-controls="corNavbar01" aria-expanded="false" aria-label="Alterna navegação">
      <span class="navbar-toggler-icon"></span>
    </button>

    <div class="collapse navbar-collapse" id="corNavbar01">
      <ul class="navbar-nav mr-auto">
        <li class="nav-item active">
          <a class="nav-link" href="#">Home <span class="sr-only">(Página atual)</span></a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Destaques</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Preços</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Sobre</a>
        </li>
      </ul>
      <form class="form-inline">
        <input class="form-control mr-sm-2" type="search" placeholder="Pesquisar" aria-label="Pesquisar">
        <button class="btn btn-outline-info my-2 my-sm-0" type="submit">Pesquisar</button>
      </form>
    </div>
  </nav>

  <nav class="navbar navbar-expand-lg navbar-dark bg-primary">
    <a class="navbar-brand" href="#">Navbar</a>
    <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#corNavbar02" aria-controls="corNavbar02" aria-expanded="false" aria-label="Alterna navegação">
      <span class="navbar-toggler-icon"></span>
    </button>

    <div class="collapse navbar-collapse" id="corNavbar02">
      <ul class="navbar-nav mr-auto">
        <li class="nav-item active">
          <a class="nav-link" href="#">Home <span class="sr-only">(Página atual)</span></a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Destaques</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Preços</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Sobre</a>
        </li>
      </ul>
      <form class="form-inline">
        <input class="form-control mr-sm-2" type="search" placeholder="Pesquisar" aria-label="Pesquisar">
        <button class="btn btn-outline-light my-2 my-sm-0" type="submit">Pesquisar</button>
      </form>
    </div>
  </nav>

  <nav class="navbar navbar-expand-lg navbar-light" style="background-color: #e3f2fd;">
    <a class="navbar-brand" href="#">Navbar</a>
    <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#corNavbar03" aria-controls="corNavbar03" aria-expanded="false" aria-label="Alterna navegação">
      <span class="navbar-toggler-icon"></span>
    </button>

    <div class="collapse navbar-collapse" id="corNavbar03">
      <ul class="navbar-nav mr-auto">
        <li class="nav-item active">
          <a class="nav-link" href="#">Home <span class="sr-only">(Página atual)</span></a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Destaques</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Preços</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Sobre</a>
        </li>
      </ul>
      <form class="form-inline">
        <input class="form-control mr-sm-2" type="search" placeholder="Pesquisar" aria-label="Pesquisar">
        <button class="btn btn-outline-primary my-2 my-sm-0" type="submit">Pesquisar</button>
      </form>
    </div>
  </nav>
</div>

{% highlight html %}
<nav class="navbar navbar-dark bg-dark">
  <!-- Conteúdo do navbar -->
</nav>

<nav class="navbar navbar-dark bg-primary">
  <!-- Conteúdo do navbar -->
</nav>

<nav class="navbar navbar-light" style="background-color: #e3f2fd;">
  <!-- Conteúdo do navbar -->
</nav>
{% endhighlight %}

## Containers

Apesar de não ser necessário, você pode envolver um `.container` em um navbar para centralizá-lo na página ou colocar um `.container` dentro para centralizar os conteúdos de um [navbar top fixo ou estático](#placement).

{% capture example %}
<div class="container">
  <nav class="navbar navbar-expand-lg navbar-light bg-light">
    <a class="navbar-brand" href="#">Navbar</a>
  </nav>
</div>
{% endcapture %}
{% include example.html content=example %}

Quando o container está dentro do seu navbar, seu padding horizontal é removido em breakpoints menores que sua classe `.navbar-expand{-sm|-md|-lg|-xl}` especificada. Isso garante que não dobraremos o padding, desnecessariamente, em viewports menores, quando seu navbar está expandido.

{% capture example %}
<nav class="navbar navbar-expand-lg navbar-light bg-light">
  <div class="container">
    <a class="navbar-brand" href="#">Navbar</a>
  </div>
</nav>
{% endcapture %}
{% include example.html content=example %}

## Posicionamento

Use nossos [utilitários de posicionamento]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/position/) para posicionar navbars em locais não estáticos. Escolha entre fixo ao topo, fixo a parte inferior ou sticky top (rola com a página e fica fixo, quando ele alcança a topo). Navbars fixos usam `position: fixed`, significando que eles estão a parte do fluxo comum do DOM e podem precisar CSS customizado (ex: `padding-top` no `<body>`) para evitar sobreposição com outros elementos.

Também perceba que **`.sticky-top` usa `position: sticky`, oquê [não é suportado, totalmente, em todos browsers](https://caniuse.com/#feat=css-sticky)**.

{% capture example %}
<nav class="navbar navbar-light bg-light">
  <a class="navbar-brand" href="#">Padrão</a>
</nav>
{% endcapture %}
{% include example.html content=example %}

{% capture example %}
<nav class="navbar fixed-top navbar-light bg-light">
  <a class="navbar-brand" href="#">Fixo na parte superior</a>
</nav>
{% endcapture %}
{% include example.html content=example %}

{% capture example %}
<nav class="navbar fixed-bottom navbar-light bg-light">
  <a class="navbar-brand" href="#">Fixo na parte inferior</a>
</nav>
{% endcapture %}
{% include example.html content=example %}

{% capture example %}
<nav class="navbar sticky-top navbar-light bg-light">
  <a class="navbar-brand" href="#">Sticky top</a>
</nav>
{% endcapture %}
{% include example.html content=example %}

## Comportamentos responsivos

Navbars podem utilizar classes `.navbar-toggler`, `.navbar-collapse` e `.navbar-expand{-sm|-md|-lg|-xl}` para alterar quando o conteúdo colapsa, atrás do botão. Em combinação com outros utilitários, você pode escolher quando mostrar ou esconder certos elementos, facilmente.

Para navbars que não estão sempre colapsados, use a classe `.navbar-expand` no navbar. Para navbars que estão sempre colapsados, não coloque nenhuma classe `.navbar-expand`.

### Toggler

Togglers navbar são alinhados a esquerda, por padrão, mas se eles seguem um elemento irmão como `.navbar-brand`, vão ser alinhados a direita, automaticamente. Revertendo sua marcação HTML vai reverter o posicionamento do toggler.

Abaixo, temos exemplos de diferentes estilos de togglers.

Sem `.navbar-brand` exibido, em breakpoints menores:

{% capture example %}
<nav class="navbar navbar-expand-lg navbar-light bg-light">
  <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarTogglerDemo01" aria-controls="navbarTogglerDemo01" aria-expanded="false" aria-label="Alterna navegação">
    <span class="navbar-toggler-icon"></span>
  </button>
  <div class="collapse navbar-collapse" id="navbarTogglerDemo01">
    <a class="navbar-brand" href="#">Marca escondida</a>
    <ul class="navbar-nav mr-auto mt-2 mt-lg-0">
      <li class="nav-item active">
        <a class="nav-link" href="#">Home <span class="sr-only">(Página atual)</span></a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#">Link</a>
      </li>
      <li class="nav-item">
        <a class="nav-link disabled" href="#">Desativado</a>
      </li>
    </ul>
    <form class="form-inline my-2 my-lg-0">
      <input class="form-control mr-sm-2" type="search" placeholder="Pesquisar" aria-label="Pesquisar">
      <button class="btn btn-outline-success my-2 my-sm-0" type="submit">Pesquisar</button>
    </form>
  </div>
</nav>
{% endcapture %}
{% include example.html content=example %}

Com o nome da marca exibido na esquerda e o toggler na direita:

{% capture example %}
<nav class="navbar navbar-expand-lg navbar-light bg-light">
  <a class="navbar-brand" href="#">Navbar</a>
  <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarTogglerDemo02" aria-controls="navbarTogglerDemo02" aria-expanded="false" aria-label="Alterna navegação">
    <span class="navbar-toggler-icon"></span>
  </button>

  <div class="collapse navbar-collapse" id="navbarTogglerDemo02">
    <ul class="navbar-nav mr-auto mt-2 mt-lg-0">
      <li class="nav-item active">
        <a class="nav-link" href="#">Home <span class="sr-only">(Página atual)</span></a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#">Link</a>
      </li>
      <li class="nav-item">
        <a class="nav-link disabled" href="#">Desativado</a>
      </li>
    </ul>
    <form class="form-inline my-2 my-lg-0">
      <input class="form-control mr-sm-2" type="search" placeholder="Pesquisar">
      <button class="btn btn-outline-success my-2 my-sm-0" type="submit">Pesquisar</button>
    </form>
  </div>
</nav>
{% endcapture %}
{% include example.html content=example %}

Com toggler na esquerda e nome da marca na direita:

{% capture example %}
<nav class="navbar navbar-expand-lg navbar-light bg-light">
  <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarTogglerDemo03" aria-controls="navbarTogglerDemo03" aria-expanded="false" aria-label="Alterna navegação">
    <span class="navbar-toggler-icon"></span>
  </button>
  <a class="navbar-brand" href="#">Navbar</a>

  <div class="collapse navbar-collapse" id="navbarTogglerDemo03">
    <ul class="navbar-nav mr-auto mt-2 mt-lg-0">
      <li class="nav-item active">
        <a class="nav-link" href="#">Home <span class="sr-only">(Página atual)</span></a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#">Link</a>
      </li>
      <li class="nav-item">
        <a class="nav-link disabled" href="#">Desativado</a>
      </li>
    </ul>
    <form class="form-inline my-2 my-lg-0">
      <input class="form-control mr-sm-2" type="search" placeholder="Pesquisar" aria-label="Pesquisar">
      <button class="btn btn-outline-success my-2 my-sm-0" type="submit">Pesquisar</button>
    </form>
  </div>
</nav>
{% endcapture %}
{% include example.html content=example %}

### Conteúdo externo

Algumas vezes você quer usar o plugin collapse para acionar conteúdo oculto, em algum lugar da página. Porque nosso plugin funciona com o pareamento de `id` e `data-target`, isso pode ser feito, facilmente!

{% capture example %}
<div class="pos-f-t">
  <div class="collapse" id="navbarToggleExternalContent">
    <div class="bg-dark p-4">
      <h5 class="text-white h4">Conteúdo expandido</h5>
      <span class="text-muted">Expansível, atráves da marca no navbar.</span>
    </div>
  </div>
  <nav class="navbar navbar-dark bg-dark">
    <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarToggleExternalContent" aria-controls="navbarToggleExternalContent" aria-expanded="false" aria-label="Alterna navegação">
      <span class="navbar-toggler-icon"></span>
    </button>
  </nav>
</div>
{% endcapture %}
{% include example.html content=example %}

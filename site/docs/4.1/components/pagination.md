---
layout: docs
title: Paginação
description: Documentação e exemplos de paginação para indicar um série de conteúdos relacionados, existentes em várias páginas.
group: components
toc: true
---

## Visão geral

Nós usamos um grande bloco de links conectados para nossa paginação, fazendo-os fácil de clicar e escalar. A paginação é feita com elementos HTML de lista para que leitores de telas possam anunciar o número de links disponíveis. Use um elemento `<nav>` como envolto para identificá-lo como uma seção de navegação aos leitores de telas e outras tecnologias assistivas.

Além do mais, já que as páginas possuem mais de uma seção de navegação, normalmente, é aconselhado usar um `aria-label` descritivo, no `<nav>`. Por exemplo, se o componente de paginação é usado para navegar entre um conjunto de resultados de pesquisa, uma boa `aria-label` seria  `aria-label="Páginas dos resultados de pesquisa"`.

{% capture example %}
<nav aria-label="Navegação de página exemplo">
  <ul class="pagination">
    <li class="page-item"><a class="page-link" href="#">Anterior</a></li>
    <li class="page-item"><a class="page-link" href="#">1</a></li>
    <li class="page-item"><a class="page-link" href="#">2</a></li>
    <li class="page-item"><a class="page-link" href="#">3</a></li>
    <li class="page-item"><a class="page-link" href="#">Próximo</a></li>
  </ul>
</nav>
{% endcapture %}
{% include example.html content=example %}

## Trabalhando com ícones

Querendo usar um ícone ou símbolo, no lugar de texto, em alguns links de paginação? Se assegure de usar os atributos `aria` apropriados e utilitários `.sr-only`.

{% capture example %}
<nav aria-label="Navegação de página exemplo">
  <ul class="pagination">
    <li class="page-item">
      <a class="page-link" href="#" aria-label="Anterior">
        <span aria-hidden="true">&laquo;</span>
        <span class="sr-only">Anterior</span>
      </a>
    </li>
    <li class="page-item"><a class="page-link" href="#">1</a></li>
    <li class="page-item"><a class="page-link" href="#">2</a></li>
    <li class="page-item"><a class="page-link" href="#">3</a></li>
    <li class="page-item">
      <a class="page-link" href="#" aria-label="Próximo">
        <span aria-hidden="true">&raquo;</span>
        <span class="sr-only">Próximo</span>
      </a>
    </li>
  </ul>
</nav>
{% endcapture %}
{% include example.html content=example %}

## Estados desativado e ativado

Links de paginação são personalizáveis para diferentes ocasiões. Use `.disabled` para links não poderem ser clicados e `.active` para indicar a página atual.

Apesar da classe `.disabled` usar  `pointer-events: none` para _tentar_ desativar a funcionalidade de link do `<a>`, esta propriedade CSS ainda não é padronizada e não conta com navegação pelo teclado. Assim, você deve sempre colocar `tabindex="-1"` em links desativados e usar JavaScript personalizado para desativar suas funcionalidades, totamente.

{% capture example %}
<nav aria-label="...">
  <ul class="pagination">
    <li class="page-item disabled">
      <a class="page-link" href="#" tabindex="-1">Anterior</a>
    </li>
    <li class="page-item"><a class="page-link" href="#">1</a></li>
    <li class="page-item active">
      <a class="page-link" href="#">2 <span class="sr-only">(atual)</span></a>
    </li>
    <li class="page-item"><a class="page-link" href="#">3</a></li>
    <li class="page-item">
      <a class="page-link" href="#">Próximo</a>
    </li>
  </ul>
</nav>
{% endcapture %}
{% include example.html content=example %}

Opcionalmente, você pode trocar âncoras ativadas e desativadas por `<span>` ou, omitir a âncora no caso de flechas anterior/próximo, para remover a funcionalide de clique e evitar foco de teclado, enquanto mantém os estilos.

{% capture example %}
<nav aria-label="...">
  <ul class="pagination">
    <li class="page-item disabled">
      <span class="page-link">Anterior</span>
    </li>
    <li class="page-item"><a class="page-link" href="#">1</a></li>
    <li class="page-item active">
      <span class="page-link">
        2
        <span class="sr-only">(atual)</span>
      </span>
    </li>
    <li class="page-item"><a class="page-link" href="#">3</a></li>
    <li class="page-item">
      <a class="page-link" href="#">Próximo</a>
    </li>
  </ul>
</nav>
{% endcapture %}
{% include example.html content=example %}

## Tamanhos

Paginação grande e chique ou pequena? Use `.pagination-lg` ou `.pagination-sm` para desfrutar dos diferentes tamanhos.

{% capture example %}
<nav aria-label="...">
  <ul class="pagination pagination-lg">
    <li class="page-item disabled">
      <a class="page-link" href="#" tabindex="-1">1</a>
    </li>
    <li class="page-item"><a class="page-link" href="#">2</a></li>
    <li class="page-item"><a class="page-link" href="#">3</a></li>
  </ul>
</nav>
{% endcapture %}
{% include example.html content=example %}

{% capture example %}
<nav aria-label="...">
  <ul class="pagination pagination-sm">
    <li class="page-item disabled">
      <a class="page-link" href="#" tabindex="-1">1</a>
    </li>
    <li class="page-item"><a class="page-link" href="#">2</a></li>
    <li class="page-item"><a class="page-link" href="#">3</a></li>
  </ul>
</nav>
{% endcapture %}
{% include example.html content=example %}

## Alinhamento

Altere o alinhamento dos componentes de paginação, usando [utilitários flexbox]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/flex/).

{% capture example %}
<nav aria-label="Navegação de página exemplo">
  <ul class="pagination justify-content-center">
    <li class="page-item disabled">
      <a class="page-link" href="#" tabindex="-1">Anterior</a>
    </li>
    <li class="page-item"><a class="page-link" href="#">1</a></li>
    <li class="page-item"><a class="page-link" href="#">2</a></li>
    <li class="page-item"><a class="page-link" href="#">3</a></li>
    <li class="page-item">
      <a class="page-link" href="#">Próximo</a>
    </li>
  </ul>
</nav>
{% endcapture %}
{% include example.html content=example %}

{% capture example %}
<nav aria-label="Navegação de página exemplo">
  <ul class="pagination justify-content-end">
    <li class="page-item disabled">
      <a class="page-link" href="#" tabindex="-1">Anterior</a>
    </li>
    <li class="page-item"><a class="page-link" href="#">1</a></li>
    <li class="page-item"><a class="page-link" href="#">2</a></li>
    <li class="page-item"><a class="page-link" href="#">3</a></li>
    <li class="page-item">
      <a class="page-link" href="#">Próximo</a>
    </li>
  </ul>
</nav>
{% endcapture %}
{% include example.html content=example %}

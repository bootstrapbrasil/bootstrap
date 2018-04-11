---
layout: docs
title: Tabelas
description: Documentação e exemplos para inclusão de diferentes tipos de tabelas (de acordo com sua necessidade de plugins JavaScript), no Bootstrap.
group: content
toc: true
---

## Exemplos

Devido ao abrangente uso de tabelas em _widgets_ de terceiros, como calendários e selecionadores da datas, nós desenvolvemos nossas tabelas de forma que sejam **alternativas**. Basta adicionar a classe `.table` em qualquer `<table>`, então, customize-a mais usando nossos estilos de costumização ou as diversas classes modificadoras.

Usando a marcação mais básica para tabelas, assim é como tabelas usando `.table` irão parecer, no Bootstrap. **Todos os estilos de tabelas são herdados no Bootstrap 4**, significando que qualquer tabela aninhada vai se comportar do mesmo modo que seus pais.

{% example html %}
<table class="table">
  <thead>
    <tr>
      <th scope="col">#</th>
      <th scope="col">Primeiro</th>
      <th scope="col">Último</th>
      <th scope="col">Nickname</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">1</th>
      <td>Mark</td>
      <td>Otto</td>
      <td>@mdo</td>
    </tr>
    <tr>
      <th scope="row">2</th>
      <td>Jacob</td>
      <td>Thornton</td>
      <td>@fat</td>
    </tr>
    <tr>
      <th scope="row">3</th>
      <td>Larry</td>
      <td>the Bird</td>
      <td>@twitter</td>
    </tr>
  </tbody>
</table>
{% endexample %}

Você também pode inverter as cores (texto claro em background escuro), usando a class `.table-dark`.

{% example html %}
<table class="table table-dark">
  <thead>
    <tr>
      <th scope="col">#</th>
      <th scope="col">Primeiro</th>
      <th scope="col">Último</th>
      <th scope="col">Nickname</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">1</th>
      <td>Mark</td>
      <td>Otto</td>
      <td>@mdo</td>
    </tr>
    <tr>
      <th scope="row">2</th>
      <td>Jacob</td>
      <td>Thornton</td>
      <td>@fat</td>
    </tr>
    <tr>
      <th scope="row">3</th>
      <td>Larry</td>
      <td>the Bird</td>
      <td>@twitter</td>
    </tr>
  </tbody>
</table>
{% endexample %}

## Opções de cabeçalhos para tabelas

Similar as tabelas comuns e tabelas escuras, use as classes modificadoras `.thead-light` ou `thead-dark` para fazer o `<thead>` ser mais claro ou escuro.

{% example html %}
<table class="table">
  <thead class="thead-dark">
    <tr>
      <th scope="col">#</th>
      <th scope="col">Primeiro</th>
      <th scope="col">Último</th>
      <th scope="col">Nickname</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">1</th>
      <td>Mark</td>
      <td>Otto</td>
      <td>@mdo</td>
    </tr>
    <tr>
      <th scope="row">2</th>
      <td>Jacob</td>
      <td>Thornton</td>
      <td>@fat</td>
    </tr>
    <tr>
      <th scope="row">3</th>
      <td>Larry</td>
      <td>the Bird</td>
      <td>@twitter</td>
    </tr>
  </tbody>
</table>

<table class="table">
  <thead class="thead-light">
    <tr>
      <th scope="col">#</th>
      <th scope="col">Primeiro</th>
      <th scope="col">Último</th>
      <th scope="col">Nickname</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">1</th>
      <td>Mark</td>
      <td>Otto</td>
      <td>@mdo</td>
    </tr>
    <tr>
      <th scope="row">2</th>
      <td>Jacob</td>
      <td>Thornton</td>
      <td>@fat</td>
    </tr>
    <tr>
      <th scope="row">3</th>
      <td>Larry</td>
      <td>the Bird</td>
      <td>@twitter</td>
    </tr>
  </tbody>
</table>
{% endexample %}

## Linhas zebradas

Use `.table-striped` para adicionar listras zebradas para qualquer `<tbody>`.

{% example html %}
<table class="table table-striped">
  <thead>
    <tr>
      <th scope="col">#</th>
      <th scope="col">Primeiro</th>
      <th scope="col">Último</th>
      <th scope="col">Nickname</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">1</th>
      <td>Mark</td>
      <td>Otto</td>
      <td>@mdo</td>
    </tr>
    <tr>
      <th scope="row">2</th>
      <td>Jacob</td>
      <td>Thornton</td>
      <td>@fat</td>
    </tr>
    <tr>
      <th scope="row">3</th>
      <td>Larry</td>
      <td>the Bird</td>
      <td>@twitter</td>
    </tr>
  </tbody>
</table>
{% endexample %}

{% example html %}
<table class="table table-striped table-dark">
  <thead>
    <tr>
      <th scope="col">#</th>
      <th scope="col">Primeiro</th>
      <th scope="col">Último</th>
      <th scope="col">Nickname</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">1</th>
      <td>Mark</td>
      <td>Otto</td>
      <td>@mdo</td>
    </tr>
    <tr>
      <th scope="row">2</th>
      <td>Jacob</td>
      <td>Thornton</td>
      <td>@fat</td>
    </tr>
    <tr>
      <th scope="row">3</th>
      <td>Larry</td>
      <td>the Bird</td>
      <td>@twitter</td>
    </tr>
  </tbody>
</table>
{% endexample %}

## Tabela com bordas

Use `.table-bordered` para colocar bordas em todos os lados da tabela e suas células.

{% example html %}
<table class="table table-bordered">
  <thead>
    <tr>
      <th scope="col">#</th>
      <th scope="col">Primeiro</th>
      <th scope="col">Último</th>
      <th scope="col">Nickname</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">1</th>
      <td>Mark</td>
      <td>Otto</td>
      <td>@mdo</td>
    </tr>
    <tr>
      <th scope="row">2</th>
      <td>Jacob</td>
      <td>Thornton</td>
      <td>@fat</td>
    </tr>
    <tr>
      <th scope="row">3</th>
      <td colspan="2">Larry the Bird</td>
      <td>@twitter</td>
    </tr>
  </tbody>
</table>
{% endexample %}

{% example html %}
<table class="table table-bordered table-dark">
  <thead>
    <tr>
      <th scope="col">#</th>
      <th scope="col">Primeiro</th>
      <th scope="col">Último</th>
      <th scope="col">Nickname</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">1</th>
      <td>Mark</td>
      <td>Otto</td>
      <td>@mdo</td>
    </tr>
    <tr>
      <th scope="row">2</th>
      <td>Jacob</td>
      <td>Thornton</td>
      <td>@fat</td>
    </tr>
    <tr>
      <th scope="row">3</th>
      <td colspan="2">Larry the Bird</td>
      <td>@twitter</td>
    </tr>
  </tbody>
</table>
{% endexample %}

## Tabela sem bordas

Use `.table-borderless` para ter uma tabela sem bordas.

{% example html %}
<table class="table table-borderless">
  <thead>
    <tr>
      <th scope="col">#</th>
      <th scope="col">Primeiro</th>
      <th scope="col">Último</th>
      <th scope="col">Nickname</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">1</th>
      <td>Mark</td>
      <td>Otto</td>
      <td>@mdo</td>
    </tr>
    <tr>
      <th scope="row">2</th>
      <td>Jacob</td>
      <td>Thornton</td>
      <td>@fat</td>
    </tr>
    <tr>
      <th scope="row">3</th>
      <td colspan="2">Larry the Bird</td>
      <td>@twitter</td>
    </tr>
  </tbody>
</table>
{% endexample %}

`.table-borderless` também pode ser usada em tabelas mais escuras.

{% example html %}
<table class="table table-borderless table-dark">
  <thead>
    <tr>
      <th scope="col">#</th>
      <th scope="col">Primeiro</th>
      <th scope="col">Último</th>
      <th scope="col">Nickname</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">1</th>
      <td>Mark</td>
      <td>Otto</td>
      <td>@mdo</td>
    </tr>
    <tr>
      <th scope="row">2</th>
      <td>Jacob</td>
      <td>Thornton</td>
      <td>@fat</td>
    </tr>
    <tr>
      <th scope="row">3</th>
      <td colspan="2">Larry the Bird</td>
      <td>@twitter</td>
    </tr>
  </tbody>
</table>
{% endexample %}

## Linhas com efeito hover

Utilize `.table-hover` para ativar um efeito hover, nas linhas dentro do `<tbody>`.

{% example html %}
<table class="table table-hover">
  <thead>
    <tr>
      <th scope="col">#</th>
      <th scope="col">Primeiro</th>
      <th scope="col">Último</th>
      <th scope="col">Nickname</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">1</th>
      <td>Mark</td>
      <td>Otto</td>
      <td>@mdo</td>
    </tr>
    <tr>
      <th scope="row">2</th>
      <td>Jacob</td>
      <td>Thornton</td>
      <td>@fat</td>
    </tr>
    <tr>
      <th scope="row">3</th>
      <td colspan="2">Larry the Bird</td>
      <td>@twitter</td>
    </tr>
  </tbody>
</table>
{% endexample %}

{% example html %}
<table class="table table-hover table-dark">
  <thead>
    <tr>
      <th scope="col">#</th>
      <th scope="col">Primeiro</th>
      <th scope="col">Último</th>
      <th scope="col">Nickname</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">1</th>
      <td>Mark</td>
      <td>Otto</td>
      <td>@mdo</td>
    </tr>
    <tr>
      <th scope="row">2</th>
      <td>Jacob</td>
      <td>Thornton</td>
      <td>@fat</td>
    </tr>
    <tr>
      <th scope="row">3</th>
      <td colspan="2">Larry the Bird</td>
      <td>@twitter</td>
    </tr>
  </tbody>
</table>
{% endexample %}

## Tabela pequena

Use `.table-sm` para fazer com que as tabelas fiquem mais compactas, já que o padding das células serão cortados ao meio.

{% example html %}
<table class="table table-sm">
  <thead>
    <tr>
      <th scope="col">#</th>
      <th scope="col">Primeiro</th>
      <th scope="col">Último</th>
      <th scope="col">Nickname</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">1</th>
      <td>Mark</td>
      <td>Otto</td>
      <td>@mdo</td>
    </tr>
    <tr>
      <th scope="row">2</th>
      <td>Jacob</td>
      <td>Thornton</td>
      <td>@fat</td>
    </tr>
    <tr>
      <th scope="row">3</th>
      <td colspan="2">Larry the Bird</td>
      <td>@twitter</td>
    </tr>
  </tbody>
</table>
{% endexample %}

{% example html %}
<table class="table table-sm table-dark">
  <thead>
    <tr>
      <th scope="col">#</th>
      <th scope="col">Primeiro</th>
      <th scope="col">Último</th>
      <th scope="col">Nickname</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">1</th>
      <td>Mark</td>
      <td>Otto</td>
      <td>@mdo</td>
    </tr>
    <tr>
      <th scope="row">2</th>
      <td>Jacob</td>
      <td>Thornton</td>
      <td>@fat</td>
    </tr>
    <tr>
      <th scope="row">3</th>
      <td colspan="2">Larry the Bird</td>
      <td>@twitter</td>
    </tr>
  </tbody>
</table>
{% endexample %}

## Classes contextuais

Use classes contextuais para colorir linhas ou células da tabela.

<div class="bd-example">
  <table class="table">
    <thead>
      <tr>
        <th scope="col">Classe</th>
        <th scope="col">Cabeçalho</th>
        <th scope="col">Cabeçalho</th>
      </tr>
    </thead>
    <tbody>
      <tr class="table-active">
        <th scope="row">Ativo</th>
        <td>Célula</td>
        <td>Célula</td>
      </tr>
      <tr>
        <th scope="row">Padrão</th>
        <td>Célula</td>
        <td>Célula</td>
      </tr>

      {% for color in site.data.theme-colors %}
      <tr class="table-{{ color.name }}">
        <th scope="row">{{ color.name | capitalize }}</th>
        <td>Célula</td>
        <td>Célula</td>
      </tr>{% endfor %}
    </tbody>
  </table>
</div>

{% highlight html %}
<!-- Em linhas -->
<tr class="table-active">...</tr>
{% for color in site.data.theme-colors %}
<tr class="table-{{ color.name }}">...</tr>{% endfor %}

<!-- Em células (`td` ou `th`) -->
<tr>
  <td class="table-active">...</td>
  {% for color in site.data.theme-colors %}
  <td class="table-{{ color.name }}">...</td>{% endfor %}
</tr>
{% endhighlight %}

Variantes de background não estão disponíveis em tabelas escuras, mas você pode usar [utilitários de texto ou background]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/colors/) para atingir estilos similares.

<div class="bd-example">
  <table class="table table-dark">
    <thead>
      <tr>
        <th scope="col">#</th>
        <th scope="col">Cabeçalho</th>
        <th scope="col">Cabeçalho</th>
      </tr>
    </thead>
    <tbody>
      <tr class="bg-primary">
        <th scope="row">1</th>
        <td>Célula</td>
        <td>Célula</td>
      </tr>
      <tr>
        <th scope="row">2</th>
        <td>Célula</td>
        <td>Célula</td>
      </tr>
      <tr class="bg-success">
        <th scope="row">3</th>
        <td>Célula</td>
        <td>Célula</td>
      </tr>
      <tr>
        <th scope="row">4</th>
        <td>Célula</td>
        <td>Célula</td>
      </tr>
      <tr class="bg-info">
        <th scope="row">5</th>
        <td>Célula</td>
        <td>Célula</td>
      </tr>
      <tr>
        <th scope="row">6</th>
        <td>Célula</td>
        <td>Célula</td>
      </tr>
      <tr class="bg-warning">
        <th scope="row">7</th>
        <td>Célula</td>
        <td>Célula</td>
      </tr>
      <tr>
        <th scope="row">8</th>
        <td>Célula</td>
        <td>Célula</td>
      </tr>
      <tr class="bg-danger">
        <th scope="row">9</th>
        <td>Célula</td>
        <td>Célula</td>
      </tr>
    </tbody>
  </table>
</div>

{% highlight html %}
<!-- Em linhas -->
<tr class="bg-primary">...</tr>
<tr class="bg-success">...</tr>
<tr class="bg-warning">...</tr>
<tr class="bg-danger">...</tr>
<tr class="bg-info">...</tr>

<!-- Em células (`td` ou `th`) -->
<tr>
  <td class="bg-primary">...</td>
  <td class="bg-success">...</td>
  <td class="bg-warning">...</td>
  <td class="bg-danger">...</td>
  <td class="bg-info">...</td>
</tr>
{% endhighlight %}

{% capture callout-include %}{% include callout-warning-color-assistive-technologies.md %}{% endcapture %}
{{ callout-include | markdownify }}

Crie tabelas responsivas envolvendo qualquer `.table` com `.table-responsive{-sm|-md|-lg|-xl}`, fazendo a tabela ter rolagem horizontal em cada _breakpoint_ de `max-width`, por volta de (não extamente) 576px, 768px, 992px e 1120px, respectivamente.

{% capture callout-include %}{% include callout-info-mediaqueries-breakpoints.md %}{% endcapture %}
{{ callout-include | markdownify }}

## Legendas

Um `<caption>` funciona como um cabeçalho para a tabela. Isso ajuda usários de _screen readers_ achar uma tabela e descobrir sobre oquê é e decidir se eles querem lê-la.

{% example html %}
<table class="table">
  <caption>Lista de usuários</caption>
  <thead>
    <tr>
      <th scope="col">#</th>
      <th scope="col">Primeiro</th>
      <th scope="col">Último</th>
      <th scope="col">Nickname</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">1</th>
      <td>Mark</td>
      <td>Otto</td>
      <td>@mdo</td>
    </tr>
    <tr>
      <th scope="row">2</th>
      <td>Jacob</td>
      <td>Thornton</td>
      <td>@fat</td>
    </tr>
    <tr>
      <th scope="row">3</th>
      <td>Larry</td>
      <td>the Bird</td>
      <td>@twitter</td>
    </tr>
  </tbody>
</table>
{% endexample %}

## Tabelas responsivas

Tabelas responsivas permitem tabelas serem roladas horizontalmente, com facilidade. Faça com que qualquer tabela seja responsiva em todas _viewports_, simplesmente, envolvendo um `.table` com `.table-responsive`. Além disso, você pode escolher um _breakpoint_ máximo para a tabela ser responsiva, usando a classe `.table-responsive{-sm|-md|-lg|-xl}`.

{% callout warning %}
##### Corte vertical

Tabelas responsivas usam `overflow-y: hidden`, declaração a qual corta qualquer conteúdo que vai além da borda de cima ou de baixo, numa tabela. Em particular, isso pode acabar cortando menus dropdowns e outros widgets de terceiros.

{% endcallout %}

### Sempre responsiva

Use `.table-responsive` para fazer que tabelas rolem horizontalmente, através de todos dispositivos.

<div class="bd-example">
  <div class="table-responsive">
    <table class="table">
      <thead>
        <tr>
          <th scope="col">#</th>
          <th scope="col">Cabeçalho</th>
          <th scope="col">Cabeçalho</th>
          <th scope="col">Cabeçalho</th>
          <th scope="col">Cabeçalho</th>
          <th scope="col">Cabeçalho</th>
          <th scope="col">Cabeçalho</th>
          <th scope="col">Cabeçalho</th>
          <th scope="col">Cabeçalho</th>
          <th scope="col">Cabeçalho</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <th scope="row">1</th>
          <td>Célula</td>
          <td>Célula</td>
          <td>Célula</td>
          <td>Célula</td>
          <td>Célula</td>
          <td>Célula</td>
          <td>Célula</td>
          <td>Célula</td>
          <td>Célula</td>
        </tr>
        <tr>
          <th scope="row">2</th>
          <td>Célula</td>
          <td>Célula</td>
          <td>Célula</td>
          <td>Célula</td>
          <td>Célula</td>
          <td>Célula</td>
          <td>Célula</td>
          <td>Célula</td>
          <td>Célula</td>
        </tr>
        <tr>
          <th scope="row">3</th>
          <td>Célula</td>
          <td>Célula</td>
          <td>Célula</td>
          <td>Célula</td>
          <td>Célula</td>
          <td>Célula</td>
          <td>Célula</td>
          <td>Célula</td>
          <td>Célula</td>
        </tr>
      </tbody>
    </table>
  </div>
</div>

{% highlight html %}
<div class="table-responsive">
  <table class="table">
    ...
  </table>
</div>
{% endhighlight %}

### Breakpoint específico

Use `.table-responsive{-sm|-md|-lg|-xl}` sempre que necessário, para criar tabelas responsivas em um breakpoint específico. Desse breakpoint pra cima, a tabela vai se comportar normalmente e não vai rolar horizontalmente.

<div class="bd-example">
{% for bp in site.data.breakpoints %}{% unless bp.breakpoint == "xs" %}
<div class="table-responsive{{ bp.abbr }}">
  <table class="table">
    <thead>
      <tr>
        <th scope="col">#</th>
        <th scope="col">Cabeçalho</th>
        <th scope="col">Cabeçalho</th>
        <th scope="col">Cabeçalho</th>
        <th scope="col">Cabeçalho</th>
        <th scope="col">Cabeçalho</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <th scope="row">1</th>
        <td>Célula</td>
        <td>Célula</td>
        <td>Célula</td>
        <td>Célula</td>
        <td>Célula</td>
      </tr>
      <tr>
        <th scope="row">2</th>
        <td>Célula</td>
        <td>Célula</td>
        <td>Célula</td>
        <td>Célula</td>
        <td>Célula</td>
      </tr>
      <tr>
        <th scope="row">3</th>
        <td>Célula</td>
        <td>Célula</td>
        <td>Célula</td>
        <td>Célula</td>
        <td>Célula</td>
      </tr>
    </tbody>
  </table>
</div>
{% endunless %}{% endfor %}
</div>

{% highlight html %}
{% for bp in site.data.breakpoints %}{% unless bp.breakpoint == "xs" %}
<div class="table-responsive{{ bp.abbr }}">
  <table class="table">
    ...
  </table>
</div>
{% endunless %}{% endfor %}
{% endhighlight %}

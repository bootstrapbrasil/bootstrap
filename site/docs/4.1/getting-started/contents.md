---
layout: docs
title: Conteúdos
description: Descubra oquê têm no Bootstrap, incluindo nosso código fonte e compilado. Lembrando-se, também, que os plugins JavaScript precisam de jQuery.
group: getting-started
toc: true
---

## Bootstrap compilado

Uma vez baixado, descompacte a pasta comprimida e verá algo como isso:

<!-- NOTA: Esta informação foi duplicada intencionalmente, no README. Copie qualquer mudança feita aqui, no README, também, mas é claro que você pode manter dentro do diretório `dist`. -->

{% highlight plaintext %}
bootstrap/
├── css/
│   ├── bootstrap-grid.css
│   ├── bootstrap-grid.css.map
│   ├── bootstrap-grid.min.css
│   ├── bootstrap-grid.min.css.map
│   ├── bootstrap-reboot.css
│   ├── bootstrap-reboot.css.map
│   ├── bootstrap-reboot.min.css
│   ├── bootstrap-reboot.min.css.map
│   ├── bootstrap.css
│   ├── bootstrap.css.map
│   ├── bootstrap.min.css
│   └── bootstrap.min.css.map
└── js/
    ├── bootstrap.bundle.js
    ├── bootstrap.bundle.js.map
    ├── bootstrap.bundle.min.js
    ├── bootstrap.bundle.min.js.map
    ├── bootstrap.js
    ├── bootstrap.js.map
    ├── bootstrap.min.js
    └── bootstrap.min.js.map
{% endhighlight %}

Basicamente, isto é o Bootstrap: arquivos compilados, para uso rápido em qualquer projeto web. Nós provemos CSS e JS compilados (`bootstrap.*`), assim como CSS e JS compilados e minificados (`bootstrap.min*`). [Source maps](https://developers.google.com/web/tools/chrome-devtools/javascript/source-maps) CSS (`bootstrap.*.map`) estão disponíveis para uso em certas ferramentas de desenvolvedores dos browsers. Arquivos JS bundle (`bootstrap.bundle.js` e a versão minificada `bootstrap.bundle.min.js`) usam [Popper](https://popper.js.org/), mas não [jQuery](https://jquery.com/).

## Arquivos CSS

Bootstrap te da um punhado de opções para usar alguns ou todos os nossos CSSs compilados.

<table class="table table-bordered">
  <thead>
    <tr>
      <th scope="col">Arquivos CSS</th>
      <th scope="col">Layout</th>
      <th scope="col">Conteúdo</th>
      <th scope="col">Componentes</th>
      <th scope="col">Utilitários</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">
        <div><code class="font-weight-normal text-nowrap">bootstrap.css</code></div>
        <div><code class="font-weight-normal text-nowrap">bootstrap.min.css</code></div>
      </th>
      <td class="text-success">Incluído</td>
      <td class="text-success">Incluído</td>
      <td class="text-success">Incluído</td>
      <td class="text-success">Incluído</td>
    </tr>
    <tr>
      <th scope="row">
        <div><code class="font-weight-normal text-nowrap">bootstrap-grid.css</code></div>
        <div><code class="font-weight-normal text-nowrap">bootstrap-grid.min.css</code></div>
      </th>
      <td><a class="text-warning" href="{{ site.baseurl }}/docs/{{ site.docs_version }}/layout/grid/">Apenas o sistema de grid</a></td>
      <td class="bg-light text-muted">Não incluído</td>
      <td class="bg-light text-muted">Não incluído</td>
      <td><a class="text-warning" href="{{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/flex/">Apenas utilitários flex</a></td>
    </tr>
    <tr>
      <th scope="row">
        <div><code class="font-weight-normal text-nowrap">bootstrap-reboot.css</code></div>
        <div><code class="font-weight-normal text-nowrap">bootstrap-reboot.min.css</code></div>
      </th>
      <td class="bg-light text-muted">Não incluído</td>
      <td><a class="text-warning" href="{{ site.baseurl }}/docs/{{ site.docs_version }}/content/reboot/">Apenas o Reboot</a></td>
      <td class="bg-light text-muted">Não incluído</td>
      <td class="bg-light text-muted">Não incluído</td>
    </tr>
  </tbody>
</table>

## Arquivos JS

Similarmente, nós temos opções para uso de alguns ou todos os nosso scripts compilados.

<table class="table table-bordered">
  <thead>
    <tr>
      <th scope="col">Arquivos JS</th>
      <th scope="col">Popper</th>
      <th scope="col">jQuery</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">
        <div><code class="font-weight-normal text-nowrap">bootstrap.bundle.js</code></div>
        <div><code class="font-weight-normal text-nowrap">bootstrap.bundle.min.js</code></div>
      </th>
      <td class="text-success">Incluído</td>
      <td class="bg-light text-muted">Não incluído</td>
    </tr>
    <tr>
      <th scope="row">
        <div><code class="font-weight-normal text-nowrap">bootstrap.js</code></div>
        <div><code class="font-weight-normal text-nowrap">bootstrap.min.js</code></div>
      </th>
      <td class="bg-light text-muted">Não incluído</td>
      <td class="bg-light text-muted">Não incluído</td>
    </tr>
  </tbody>
</table>

## Código fonte Bootstrap

O código fonte Bootstrap inclui assets CSS e JS pré-compilados, junto com a fonte Sass, JavaScript e documentação. Mais especificamente, ele possui o seguinte e mais:

{% highlight plaintext %}
bootstrap/
├── dist/
│   ├── css/
│   └── js/
├── docs/
│   └── examples/
├── js/
└── scss/
{% endhighlight %}

Os diretórios `scss/` e `js/` são os códigos fontes do nosso CSS e JavaScript. A pasta `dist/` inclui tudo listado no download precompilado, que vimos na seção acima. O `docs/` possui o código fonte da documentação e no `examples/` temos a código para exemplos de uso do Bootstrap. Além disso, qualquer outro arquivo tem papel de dar suporte à pacotes, informações de licenças e desenvolvimento. 

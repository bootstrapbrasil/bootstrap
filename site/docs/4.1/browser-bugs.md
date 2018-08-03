---
layout: docs
title: Mural dos bugs de navegadores
group: browser-bugs
---

Bootstrap, atualmente, contorna diversos bugs nos maiores browsers, para prover a melhor experiência cross-browser, possível. No entanto, alguns bugs, como os listados abaixo, não podemos resolver.

Optamos por publicar nossos bugs mais impactantes, aqui. Isso para tentar resolvê-los mais rápido. Para mais informações sobre compatibilidade de browsers, [veja nossa documentação a respeito]({{ site.baseurl }}/docs/{{ site.docs_version }}/getting-started/browsers-devices/#supported-browsers).

Veja também:

* [Issue 536263 do Chromium: [meta] problemas afetando Bootstrap](https://bugs.chromium.org/p/chromium/issues/detail?id=536263)
* [Bug 1230801 do Mozilla: correção de problemas que afetam o Bootstrap](https://bugzilla.mozilla.org/show_bug.cgi?id=1230801)
* [Bug 159753 do Webkit: [meta] Problemas que afetam o Bootstrap](https://bugs.webkit.org/show_bug.cgi?id=159753)
* [Correção de bugs com jQuery](https://docs.google.com/document/d/1LPaPA30bLUB_publLIMF0RlhdnPx_ePXm7oW02iiT6o)

<table class="bd-browser-bugs table table-bordered table-hover">
  <thead>
    <tr>
      <th>Browser(s)</th>
      <th>Descrição</th>
      <th>Reporte original</th>
      <th>Reporte Bootstrap</th>
    </tr>
  </thead>
  <tbody>
    {% for bug in site.data.browser-bugs %}
    <tr>
      <td>{{ bug.browser }}</td>
      <td>{{ bug.summary | markdownify }}</td>
      <td>{% include bugify.html content=bug.upstream_bug %}</td>
      <td>{% include bugify.html content=bug.origin %}</td>
    </tr>
    {% endfor %}
  </tbody>
</table>

# Recursos mais desejados

Existem vários recursos nos padrões web que permitiriam-nos fazer o Bootstrap ser mais robusto, elegante e performático, mas que ainda não estão implementados em alguns browsers, portanto, evitando que nós tiremos vantagem deles.

Devido a isso, publicamos esta tabela de recursos mais pedidos, aqui. Com isso, esperamos incentivar suas implementações.

<table class="bd-browser-bugs table table-bordered table-hover">
  <thead>
    <tr>
      <th>Browser(s)</th>
      <th>Descrição</th>
      <th>Pedido de implementação original</th>
      <th>Pedido de implementação Bootstrap</th>
    </tr>
  </thead>
  <tbody>
    {% for feat in site.data.browser-features %}
    <tr>
      <td>{{ feat.browser }}</td>
      <td>{{ feat.summary | markdownify }}</td>
      <td>{% include bugify.html content=feat.upstream_bug %}</td>
      <td>{% include bugify.html content=feat.origin %}</td>
    </tr>
    {% endfor %}
  </tbody>
</table>

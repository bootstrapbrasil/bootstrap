---
layout: docs
title: Webpack
description: Aprenda como integrar o Bootstrap ao seu projeto, usando Webpack 3.
group: getting-started
toc: true
---

## Instalação do Bootstrap

[Instale o Bootstrap]({{ site.baseurl }}/docs/{{ site.docs_version }}/getting-started/download/#npm) como um módulo do Node.js, usando npm.

## Inportação do JavaScript

Importe o [JavaScript Bootstrap]({{ site.baseurl }}/docs/{{ site.docs_version }}/getting-started/javascript/), adicionando esta linha ao _entry point_ do seu app (`index.js` ou `app.js`, normalmente):

{% highlight js %}
import 'bootstrap';
{% endhighlight %}

Opcionalmente, você também pode **importar plugins individualmente**, sempre que necessário:

{% highlight js %}
import 'bootstrap/js/dist/util';
import 'bootstrap/js/dist/dropdown';
...
{% endhighlight %}

Bootstrap depende do [jQuery](https://jquery.com/) e [Popper](https://popper.js.org/), os quais são definidos como `peerDependencies`, significando que você terá que se certificar de adicionar os dois ao seu `package.json`, usando `npm install --save jquery popper.js`.

{% capture callout %}
Perceba que se você escolher **importar os plugins individualmente**, deverá instalar o [exports-loader](https://github.com/webpack-contrib/exports-loader), também.
{% endcapture %}
{% include callout.html content=callout type="warning" %}

## Importar estilos

### Importação do Sass pré-compilado

Para aproveitar todo potencial e personalizar o Bootstrap do jeito que quiser, use os arquivos fontes como parte do seu _bundling process_.

Primeiro, crie seu próprio `_custom.scss` e use-o para sobrescrever as [variáveis integradas de customização]({{ site.baseurl }}/docs/{{ site.docs_version }}/getting-started/options/). Assim, use o arquivo Sass principal para importar suas variáveis personalizadas e depois o Bootstrap, em si:

{% highlight scss %}
@import "custom";
@import "~bootstrap/scss/bootstrap";
{% endhighlight %}

Para o Bootstrap compilar, certifique-se de instalar e usar os _loaders_ necessários, que são: [sass-loader](https://github.com/webpack-contrib/sass-loader) e [postcss-loader](https://github.com/postcss/postcss-loader) com [Autoprefixer](https://github.com/postcss/autoprefixer#webpack). Nas mínimas configurações, seu Webpack deve ter esta regra ou algo parecido:

{% highlight js %}
  ...
  {
    test: /\.(scss)$/,
    use: [{
      loader: 'style-loader', // injeta CSS na página
    }, {
      loader: 'css-loader', // traduz CSS em módulos commonJS
    }, {
      loader: 'postcss-loader', // Executa tarefas do postcss
      options: {
        plugins: function () { // plugins postcss, podem ser exportados para o postcss.config.js
          return [
            require('precss'),
            require('autoprefixer')
          ];
        }
      }
    }, {
      loader: 'sass-loader' // compila Sass em CSS
    }]
  },
  ...
{% endhighlight %}

### Importação do CSS compilado

Opcionalmente, você pode usar o CSS Bootstrap pronto para uso, simplesmente, adicionando esta linha ao _entry point_ do seu projeto:

{% highlight js %}
import 'bootstrap/dist/css/bootstrap.min.css';
{% endhighlight %}

Neste caso, você pode usar suas regras `CSS` sem nenhuma modificação especial nas configurações webpack. Assim, você não precisa do `sass-loader`, apenas do [style-loader](https://github.com/webpack-contrib/style-loader) e [css-loader](https://github.com/webpack-contrib/css-loader).

{% highlight js %}
  ...
  module: {
    rules: [
      {
        test: /\.css$/,
        use: ['style-loader', 'css-loader']
      }
    ]
  }
  ...
{% endhighlight %}

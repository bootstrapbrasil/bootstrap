---
layout: docs
title: Download
description: Baixe o Bootstrap e obtenha o CSS e JavaScript compilado, além do código fonte. Também, você pode incluir o framework no seu gerenciador de pacotes predileto como npm, RubyGems, etc.
group: getting-started
toc: true
---

## CSS e JS compilado

Baixe o código compilado e pronto para uso do **Bootstrap v{{ site.current_version}}** para, facilmente, começar seu projeto. O download inclui:

- Pacotes de CSS minificados e compilados (veja a [comparação de arquivos CSS]({{ site.baseurl }}/docs/{{ site.docs_version }}/getting-started/contents/#css-files));
- Plugins JavaScripts compilados e minificados.

Este download não inclui documentação, códigos fontes ou qualquer dependências JavaScripts (jQuery ou Popper.js).

<a href="{{ site.download.dist }}" class="btn btn-bd-primary" onclick="ga('send', 'event', 'Getting started', 'Download', 'Download Bootstrap');">Baixar</a>

## Arquivos fontes

Compile o Bootstrap com suas próprias ferramentas, baixando nosso Sass, JavaScript e arquivos da documentação. Esta opção requer algumas ferramentas adicionais:

- Compilador Sass (Libsass ou Ruby Sass) para compilar seu CSS;
- [Autoprefixer](https://github.com/postcss/autoprefixer) para usar prefixos CSS.

[Ferramentas de build]({{ site.baseurl }}/docs/{{ site.docs_version }}/getting-started/build-tools/#tooling-setup) são usadas para desenvolver o Bootstrap e sua documentação, mas pode ser que sejam desncessárias para você.

<a href="{{ site.download.source }}" class="btn btn-bd-primary" onclick="ga('send', 'event', 'Getting started', 'Download', 'Download source');">Baixar fonte</a>

## BootstrapCDN

Evite o download, usando a [BootstrapCDN](https://www.bootstrapcdn.com/) para ter uma versão em cache dos CSS e JS compilados, em seu porjeto.

{% highlight html %}
<link rel="stylesheet" href="{{ site.cdn.css }}" integrity="{{ site.cdn.css_hash }}" crossorigin="anonymous">
<script src="{{ site.cdn.js }}" integrity="{{ site.cdn.js_hash }}" crossorigin="anonymous"></script>
{% endhighlight %}

Se você está usando nosso JavaScript compilado, não esqueça de incluir as versões em CDN do jQuery e Popper.js, antes dele.

{% highlight html %}
<script src="{{ site.cdn.jquery }}" integrity="{{ site.cdn.jquery_hash }}" crossorigin="anonymous"></script>
<script src="{{ site.cdn.popper }}" integrity="{{ site.cdn.popper_hash }}" crossorigin="anonymous"></script>
{% endhighlight %}

## Gerenciador de pacotes

Use o **código fonte** Bootstrap em qualquer projeto, com ajuda dos mais populares gerenciadores de pacotes. Não importa o gerenciador de pacotes, o Bootstrap **vai precisar de um compilador Sass e do [Autoprefixer](https://github.com/postcss/autoprefixer)**, para se ter uma configuração compatível com nossa versão compilada oficial.

### npm

Instale o Bootstrap em seus apps Node.js com o [pacote npm](https://www.npmjs.com/package/bootstrap):

{% highlight sh %}
npm install bootstrap
{% endhighlight %}

`require('bootstrap')` vai carregar todos os plugins jQuery no objeto jQuery. O próprio módulo `bootstrap` não exporta nada. Você pode, manualmente, carregar os plugins jQuery Bootstrap individualmente, carregando os arquivos `/js/*.js` dentro do diretório principal dos pacotes.

O `package.json` possui alguns metadados, nas seguintes chaves:

- `sass` - caminho para o principal arquivo [Sass](https://sass-lang.com/) Bootstrap;
- `style` - caminho para o CSS não minificado Bootstrap, o qual foi pré-compilado usando configurações padrões (sem customização).

### RubyGems

Instale o Bootstrap em seus apps Ruby, usando o [Bundler](https://bundler.io/) (**recomendado**) e [RubyGems](https://rubygems.org/), adicionando a seguinte linha ao seu [`Gemfile`](https://bundler.io/gemfile.html):

{% highlight ruby %}
gem 'bootstrap', '~> {{ site.current_ruby_version }}'
{% endhighlight %}

Alternativamente, se você não está usando o Bundler, pode instalar a gem executando este comando:

{% highlight sh %}
gem install bootstrap -v {{ site.current_ruby_version }}
{% endhighlight %}

[Veja o README da gem](https://github.com/twbs/bootstrap-rubygem/blob/master/README.md), para mais detalhes.

### Composer

Você também pode instalar e gerenciar o Sass e JavaScript do Bootstrap, usando o [Composer](https://getcomposer.org/):

{% highlight sh %}
composer require twbs/bootstrap:{{ site.current_version }}
{% endhighlight %}

### NuGet

Se você desenvolve em .NET, também pode instalar e gerenciar [CSS](https://www.nuget.org/packages/bootstrap/), [Sass](https://www.nuget.org/packages/bootstrap.sass/) e Javascript, usando [NuGet](https://www.nuget.org/):

{% highlight powershell %}
Install-Package bootstrap
{% endhighlight %}

{% highlight powershell %}
Install-Package bootstrap.sass
{% endhighlight %}

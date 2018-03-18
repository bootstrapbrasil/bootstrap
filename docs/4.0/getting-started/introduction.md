---
layout: docs
title: Introdução
description: Descubra o Bootstrap, o mais framework mais conhecido do mundo para criar sites responsivos e mobile, comece com o BootstrapCDN e nosso template inicial.
group: getting-started
redirect_from:
  - /docs/
  - /docs/4.0/
  - /docs/4.0/getting-started/
  - /docs/getting-started/
toc: true
---

## Visão rápida

Tentando adicionar rapidamente o Bootstrap ao seu projeto? Use o BootstrapCDN, provido gratuitamente pelo pessoal da MaxCDN. Usando um gerenciador ded pacotes ou precisa do código fonte? [Vá para a página de downloads.]({{ site.baseurl }}/docs/{{ site.docs_version }}/getting-started/download/)

### CSS

Copie e cole o arquivo de estilo `<link>` dentro da sua `<head>` antes de todos os outros arquivos de estilo para carregar nosso CSS.

{% highlight html %}
<link rel="stylesheet" href="{{ site.cdn.css }}" integrity="{{ site.cdn.css_hash }}" crossorigin="anonymous">
{% endhighlight %}

### JS

Muitos dos nossos componentes precisansam de JavaScript para funcionar. Mais especificamente, eles precisansam do [jQuery](https://jquery.com), [Popper.js](https://popper.js.org/) e do nossos próprios plugins JavaScript. Coloque os seguintes `<script>`s perto do final da sua página, logo antes do fechamento da tag `</body>`, para habilitá-los. jQuery tem que vir antes, depois o Popper.js e só depois nossos plugins JavaScript.

Nós usamos a [build slim do jQuery](https://blog.jquery.com/2016/06/09/jquery-3-0-final-released/), mas a versão completa também é suportada.

{% highlight html %}
<script src="{{ site.cdn.jquery }}" integrity="{{ site.cdn.jquery_hash }}" crossorigin="anonymous"></script>
<script src="{{ site.cdn.popper }}" integrity="{{ site.cdn.popper_hash }}" crossorigin="anonymous"></script>
<script src="{{ site.cdn.js }}" integrity="{{ site.cdn.js_hash }}" crossorigin="anonymous"></script>
{% endhighlight %}

Curiosidade para saber quais componentes precisam de jQuery, nosso JS e Popper,js? Clique em "Mostrar componentes dependentes de JavaScript" logo abaixo. Se resta dúvidas sobre a estrutura da página em geral, continue lendo para um templete de exemplo de página.

<details>
<summary class="text-primary mb-3">Mostrar componentes dependentes de JavaScript</summary>
{% capture markdown %}
- Alerts for dismissing
- Buttons for toggling states and checkbox/radio functionality
- Carousel for all slide behaviors, controls, and indicators
- Collapse for toggling visibility of content
- Dropdowns for displaying and positioning (also requires [Popper.js](https://popper.js.org/))
- Modals for displaying, positioning, and scroll behavior
- Navbar for extending our Collapse plugin to implement responsive behavior
- Tooltips and popovers for displaying and positioning (also requires [Popper.js](https://popper.js.org/))
- Scrollspy for scroll behavior and navigation updates
{% endcapture %}
{{ markdown | markdownify }}
</details>

## Template inicial

Be sure to have your pages set up with the latest design and development standards. That means using an HTML5 doctype and including a viewport meta tag for proper responsive behaviors. Put it all together and your pages should look like this:

{% highlight html %}
<!doctype html>
<html lang="pt-br">
  <head>
    <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">

    <!-- Bootstrap CSS -->
    <link rel="stylesheet" href="{{ site.cdn.css }}" integrity="{{ site.cdn.css_hash }}" crossorigin="anonymous">

    <title>Olá, mundo!</title>
  </head>
  <body>
    <h1>Olá, mundo!</h1>

    <!-- Optional JavaScript -->
    <!-- jQuery first, then Popper.js, then Bootstrap JS -->
    <script src="{{ site.cdn.jquery }}" integrity="{{ site.cdn.jquery_hash }}" crossorigin="anonymous"></script>
    <script src="{{ site.cdn.popper }}" integrity="{{ site.cdn.popper_hash }}" crossorigin="anonymous"></script>
    <script src="{{ site.cdn.js }}" integrity="{{ site.cdn.js_hash }}" crossorigin="anonymous"></script>
  </body>
</html>
{% endhighlight %}

That's all you need for overall page requirements. Visit the [Layout docs]({{ site.baseurl }}/docs/{{ site.docs_version }}/layout/overview/) or [our official examples]({{ site.baseurl }}/docs/{{ site.docs_version }}/examples/) to start laying out your site's content and components.

## Importância geral

Bootstrap employs a handful of important global styles and settings that you'll need to be aware of when using it, all of which are almost exclusively geared towards the *normalization* of cross browser styles. Let's dive in.

### HTML5 doctype

Bootstrap requires the use of the HTML5 doctype. Without it, you'll see some funky incomplete styling, but including it shouldn't cause any considerable hiccups.

{% highlight html %}
<!doctype html>
<html lang="en">
  ...
</html>
{% endhighlight %}

### Meta tag responsiva

Bootstrap is developed *mobile first*, a strategy in which we optimize code for mobile devices first and then scale up components as necessary using CSS media queries. To ensure proper rendering and touch zooming for all devices, **add the responsive viewport meta tag** to your `<head>`.

{% highlight html %}
<meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
{% endhighlight %}

You can see an example of this in action in the [starter template](#starter-template).

### Box-sizing

For more straightforward sizing in CSS, we switch the global `box-sizing` value from `content-box` to `border-box`. This ensures `padding` does not affect the final computed width of an element, but it can cause problems with some third party software like Google Maps and Google Custom Search Engine.

On the rare occasion you need to override it, use something like the following:

{% highlight css %}
.selector-for-some-widget {
  box-sizing: content-box;
}
{% endhighlight %}

With the above snippet, nested elements—including generated content via `::before` and `::after`—will all inherit the specified `box-sizing` for that `.selector-for-some-widget`.

Learn more about [box model and sizing at CSS Tricks](https://css-tricks.com/box-sizing/).

### Reinicialização 

For improved cross-browser rendering, we use [Reboot]({{ site.baseurl }}/docs/{{ site.docs_version }}/content/reboot/) to correct inconsistencies across browsers and devices while providing slightly more opinionated resets to common HTML elements.

## Comunidade

Stay up to date on the development of Bootstrap and reach out to the community with these helpful resources.

- Follow [@getbootstrap on Twitter](https://twitter.com/getbootstrap).
- Read and subscribe to [The Official Bootstrap Blog]({{ site.blog }}).
- Join [the official Slack room]({{ site.slack }}).
- Chat with fellow Bootstrappers in IRC. On the `irc.freenode.net` server, in the `##bootstrap` channel.
- Implementation help may be found at Stack Overflow (tagged [`bootstrap-4`](https://stackoverflow.com/questions/tagged/bootstrap-4)).
- Developers should use the keyword `bootstrap` on packages which modify or add to the functionality of Bootstrap when distributing through [npm](https://www.npmjs.com/browse/keyword/bootstrap) or similar delivery mechanisms for maximum discoverability.

You can also follow [@getbootstrap on Twitter](https://twitter.com/getbootstrap) for the latest gossip and awesome music videos.

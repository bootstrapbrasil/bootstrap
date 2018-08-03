---
layout: docs
title: Introdução
description: Descubra o Bootstrap, o framework mais conhecido do mundo para criar sites responsivos e mobile, comece com o BootstrapCDN e nosso template inicial.
group: getting-started
  - /docs/
  - /docs/4.1/
  - /docs/4.1/getting-started/
  - /docs/getting-started/
toc: true
---

## Visão rápida

Tentando adicionar rapidamente o Bootstrap ao seu projeto? Use o BootstrapCDN, fornecido gratuitamente pelo pessoal da MaxCDN. Usando um gerenciador de pacotes ou precisa do código fonte? [Vá para a página de downloads.]({{ site.baseurl }}/docs/{{ site.docs_version }}/getting-started/download/)

### CSS

Copie e cole o arquivo de estilo `<link>` dentro da sua `<head>` antes de todos os outros arquivos de estilo para carregar nosso CSS.

{% highlight html %}
<link rel="stylesheet" href="{{ site.cdn.css }}" integrity="{{ site.cdn.css_hash }}" crossorigin="anonymous">
{% endhighlight %}

### JS

Muitos dos nossos componentes precisam de JavaScript para funcionar. Mais especificamente, eles precisam do [jQuery](https://jquery.com), [Popper.js](https://popper.js.org/) e do nossos próprios plugins JavaScript. Coloque os seguintes `<script>`s perto do final da sua página, logo antes do fechamento da tag `</body>`. jQuery tem que vir antes, depois o Popper.js e só depois nossos plugins JavaScript.

Nós usamos a [build slim do jQuery](https://blog.jquery.com/2016/06/09/jquery-3-0-final-released/), mas a versão completa também é suportada.

{% highlight html %}
<script src="{{ site.cdn.jquery }}" integrity="{{ site.cdn.jquery_hash }}" crossorigin="anonymous"></script>
<script src="{{ site.cdn.popper }}" integrity="{{ site.cdn.popper_hash }}" crossorigin="anonymous"></script>
<script src="{{ site.cdn.js }}" integrity="{{ site.cdn.js_hash }}" crossorigin="anonymous"></script>
{% endhighlight %}

Curiosidade para saber quais componentes precisam de jQuery, nosso JS e Popper.js? Clique em "Mostrar componentes dependentes de JavaScript" logo abaixo. Se ainda tem dúvidas sobre a estrutura da página em geral, continue lendo para um templete de exemplo de página.

Our `bootstrap.bundle.js` and `bootstrap.bundle.min.js` include [Popper](https://popper.js.org/), but not [jQuery](https://jquery.com/). For more information about what's included in Bootstrap, please see our [contents]({{ site.baseurl }}/docs/{{ site.docs_version }}/getting-started/contents/#precompiled-bootstrap) section.

<details>
<summary class="text-primary mb-3">Mostrar componentes dependentes de JavaScript</summary>
{% capture markdown %}
- Botões de dispensar alertas;
- Botões para alternar estados e funcionalidades dos botões checkboxes e radios;
- Comportamento de deslize, controles e indicadores do Carousel;
- Colapso para alternar visibilidade de conteúdo;
- Apresentação e posicionamento de dropdowns;
  - Também requer [Popper.js](https://popper.js.org/).
- Apresentação, posicionamento e rolagem nos Modais;
- Aprimorar nosso plugin de colapso em navbars, para implementar comportamento responsivo;
- Posicionamento e apresentação de tooltips e popovers;
  - Também requer [Popper.js](https://popper.js.org/).
- Comportamento de rolagem e atualizações de navegação no Scrollspy.
{% endcapture %}
{{ markdown | markdownify }}
</details>

## Template inicial

Tenha certeza de configurar suas páginas com padrões recentes de desenvolvimento e design. Ou seja, utilizando HTML5 doctype e a meta tag viewport para proporcionar o funcionamento responsivo adequado. Feito isto, suas páginas devem ficar assim:

{% highlight html %}
<!DOCTYPE html>
<html lang="pt-br">
  <head>
    <!-- Meta tags Obrigatórias -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">

    <!-- Bootstrap CSS -->
    <link rel="stylesheet" href="{{ site.cdn.css }}" integrity="{{ site.cdn.css_hash }}" crossorigin="anonymous">

    <title>Olá, mundo!</title>
  </head>
  <body>
    <h1>Olá, mundo!</h1>

    <!-- JavaScript (Opcional) -->
    <!-- jQuery primeiro, depois Popper.js, depois Bootstrap JS -->
    <script src="{{ site.cdn.jquery }}" integrity="{{ site.cdn.jquery_hash }}" crossorigin="anonymous"></script>
    <script src="{{ site.cdn.popper }}" integrity="{{ site.cdn.popper_hash }}" crossorigin="anonymous"></script>
    <script src="{{ site.cdn.js }}" integrity="{{ site.cdn.js_hash }}" crossorigin="anonymous"></script>
  </body>
</html>
{% endhighlight %}

No geral, são esses os requisitos para o funcionamento da página. Visite a [Documentação de Layout]({{ site.baseurl }}/docs/{{ site.docs_version }}/layout/overview/) ou [nossos exemplos oficiais]({{ site.baseurl }}/docs/{{ site.docs_version }}/examples/) para começar a incluir conteúdos e componentes em seu site.

## Importância geral

O Bootstrap usa um punhado de estilos globais e configurações importantes que você precisará ficar atento, quando tiver usando, os quais são guiados a *normalização* de estilos cross browsers. Vamos lá!

### HTML5 doctype

Bootstrap exige o uso do doctype HTML5. Sem isso, você verá alguns estilos incompletos e esquisitos.

{% highlight html %}
<!DOCTYPE html>
<html lang="pt-br">
  ...
</html>
{% endhighlight %}

### Meta tag responsiva

Bootstrap tem uma abordagem *mobile first*, uma estratégia que optimizamos o código para dispositivos móveis primeiro e, então, é que começamos a pensar em media queries para aparelhos maiores. Por isso, para garantir renderização adequada e _touch zooming_ em todos eletrônicos, **use a tag responsiva viewport** no `<head>`.

{% highlight html %}
<meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
{% endhighlight %}

Você pode ver um exemplo disso em ação, neste [template iniciante](#starter-template).

### Box-sizing

Para um redimensionamento mais intuitivo no CSS, nós trocamos o valor do `box-sizing` global de `content-box` para `border-box`. Dessa maneira, garantimos que o `padding` não afetará a largura computada final de um elemento, apesar de isto poder causar problemas em alguns softwares de terceiros, como Google Maps e Google Search Engine.

Na rara ocasião de precisar sobrecrever isso, use algo como o seguinte:

{% highlight css %}
.seletor-para-algum-widget {
  box-sizing: content-box;
}
{% endhighlight %}

Com o snippet acima, elementos aninhados (incluindo conteúdo gerado via `::before` e `::after`) vão herdar o `box-sizing` especificado no `seletor-para-algum-widget`.

Aprenda mais sobre o [box model e dimensionamento, no CSS Tricks](https://css-tricks.com/box-sizing/).

### Reboot

Para uma renderização cross-browser melhorada, nós usamos o [Reboot]({{ site.baseurl }}/docs/{{ site.docs_version }}/content/reboot/) para corrigir inconsistências através dos browsers, enquanto provemos resets um pouquinho customizados para elementos HTML comuns.


## Comunidade

Fique atualizado no desenvolvimento do Bootstrap e encontre nossa comunidade através destas fontes úteis:

- Siga [@getbootstrap no Twitter](https://twitter.com/getbootstrap);
- Leia e se inscreva no [Blog Bootstrap Oficial]({{ site.blog }});
- Participe da [nossa sala oficial no Slack]({{ site.slack }});
- Converse com os Bootstrappers via IRC, através do servidor `irc.freenode.net`, no canal `##bootstrap`;
- Ajuda com implementação pode ser encontrada no Stack Overflow (tag [`bootstrap-4`](https://stackoverflow.com/questions/tagged/bootstrap-4));
- Desenvolvedores devem usar a palavra-chave `bootstrap` em pacotes que modificarem ou adicionarem funcionalidades do Bootstrap, quando distribuindo via [npm](https://www.npmjs.com/browse/keyword/bootstrap) ou sistemas de entrega semelhantes, para máxima visibilidade.

Você também pode seguir o [@getbootstrap no Twitter](https://twitter.com/getbootstrap), para as melhores fofocas e vídeo clipes. =)

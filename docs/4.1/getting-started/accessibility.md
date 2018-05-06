---
layout: docs
title: Acessibilidade
description: Uma breve visão geral dos recursos e limitações do Bootstrap para a criação de conteúdo acessível.
group: getting-started
toc: true
---

O Bootstrap fornece um framework fácil de usar, com estilos prontos, ferramentas de layout e componentes interativos, permitindo que os desenvolvedores criem sites e aplicações que sejam visualmente atraentes, ricas em funcionalidades e de rápido acesso.

## Visão geral e limitações

A acessibilidade no geral de qualquer projeto criado com o Bootstrap depende, em grande parte, da marcação do autor, do estilo adicional e do script que eles incluíram. No entanto, desde que estes tenham sido implementados corretamente, deve ser perfeitamente possível criar sites e aplicativos com Bootstrap que preencham as normas e requisitos de acessibilidade da [<abbr title="Web Content Accessibility Guidelines">WCAG</abbr> 2.0](https://www.w3.org/TR/WCAG20/) (A/AA/AAA), [Seção 508](https://www.section508.gov/) e semelhantes.

### Marcação estrutural

O estilo e o layout do Bootstrap podem ser aplicados a uma ampla variedade de estruturas de marcações. Esta documentação tem como objetivo fornecer aos desenvolvedores os melhores exemplos e práticas para demonstrar o uso do próprio Bootstrap e ilustrar a marcação semântica apropriada, incluindo maneiras pelas quais possíveis preocupações de acessibilidade podem ser evitadas.

### Componentes interativos

Os componentes interativos do Bootstrap, como modais, menus suspensos e dicas de ferramentas personalizadas, são projetados para funcionar com touch-pad, mouse e teclado. Por meio do uso de funções e atributos relevantes do [<abbr title="Web Accessibility Initiative">WAI</abbr>-<abbr title="Accessible Rich Internet Applications">ARIA</abbr>](https://www.w3.org/WAI/intro/aria), esses componentes também devem ser compreensíveis e operáveis usando tecnologias assistivas (como leitores de tela).

Como os componentes do Bootstrap são propositadamente projetados para serem bastante genéricos, os autores podem precisar incluir mais regras e atributos do <abbr title="Accessible Rich Internet Applications">ARIA</abbr>, bem como o comportamento do JavaScript, para transmitir com mais precisão a natureza e funcionalidade precisas de seus componentes. Isso geralmente é observado na documentação.

### Contraste de cor

A maioria das cores que atualmente compõem a paleta padrão do Bootstrap - usada em toda a estrutura para variações de botões, variações de alerta, indicadores de validação de formulário - leva a um contraste de cores insuficiente (abaixo da relação de contraste de cores recomendada [WCAG 2.0 color contrast ratio of 4.5:1](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-contrast.html)) quando usado contra um fundo claro. Os autores precisarão modificar / estender manualmente essas cores padrão para garantir taxas de contraste de cores adequadas.

### Conteúdo visualmente oculto

O conteúdo que deve estar visualmente oculto, mas permanecer acessível a tecnologias assistivas, como leitores de tela, pode ser estilizado usando a classe `.sr-only`. Isso pode ser útil em situações em que informações ou dicas visuais adicionais (como o significado denotado pelo uso da cor) também precisam ser transmitidas a usuários não visuais.

{% highlight html %}
<p class="text-danger">
  <span class="sr-only">Perigo: </span>
  Esta ação não é reversível.
</p>
{% endhighlight %}

Para controles interativos visualmente ocultos, como os links “skip” tradicionais, o `.sr-only` pode ser combinado com a classe `.sr-only-focusable`. Isso garantirá que o controle se torne visível uma vez em foco (para usuários de teclado com visão).

{% highlight html %}
<a class="sr-only sr-only-focusable" href="#content">Voltar ao conteúdo principal.</a>
{% endhighlight %}

## Recursos Adicionais

- [Web Content Accessibility Guidelines (WCAG) 2.0](https://www.w3.org/TR/WCAG20/)
- [The A11Y Project](http://a11yproject.com/)
- [MDN accessibility documentation](https://developer.mozilla.org/en-US/docs/Web/Accessibility)
- [Tenon.io Accessibility Checker](https://tenon.io/)
- [Colour Contrast Analyser (CCA)](https://developer.paciellogroup.com/resources/contrastanalyser/)
- ["HTML Codesniffer" bookmarklet for identifying accessibility issues](https://github.com/squizlabs/HTML_CodeSniffer)

---
layout: docs
title: JavaScript
description: Traga o Bootstrap a vida com nossos plugins opcionais, construídos com jQuery. Aprenda sobre cada plugin, nossos dados e API programática, entre outras coisas.
group: getting-started
toc: true
---

## Individualmente ou compilado

Plugins podem ser incluídos individualmente, usando os arquivos Bootstrap `*.js` individuais. Também é possível incluir todos de uma vez, usando `bootstrap.js` ou a versão minificada `bootstrap.min.js`.

## Dependências

Alguns plugins e componentes CSS dependem de outros plugins. Se você incluir plugins individualmente, tenha certeza de ler sobre estas dependências, na documentação. Também perceba que **todos plugins dependem do jQuery**, significando que esta biblioteca deve ser adicionada **antes** dos arquivos dos plugins. [Consulte o `package.json`]({{ site.repo }}/blob/v{{ site.current_version }}/package.json) para ver quais versões do jQuery são suportadas.

Nossos dropdowns, popovers e tooltips também dependem do [Popper.js](https://popper.js.org/).

## Atributos data

Quase todos plugins Bootstrap podem ser ativados e configurados somente através do HTML, usando atributos data (nosso jeito preferido de usar essa funcionalidade JavaScript). Assegure-se de **usar apenas um atributo data**, por elemento. Exemplo: você não pode acionar um tooltip e um modal, usando o mesmo botão.

No entanto, em algumas situações você pode querer desativar esta funcionalidade. Para desativar a API do atributo data, você pode desvincular todos eventos no documento nomeados com `data-api`, fazendo algo como isso:

{% highlight js %}
$(document).off('.data-api')
{% endhighlight %}

Opcionalmente, para desvincular um plugin específico, basta usar o _namespace_ do plugin seguido do _namespace_ data-api, como isso:

{% highlight js %}
$(document).off('.alert.data-api')
{% endhighlight %}

{% capture callout %}
##### Escapando seletores
Se você usa algum tipo de seletor especial (como `collapse:Example`), se garanta de escapá-lo porque ele vai ser analisado pelo jQuery.
{% endcapture %}
{% include callout.html content=callout type="warning" %}

## Eventos

Bootstrap provê eventos customizados para a maioria das ações dos plugins. Geralmente, eles aparecem no infinitivo ou passado particípio, onde o infinitivo (`show`, por exemplo) é acionado no começo de um evento e sua forma no passado particípio (`shown`) é acionada no final de uma ação.

Todos eventos no infinitivo possuem a funcionalidade [`preventDefault()`](https://developer.mozilla.org/en-US/docs/Web/API/Event/preventDefault). Assim, tem-se a habilidade de parar a execução de uma ação, antes que ela começe. Retornar `false` em um evento também vai invocar o método `preventDefault()`, automaticamente.

{% highlight js %}
$('#myModal').on('show.bs.modal', function (e) {
  if (!data) return e.preventDefault() // Evita que o modal apareça
})
{% endhighlight %}

## API programática

Nós também acreditamos que você será capaz de usar todos plugins Bootstrap, somente usando a API JavaScript. Todas APIs públicas são métodos encadeáveis e peculiares, além de retornarem a coleção que analisaram.

{% highlight js %}
$('.btn.danger').button('toggle').addClass('fat')
{% endhighlight %}

Todos métodos devem aceitar um objeto options opcional, uma string que olha por um método específico ou nada (oquê inicia o comportamento padrão dos plugins):

{% highlight js %}
$('#myModal').modal()                      // inicia com padrões
$('#myModal').modal({ keyboard: false })   // inicia sem teclado
$('#myModal').modal('show')                // inicia e invoca show, imediatamente.
{% endhighlight %}

Cada plugin também expõe seu construtor na propriedade `Constructor` (`$.fn.popover.Constructor`). Se você quer de obter uma instância específica de um plugin, recupere-a de um elemento (`$('[rel="popover"]').data('popover')`), diretamente.

### Funções e transições assíncronas

Todos métodos de API programáticas são **assíncronos** e retornam o invocador, uma vez que a transição é iniciada (**mas é antes que ela finalize**).

Para executar uma ação quando a transição é finalizada, você pode "ouvir" o evento correspondente.

{% highlight js %}
$('#myCollapse').on('shown.bs.collapse', function (e) {
  // Ação a executar, uma vez que a área colapsável é expandida
})
{% endhighlight %}

Além disso, a invocação de método **num componente em transição** vai ser ignorada.

{% highlight js %}
$('#myCarousel').on('slid.bs.carousel', function (e) {
  $('#myCarousel').carousel('2') // Vai deslizar para o slide 2, antes que a transição do slide 1 finalize
})

$('#myCarousel').carousel('1') // Vai começar deslizando para o slide 1 e retornará o invocador
$('#myCarousel').carousel('2') // !! Vai ser ignorado, já que a transição para o slide 1 ainda não finalizou !!
{% endhighlight %}

### Configurações padrões

Você pode alterar as configurações padrões de um plugin, modificado o objeto `Constructor.Default` do plugin:

{% highlight js %}
$.fn.modal.Constructor.Default.keyboard = false // altera o default da opção `keyboard` do plugin modal para `false`
{% endhighlight %}

## Sem conflitos

Algumas vezes, pode ser necessário usar plugins Bootstrap com outros frameworks UI. nestas circunstâncias, colisões de _namespace_ podem ocorrer, ocasionalmente. Se isso acontecer, você pode invocar `.noconflict` no plugin que você quiser reverter o valor.

{% highlight js %}
var bootstrapButton = $.fn.button.noConflict() // retorna $.fn.button para o valor declarado anteriormente
$.fn.bootstrapBtn = bootstrapButton            // dá a funcionalidade Bootstrap ao $().bootstrapBtn
{% endhighlight %}

## Número de versões

A versão de cada plugin Bootstrap feito com jQuery pode ser acessada usando a propriedade `VERSION` do construtor do plugin. Por exemplo, usando o plugin tooltip:

{% highlight js %}
$.fn.tooltip.Constructor.VERSION // => "{{ site.current_version }}"
{% endhighlight %}

## JavaScript desativado

Os plugins Bootstrap não possuem um fallback muito bom, quando o JavaScript está desativado. Se você se importa com a experiência do usuário, neste caso, use [`<noscript>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/noscript) para explicar a situação, como reativar o JavaScript e/ou adicionar seus próprios fallbacks.

{% capture callout %}
##### Bibliotecas de terceiros

**Bootstrap não suporta biblioteca de terceiros**, oficialmente, como Prototype ou jQuery UI. Tirando o `.noConflict` e eventos com _namespace_, pode acontecer problemas de compatibilidade que você precisará consertar sozinho.
{% endcapture %}
{% include callout.html content=callout type="warning" %}

## Util

Todos arquivos JavaScript Bootstrap dependem do `util.js`, fazendo com que seja necessário incluí-lo junto aos outros arquivos JavaScript. Se você está usando o `bootstrap.js` minificado, não há necessidade de incluir o `util.js` porque ele já está incluído no `bootstrap.min.js`.

O `util.js` possui funções utilitárias e ajuda básica para eventos `transitionEnd`, assim como um emulador de transição CSS. Isso é usado pelos outros plugins para conferir suporte de transições CSS e capturar transições suspensas.

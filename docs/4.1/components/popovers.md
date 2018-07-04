---
layout: docs
title: Popovers
description: Documentação e exemplos para criar popovers Bootstrap (igual aqueles do iOS), em qualquer elemento do seu site.
group: components
toc: true
---

## Visão geral

Coisas para saber, quando usando o plugin popover:

- O popover depende da biblioteca externa [Popper.js](https://popper.js.org/), para posicionamento;
  - Você deve colocar [popper.min.js]({{ site.cdn.popper }}) antes de `bootstrap.js` ou usar `bootstrap.bundle.min.js` / `bootstrap.bundle.js`, os quais contém Popper.js para o popover funcionar.
- Popovers precisam do [plugin tooltip]({{ site.baseurl }}/docs/{{ site.docs_version }}/components/tooltips/), como sua dependência;
- Se você está montando o JavaScript a partir da fonte, vai precisar do [`util.js`]({{ site.baseurl }}/docs/{{ site.docs_version }}/getting-started/javascript/#util);
- Popovers são opcionais por motivos de desempenho, então, **você deve inciá-lo, por conta própria**;
- Atributos `title` e `content` vazios nunca vão ser mostrados em um popover;
- Declare `container: 'body'` para evitar problemas de renderização, em componentes mais complexos (como nos grupos de inputs ou botões);
- Acionar popovers em elementos ocultos não funciona;
- Popovers em elementos `.disabled` ou `disabled` devem ser acionados em um elemento pai;
- Quando acionados por âncoras que envolvem várias linhas, os popovers serão centralizados entre a largura total das âncoras;
  - Use `white-space: nowrap;` em seus `<a>`, para evitar este comportamento.
- Popovers devem ser ocultos, antes que seus elementos correspondentes sejam removidos do DOM.

Continue lendo, para ver como popovers funcionam, em alguns exemplos.

## Ative popovers, em qualquer lugar.

Uma maneira de inicializar todos popovers, em uma página, seria selecioná-los por seus atributos `data-toggle`:

{% highlight js %}
$(function () {
  $('[data-toggle="popover"]').popover()
})
{% endhighlight %}

## Usando o parâmetro `container`.

Quando você tem alguns estilos em um elemento pai que interfere no popover, você vai querer especificar um `container` personalizado para que, pelo contrário, o HTML do popover apareça dentro do elemento.

{% highlight js %}
$(function () {
  $('.popover-exemplo').popover({
    container: 'body'
  })
})
{% endhighlight %}

## Demonstração

{% capture example %}
<button type="button" class="btn btn-lg btn-danger" data-toggle="popover" title="Título do popover" data-content="Aqui vai algum tipo de conteúdo. Muito da hora, né?!">Clique para ver o popover</button>
{% endcapture %}
{% include example.html content=example %}

### As quatro direções

Quatro opções de direção estão disponíveis: top, right, bottom e left.

<div class="bd-example popover-demo">
  <div class="bd-example-popovers">
    <button type="button" class="btn btn-secondary" data-container="body" data-toggle="popover" data-placement="top" data-content="Vivamus sagittis lacus vel augue laoreet rutrum faucibus.">
      Popover na parte superior
    </button>
    <button type="button" class="btn btn-secondary" data-container="body" data-toggle="popover" data-placement="right" data-content="Vivamus sagittis lacus vel augue laoreet rutrum faucibus.">
      Popover na direita
    </button>
    <button type="button" class="btn btn-secondary" data-container="body" data-toggle="popover" data-placement="bottom" data-content="Vivamus sagittis lacus vel augue laoreet rutrum faucibus.">
      Popover na parte inferior
    </button>
    <button type="button" class="btn btn-secondary" data-container="body" data-toggle="popover" data-placement="left" data-content="Vivamus sagittis lacus vel augue laoreet rutrum faucibus.">
      Popover na esquerda
    </button>
  </div>
</div>

{% highlight html %}
<button type="button" class="btn btn-secondary" data-container="body" data-toggle="popover" data-placement="top" data-content="Vivamus sagittis lacus vel augue laoreet rutrum faucibus.">
  Popover na parte superior
</button>

<button type="button" class="btn btn-secondary" data-container="body" data-toggle="popover" data-placement="right" data-content="Vivamus sagittis lacus vel augue laoreet rutrum faucibus.">
  Popover na direita
</button>

<button type="button" class="btn btn-secondary" data-container="body" data-toggle="popover" data-placement="bottom" data-content="Vivamus sagittis lacus vel augue laoreet rutrum faucibus.">
  Popover na parte inferior
</button>

<button type="button" class="btn btn-secondary" data-container="body" data-toggle="popover" data-placement="left" data-content="Vivamus sagittis lacus vel augue laoreet rutrum faucibus.">
  Popover na esquerda
</button>
{% endhighlight %}

### Dispensar no próximo clique

Use o gatilho `focus` para dispensar popovers, no próximo clique do usuário, em um elemento diferente do qual ativou o popover.

{% capture callout %}
#### Marcação HTML necessária para dispensar, no próximo clique.

Para um comportamento cross-browser e cross-platform, adequado, você deve usar a tag `<a>`, mas _não_ `<button>`. Além do mais, você deve usar o atributo [`tabindex`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/tabindex).

{% endcapture %}
{% include callout.html content=callout type="danger" %}

{% capture example %}
<a tabindex="0" class="btn btn-lg btn-danger" role="button" data-toggle="popover" data-trigger="focus" title="Popover dispensável" data-content="Aqui vai algum tipo de conteúdo. Muito da hora, né?!">Popover dispensável</a>
{% endcapture %}
{% include example.html content=example %}

{% highlight js %}
$('.popover-dismiss').popover({
  trigger: 'focus'
})
{% endhighlight %}

### Elementos desativados

Elementos com o atributo `disabled` não são interativos, significando que usuários não podem passar o mouse sobre eles  ou clicar para acionar um popover ou tooltip. Como uma forma de contornar a situação, você vai querer acionar o popover a partir de um elemento pai `<div>` ou `<span>` e sobrescrever o `pointer-eventer`, no elemento desativado.

Para acionadores de popovers desativados, você também podem preferir usar `data-trigger="hover"` para que o popover apareça como um feedback visual imediato para seus usuários, já que eles esperam não ter que clicar em um elemento desativado.

{% capture example %}
<span class="d-inline-block" data-toggle="popover" data-content="Popover desativado">
  <button class="btn btn-primary" style="pointer-events: none;" type="button" disabled>Botão desativado</button>
</span>
{% endcapture %}
{% include example.html content=example %}

## Modo de uso

Ative popovers, via JavaScript:

{% highlight js %}$('#exemplo').popover(options){% endhighlight %}

### Parâmetros

Parâmetros podem ser passados via atributos data ou JavaScript. No caso de atributos data, anexe o nome do parâmetro ao prefixo `data-`, como em `data-animation=""`.

<table class="table table-bordered table-striped">
  <thead>
    <tr>
      <th style="width: 100px;">Nome</th>
      <th style="width: 100px;">Tipo</th>
      <th style="width: 50px;">Padrão</th>
      <th>Descrição</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>animation</td>
      <td>booleano</td>
      <td>true</td>
      <td>Aplica um transição fade CSS, no popover.</td>
    </tr>
    <tr>
      <td>container</td>
      <td>string | elemento | false</td>
      <td>false</td>
      <td>
        <p>Anexa o popover, em um elemento específico. Este parâmetro é, particularmente, útil porque permite você posiciona o popover, no fluxo do documento, perto do elemento gatilho. Isso vai evitar que o popover flutue para longe do elemento gatilho, durante redimensionamento de janela. Exemplo de uso: <code>container: 'body'</code>.</p>
      </td>
    </tr>
    <tr>
      <td>content</td>
      <td>string | elemento | função</td>
      <td>''</td>
      <td>
        <p>Valor padrão do conteúdo, se o atributo <code>data-content</code> não está presente.</p>
        <p>Se uma função é provida, ela vai ser invocada com sua referência <code>this</code> definida no elemento que o popover é anexado.</p>
      </td>
    </tr>
    <tr>
      <td>delay</td>
      <td>number | objeto</td>
      <td>0</td>
      <td>
        <p>Atraso na hora de exibir ou ocultar o popover, em ms. Não se aplica ao tipo de acionamento manual.</p>
        <p>Se um número é provido, o atraso é aplicado tanto em exibição, quanto em ocultação.</p>
        <p>A estrutura do objeto é: <code>delay: { "show": 500, "hide": 100 }</code></p>
      </td>
    </tr>
    <tr>
      <td>html</td>
      <td>booleano</td>
      <td>false</td>
      <td>Coloque HTML, dentro do popover. Se falso, o método jQuery <code>text</code> será usado para inserir conteúdo no DOM. Use texto, se você está preocupado com ataques XSS.</td>
    </tr>
    <tr>
      <td>placement</td>
      <td>string | função</td>
      <td>'right'</td>
      <td>
        <p>Define como posicionar o popover (auto, top, botton, left ou right). Quando <code>auto</code> é definido, ele vai reorientar o popover, dinamicamente.</p>
        <p>Quando uma função é usada para determinar o posicionamento, ela é invocada com o nó DOM do popover, como seu primeiro argumento e aciona o nó DOM como o segundo argumento. O contexto <code>this</code> é definido na instância popover.</p>
      </td>
    </tr>
    <tr>
      <td>selector</td>
      <td>string | false</td>
      <td>false</td>
      <td>Se um seletor é provido, objetos popover serão delegados a alvos específicos. Na prática, isso é usado para permitir um conteúdo HTML dinâmico ter popover. Veja <a href="https://github.com/twbs/bootstrap/issues/4215">isto</a> e <a href="https://jsbin.com/zopod/1/edit">um exemplo informativo</a>.</td>
    </tr>
    <tr>
      <td>template</td>
      <td>string</td>
      <td><code>'&lt;div class="popover" role="tooltip"&gt;&lt;div class="arrow"&gt;&lt;/div&gt;&lt;h3 class="popover-header"&gt;&lt;/h3&gt;&lt;div class="popover-body"&gt;&lt;/div&gt;&lt;/div&gt;'</code></td>
      <td>
        <p>HTML base para criar um popover.</p>
        <p>O <code>title</code> do popover será injetado em um <code>.popover-header</code>.</p>
        <p>O <code>content</code> do popover será injetado em um <code>.popover-body</code>.</p>
        <p>O <code>.arrow</code> se tornará a flecha do popover.</p>
        <p>O elemento pai mais externo deve receber a classe <code>.popover</code>.</p>
      </td>
    </tr>
    <tr>
      <td>title</td>
      <td>string | elemento | função</td>
      <td>''</td>
      <td>
        <p>Valor padrão para o título, se o atributo <code>title</code> não está presente.</p>
        <p>Se uma função é provida, ela vai ser invocada com sua referência <code>this</code> definida no elemento que o popover é anexado.</p>
      </td>
    </tr>
    <tr>
      <td>trigger</td>
      <td>string</td>
      <td>'click'</td>
      <td>Define como o popover é acionado (clique, hover, focus ou manual). Você pode passar vários acionadores, separando eles com espaço. No entanto, `manual` não pode ser passado com outros acionadores.</td>
    </tr>
    <tr>
      <td>offset</td>
      <td>number | string</td>
      <td>0</td>
      <td>Define o deslocamento do popover, em relação a seu alvo. Para mais informação, leia a <a href="https://popper.js.org/popper-documentation.html#modifiers..offset.offset">documentação offset</a> do Popper.js.</td>
    </tr>
    <tr>
      <td>fallbackPlacement</td>
      <td>string | array</td>
      <td>'flip'</td>
      <td>Permite especificar qual posição Popper vai usar, em fallback. Para mais informação leia a <a href="https://popper.js.org/popper-documentation.html#modifiers..flip.behavior">documentação de comportamento</a> do Popper.js.</td>
    </tr>
    <tr>
      <td>boundary</td>
      <td>string | elemento</td>
      <td>'scrollParent'</td>
      <td>Limite de transbordamento do popover. Aceita os valores <code>'viewport'</code>, <code>'window'</code>, <code>'scrollParent'</code> ou uma referência HTMLElement (apenas JavaScript). Para mais informação, leia a <a href="https://popper.js.org/popper-documentation.html#modifiers..preventOverflow.boundariesElement">documentação preventOverflow</a> do Popper.js.</td>
    </tr>
  </tbody>
</table>

{% capture callout %}
#### Atributos data para popovers individuais

Parâmetros para popovers individuais podem ser, opcionalmente, especificados usando atributos data, como explicado acime.
{% endcapture %}
{% include callout.html content=callout type="info" %}

### Métodos

{% include callout-danger-async-methods.md %}

#### `$().popover(options)`

Inicializa popovers em uma coleção de elementos.

#### `.popover('show')`

Revela o popover de um elemento. **Retorna ao invocador, antes do popover ter sido exibido, de fato** (antes do evento `shown.bs.popover` ocorrer). Isto é considerado um acionamento "manual" do popover. Popovers, os quais possuem atributos `title` e `content` vazios, nunca são exibidos.

{% highlight js %}$('#elemento').popover('show'){% endhighlight %}

#### `.popover('hide')`

Esconde o popover de um elemento. **Retorna ao invocador, antes do popover ter sido escondido, de fato** (antes do evento `hidden.bs.popover` ocorrer). Isto é considerado um acionamento "manual" do popover.

{% highlight js %}$('#elemento').popover('hide'){% endhighlight %}

#### `.popover('toggle')`

Alterna a visibilidade do popover de um elemento. **Retorna ao invocador, antes do popover ter sido escondido ou exibido, de fato** (antes dos eventos `shown.bs.popover` e `hidden.bs.popover` ocorrerem). Isto é considerado um acionamento "manual" do popover.

{% highlight js %}$('#elemento').popover('toggle'){% endhighlight %}

#### `.popover('dispose')`

Esconde e destrói o popover de um elemento. Popovers que usam delegação (são criados usando [o parâmetro `selector`](#options)), não podem ser destruídos individualmente, em elementos gatilhos descendentes.

{% highlight js %}$('#elemento').popover('dispose'){% endhighlight %}

#### `.popover('enable')`

Dá ao popover de um elemento a habildiade de ser exibido. **Ativado por padrão.**

{% highlight js %}$('#elemento').popover('enable'){% endhighlight %}

#### `.popover('disable')`

Retira a habilidade do popover de um elemento de ser exibido. O popover só poderá ser exibido, se este método for reativado.

{% highlight js %}$('#elemento').popover('disable'){% endhighlight %}

#### `.popover('toggleEnabled')`

Alterna a habilidade do popover de um elemento ser exibido ou oculto.

{% highlight js %}$('#elemento').popover('toggleEnabled'){% endhighlight %}

#### `.popover('update')`

Atualiza a posição do popover de um elemento.

{% highlight js %}$('#elemento').popover('update'){% endhighlight %}

### Eventos

<table class="table table-bordered table-striped">
  <thead>
    <tr>
      <th style="width: 150px;">Evento</th>
      <th>Descrição</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>show.bs.popover</td>
      <td>Este evento é acionado, imediatamente, quando o método <code>show</code> é invocado.</td>
    </tr>
    <tr>
      <td>shown.bs.popover</td>
      <td>Este evento é acionado quando o popover se torna visível ao usuário (espera as transições CSS serem finalizadas).</td>
    </tr>
    <tr>
      <td>hide.bs.popover</td>
      <td>Este evento é acionado, imediatamente, quando o método <code>hide</code> é invocado.</td>
    </tr>
    <tr>
      <td>hidden.bs.popover</td>
      <td>Este evento é acionado quando o popover não está mais oculto ao usuário (espera as transições CSS serem finalizadas).</td>
    </tr>
    <tr>
      <td>inserted.bs.popover</td>
      <td>Este evento é acionado depois do evento <code>show.bs.popover</code>, quando o template do popover é adicionado ao DOM.</td>
    </tr>
  </tbody>
</table>

{% highlight js %}
$('#meuPopover').on('hidden.bs.popover', function () {
  // Faça algo, aqui…
})
{% endhighlight %}

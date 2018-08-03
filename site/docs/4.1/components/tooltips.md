---
layout: docs
title: Tooltips
description: Documentação e exemplos para criar tooltips Bootstrap personalizados com CSS e JavaScript, usando CSS3 para animações e atributos data para armazenamento local de título.
group: components
toc: true
---

## Visão geral

Oquê saber, quando usar o plugin tooltip:

- Tooltips dependem da biblioteca externa [Popper.js](https://popper.js.org/), para posicionamento;
  - Você deve colocar [popper.min.js]({{ site.cdn.popper }}) antes do bootstrap.js ou usar `bootstrap.bundle.min.js` / `bootstrap.bundle.js`, os quais já possuem Popper.js.
- Se você está montando nosso JavaScript a partir da fonte, vai precisar do [`util.js`]({{ site.baseurl }}/docs/{{ site.docs_version }}/getting-started/javascript/#util);
- Tooltips são opcionais por questões de desempenho, então, **você deve inicializá-lo por conta própria**;
- Tooltips com `title` sem valor, nunca serão exibidos;
- Declare `container: 'body'` para evitar problemas de renderização, em componentes mais complexos (como grupos de botões ou input);
- Acionar tooltips em elementos ocultos não é possível;
- Tooltips para elementos `.disabled` ou `disabled` devem ser acionados em um elemento pai;
- Quando acionados a partir de âncoras que envolvem várias linhas, tooltips são centralizados;
  - Use `white-space: nowrap;` nos `<a>` para evitar este comportamento.
- Tooltips devem ser escondidos, antes que seus elementos correspondentes sejam removidos do DOM.

Pegou tudo isso? Perfeito! Vamo ver como isso funciona, em algums exemplos.

## Ative tooltips, em qualquer lugar.

Uma maneira de inicializar todos tooltips, em uma página, seria selecioná-los por seus atributos  `data-toggle`:

{% highlight js %}
$(function () {
  $('[data-toggle="tooltip"]').tooltip()
})
{% endhighlight %}

## Exemplos

Passe o mouse sobre os links abaixo, para ver tooltips:

<div class="bd-example tooltip-demo">
  <p class="muted">Et sit consectetur laboriosam accusamus. <a href="#" data-toggle="tooltip" title="Tooltip padrão">Ipsam amet</a> aut. Exercitationem quasi accusantium et et ut. Alias quam sed. Omnis minus ad repellendus. Et sit consectetur laboriosam accusamus. Ipsam amet aut. Exercitationem quasi accusantium et et ut. Alias quam sed. Omnis minus ad repellendus. Et sit consectetur laboriosam accusamus. Ipsam amet aut. Exercitationem quasi accusantium et et ut. <a href="#" data-toggle="tooltip" title="Outro tooltip, aqui...">Alias quam</a> sed. Omnis minus ad repellendus. Et sit consectetur laboriosam accusamus. Ipsam amet aut. Exercitationem quasi <a href="#" data-toggle="tooltip" title="Olha, só! Outro tooltip.">accusantium</a> et et ut. Alias quam sed. Omnis minus ad repellendus. <a href="#" data-toggle="tooltip" title="Último tooltip. Juro!">Et sit consectetur</a> laboriosam accusamus. Ipsam amet aut. Exercitationem quasi accusantium et et ut. Alias quam sed. Omnis minus ad repellendus.</p>
</div>

Passe o mouse sobre os botões abaixo para ver as quatro direções de tooltip, possíveis: top, right, bottom e left.

<div class="bd-example tooltip-demo">
  <div class="bd-example-tooltips">
    <button type="button" class="btn btn-secondary" data-toggle="tooltip" data-placement="top" title="Tooltip na parte superior">Tooltip na parte superior</button>
    <button type="button" class="btn btn-secondary" data-toggle="tooltip" data-placement="right" title="Tooltip na direita">Tooltip na direita</button>
    <button type="button" class="btn btn-secondary" data-toggle="tooltip" data-placement="bottom" title="Tooltip na parte inferior">Tooltip na parte inferior</button>
    <button type="button" class="btn btn-secondary" data-toggle="tooltip" data-placement="left" title="Tooltip na esquerda">Tooltip na esquerda</button>
  </div>
</div>

{% highlight html %}
<button type="button" class="btn btn-secondary" data-toggle="tooltip" data-placement="top" title="Tooltip na parte superior">
  Tooltip na parte superior
</button>
<button type="button" class="btn btn-secondary" data-toggle="tooltip" data-placement="right" title="Tooltip na direita">
  Tooltip na direita
</button>
<button type="button" class="btn btn-secondary" data-toggle="tooltip" data-placement="bottom" title="Tooltip na parte inferior">
  Tooltip na parte inferior
</button>
<button type="button" class="btn btn-secondary" data-toggle="tooltip" data-placement="left" title="Tooltip na esquerda">
  Tooltip na esquerda
</button>
{% endhighlight %}

Ou um exemplo de tooltip que usa HTML, no seu conteúdo.

<div class="bd-example tooltip-demo">
  <div class="bd-example-tooltips">
    <button type="button" class="btn btn-secondary" data-toggle="tooltip" data-html="true" title="<em>Tooltip</em> <u>with</u> <b>HTML</b>">Tooltip com HTML</button>
  </div>
</div>

{% highlight html %}
<button type="button" class="btn btn-secondary" data-toggle="tooltip" data-html="true" title="<em>Tooltip</em> <u>with</u> <b>HTML</b>">
  Tooltip com HTML
</button>
{% endhighlight %}

## Modo de uso

O plugin tooltip gera conteúdo e marcação sob demanda e, por padrão, posiciona tooltips depois de seus elementos acionadores.

Acione o tooltip via JavaScript:

{% highlight js %}
$('#exemplo').tooltip(options)
{% endhighlight %}

{% capture callout %}
##### Overflow `auto` and `scroll`

Tooltip position attempts to automatically change when a parent container has `overflow: auto` or `overflow: scroll` like our `.table-responsive`, but still keeps the original placement's positioning. To resolve, set the `boundary` option to anything other than default value, `'scrollParent'`, such as `'window'`:

{% highlight js %}
$('#example').tooltip({ boundary: 'window' })
{% endhighlight %}
{% endcapture %}
{% include callout.html content=callout type="warning" %}

### Marcação

A marcação necessária para um tooltip só são os atributos `data` e `title`, no elemento HTML que você deseja ter um tooltip. A marcação gerada de um tooltip é bem simples, mas precisa de posicionamento (definido como `top`, por padrão).

{% capture callout %}
##### Fazendo tooltips funcionarem para usuários de teclado e tecnologias assistivas

Você só deveria colocar tooltips em elementos HTML que são, tradicionalmente, focáveis com teclado e interativos (como links e campos de formulário). Apesar de elementos HTML genéricos (como `<span>`) poderem se tornar focáveis, adicionando o atributo `tabindex="0"`, isso vai criar potenciais tabulações irritantes e confusas, em elementos não interativos para usuários de teclado. Além disso, a maioria das tecnologias assistivas, atualmente, não transmitem o tooltip, nesta situação.

Além do mais, não dependa só no `hover` como acionador para seu tooltip, já que isso vai fazer seus tooltips impossíveis de serem acionados por usuários de teclado.
{% endcapture %}
{% include callout.html content=callout type="warning" %}

{% highlight html %}
<!-- HTML a se escrever -->
<a href="#" data-toggle="tooltip" title="Some tooltip text!">Passe o mouse em mim</a>

<!-- Marcação gerada, pelo pluguin -->
<div class="tooltip bs-tooltip-top" role="tooltip">
  <div class="arrow"></div>
  <div class="tooltip-inner">
    Algum texto de tooltip
  </div>
</div>
{% endhighlight %}

### Elementos desativados

Elementos com o atributo `disabled` não são interativos, significando que usuários não podem focar, clicar ou passar o mouse sobre eles para acionar o tooltip (ou popover). Como uma forma de contornar a situação, você vai querer acionar o tooltip a partir de um elemento pai `<div>` ou `<span>`, idealmente, fazendo-os serem focáveis com `tabindex="0"` e sobrescrever a `pointer-events`, no elemento desativado.

<div class="tooltip-demo">
{% capture example %}
<span class="d-inline-block" tabindex="0" data-toggle="tooltip" title="Tooltip em elemento desativado">
  <button class="btn btn-primary" style="pointer-events: none;" type="button" disabled>Botão desativado</button>
</span>
{% endcapture %}
{% include example.html content=example %}
</div>

### Parâmetros

Parâmetros podem ser passados via atributos data ou JavaScript. No caso de atributos data, anexe o nome do parâmetro ao prefixo `data-`, como em `data-animation=""`.

<table class="table table-bordered table-striped">
  <thead>
    <tr>
      <th style="width: 100px;">Nome</th>
      <th style="width: 100px;">Tipo</th>
      <th style="width: 50px;">Padrão</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>animation</td>
      <td>booleano</td>
      <td>true</td>
      <td>Aplica uma transição CSS fade, no tooltip.</td>
    </tr>
    <tr>
      <td>container</td>
      <td>string | elemento | false</td>
      <td>false</td>
      <td>
        <p>Anexa o tooltip ao elemento específico. Este parâmetro é, particularmente, útil porque permite você posicionar o tooltip no fluxo do documento, perto do elemento gatilho (o que vai evitar que o tooltip flutue para longe do elemento gatilho, no redimensionamento de página). Exemplo: <code>container: 'body'</code>.</p>
      </td>
    </tr>
    <tr>
      <td>delay</td>
      <td>number | objeto</td>
      <td>0</td>
      <td>
        <p>Atraso na exibição e ocultação do tooltip, em ms. Não se aplica ao tipo de acionamento manual.</p>
        <p>Se um número é provido, o atraso é aplicado tanto a exibição quanto a ocultação.</p>
        <p>A estrutura do objeto é: <code>delay: { "show": 500, "hide": 100 }</code></p>
      </td>
    </tr>
    <tr>
      <td>html</td>
      <td>booleano</td>
      <td>false</td>
      <td>
        <p>Permite HTML, no tooltip.</p>
        <p>Se declarado como true, tags HTML no título do tooltip serão renderizadas. Se definido como false, o método jQuery <code>text</code> será usado para inserir conteúdo no DOM.</p>
      </td>
    </tr>
    <tr>
      <td>placement</td>
      <td>string | função</td>
      <td>'top'</td>
      <td>
        <p>Define como posicionar o tooltip (auto, top, bottom, left e right). Quando <code>auto</code> é especificado, ele vai reorientar o tooltip, automaticamente.</p>
        <p>Quando uma função é usada para determinar o posicionamento, ela é invocada com o nó DOM do tooltip como seu primeiro argumento e o nó DOM do elemento acionador como o segundo. O contexto <code>this</code> é definido para a instância tooltip.</p>
      </td>
    </tr>
    <tr>
      <td>selector</td>
      <td>string | false</td>
      <td>false</td>
      <td>Se um seletor é provido, objetos tooltip serão delegados aos alvos específicos. Na prática, isto é usado para permitir conteúdo HTML dinâmico ter popovers. Veja <a href="https://github.com/twbs/bootstrap/issues/4215">isto</a> e <a href="https://codepen.io/Johann-S/pen/djJYPb">um exemplo informativo</a>.</td>
    </tr>
    <tr>
      <td>template</td>
      <td>string</td>
      <td><code>'&lt;div class="tooltip" role="tooltip"&gt;&lt;div class="arrow"&gt;&lt;/div&gt;&lt;div class="tooltip-inner"&gt;&lt;/div&gt;&lt;/div&gt;'</code></td>
      <td>
        <p>HTML base para criação de tooltip.</p>
        <p>O <code>title</code> do tooltip será injetado no <code>.tooltip-inner</code>.</p>
        <p>A <code>.arrow</code> se tornará a flecha do tooltip.</p>
        <p>O elemento pai mais exeterno deve ter a classe <code>.tooltip</code> e atributo <code>role="tooltip"</code>.</p>
      </td>
    </tr>
    <tr>
      <td>title</td>
      <td>string | elemento | função</td>
      <td>''</td>
      <td>
        <p>Define o título padrão, se o valor do atributo <code>title</code> não está presente.</p>
        <p>Se uma função é declarada, ela será invocada com sua referência <code>this</code> definida para o elemento que o tooltip está anexado.</p>
      </td>
    </tr>
    <tr>
      <td>trigger</td>
      <td>string</td>
      <td>'hover focus'</td>
      <td>
        <p>Define como o tooltip é acionado (click, hover, focus e manual). Você pode passar vários acionadores, separando-os com espaço.</p>
        <p><code>'manual'</code> indica que o tooltip será acionado, programaticamente, pelos métodos <code>.tooltip('show')</code>, <code>.tooltip('hide')</code> e <code>.tooltip('toggle')</code>. Este valor não pode ser combinado com os outros acionadores.</p>
        <p>Usar só o <code>'hover'</code> vai resultar em tooltips que não podem ser acionados por teclado e só devem ser usados se métodos alternativos, para transmitir a mesma informação para usuários de teclado, existem.</p>
      </td>
    </tr>
    <tr>
      <td>offset</td>
      <td>number | string</td>
      <td>0</td>
      <td>Deslocamento do tooltip, em relação ao seu alvo. Para mais informação, leia a <a href="https://popper.js.org/popper-documentation.html#modifiers..offset.offset">documentação offset</a> do Popper.js.</td>
    </tr>
    <tr>
      <td>fallbackPlacement</td>
      <td>string | array</td>
      <td>'flip'</td>
      <td>Permite especificar qual posição o Popper vai usar, em caso de fallback. Para mais informação, leia a <a href="https://popper.js.org/popper-documentation.html#modifiers..flip.behavior">documentação de comportamento</a> do Popper.js.</td>
    </tr>
    <tr>
      <td>boundary</td>
      <td>string | elemento</td>
      <td>'scrollParent'</td>
      <td>Define o limite de transbordamento do tooltip. Aceita os valores <code>'viewport'</code>, <code>'window'</code>, <code>'scrollParent'</code> ou uma referência HTMLElement (apenas JavaScript). Para mais informação, leia a <a href="https://popper.js.org/popper-documentation.html#modifiers..preventOverflow.boundariesElement">documentação preventOverflow</a> do Popper.js.</td>
    </tr>
  </tbody>
</table>

{% capture callout %}
#### Atributos data para tooltips individuais

Parâmetros para tooltips individuais podem, opcionalmente, serem especificados usando atributos data, como mostrado acima.
{% endcapture %}
{% include callout.html content=callout type="info" %}

### Métodos

{% include callout-danger-async-methods.md %}

#### `$().tooltip(options)`

Anexa um manipulador tooltip, em uma coleção de elementos.

#### `.tooltip('show')`

Revela o tooltip de um elemento. **Retorna ao invocador, antes do tooltip ter sido exibido, de fato** (antes do evento `shown.bs.tooltip` ocorrer). Isto é considerado um acionamento "manual" do tooltip. Tooltips com `title` vazios, nunca são mostrados.

{% highlight js %}$('#elemento').tooltip('show'){% endhighlight %}

#### `.tooltip('hide')`

Esconde o tooltip de um elemento. **Retorna ao invocador, antes do tooltip ter sido oculto, de fato** (antes do evento `hidden.bs.tooltip` ocorrer). Isto é considerado um acionamento "manual" do tooltip.

{% highlight js %}$('#elemento').tooltip('hide'){% endhighlight %}

#### `.tooltip('toggle')`

Alterna a visibilidade do tooltip de um elemento. **Retorna ao invocador, antes do tooltip ter sido exibido ou oculto, de fato** (antes dos eventos `shown.bs.tooltip` e `hidden.bs.tooltip` ocorrerem). Isto é considerado um acionamento "manual" do tooltip.

{% highlight js %}$('#elemento').tooltip('toggle'){% endhighlight %}

#### `.tooltip('dispose')`

Esconde e destrói o tooltip de um elemento. Tooltips que usam delegação (são criadas usando o [parâmetro `selector`](#options)) não podem ser, individualmente, destruídos em elementos acionadores descendentes.

{% highlight js %}$('#elemento').tooltip('dispose'){% endhighlight %}

#### `.tooltip('enable')`

Dá a habilide de se exibir ao tooltip de um elemento. **Ativado por padrão.**

{% highlight js %}$('#elemento').tooltip('enable'){% endhighlight %}

#### `.tooltip('disable')`

Remove a habilidade de se exibir do tooltip de um elemento. O tooltip só será capaz de ser exibido se isto for reativado.

{% highlight js %}$('#elemento').tooltip('disable'){% endhighlight %}

#### `.tooltip('toggleEnabled')`

Alterna a capacidade do tooltip de um elemento de ser exibido ou oculto.

{% highlight js %}$('#elemento').tooltip('toggleEnabled'){% endhighlight %}

#### `.tooltip('update')`

Atualiza a posição do tooltip de um elemento.

{% highlight js %}$('#elemento').tooltip('update'){% endhighlight %}

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
      <td>show.bs.tooltip</td>
      <td>Este evento é acionado quando o método <code>show</code> é invocado.</td>
    </tr>
    <tr>
      <td>shown.bs.tooltip</td>
      <td>Este evento é acionado quando o tooltip foi exibido ao usuário (espera as transições CSS finalizarem).</td>
    </tr>
    <tr>
      <td>hide.bs.tooltip</td>
      <td>Este evento é acionado, imediatamente, quando o método <code>hide</code> é invocado.</td>
    </tr>
    <tr>
      <td>hidden.bs.tooltip</td>
      <td>Este evento é acionado quando o tooltip acaba de se ocultar do usuário (espera as transições CSS finalizarem).</td>
    </tr>
    <tr>
      <td>inserted.bs.tooltip</td>
      <td>Este evento é acionado depois do evento <code>show.bs.tooltip</code>, quando o template tooltip foi adicionado ao DOM.</td>
    </tr>
  </tbody>
</table>

{% highlight js %}
$('#meuTooltip').on('hidden.bs.tooltip', function () {
  // Faça algo, aqui…
})
{% endhighlight %}

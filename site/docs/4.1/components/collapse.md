---
layout: docs
title: Collapse
description: Alterne a visibilidade do conteúdo de seu projeto com algumas classes e nossos plugins JavaScript.
group: components
toc: true
---

## Como funciona

O plugin JavaScript collapse é usado para mostrar e esconder conteúdo. Botões ou âncoras são usados como gatilhos que são mapeados para elementos específicos que você alterna visibilidade. Mostrar um elemento (de tal maneira) vai animar a `height`, de seu valor atual, para `0`. Dado como CSS lida com animações, você não pode usar `padding` em um elemento `.collapse`. Pelo contrário, use esta classe como um elemento pai independente.

## Exemplo

Clique nos botões abaixo para mostrar e esconder outro elemento, através de mudanças de classes:

- `.collapse` esconde o conteúdo;
- `.collapsing` é aplicado durante a transição;
- `.collapse.show` mostra o conteúdo.

Você pode usar um link com o atributo `href` ou um botão com `data-target`. Em ambos casos, `data-toggle="collapse"` é exigido.

{% capture example %}
<p>
  <a class="btn btn-primary" data-toggle="collapse" href="#collapseExample" role="button" aria-expanded="false" aria-controls="collapseExample">
    Link com href
  </a>
  <button class="btn btn-primary" type="button" data-toggle="collapse" data-target="#collapseExample" aria-expanded="false" aria-controls="collapseExample">
    Botão com data-target
  </button>
</p>
<div class="collapse" id="collapseExample">
  <div class="card card-body">
    Anim pariatur cliche reprehenderit, enim eiusmod high life accusamus terry richardson ad squid. Nihil anim keffiyeh helvetica, craft beer labore wes anderson cred nesciunt sapiente ea proident.
  </div>
</div>
{% endcapture %}
{% include example.html content=example %}

## Vários alvos

Um `<button>` ou uma `<a>` pode mostrar e esconder vários elementos, referenciando-os com um seletor jQuery em seu `href` ou `data-target`.
Vários `<button>` ou `<a>` podem mostrar e esconder um elemento, se cada um deles referenciá-lo com seus `href` ou `data-target`.

{% capture example %}
<p>
  <a class="btn btn-primary" data-toggle="collapse" href="#multiCollapseExample1" role="button" aria-expanded="false" aria-controls="multiCollapseExample1">Alterna primeiro elemento</a>
  <button class="btn btn-primary" type="button" data-toggle="collapse" data-target="#multiCollapseExample2" aria-expanded="false" aria-controls="multiCollapseExample2">Alterna segundo elemento</button>
  <button class="btn btn-primary" type="button" data-toggle="collapse" data-target=".multi-collapse" aria-expanded="false" aria-controls="multiCollapseExample1 multiCollapseExample2">Alterna terceiro elemento</button>
</p>
<div class="row">
  <div class="col">
    <div class="collapse multi-collapse" id="multiCollapseExample1">
      <div class="card card-body">
        Anim pariatur cliche reprehenderit, enim alemanha 7x1 brasil life accusamus terry richardson ad squid. Nihil anim keffiyeh helvetica, craft beer labore wes anderson cred nesciunt sapiente ea proident.
      </div>
    </div>
  </div>
  <div class="col">
    <div class="collapse multi-collapse" id="multiCollapseExample2">
      <div class="card card-body">
        Anim pariatur cliche reprehenderit, enim eiusmod high life accusamus terry richardson ad squid. Nihil anim keffiyeh helvetica, craft beer labore wes anderson cred nesciunt sapiente ea proident.
      </div>
    </div>
  </div>
</div>
{% endcapture %}
{% include example.html content=example %}

## Exemplo de acordeão

Usando o componente  [card]({{ site.baseurl }}/docs/{{ site.docs_version }}/components/card/), você pode extender o comportamento padrão do collapse, para criar um acordeão.

{% capture example %}
<div class="accordion" id="accordionExample">
  <div class="card">
    <div class="card-header" id="headingOne">
      <h5 class="mb-0">
        <button class="btn btn-link" type="button" data-toggle="collapse" data-target="#collapseOne" aria-expanded="true" aria-controls="collapseOne">
          Grupo de itens colapsável #1
        </button>
      </h5>
    </div>

    <div id="collapseOne" class="collapse show" aria-labelledby="headingOne" data-parent="#accordionExample">
      <div class="card-body">
        Anim pariatur cliche reprehenderit, enim eiusmod high life accusamus terry richardson ad squid. 3 wolf moon officia aute, non alemanha 0 x 2 coreia do sul cupidatat skateboard dolor brunch. Food truck quinoa nesciunt laborum eiusmod. Brunch 3 wolf moon tempor, sunt aliqua put a bird on it squid single-origin coffee nulla assumenda shoreditch et. Nihil anim keffiyeh helvetica, craft beer labore wes anderson cred nesciunt sapiente ea proident. Ad vegan excepteur butcher vice lomo. Leggings occaecat craft beer farm-to-table, raw denim aesthetic synth nesciunt you probably haven't heard of them accusamus labore sustainable VHS.
      </div>
    </div>
  </div>
  <div class="card">
    <div class="card-header" id="headingTwo">
      <h5 class="mb-0">
        <button class="btn btn-link collapsed" type="button" data-toggle="collapse" data-target="#collapseTwo" aria-expanded="false" aria-controls="collapseTwo">
          Grupo de itens colapsável #2
        </button>
      </h5>
    </div>
    <div id="collapseTwo" class="collapse" aria-labelledby="headingTwo" data-parent="#accordionExample">
      <div class="card-body">
        Anim pariatur cliche reprehenderit, enim eiusmod high life accusamus terry richardson ad squid. 3 wolf moon officia aute, non cupidatat skateboard dolor brunch. Food truck quinoa nesciunt laborum eiusmod. Brunch 3 wolf moon tempor, sunt aliqua put a bird on it squid single-origin coffee nulla assumenda shoreditch et. Nihil anim keffiyeh helvetica, craft beer labore wes anderson cred nesciunt sapiente ea proident. Ad vegan excepteur butcher vice lomo. Leggings occaecat craft beer farm-to-table, raw denim aesthetic synth nesciunt you probably haven't heard of them accusamus labore sustainable VHS.
      </div>
    </div>
  </div>
  <div class="card">
    <div class="card-header" id="headingThree">
      <h5 class="mb-0">
        <button class="btn btn-link collapsed" type="button" data-toggle="collapse" data-target="#collapseThree" aria-expanded="false" aria-controls="collapseThree">
          Grupo de itens colapsável #3
        </button>
      </h5>
    </div>
    <div id="collapseThree" class="collapse" aria-labelledby="headingThree" data-parent="#accordionExample">
      <div class="card-body">
        Anim pariatur cliche reprehenderit, enim eiusmod high life accusamus terry richardson ad squid. 3 wolf moon officia aute, non cupidatat skateboard dolor brunch. Food truck quinoa nesciunt laborum eiusmod. Brunch 3 wolf moon tempor, sunt aliqua put a bird on it squid single-origin coffee nulla assumenda shoreditch et. Nihil anim keffiyeh helvetica, craft beer labore wes anderson cred nesciunt sapiente ea proident. Ad vegan excepteur butcher vice lomo. Leggings occaecat craft beer farm-to-table, raw denim aesthetic synth nesciunt you probably haven't heard of them accusamus labore sustainable VHS.
      </div>
    </div>
  </div>
</div>
{% endcapture %}
{% include example.html content=example %}

## Acessibilidade

- Se assegure de usar `aria-expanded` no elemento controle. Este atributo transmite o atual estado do elemento colapsável, ligado ao contole, para leitores de telas e tecnologias assistivas;
- Se o elemento colapsável é fechado por padrão, o atributo no elemento controle deve ter o valor de `aria-expanded="false"`;
  - Já, se você configurou para que o elemento estivesse aberto, por padrão, usando a classe `.show`, defina `aria-expanded="true"` no controle;
  - O plugin vai, automaticamente, alternar este atributo no controle, verificando se o elemento colapsável foi aberto ou não, via JavaScript ou porque o usuário acionou um outro elemento controle, também vinculado ao mesmo elemento colapsável. 
- Se a tag do elemento controle não é um botão (ex: `<a>` ou `<div>`), o atributo `role="button"` deve ser usado no elemento;
- Se seu elemento controle está atingindo só um elemento colapsável (`data-target` referenciando um seletor de id), você deve adicionar o atributo `aria-controls` no elemento controle.
  - Leitores de telas modernos e tecnologias assistivas similares fazem uso desse atributo para dar atalhos adicionais aos usuários, para navegar diretamente para o próprio elemento colapsável.

Perceba que a atual implementação do Bootstrap não cobre as diversas interações de teclado descritas no [WAI-ARIA Authoring Practices 1.1 accordion pattern](https://www.w3.org/TR/wai-aria-practices-1.1/#accordion). Você vai precisar incluir elas, com seu próprio JavaScript.
d
## Modo de uso

O plugin collapse usa algumas classes para cumprir seu dever:

- `.collapse` esconde o conteúdo;
- `.collapse.show` mostra o conteúdo;
- `.collapsing` é adicionado quando a transição inicia e removido quando finaliza.

Essas classes podem ser encontradas em `_transitions.scss`.

### Via atributos data

- Basta adicionar `data-toggle="collapse"` e um `data-target` no elemento para, automaticamente, atribuir controle em um ou mais elementos colapsáveis;
  - O atributo `data-target` aceita um seletor CSS para aplicar o colapso. 
- Se assegure de adicionar a classe `.collapse` no elemento colapsável. 
  - Se quer que ele esteja aberto por padrão, use a classe adicional `show`.

Para criar um acordeão em uma área colapsável, use o atributo `data-parent="#seletor"`. Veja a demonstração, para ver isso em ação.

### Via JavaScript

Ative, manualmente, usando:

{% highlight js %}
$('.collapse').collapse()
{% endhighlight %}

### Opções

Opções podem ser passadas via atributos data ou JavaScript. Para atributos data, anexe o nome da opção no prefixo `data-`, como em `data-parent=""`.

<table class="table table-bordered table-striped">
  <thead>
    <tr>
      <th style="width: 100px;">Nome</th>
      <th style="width: 50px;">Tipo</th>
      <th style="width: 50px;">Padrão</th>
      <th>Descrição</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>parent</td>
      <td>seletor | objeto jQuery | elemento DOM </td>
      <td>false</td>
      <td>Se o pai é provido, então, todos elementos colapsáveis dentro dele vão ser fechados quando este item colapsável é mostrado (semelhante ao comportamento do acordeão, dependendo da classe do <code>card</code>). O atributo deve ser definido na área colapsável do alvo.</td>
    </tr>
    <tr>
      <td>toggle</td>
      <td>booleano</td>
      <td>true</td>
      <td>Alterna o elemento colapsável, na invocação.</td>
    </tr>
  </tbody>
</table>

### Métodos

{% include callout-danger-async-methods.md %}

#### `.collapse(options)`

Ativa seu conteúdo como sendo um elemento colapsável. Aceita um `objeto` de opções, opcionalmente.

{% highlight js %}
$('#myCollapsible').collapse({
  toggle: false
})
{% endhighlight %}

#### `.collapse('toggle')`

Alterna um elemento colapsável para mostrar ou escondê-lo. **Retorna ao invocador antes do elemento colapsável ter sido mostrado ou escondido, de fato** (antes do evento `shown.bs.collapse` ou `hidden.bs.collapse` ocorrer).

#### `.collapse('show')`

Mostra um elemento colapsável. **Retorna ao invocador antes do elemento colapsável ter sido mostrado, de fato** (antes do evento `shown.bs.collapse` ocorrer).

#### `.collapse('hide')`

Esconde um elemento colapsável. **Retorna ao invocar antes do elemento colapsável ter sido escondido, de fato** (antes do evento `hidden.bs.collapse` ocorrer).

#### `.collapse('dispose')`

Destroi o colapso de um elemento.

### Eventos

A classe Bootstrap do collapse tem alguns eventos para ativar a funcionalidade de colapso.

<table class="table table-bordered table-striped">
  <thead>
    <tr>
      <th style="width: 150px;">Tipo de evento</th>
      <th>Descrição</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>show.bs.collapse</td>
      <td>Este evento é acionado, imediatamente, quando o método <code>show</code> é chamado.</td>
    </tr>
    <tr>
      <td>shown.bs.collapse</td>
      <td>Este evento é acionado quando um elemento colapsável fica visível para o usuário (espera as transições CSS finalizarem).</td>
    </tr>
    <tr>
      <td>hide.bs.collapse</td>
      <td>Este evento é acionado, imediatamente, quando o método <code>hide</code> é chamado.</td>
    </tr>
    <tr>
      <td>hidden.bs.collapse</td>
      <td>Este evento é acionado quando um elemento colapsável foi escondido do usuário (espera as transições CSS finalizarem).</td>
    </tr>
  </tbody>
</table>

{% highlight js %}
$('#myCollapsible').on('hidden.bs.collapse', function () {
  //faça algo, aqui...
})
{% endhighlight %}

---
layout: docs
title: Grupo de lista
description: Grupos de listas são componentes flexíveis e poderosos para mostrar vários conteúdos. Modifique e aprimore-o para suportar quase qualquer conteúdo.
group: components
toc: true
---

## Exemplo básico

O grupo de lista mais básico é uma `<ul>` com `<li>` e algumas classes específicas. Desenvolva com as opções a seguir ou com seu próprio CSS, dependendo da sua necessidade.

{% capture example %}
<ul class="list-group">
  <li class="list-group-item">Cras justo odio</li>
  <li class="list-group-item">Dapibus ac facilisis in</li>
  <li class="list-group-item">Morbi leo risus</li>
  <li class="list-group-item">Porta ac consectetur ac</li>
  <li class="list-group-item">Vestibulum at eros</li>
</ul>
{% endcapture %}
{% include example.html content=example %}

## Itens ativos

Use `.active` em um `.list-group-item` para indicar a seleção ativa, no momento.

{% capture example %}
<ul class="list-group">
  <li class="list-group-item active">Cras justo odio</li>
  <li class="list-group-item">Dapibus ac facilisis in</li>
  <li class="list-group-item">Morbi leo risus</li>
  <li class="list-group-item">Porta ac consectetur ac</li>
  <li class="list-group-item">Vestibulum at eros</li>
</ul>
{% endcapture %}
{% include example.html content=example %}

## Itens desativados

Use `.disabled` em um `.list-group-item` para fazê-lo ter _aparência_ desativada. Perceba que alguns elementos com `.disabled` vão precisar de JavaScript customizado para desativar seus eventos de clique, totalmente (ex: links).

{% capture example %}
<ul class="list-group">
  <li class="list-group-item disabled">Cras justo odio</li>
  <li class="list-group-item">Dapibus ac facilisis in</li>
  <li class="list-group-item">Morbi leo risus</li>
  <li class="list-group-item">Porta ac consectetur ac</li>
  <li class="list-group-item">Vestibulum at eros</li>
</ul>
{% endcapture %}
{% include example.html content=example %}

## Links e botões

Use `<a>` ou `<button>` para criar itens do grupo de lista _acionáveis_ com estados hover, disabled e active, adicionando `.list-group-item-action`. Nós separamos estas pseudo-classes, para assegurar que grupos de listas feitos com elementos não interativos (tipo `<li>` ou `<div>`) não permitam insinuações de clique ou toque. 

Se assegure de **não usar as classes `.btn` padrões, aqui**.

{% capture example %}
<div class="list-group">
  <a href="#" class="list-group-item list-group-item-action active">
    Cras justo odio
  </a>
  <a href="#" class="list-group-item list-group-item-action">Dapibus ac facilisis in</a>
  <a href="#" class="list-group-item list-group-item-action">Morbi leo risus</a>
  <a href="#" class="list-group-item list-group-item-action">Porta ac consectetur ac</a>
  <a href="#" class="list-group-item list-group-item-action disabled">Vestibulum at eros</a>
</div>
{% endcapture %}
{% include example.html content=example %}

Com `<button>`, você também pode fazer uso do atributo `disabled`, invés da classe `.disabled`. Infelizmente, elementos `<a>` não suportam o atributo disabled.

{% capture example %}
<div class="list-group">
  <button type="button" class="list-group-item list-group-item-action active">
    Cras justo odio
  </button>
  <button type="button" class="list-group-item list-group-item-action">Dapibus ac facilisis in</button>
  <button type="button" class="list-group-item list-group-item-action">Morbi leo risus</button>
  <button type="button" class="list-group-item list-group-item-action">Porta ac consectetur ac</button>
  <button type="button" class="list-group-item list-group-item-action" disabled>Vestibulum at eros</button>
</div>
{% endcapture %}
{% include example.html content=example %}

## Flush

Use `.list-group-flush` para remover algumas bordas e cantos arredondados para renderizar itens do grupo de lista, de ponta-a-ponta, em um container pai.

{% capture example %}
<ul class="list-group list-group-flush">
  <li class="list-group-item">Cras justo odio</li>
  <li class="list-group-item">Dapibus ac facilisis in</li>
  <li class="list-group-item">Morbi leo risus</li>
  <li class="list-group-item">Porta ac consectetur ac</li>
  <li class="list-group-item">Vestibulum at eros</li>
</ul>
{% endcapture %}
{% include example.html content=example %}

## Classes contextuais

Use classes contextuais para estilizar itens da lista com belos caracteres e cor de fundo.

{% capture example %}
<ul class="list-group">
  <li class="list-group-item">Dapibus ac facilisis in</li>

  {% for color in site.data.theme-colors %}
  <li class="list-group-item list-group-item-{{ color.name }}">Um simples item {{ color.name }} do grupo de lista</li>{% endfor %}
</ul>
{% endcapture %}
{% include example.html content=example %}

Classes contextuais também funcionam com `.list-group-item-action`. Perceba a presença dos estilos hover, os quais não estavam no presentes no exemplo anterior. O estado `.active` também é suportado, bastando aplicá-lo para indicar uma seleção ativa em um item do grupo de lista.

{% capture example %}
<div class="list-group">
  <a href="#" class="list-group-item list-group-item-action">Dapibus ac facilisis in</a>

  {% for color in site.data.theme-colors %}
  <a href="#" class="list-group-item list-group-item-action list-group-item-{{ color.name }}">Um simples item {{ color.name }} do grupo de lista</a>{% endfor %}
</div>
{% endcapture %}
{% include example.html content=example %}

{% include callout-warning-color-assistive-technologies.md %}

## Usando badges

Coloque badges em qualquer item do grupo de lista para exibir contadores, atividade e muito mais, com ajuda de alguns [utilitários]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/flex/).

{% capture example %}
<ul class="list-group">
  <li class="list-group-item d-flex justify-content-between align-items-center">
    Cras alemanha odio
    <span class="badge badge-primary badge-pill">7</span>
  </li>
  <li class="list-group-item d-flex justify-content-between align-items-center">
    Dapibus ac facilisis in
    <span class="badge badge-primary badge-pill">x</span>
  </li>
  <li class="list-group-item d-flex justify-content-between align-items-center">
    Morbi brasil risus
    <span class="badge badge-primary badge-pill">1</span>
  </li>
</ul>
{% endcapture %}
{% include example.html content=example %}

## Conteúdo customizado

Coloque quase qualquer HTML dentro, mesmo em grupos de listas linkados, como o mostrado abaixo, com ajuda de [utilitários flexbox]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/flex/).

{% capture example %}
<div class="list-group">
  <a href="#" class="list-group-item list-group-item-action flex-column align-items-start active">
    <div class="d-flex w-100 justify-content-between">
      <h5 class="mb-1">Cabeçalho do item</h5>
      <small>3 dias atrás</small>
    </div>
    <p class="mb-1">Donec id elit non mi porta gravida at eget metus. Maecenas sed diam eget risus varius blandit.</p>
    <small>Donec id elit non mi porta.</small>
  </a>
  <a href="#" class="list-group-item list-group-item-action flex-column align-items-start">
    <div class="d-flex w-100 justify-content-between">
      <h5 class="mb-1">Cabeçalho do item</h5>
      <small class="text-muted">3 dias atrás</small>
    </div>
    <p class="mb-1">Donec id elit non mi porta gravida at eget metus. Maecenas sed diam eget risus varius blandit.</p>
    <small class="text-muted">Donec id elit non mi porta.</small>
  </a>
  <a href="#" class="list-group-item list-group-item-action flex-column align-items-start">
    <div class="d-flex w-100 justify-content-between">
      <h5 class="mb-1">Cabeçalho do item</h5>
      <small class="text-muted">3 dias atrás</small>
    </div>
    <p class="mb-1">Donec id elit non mi porta gravida at eget metus. Maecenas sed diam eget risus varius blandit.</p>
    <small class="text-muted">Donec id elit non mi porta.</small>
  </a>
</div>
{% endcapture %}
{% include example.html content=example %}

## Comportamento JavaScript

Use o plugin JavaScript tab (inclua-o, individualmente, ou usando o arquivo compilado `bootstrap.js`) para aprimorar nosso grupo de lista para criar paineis de abas de conteúdo local.

<div class="bd-example" role="tabpanel">
  <div class="row">
    <div class="col-4">
      <div class="list-group" id="list-tab" role="tablist">
        <a class="list-group-item list-group-item-action active" id="list-home-list" data-toggle="tab" href="#lista-home" role="tab" aria-controls="list-home">Home</a>
        <a class="list-group-item list-group-item-action" id="list-profile-list" data-toggle="tab" href="#list-profile" role="tab" aria-controls="list-profile">Perfil</a>
        <a class="list-group-item list-group-item-action" id="list-messages-list" data-toggle="tab" href="#lista-mensagens" role="tab" aria-controls="list-messages">Mensagens</a>
        <a class="list-group-item list-group-item-action" id="list-settings-list" data-toggle="tab" href="#lista-configuracoes" role="tab" aria-controls="list-settings">Configurações</a>
      </div>
    </div>
    <div class="col-8">
      <div class="tab-content" id="nav-tabContent">
        <div class="tab-pane fade show active" id="list-home" role="tabpanel" aria-labelledby="list-home-list">
          <p>Velit aute mollit ipsum ad dolor consectetur nulla officia culpa adipisicing exercitation fugiat tempor. Voluptate deserunt sit sunt nisi aliqua fugiat proident ea ut. Mollit voluptate reprehenderit occaecat nisi ad non minim tempor sunt voluptate consectetur exercitation id ut nulla. Ea et fugiat aliquip nostrud sunt incididunt consectetur culpa aliquip eiusmod dolor. Anim ad Lorem aliqua in cupidatat nisi enim eu nostrud do aliquip veniam minim.</p>
        </div>
        <div class="tab-pane fade" id="list-profile" role="tabpanel" aria-labelledby="list-profile-list">
          <p>Cupidatat quis ad sint excepteur laborum in esse qui. Et excepteur consectetur ex nisi eu do cillum ad laborum. Mollit et eu officia dolore sunt Lorem culpa qui commodo velit ex amet id ex. Officia anim incididunt laboris deserunt anim aute dolor incididunt veniam aute dolore do exercitation. Dolor nisi culpa ex ad irure in elit eu dolore. Ad laboris ipsum reprehenderit irure non commodo enim culpa commodo veniam incididunt veniam ad.</p>
        </div>
        <div class="tab-pane fade" id="list-messages" role="tabpanel" aria-labelledby="list-messages-list">
          <p>Ut ut do pariatur aliquip aliqua aliquip exercitation do nostrud commodo reprehenderit aute ipsum voluptate. Irure Lorem et laboris nostrud amet cupidatat cupidatat anim do ut velit mollit consequat enim tempor. Consectetur est minim nostrud nostrud consectetur irure labore voluptate irure. Ipsum id Lorem sit sint voluptate est pariatur eu ad cupidatat et deserunt culpa sit eiusmod deserunt. Consectetur et fugiat anim do eiusmod aliquip nulla laborum elit adipisicing pariatur cillum.</p>
        </div>
        <div class="tab-pane fade" id="list-settings" role="tabpanel" aria-labelledby="list-settings-list">
          <p>Irure enim occaecat labore sit qui aliquip reprehenderit amet velit. Deserunt ullamco ex elit nostrud ut dolore nisi officia magna sit occaecat laboris sunt dolor. Nisi eu minim cillum occaecat aute est cupidatat aliqua labore aute occaecat ea aliquip sunt amet. Aute mollit dolor ut exercitation irure commodo non amet consectetur quis amet culpa. Quis ullamco nisi amet qui aute irure eu. Magna labore dolor quis ex labore id nostrud deserunt dolor eiusmod eu pariatur culpa mollit in irure.</p>
        </div>
      </div>
    </div>
  </div>
</div>

{% highlight html %}
<div class="row">
  <div class="col-4">
    <div class="list-group" id="list-tab" role="tablist">
      <a class="list-group-item list-group-item-action active" id="list-home-list" data-toggle="list" href="#lista-home" role="tab" aria-controls="home">Home</a>
      <a class="list-group-item list-group-item-action" id="list-profile-list" data-toggle="list" href="#list-profile" role="tab" aria-controls="profile">Perfil</a>
      <a class="list-group-item list-group-item-action" id="list-messages-list" data-toggle="list" href="#lista-mensagens" role="tab" aria-controls="messages">Mensagens</a>
      <a class="list-group-item list-group-item-action" id="list-settings-list" data-toggle="list" href="#lista-configuracoes" role="tab" aria-controls="settings">Configurações</a>
    </div>
  </div>
  <div class="col-8">
    <div class="tab-content" id="nav-tabContent">
      <div class="tab-pane fade show active" id="list-home" role="tabpanel" aria-labelledby="list-home-list">...</div>
      <div class="tab-pane fade" id="list-profile" role="tabpanel" aria-labelledby="list-profile-list">...</div>
      <div class="tab-pane fade" id="list-messages" role="tabpanel" aria-labelledby="list-messages-list">...</div>
      <div class="tab-pane fade" id="list-settings" role="tabpanel" aria-labelledby="list-settings-list">...</div>
    </div>
  </div>
</div>
{% endhighlight %}

### via atributos data

Você pode ativar uma nevegação do grupo de lista, sem escrever qualquer JavaScript, simplesmente, especificando `data-toggle="list"` em um elemento. Use estes atributos data em um `.list-group-item`.

<div role="tabpanel">
{% highlight html %}
<!-- Grupo de lista -->
<div class="list-group" id="minhaLista" role="tablist">
  <a class="list-group-item list-group-item-action active" data-toggle="list" href="#home" role="tab">Home</a>
  <a class="list-group-item list-group-item-action" data-toggle="list" href="#perfil" role="tab">Perfil</a>
  <a class="list-group-item list-group-item-action" data-toggle="list" href="#mensagens" role="tab">Mensagens</a>
  <a class="list-group-item list-group-item-action" data-toggle="list" href="#configuracoes" role="tab">Configurações</a>
</div>

<!-- Painel de abas -->
<div class="tab-content">
  <div class="tab-pane active" id="home" role="tabpanel">...</div>
  <div class="tab-pane" id="perfil" role="tabpanel">...</div>
  <div class="tab-pane" id="mensagens" role="tabpanel">...</div>
  <div class="tab-pane" id="configuracoes" role="tabpanel">...</div>
</div>
{% endhighlight %}
</div>

### Via JavaScript

Ative uma aba item de lista, via JavaScript (cada item de lista precisa ser ativado, individualmente):

{% highlight js %}
$('#minhaLista a').on('click', function (e) {
  e.preventDefault()
  $(this).tab('show')
})
{% endhighlight %}

Você pode ativar itens de listas individuais, em diversas maneiras:

{% highlight js %}
$('#minhaLista a[href="#perfil"]').tab('show') // Selecione pelo ID da tag
$('#minhaLista a:first-child').tab('show') // Seleciona primeira aba
$('#minhaLista a:last-child').tab('show') // Seleciona última aba
$('#minhaLista a:nth-child(3)').tab('show') // Seleciona terceira aba
{% endhighlight %}

### Efeito fade

Para fazer o painel de abas receber o efeito fade in, use `.fade` em cada `.tab-pane`. A primeira aba também deve receber `.show`, para fazer o conteúdo inicial visível.

{% highlight html %}
<div class="tab-content">
  <div class="tab-pane fade show active" id="home" role="tabpanel">...</div>
  <div class="tab-pane fade" id="perfil" role="tabpanel">...</div>
  <div class="tab-pane fade" id="mensagens" role="tabpanel">...</div>
  <div class="tab-pane fade" id="configuracoes" role="tabpanel">...</div>
</div>
{% endhighlight %}

### Métodos

#### $().tab

Ativa um item de lista e o container de conteúdo. Abas devem ter um `data-target` ou um `href` remetendo a um container, no DOM.

{% highlight html %}
<div class="list-group" id="minhaLista" role="tablist">
  <a class="list-group-item list-group-item-action active" data-toggle="list" href="#home" role="tab">Home</a>
  <a class="list-group-item list-group-item-action" data-toggle="list" href="#perfil" role="tab">Perfil</a>
  <a class="list-group-item list-group-item-action" data-toggle="list" href="#mensagens" role="tab">Mensagens</a>
  <a class="list-group-item list-group-item-action" data-toggle="list" href="#configuracoes" role="tab">Configurações</a>
</div>

<div class="tab-content">
  <div class="tab-pane active" id="home" role="tabpanel">...</div>
  <div class="tab-pane" id="perfil" role="tabpanel">...</div>
  <div class="tab-pane" id="mensagens" role="tabpanel">...</div>
  <div class="tab-pane" id="configuracoes" role="tabpanel">...</div>
</div>

<script>
  $(function () {
    $('#minhaLista a:last-child').tab('show')
  })
</script>
{% endhighlight %}

#### .tab('show')

Seleciona o item de lista específico e mostra o painel associado a ele. Qualquer outro item de lista que foi, anteriormente selecionado, se torna não selecionado e seu painel associado se esconde. **Retorna ao invocador, antes do painel de abas ser exibido, de fato** (antes do evento `shown.bs.tab` ocorrer, por exemplo).

{% highlight js %}
$('#algumListItem').tab('show')
{% endhighlight %}

### Eventos

Quando mostrando uma nova aba, os eventos se acionam na seguinte ordem:

1. `hide.bs.tab` (na aba ativa, no momento)
2. `show.bs.tab` (na aba que está para ser exibida)
3. `hidden.bs.tab` (na aba ativa anteriormente, a mesma do evento `hide.bs.tab`)
4. `shown.bs.tab` (na aba recém ativa, a mesma do evento `show.bs.tab`)

Se nenhuma aba já foi ativada, os eventos `hide.bs.tab` e `hidden.bs.tab` não serão mostrados.

<table class="table table-bordered table-striped">
  <thead>
    <tr>
      <th style="width: 150px;">Tipo de evento</th>
      <th>Descrição</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>show.bs.tab</td>
      <td>Este evento é acionado na exibição de aba, mas antes da nova aba ser exibida. Use <code>event.target</code> e <code>event.relatedTarget</code> para atingir a aba ativa e a aba anteriormente ativa, respectivamente.</td>
    </tr>
    <tr>
      <td>shown.bs.tab</td>
      <td>Este evento é acionado na exibição de aba, depois da aba ser mostrada. Use <code>event.target</code> e <code>event.relatedTarget</code> para atingir a aba ativa e a aba anteriormente ativa, respectivamente.</td>
    </tr>
    <tr>
      <td>hide.bs.tab</td>
      <td>Este evento é acionado quando uma nova aba está para ser exibida e a aba anterior está para ser oculta. Use <code>event.target</code> e <code>event.relatedTarget</code> para atingir a aba ativa, no momento, e a próxima aba que está para ser ativa, respectivamente.</td>
    </tr>
    <tr>
      <td>hidden.bs.tab</td>
      <td>Este evento é acionado depois de uma nova aba ser exibida e a aba ativada anteriormente estar escondida. Use <code>event.target</code> e <code>event.relatedTarget</code> para atingir a aba ativa anteriormente e a nova aba ativa, respectivamente.</td>
    </tr>
  </tbody>
</table>

{% highlight js %}
$('a[data-toggle="list"]').on('shown.bs.tab', function (e) {
  e.target // Aba recém ativa
  e.relatedTarget // Aba ativa anteriorment
})
{% endhighlight %}

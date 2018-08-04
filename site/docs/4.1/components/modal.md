---
layout: docs
title: Modal
description: Use o plugin JavaScript modal para criar diálogos em seu site para notificações e outros tipos de conteúdos customizados.
group: components
toc: true
---

## Como funciona

Antes de começar a usar o modal Bootstrap, se assegure de ler o seguinte, já que nossas opções de menu mudaram, recentemente.

- Modals são feitos com HTML, CSS e JavaScript;
  - Eles são posicionados acima de todas as coisas do documento e removem rolagem do `<body>` para que o conteúdo do modal role.
- Clicar na tela atrás do modal vai fazer com que ele seja fechado, automaticamente;
- Bootstrap só suporta uma janela modal, por vez;
  - Modals aninhados não são suportados, já que acreditamos proporcionarem pobres experiências ou usuário.
- Modals usam `position: fixed`, o que pode ser um pouco chatinha, no que diz a respeito de sua renderização;
  - Sempre que possível, coloque o HTML do seu modal em uma posição prioritária para evitar potenciais interferências de outros elementos;
  - Você vai passar por problemas, quando aninhar um `.modal` com outro elemento fixo.
- Mais uma vez, devido a `position: fixed`, existem alguns problemas sobre o uso de modais em dispositivos móveis;
  - [Veja nossa documentação de suporte a browsers]({{ site.baseurl }}/docs/{{ site.docs_version }}/getting-started/browsers-devices/#modals-and-dropdowns-on-mobile), para mais detalhes.
- Dado como HTML5 define suas semânticas, o [atributo HTML `autofocus`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#attr-autofocus) não tem efeito em modals Bootstrap.
  - Para alcançar o mesmo efeito, use algum tipo de JavaScript customizado:

{% highlight js %}
$('#meuModal').on('shown.bs.modal', function () {
  $('#meuInput').trigger('focus')
})
{% endhighlight %}

Continue lendo, para demonstrações e instruções de uso.

## Exemplos

### Componentes modal

Abaixo, temos um exemplo de modal _static_ (`position` e `display` sobrescritos). Pode-se ver o cabeçalho, corpo (precisa de padding) e footer (opcional) do modal. Nós só pedimos que você crie cabeçalhos modal com recursos de dispensa, sempre que possível, ou dê outra opção de dispensa ao usuário.

<div class="bd-example bd-example-modal">
  <div class="modal" tabindex="-1" role="dialog">
    <div class="modal-dialog" role="document">
      <div class="modal-content">
        <div class="modal-header">
          <h5 class="modal-title">Título do modal</h5>
          <button type="button" class="close" data-dismiss="modal" aria-label="Fechar">
            <span aria-hidden="true">&times;</span>
          </button>
        </div>
        <div class="modal-body">
          <p>Texto do corpo do modal, é aqui.</p>
        </div>
        <div class="modal-footer">
          <button type="button" class="btn btn-secondary" data-dismiss="modal">Fechar</button>
          <button type="button" class="btn btn-primary">Salvar mudanças</button>
        </div>
      </div>
    </div>
  </div>
</div>

{% highlight html %}
<div class="modal" tabindex="-1" role="dialog">
  <div class="modal-dialog" role="document">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title">Título do modal</h5>
        <button type="button" class="close" data-dismiss="modal" aria-label="Fechar">
          <span aria-hidden="true">&times;</span>
        </button>
      </div>
      <div class="modal-body">
        <p>Texto do corpo do modal, é aqui.</p>
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-dismiss="modal">Fechar</button>
        <button type="button" class="btn btn-primary">Salvar mudanças</button>
      </div>
    </div>
  </div>
</div>
{% endhighlight %}

### Demonstração em tempo real

Veja um exemplo de modal, clicando no botão abaixo. Ele vai deslizar para baixo, enquanto aparece gradualmente.

<div id="exampleModalLive" class="modal fade" tabindex="-1" role="dialog" aria-labelledby="exampleModalLiveLabel" aria-hidden="true">
  <div class="modal-dialog" role="document">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title" id="exampleModalLiveLabel">Título do modal</h5>
        <button type="button" class="close" data-dismiss="modal" aria-label="Fechar">
          <span aria-hidden="true">&times;</span>
        </button>
      </div>
      <div class="modal-body">
        <p>Aêêê! Você tá vendo esse texto, dentro do modal.</p>
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-dismiss="modal">Fechar</button>
        <button type="button" class="btn btn-primary">Salvar mudanças</button>
      </div>
    </div>
  </div>
</div>

<div class="bd-example">
  <button type="button" class="btn btn-primary" data-toggle="modal" data-target="#exampleModalLive">
    Abrir modal de demonstração
  </button>
</div>

{% highlight html %}
<!-- Botão para acionar modal -->
<button type="button" class="btn btn-primary" data-toggle="modal" data-target="#modalExemplo">
  Abrir modal de demonstração
</button>

<!-- Modal -->
<div class="modal fade" id="modalExemplo" tabindex="-1" role="dialog" aria-labelledby="exampleModalLabel" aria-hidden="true">
  <div class="modal-dialog" role="document">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title" id="exampleModalLabel">Título do modal</h5>
        <button type="button" class="close" data-dismiss="modal" aria-label="Fechar">
          <span aria-hidden="true">&times;</span>
        </button>
      </div>
      <div class="modal-body">
        ...
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-dismiss="modal">Fechar</button>
        <button type="button" class="btn btn-primary">Salvar mudanças</button>
      </div>
    </div>
  </div>
</div>
{% endhighlight %}

### Rolando conteúdo longo

Quando modals são muito longos para a viewport do usuário ou dispositivo, eles possuem rolagem independente da página. Teste a demo abaixo, para saber de oquê estamos falando.

<div id="ModalLongoExemplo" class="modal fade" tabindex="-1" role="dialog" aria-labelledby="TituloModalLongoExemplo" aria-hidden="true">
  <div class="modal-dialog" role="document">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title" id="TituloModalLongoExemplo">Título do modal</h5>
        <button type="button" class="close" data-dismiss="modal" aria-label="Fechar">
          <span aria-hidden="true">&times;</span>
        </button>
      </div>
      <div class="modal-body">
        <p>Cras mattis consectetur purus sit amet fermentum. Cras justo odio, dapibus ac facilisis in, egestas eget quam. Morbi leo risus, porta ac consectetur ac, vestibulum at eros.</p>
        <p>Praesent commodo cursus magna, vel scelerisque nisl consectetur et. Vivamus sagittis lacus vel augue laoreet rutrum faucibus dolor auctor.</p>
        <p>Aenean lacinia bibendum nulla sed consectetur. Praesent commodo cursus magna, vel scelerisque nisl consectetur et. Donec sed odio dui. Donec ullamcorper nulla non metus auctor fringilla.</p>
        <p>Cras mattis consectetur purus sit amet fermentum. Cras justo odio, dapibus ac facilisis in, egestas eget quam. Morbi leo risus, porta ac consectetur ac, vestibulum at eros.</p>
        <p>Praesent commodo cursus magna, vel scelerisque nisl consectetur et. Vivamus sagittis lacus vel augue laoreet rutrum faucibus dolor auctor.</p>
        <p>Aenean lacinia bibendum nulla sed consectetur. Praesent commodo cursus magna, vel scelerisque nisl consectetur et. Donec sed odio dui. Donec ullamcorper nulla non metus auctor fringilla.</p>
        <p>Cras mattis consectetur purus sit amet fermentum. Cras justo odio, dapibus ac facilisis in, egestas eget quam. Morbi leo risus, porta ac consectetur ac, vestibulum at eros.</p>
        <p>Praesent commodo cursus magna, vel scelerisque nisl consectetur et. Vivamus sagittis lacus vel augue laoreet rutrum faucibus dolor auctor.</p>
        <p>Aenean lacinia bibendum nulla sed consectetur. Praesent commodo cursus magna, vel scelerisque nisl consectetur et. Donec sed odio dui. Donec ullamcorper nulla non metus auctor fringilla.</p>
        <p>Cras mattis consectetur purus sit amet fermentum. Cras justo odio, dapibus ac facilisis in, egestas eget quam. Morbi leo risus, porta ac consectetur ac, vestibulum at eros.</p>
        <p>Praesent commodo cursus magna, vel scelerisque nisl consectetur et. Vivamus sagittis lacus vel augue laoreet rutrum faucibus dolor auctor.</p>
        <p>Aenean lacinia bibendum nulla sed consectetur. Praesent commodo cursus magna, vel scelerisque nisl consectetur et. Donec sed odio dui. Donec ullamcorper nulla non metus auctor fringilla.</p>
        <p>Cras mattis consectetur purus sit amet fermentum. Cras justo odio, dapibus ac facilisis in, egestas eget quam. Morbi leo risus, porta ac consectetur ac, vestibulum at eros.</p>
        <p>Praesent commodo cursus magna, vel scelerisque nisl consectetur et. Vivamus sagittis lacus vel augue laoreet rutrum faucibus dolor auctor.</p>
        <p>Aenean lacinia bibendum nulla sed consectetur. Praesent commodo cursus magna, vel scelerisque nisl consectetur et. Donec sed odio dui. Donec ullamcorper nulla non metus auctor fringilla.</p>
        <p>Cras mattis consectetur purus sit amet fermentum. Cras justo odio, dapibus ac facilisis in, egestas eget quam. Morbi leo risus, porta ac consectetur ac, vestibulum at eros.</p>
        <p>Praesent commodo cursus magna, vel scelerisque nisl consectetur et. Vivamus sagittis lacus vel augue laoreet rutrum faucibus dolor auctor.</p>
        <p>Aenean lacinia bibendum nulla sed consectetur. Praesent commodo cursus magna, vel scelerisque nisl consectetur et. Donec sed odio dui. Donec ullamcorper nulla non metus auctor fringilla.</p>
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-dismiss="modal">Fechar</button>
        <button type="button" class="btn btn-primary">Salvar mudanças</button>
      </div>
    </div>
  </div>
</div>

<div class="bd-example">
  <button type="button" class="btn btn-primary" data-toggle="modal" data-target="#ModalLongoExemplo">
    Abrir modal de demonstração
  </button>
</div>

{% highlight html %}
<!-- Botão para acionar modal -->
<button type="button" class="btn btn-primary" data-toggle="modal" data-target="#ModalLongoExemplo">
  Abrir modal de demonstração
</button>

<!-- Modal -->
<div class="modal fade" id="ModalLongoExemplo" tabindex="-1" role="dialog" aria-labelledby="TituloModalLongoExemplo" aria-hidden="true">
  <div class="modal-dialog" role="document">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title" id="TituloModalLongoExemplo">Título do modal</h5>
        <button type="button" class="close" data-dismiss="modal" aria-label="Fechar">
          <span aria-hidden="true">&times;</span>
        </button>
      </div>
      <div class="modal-body">
        ...
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-dismiss="modal">Fechar</button>
        <button type="button" class="btn btn-primary">Salvar mudanças</button>
      </div>
    </div>
  </div>
</div>
{% endhighlight %}

### Verticalmente centralizado

Use `.modal-dialog-centered` no `.modal-dialog` para, verticalmente, centralizar o modal.

<div id="ExemploModalCentralizado" class="modal fade" tabindex="-1" role="dialog" aria-labelledby="TituloModalCentralizado" aria-hidden="true">
  <div class="modal-dialog modal-dialog-centered" role="document">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title" id="TituloModalCentralizado">Título do modal</h5>
        <button type="button" class="close" data-dismiss="modal" aria-label="Fechar">
          <span aria-hidden="true">&times;</span>
        </button>
      </div>
      <div class="modal-body">
        <p>Cras mattis consectetur purus sit amet fermentum. Cras justo odio, dapibus ac facilisis in, egestas eget quam. Morbi leo risus, porta ac consectetur ac, vestibulum at eros.</p>
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-dismiss="modal">Fechar</button>
        <button type="button" class="btn btn-primary">Salvar mudanças</button>
      </div>
    </div>
  </div>
</div>

<div class="bd-example">
  <button type="button" class="btn btn-primary" data-toggle="modal" data-target="#ExemploModalCentralizado">
    Abrir modal de demonstração
  </button>
</div>

{% highlight html %}
<!-- Botão para acionar modal -->
<button type="button" class="btn btn-primary" data-toggle="modal" data-target="#ExemploModalCentralizado">
  Abrir modal de demonstração
</button>

<!-- Modal -->
<div class="modal fade" id="ExemploModalCentralizado" tabindex="-1" role="dialog" aria-labelledby="TituloModalCentralizado" aria-hidden="true">
  <div class="modal-dialog modal-dialog-centered" role="document">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title" id="TituloModalCentralizado">Título do modal</h5>
        <button type="button" class="close" data-dismiss="modal" aria-label="Fechar">
          <span aria-hidden="true">&times;</span>
        </button>
      </div>
      <div class="modal-body">
        ...
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-dismiss="modal">Fechar</button>
        <button type="button" class="btn btn-primary">Salvar mudanças</button>
      </div>
    </div>
  </div>
</div>
{% endhighlight %}

### Tooltips e popovers

[Tooltips]({{ site.baseurl }}/docs/{{ site.docs_version }}/components/tooltips/) e [popovers]({{ site.baseurl }}/docs/{{ site.docs_version }}/components/popovers/) podem ser posicionados dentro de modals, sempre que necessário. Quando modals são fechados, qualquer tooltip ou popover dentro deles e fechado, automaticamente.

<div id="exampleModalPopovers" class="modal fade" tabindex="-1" role="dialog" aria-labelledby="exampleModalPopoversLabel" aria-hidden="true">
  <div class="modal-dialog" role="document">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title" id="exampleModalPopoversLabel">Título do modal</h5>
        <button type="button" class="close" data-dismiss="modal" aria-label="Fechar">
          <span aria-hidden="true">&times;</span>
        </button>
      </div>
      <div class="modal-body">
        <h5>Popover em um modal</h5>
        <p>Este <a href="#" role="button" class="btn btn-secondary popover-test" title="Título do popover" data-content="O conteúdo do popover é definido aqui." data-container="#exampleModalPopovers">botão</a> aciona um popover, ao clicar nele.</p>
        <hr>
        <h5>Tooltips em um modal</h5>
        <p><a href="#" class="tooltip-test" title="Tooltip" data-container="#exampleModalPopovers">Este link</a> e <a href="#" class="tooltip-test" title="Tooltip" data-container="#exampleModalPopovers">este outro</a> mostra tooltips, quando passamos o mouse sobre.</p>
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-dismiss="modal">Fechar</button>
        <button type="button" class="btn btn-primary">Salvar mudanças</button>
      </div>
    </div>
  </div>
</div>

<div class="bd-example">
  <button type="button" class="btn btn-primary" data-toggle="modal" data-target="#exampleModalPopovers">
    Abrir modal de demonstração
  </button>
</div>

{% highlight html %}
<div class="modal-body">
  <h5>Popover em um modal</h5>
  <p>Este <a href="#" role="button" class="btn btn-secondary popover-test" title="Título do popover" data-content="O conteúdo do popover é definido aqui.">botão</a> aciona um popover, ao clicar nele.</p>
  <hr>
  <h5>Tooltips em um modal</h5>
  <p><a href="#" class="tooltip-test" title="Tooltip">Este link</a> e <a href="#" class="tooltip-test" title="Tooltip">este outro</a> mostra tooltips, quando passamos o mouse sobre eles.</p>
</div>
{% endhighlight %}

### Usando o grid

Use o sistema grid Bootstrap dentro de um modal, aninhando `.container-fluid` no `.modal-body`. Depois, use as classes do sistema grid, assim como faria em outros locais.

<div id="gridSystemModal" class="modal fade" tabindex="-1" role="dialog" aria-labelledby="gridModalLabel" aria-hidden="true">
  <div class="modal-dialog" role="document">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title" id="gridModalLabel">Grids em modals</h5>
        <button type="button" class="close" data-dismiss="modal" aria-label="Fechar"><span aria-hidden="true">&times;</span></button>
      </div>
      <div class="modal-body">
        <div class="container-fluid bd-example-row">
          <div class="row">
            <div class="col-md-4">.col-md-4</div>
            <div class="col-md-4 ml-auto">.col-md-4 .ml-auto</div>
          </div>
          <div class="row">
            <div class="col-md-3 ml-auto">.col-md-3 .ml-auto</div>
            <div class="col-md-2 ml-auto">.col-md-2 .ml-auto</div>
          </div>
          <div class="row">
            <div class="col-md-6 ml-auto">.col-md-6 .ml-auto</div>
          </div>
          <div class="row">
            <div class="col-sm-9">
              Level 1: .col-sm-9
              <div class="row">
                <div class="col-8 col-sm-6">
                  Level 2: .col-8 .col-sm-6
                </div>
                <div class="col-4 col-sm-6">
                  Level 2: .col-4 .col-sm-6
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-dismiss="modal">Fechar</button>
        <button type="button" class="btn btn-primary">Salvar mudanças</button>
      </div>
    </div>
  </div>
</div>

<div class="bd-example">
<button type="button" class="btn btn-primary" data-toggle="modal" data-target="#gridSystemModal">
  Abrir modal de demonstração
</button>
</div>

{% highlight html %}
<div class="modal-body">
  <div class="container-fluid">
    <div class="row">
      <div class="col-md-4">.col-md-4</div>
      <div class="col-md-4 ml-auto">.col-md-4 .ml-auto</div>
    </div>
    <div class="row">
      <div class="col-md-3 ml-auto">.col-md-3 .ml-auto</div>
      <div class="col-md-2 ml-auto">.col-md-2 .ml-auto</div>
    </div>
    <div class="row">
      <div class="col-md-6 ml-auto">.col-md-6 .ml-auto</div>
    </div>
    <div class="row">
      <div class="col-sm-9">
        Level 1: .col-sm-9
        <div class="row">
          <div class="col-8 col-sm-6">
            Level 2: .col-8 .col-sm-6
          </div>
          <div class="col-4 col-sm-6">
            Level 2: .col-4 .col-sm-6
          </div>
        </div>
      </div>
    </div>
  </div>
</div>
{% endhighlight %}

### Variando o conteúdo de modais

Tem vários botões que acionam o mesmo modal, mas com o conteúdo um pouco diferente? Use `event.relatedTarget` e [atributos HTML `data-*`](https://developer.mozilla.org/en-US/docs/Learn/HTML/Howto/Use_data_attributes) ([via jQuery](https://api.jquery.com/data/), se possível) para variar o conteúdo do modal, dependendo de qual botão foi clicado.

Abaixo, temos uma demonstração seguida de um exemplo HTML e JavaScript. Para mais informação, [leia a documentação de eventos do modal](#events) para detalhes sobre `relatedTarget`.

{% capture example %}
<button type="button" class="btn btn-primary" data-toggle="modal" data-target="#exampleModal" data-whatever="@mdo">Falar com @mdo</button>
<button type="button" class="btn btn-primary" data-toggle="modal" data-target="#exampleModal" data-whatever="@fat">Falar com @fat</button>
<button type="button" class="btn btn-primary" data-toggle="modal" data-target="#exampleModal" data-whatever="@getbootstrap">Falar com @getbootstrap</button>

<div class="modal fade" id="exampleModal" tabindex="-1" role="dialog" aria-labelledby="exampleModalLabel" aria-hidden="true">
  <div class="modal-dialog" role="document">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title" id="exampleModalLabel">Nova mensagem</h5>
        <button type="button" class="close" data-dismiss="modal" aria-label="Fechar">
          <span aria-hidden="true">&times;</span>
        </button>
      </div>
      <div class="modal-body">
        <form>
          <div class="form-group">
            <label for="recipient-name" class="col-form-label">Destinatário:</label>
            <input type="text" class="form-control" id="recipient-name">
          </div>
          <div class="form-group">
            <label for="message-text" class="col-form-label">Mensagem:</label>
            <textarea class="form-control" id="message-text"></textarea>
          </div>
        </form>
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-dismiss="modal">Fechar</button>
        <button type="button" class="btn btn-primary">Enviar</button>
      </div>
    </div>
  </div>
</div>
{% endcapture %}
{% include example.html content=example %}

{% highlight js %}
$('#exampleModal').on('show.bs.modal', function (event) {
  var button = $(event.relatedTarget) // Botão que acionou o modal
  var recipient = button.data('whatever') // Extrai informação dos atributos data-*
  // Se necessário, você pode iniciar uma requisição AJAX aqui e, então, fazer a atualização em um callback.
  // Atualiza o conteúdo do modal. Nós vamos usar jQuery, aqui. No entanto, você poderia usar uma biblioteca de data binding ou outros métodos.
  var modal = $(this)
  modal.find('.modal-title').text('Nova mensagem para ' + recipient)
  modal.find('.modal-body input').val(recipient)
})
{% endhighlight %}

### Remover animação

Para modals que, simplesmente, aparecem de supetão, invés de gradualmente, remova a classe `.fade` da marcação do seu modal.

{% highlight html %}
<div class="modal" tabindex="-1" role="dialog" aria-labelledby="..." aria-hidden="true">
  ...
</div>
{% endhighlight %}

### Alturas dinâmicas

Se a altura do modal muda enquanto é aberta, você deveria invocar `$('#meuModal').modal('handleUpdate')` para reajustar a posição do modal, caso a barra de rolagem apareça.

### Acessibilidade

Se assegure de usar `role="dialog"` e `aria-labelledby="..."`, remetendo o título do modal ao `.modal` e `role="document"` ao `.modal-dialog`. Alternativamente, você pode dar uma descrição do seu modal, no `aria-describedby` do `.modal`.

### Embutindo vídeos do YouTube

Embutir vídeos do YouTube em modals pede JavaScript adicional, para parar o playback e outras coisas, automaticamente. [Veja este ótimo post, no Stack Overflow](https://stackoverflow.com/questions/18622508/bootstrap-3-and-youtube-in-modal), para mais informação.

## Tamanhos opcionais

Modals possuem três tamanhos alternativos, disponíveis via classes modificadoras e a serem colocadas em um `.modal-dialog`. Estes tamanhos são cancelados, em certos breakpoints, para evitar rolagem horizontal em viewports menores.

<table class="table table-bordered table-striped">
  <thead>
    <tr>
      <th>Tamanho</th>
      <th>Classe</th>
      <th>Largura máxima</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Pequeno</td>
      <td><code>.modal-sm</code></td>
      <td><code>300px</code></td>
    </tr>
    <tr>
      <td>Padrão</td>
      <td class="text-muted">Nenhuma</td>
      <td><code>500px</code></td>
    </tr>
    <tr>
      <td>Grande</td>
      <td><code>.modal-lg</code></td>
      <td><code>800px</code></td>
    </tr>
    <tr>
      <td>Extra grande</td>
      <td><code>.modal-xl</code></td>
      <td><code>1140px</code></td>
    </tr>
  </tbody>
</table>

Nosso modal padrão sem classe modificadora constitui o modal de tamanho médio.

<div class="bd-example">
  <button type="button" class="btn btn-primary" data-toggle="modal" data-target=".bd-example-modal-xl">Modal extra grande</button>
  <button type="button" class="btn btn-primary" data-toggle="modal" data-target=".bd-example-modal-lg">Modal grande</button>
  <button type="button" class="btn btn-primary" data-toggle="modal" data-target=".bd-example-modal-sm">Modal pequeno</button>
</div>

{% highlight html %}
<!-- Modal extra grande -->
<button class="btn btn-primary" data-toggle="modal" data-target=".bd-example-modal-xl">Modal extra grande</button>

<div class="modal fade bd-example-modal-xl" tabindex="-1" role="dialog" aria-labelledby="myExtraLargeModalLabel" aria-hidden="true">
  <div class="modal-dialog modal-xl">
    <div class="modal-content">
      ...
    </div>
  </div>
</div>

<!-- Modal grande -->
<button type="button" class="btn btn-primary" data-toggle="modal" data-target=".bd-example-modal-lg">Modal grande</button>

<div class="modal fade bd-example-modal-lg" tabindex="-1" role="dialog" aria-labelledby="myLargeModalLabel" aria-hidden="true">
  <div class="modal-dialog modal-lg">
    <div class="modal-content">
      ...
    </div>
  </div>
</div>

<!-- Modal pequeno -->
<button type="button" class="btn btn-primary" data-toggle="modal" data-target=".bd-example-modal-sm">Modal pequeno</button>

<div class="modal fade bd-example-modal-sm" tabindex="-1" role="dialog" aria-labelledby="mySmallModalLabel" aria-hidden="true">
  <div class="modal-dialog modal-sm">
    <div class="modal-content">
      ...
    </div>
  </div>
</div>
{% endhighlight %}

<div class="modal fade bd-example-modal-xl" tabindex="-1" role="dialog" aria-labelledby="myExtraLargeModalLabel" aria-hidden="true">
  <div class="modal-dialog modal-xl">
    <div class="modal-content">

      <div class="modal-header">
        <h5 class="modal-title h4" id="myExtraLargeModalLabel">Modal extra grande</h5>
        <button type="button" class="close" data-dismiss="modal" aria-label="Close">
          <span aria-hidden="true">&times;</span>
        </button>
      </div>
      <div class="modal-body">
        ...
      </div>
    </div>
  </div>
</div>

<div class="modal fade bd-example-modal-lg" tabindex="-1" role="dialog" aria-labelledby="myLargeModalLabel" aria-hidden="true">
  <div class="modal-dialog modal-lg">
    <div class="modal-content">

      <div class="modal-header">
        <h5 class="modal-title h4" id="myLargeModalLabel">Modal grande</h5>
        <button type="button" class="close" data-dismiss="modal" aria-label="Fechar">
          <span aria-hidden="true">&times;</span>
        </button>
      </div>
      <div class="modal-body">
        ...
      </div>
    </div>
  </div>
</div>

<div class="modal fade bd-example-modal-sm" tabindex="-1" role="dialog" aria-labelledby="mySmallModalLabel" aria-hidden="true">
  <div class="modal-dialog modal-sm">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title h4" id="mySmallModalLabel">Modal pequeno</h5>
        <button type="button" class="close" data-dismiss="modal" aria-label="Fechar">
          <span aria-hidden="true">&times;</span>
        </button>
      </div>
      <div class="modal-body">
        ...
      </div>
    </div>
  </div>
</div>

## Modo de uso

O plugin modal alterna a visibilidade do seu conteúdo, via atributos data ou JavaScript. Ele também coloca `.modal-open` no `<body>` para sobrescrever o comportamento padrão de rolagem e gerar um `.modal-backdrop` para dar uma área de clique fora do modal que permite fechá-lo.

### Via atributos data

Ativa o modal sem escrever JavaScript. Defina `data-toggle="modal"` em um elemento de controle (como um botão), junto com um `data-target="#foo"` ou `href="#foo"` que remeta a um modal específico a ser acionado.

{% highlight html %}
<button type="button" data-toggle="modal" data-target="#meuModal">Abrir modal</button>
{% endhighlight %}

### Via JavaScript

Invoque um modal com ID `meuModal`, usando uma única linha JavaScript:

{% highlight js %}$('#meuModal').modal(options){% endhighlight %}

### Parâmetros

Parâmetros podem ser passados via atributos data ou JavaScript. Para atributos data, anexe o nome do parâmetro ao prefixo `data-*`, como em `data-backdrop=""`.

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
      <td>backdrop</td>
      <td>booleano ou a string <code>'static'</code></td>
      <td>true</td>
      <td>Cria um elemento modal backdrop. Alternativamente, use <code>static</code> para um backdrop que não fecha o modal, ao clicar.</td>
    </tr>
    <tr>
      <td>keyboard</td>
      <td>boolean</td>
      <td>true</td>
      <td>Fecha o modal, quando a tecla <kbd>esc</kbd> é pressionada.</td>
    </tr>
    <tr>
      <td>focus</td>
      <td>boolean</td>
      <td>true</td>
      <td>Foca no modal, quando inicializado.</td>
    </tr>
    <tr>
      <td>show</td>
      <td>boolean</td>
      <td>true</td>
      <td>Mostra o modal, quando inicializado.</td>
    </tr>
  </tbody>
</table>

### Métodos

{% include callout-danger-async-methods.md %}

#### `.modal(options)`

Define seu conteúdo como um modal. Aceita um `objeto` de parâmetros, opcional.

{% highlight js %}
$('#meuModal').modal({
  keyboard: false
})
{% endhighlight %}

#### `.modal('toggle')`

Manualmente, alterna a visibilidade do modal. **Retorna ao invocador, antes do modal ter sido exibido ou escondido, de fato** (antes dos eventos `shown.bs.modal` ou `hidden.bs.modal` ocorrerem).

{% highlight js %}$('#meuModal').modal('toggle'){% endhighlight %}

#### `.modal('show')`

Manualmente, abre o modal. **Retorna ao invocador, antes do modal ter sido exibido, de fato** (antes do evento `shown.bs.modal` ocorrer).

{% highlight js %}$('#meuModal').modal('show'){% endhighlight %}

#### `.modal('hide')`

Manualmente, esconde o modal. **Retorna ao invocador, antes do modal ter sido escondido, de fato** (antes do evento `hidden.bs.modal` ocorrer).

{% highlight js %}$('#meuModal').modal('hide'){% endhighlight %}

#### `.modal('handleUpdate')`

Manualmente, reajuste a posição do modal se a altura dele se alterar, enquanto está aberto (caso uma barra de rolagem apareça).

{% highlight js %}$('#meuModal').modal('handleUpdate'){% endhighlight %}

#### `.modal('dispose')`

Destrói o modal de um elemento.

### Eventos

A classe modal Bootstrap possui alguns eventos para criar a funcionalidade modal, em si. Todos eventos modal são acionados nele mesmo (no `<div class="modal">`).

<table class="table table-bordered table-striped">
  <thead>
    <tr>
      <th style="width: 150px;">Tipo de evento</th>
      <th>Descrição</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>show.bs.modal</td>
      <td>Este evento é acionado, imediatamente, quando o método <code>show</code> é invocado. Se acionado por um clique, o elemento clicado fica disponível como a propriedade <code>relatedTarget</code> do evento.</td>
    </tr>
    <tr>
      <td>shown.bs.modal</td>
      <td>Este evento é acionado quando o modal se torna visível ao usuário (espera as transições CSS finalizarem). Se acionado por um clique, o elemento clicado fica disponível como a propriedade <code>relatedTarget</code> do evento.</td>
    </tr>
    <tr>
      <td>hide.bs.modal</td>
      <td>Este evento é acionado, imediatamente, quando o método <code>hide</code> é invocado.</td>
    </tr>
    <tr>
      <td>hidden.bs.modal</td>
      <td>Este evento é acionado quando o modal acaba de ser oculto ao usuário (espera as transições CSS finalizarem).</td>
    </tr>
  </tbody>
</table>

{% highlight js %}
$('#meuModal').on('hidden.bs.modal', function (e) {
  // Faça algo, aqui...
})
{% endhighlight %}

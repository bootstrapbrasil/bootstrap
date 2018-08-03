---
layout: docs
title: Alertas
description: Apresente mensagens contextuais para ações típicas dos usuários, usando este punhado flexível de mensagens de alerta.
group: components
toc: true
---

## Exemplos

Alertas estão disponíveis para qualquer tamanho de texto, assim como um botão de dispersão opcional. Para uma estilização adequada, use uma das oito **requeridas** classes contextuais (ex: `.alert-success`). Para dispersão inline, use o plugin [jQuery alerts](#dismissing).

{% capture example %}
{% for color in site.data.theme-colors %}
<div class="alert alert-{{ color.name }}" role="alert">
  Um simples alerta {{ color.name }}. Olha só!
</div>{% endfor %}
{% endcapture %}
{% include example.html content=example %}

{% include callout-warning-color-assistive-technologies.md %}

### Cores de links

Use a classe utilitária `.alert-link` para, rapidamente, conseguir cores de links que combinam com o alerta.

{% capture example %}
{% for color in site.data.theme-colors %}
<div class="alert alert-{{ color.name }}" role="alert">
  Um simples alerta {{ color.name }} com <a href="#" class="alert-link">um link de exemplo</a>. Clique nele, se quiser.
</div>{% endfor %}
{% endcapture %}
{% include example.html content=example %}

### Conteúdo adicional

Alertas também podem conter elementos HTML adicionais como cabeçalhos, parágrafos e divisores.

{% capture example %}
<div class="alert alert-success" role="alert">
  <h4 class="alert-heading">Muito bem!</h4>
  <p>Aêêê! Você conseguiu ler essa mensagem de alerta. Esse texto vai ter quer se extender um pouquinho pra você conseguir ver como o espaçamento dentro de um alerta funciona.</p>
  <hr>
  <p class="mb-0">Sempre que precisar, use utilitários de margem para manter as coisas perfeitas.</p>
</div>
{% endcapture %}
{% include example.html content=example %}


### Dispersão

Usando o plugin JavaScript de alerta, é possível dispersar qualquer alerta inline, dessa forma:

- Se assegure de carregar o plugin de alerta ou o JavaScript Bootstrap compilado;
- Se você está construindo nosso JavaScript a partir da fonte, vai precisar do [`util.js`]({{ site.baseurl }}/docs/{{ site.docs_version }}/getting-started/javascript/#util);
  - A versão compilada já inclui ele.
- Adicione um botão de dispersão e a classe `.alert-dismissible`, a qual adiciona padding extra a direita do alerta e posiciona o botão `.close`;
- No botão de dispersão, use o atributo `data-dismiss="alert"`, o qual aciona a funcionalidade JavaScript;
  - Tenha certeza de usar o elemento `<button>` com isso, para que ele se comporte em todos os dispositivos, adequadamente.
- Para animar alertas quando dispersá-los, se assegure de usar as classes `.fade` e `.show`.

Você pode ver isso, em ação, com essa demonstração em tempo real:

{% capture example %}
<div class="alert alert-warning alert-dismissible fade show" role="alert">
  <strong>Oloco, meu!</strong> Olha esse alerta animado, como é chique!
  <button type="button" class="close" data-dismiss="alert" aria-label="Close">
    <span aria-hidden="true">&times;</span>
  </button>
</div>
{% endcapture %}
{% include example.html content=example %}

## Comportamento JavaScript

### Acionadores

Ative a dispersão de um alerta, usando JavaScript:

{% highlight js %}
$('.alert').alert()
{% endhighlight %}

Também é possível, usando atributos `data` em um **botão dentro do alerta**, como vemos abaixo:

{% highlight html %}
<button type="button" class="close" data-dismiss="alert" aria-label="Close">
  <span aria-hidden="true">&times;</span>
</button>
{% endhighlight %}

Perceba que dispersar um alerta irá removê-lo do DOM.

### Métodos

| Método | Descrição |
| --- | --- |
| `$().alert()` | Faz um alerta esperar por eventos de cliques em elementos descendentes, os quais possuem o atributo `data-dismiss="alert"` (não é necessário, quando usando a auto-inicialização do data-api). |
| `$().alert('close')` | Fecha um alerta, removendo-o do DOM. Se as classes `.fade` e `.show` estão presentes no elemento, o alerta vai esmaecer antes de ser removido. |
| `$().alert('dispose')` | Destroi o alerta de um elemento. |

{% highlight js %}$(".alert").alert('close'){% endhighlight %}

### Eventos

O plugin de alerta do Bootstrap usa alguns eventos para se ligar com a funcionalidade de alerta.


| Evento | Descrição |
| --- | --- |
| `close.bs.alert` | Este evento é acionado, imediadatamente, quando a instância do método <code>close</code> é invocada. |
| `closed.bs.alert` | Este evento é acionado quando o alerta é fechado (vai esperar a transição CSS se finalizada). |

{% highlight js %}
$('#myAlert').on('closed.bs.alert', function () {
  // do something…
})
{% endhighlight %}

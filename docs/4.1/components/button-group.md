---
layout: docs
title: Grupos de botões
description: Agrupe vários botões em uma única linha e tune eles com JavaScript, usando este componente.
group: components
toc: true
---

## Exemplo básico

Envolva vários botões (que possuem `.btn`) em um elemento com `.btn-group`. Adicione um comportamento JavaScript opcional de radio ou checkbox com [nosso plugin buttons]({{ site.baseurl }}/docs/{{ site.docs_version }}/components/buttons/#button-plugin).

{% capture example %}
<div class="btn-group" role="group" aria-label="Exemplo básico">
  <button type="button" class="btn btn-secondary">Esquerda</button>
  <button type="button" class="btn btn-secondary">Meio</button>
  <button type="button" class="btn btn-secondary">Direita</button>
</div>
{% endcapture %}
{% include example.html content=example %}

{% capture callout %}
##### Certifique-se de usar o `role` correto e prover uma label

Para que uma tecnologia assistiva (como leitores de telas) consiga entender que está lidando com uma série de botões agrupados, um atributo `role`, apropriado, deve ser usado. Para grupos de botões, o atributo poder ser `role="group"`. Enquanto que toolbars devem usar `role="toolbar"`.

Além disso, grupos de botões e toolbars devem receber uma label, já que a maioria das tecnologias assistivas não vão fazer isso, independente da presença do atributo role. Nos exemplos mostrados aqui, usamos `aria-label`, mas alternativas como `aria-labelledby` também podem serem usadas.
{% endcapture %}
{% include callout.html content=callout type="warning" %}

## Toolbars

Combine grupos de botões para criar uma toolbar e ter um componente mais complexo. Use classes utilitárias, sempre que precisar, para espaçar grupos, botões e outras coisas.

{% capture example %}
<div class="btn-toolbar" role="toolbar" aria-label="Toolbar com grupos de botões">
  <div class="btn-group mr-2" role="group" aria-label="Primeiro grupo">
    <button type="button" class="btn btn-secondary">1</button>
    <button type="button" class="btn btn-secondary">2</button>
    <button type="button" class="btn btn-secondary">3</button>
    <button type="button" class="btn btn-secondary">4</button>
  </div>
  <div class="btn-group mr-2" role="group" aria-label="Segundo grupo">
    <button type="button" class="btn btn-secondary">5</button>
    <button type="button" class="btn btn-secondary">6</button>
    <button type="button" class="btn btn-secondary">7</button>
  </div>
  <div class="btn-group" role="group" aria-label="Terceiro grupo">
    <button type="button" class="btn btn-secondary">8</button>
  </div>
</div>
{% endcapture %}
{% include example.html content=example %}

Sinta-se livre para usar uma mistura de grupos de inputs e botões, em suas toolbars. Similar ao exemplo acima, você vai precisar de alguns utilitários para espaçar as coisas, provavelmente.

{% capture example %}
<div class="btn-toolbar mb-3" role="toolbar" aria-label="Toolbar com grupos de botões">
  <div class="btn-group mr-2" role="group" aria-label="Primeiro grupo">
    <button type="button" class="btn btn-secondary">1</button>
    <button type="button" class="btn btn-secondary">2</button>
    <button type="button" class="btn btn-secondary">3</button>
    <button type="button" class="btn btn-secondary">4</button>
  </div>
  <div class="input-group">
    <div class="input-group-prepend">
      <div class="input-group-text" id="btnGroupAddon">@</div>
    </div>
    <input type="text" class="form-control" placeholder="Exemplo de grupo de input" aria-label="Exemplo de grupo de input" aria-describedby="btnGroupAddon">
  </div>
</div>

<div class="btn-toolbar justify-content-between" role="toolbar" aria-label="Toolbar com grupos de botões">
  <div class="btn-group" role="group" aria-label="Primeiro grupo">
    <button type="button" class="btn btn-secondary">1</button>
    <button type="button" class="btn btn-secondary">2</button>
    <button type="button" class="btn btn-secondary">3</button>
    <button type="button" class="btn btn-secondary">4</button>
  </div>
  <div class="input-group">
    <div class="input-group-prepend">
      <div class="input-group-text" id="btnGroupAddon2">@</div>
    </div>
    <input type="text" class="form-control" placeholder="Exemplo de grupo de input" aria-label="Exemplo de grupo de input" aria-describedby="btnGroupAddon2">
  </div>
</div>
{% endcapture %}
{% include example.html content=example %}

## Dimensionamento

Invés de aplicar classes para dimensionamento em cada botão de um grupo, basta adicionar `.btn-group-*` para cada `.btn-group`, incluindo cada um quando aninhar vários grupos.

<div class="bd-example">
  <div class="btn-group btn-group-lg" role="group" aria-label="Grupos de botões grandes">
    <button type="button" class="btn btn-secondary">Esquerda</button>
    <button type="button" class="btn btn-secondary">Meio</button>
    <button type="button" class="btn btn-secondary">Direita</button>
  </div>
  <br>
  <div class="btn-group" role="group" aria-label="Grupos de botões padrão">
    <button type="button" class="btn btn-secondary">Esquerda</button>
    <button type="button" class="btn btn-secondary">Meio</button>
    <button type="button" class="btn btn-secondary">Direita</button>
  </div>
  <br>
  <div class="btn-group btn-group-sm" role="group" aria-label="Grupos de botões pequenos">
    <button type="button" class="btn btn-secondary">Esquerda</button>
    <button type="button" class="btn btn-secondary">Meio</button>
    <button type="button" class="btn btn-secondary">Direita</button>
  </div>
</div>

{% highlight html %}
<div class="btn-group btn-group-lg" role="group" aria-label="...">...</div>
<div class="btn-group" role="group" aria-label="...">...</div>
<div class="btn-group btn-group-sm" role="group" aria-label="...">...</div>
{% endhighlight %}

## Aninhamento

Coloque um `.btn-group` dentro de outro `.btn-group` quando quiser menus dropdowns misturados com vários botões.

{% capture example %}
<div class="btn-group" role="group" aria-label="Grupo de botões com dropdown aninhado">
  <button type="button" class="btn btn-secondary">1</button>
  <button type="button" class="btn btn-secondary">2</button>

  <div class="btn-group" role="group">
    <button id="btnGroupDrop1" type="button" class="btn btn-secondary dropdown-toggle" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
      Dropdown
    </button>
    <div class="dropdown-menu" aria-labelledby="btnGroupDrop1">
      <a class="dropdown-item" href="#">Link dropdown</a>
      <a class="dropdown-item" href="#">Link dropdown</a>
    </div>
  </div>
</div>
{% endcapture %}
{% include example.html content=example %}

## Variação vertical

Faça com que uma série de botões apareça verticalmente, invés de horizontalmente. **Botões dropdowns divididos não são suportados, nesse caso.**

<div class="bd-example">
  <div class="btn-group-vertical" role="group" aria-label="Grupos de botões vertical">
    <button type="button" class="btn btn-secondary">Botão</button>
    <button type="button" class="btn btn-secondary">Botão</button>
    <button type="button" class="btn btn-secondary">Botão</button>
    <button type="button" class="btn btn-secondary">Botão</button>
    <button type="button" class="btn btn-secondary">Botão</button>
    <button type="button" class="btn btn-secondary">Botão</button>
  </div>
</div>


<div class="bd-example">
  <div class="btn-group-vertical" role="group" aria-label="Grupos de botões vertical">
    <button type="button" class="btn btn-secondary">Botão</button>
    <button type="button" class="btn btn-secondary">Botão</button>
    <div class="btn-group" role="group">
      <button id="btnGroupVerticalDrop1" type="button" class="btn btn-secondary dropdown-toggle" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
        Dropdown
      </button>
      <div class="dropdown-menu" aria-labelledby="btnGroupVerticalDrop1">
        <a class="dropdown-item" href="#">Link dropdown</a>
        <a class="dropdown-item" href="#">Link dropdown</a>
      </div>
    </div>
    <button type="button" class="btn btn-secondary">Botão</button>
    <button type="button" class="btn btn-secondary">Botão</button>
    <div class="btn-group" role="group">
      <button id="btnGroupVerticalDrop2" type="button" class="btn btn-secondary dropdown-toggle" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
        Dropdown
      </button>
      <div class="dropdown-menu" aria-labelledby="btnGroupVerticalDrop2">
        <a class="dropdown-item" href="#">Link dropdown</a>
        <a class="dropdown-item" href="#">Link dropdown</a>
      </div>
    </div>
    <div class="btn-group" role="group">
      <button id="btnGroupVerticalDrop3" type="button" class="btn btn-secondary dropdown-toggle" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
        Dropdown
      </button>
      <div class="dropdown-menu" aria-labelledby="btnGroupVerticalDrop3">
        <a class="dropdown-item" href="#">Link dropdown</a>
        <a class="dropdown-item" href="#">Link dropdown</a>
      </div>
    </div>
    <div class="btn-group" role="group">
      <button id="btnGroupVerticalDrop4" type="button" class="btn btn-secondary dropdown-toggle" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
        Dropdown
      </button>
      <div class="dropdown-menu" aria-labelledby="btnGroupVerticalDrop4">
        <a class="dropdown-item" href="#">Link dropdown</a>
        <a class="dropdown-item" href="#">Link dropdown</a>
      </div>
    </div>
  </div>
</div>

{% highlight html %}
<div class="btn-group-vertical">
  ...
</div>
{% endhighlight %}

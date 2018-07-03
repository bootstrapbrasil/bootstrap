---
layout: docs
title: Grupo de input
description: Facilmente, extenda os controles de formulário com textos, botões, selects personalizados, etc.
group: components
toc: true
---

## Exemplo básico

Coloque um add-on ou botão em qualquer um dos lados de um input. Você também pode colocar um botão em cada lado do input. No entanto, lembre-se de colocar o `<label>` fora do grupo de input.

{% capture example %}
<div class="input-group mb-3">
  <div class="input-group-prepend">
    <span class="input-group-text" id="basic-addon1">@</span>
  </div>
  <input type="text" class="form-control" placeholder="Usuário" aria-label="Usuário" aria-describedby="basic-addon1">
</div>

<div class="input-group mb-3">
  <input type="text" class="form-control" placeholder="Recipiente para nickname" aria-label="Recipiente para nickname" aria-describedby="basic-addon2">
  <div class="input-group-append">
    <span class="input-group-text" id="basic-addon2">@exemplo.com</span>
  </div>
</div>

<label for="basic-url">Sua tão honrada URL</label>
<div class="input-group mb-3">
  <div class="input-group-prepend">
    <span class="input-group-text" id="basic-addon3">https://exemplo.com.br/users/</span>
  </div>
  <input type="text" class="form-control" id="basic-url" aria-describedby="basic-addon3">
</div>

<div class="input-group mb-3">
  <div class="input-group-prepend">
    <span class="input-group-text">R$</span>
  </div>
  <input type="text" class="form-control" aria-label="Quantia">
  <div class="input-group-append">
    <span class="input-group-text">.00</span>
  </div>
</div>

<div class="input-group">
  <div class="input-group-prepend">
    <span class="input-group-text">Addon com textarea</span>
  </div>
  <textarea class="form-control" aria-label="Com textarea"></textarea>
</div>
{% endcapture %}
{% include example.html content=example %}

## Tamanhos

Use as classes de dimensionamento de formulário no `.input-group` e conteúdos dentro dele vão, automaticamente, redimensionar (não é necessário classes de dimensionamento em cada elemento).

**Dimensionamento em elementos individuais do grupo de inputs, não é possível.**

{% capture example %}
<div class="input-group input-group-sm mb-3">
  <div class="input-group-prepend">
    <span class="input-group-text" id="inputGroup-sizing-sm">Pequeno</span>
  </div>
  <input type="text" class="form-control" aria-label="Pequeno" aria-describedby="inputGroup-sizing-sm">
</div>

<div class="input-group mb-3">
  <div class="input-group-prepend">
    <span class="input-group-text" id="inputGroup-sizing-default">Padrão</span>
  </div>
  <input type="text" class="form-control" aria-label="Padrão" aria-describedby="inputGroup-sizing-default">
</div>

<div class="input-group input-group-lg">
  <div class="input-group-prepend">
    <span class="input-group-text" id="inputGroup-sizing-lg">Grande</span>
  </div>
  <input type="text" class="form-control" aria-label="Grande" aria-describedby="inputGroup-sizing-sm">
</div>
{% endcapture %}
{% include example.html content=example %}

## Checkboxes e radios

Coloque qualquer checkbox ou radio dentro do addon de grupo de input, invés de texto.

{% capture example %}
<div class="input-group mb-3">
  <div class="input-group-prepend">
    <div class="input-group-text">
      <input type="checkbox" aria-label="Chebox para permitir input text">
    </div>
  </div>
  <input type="text" class="form-control" aria-label="Input text com checkbox">
</div>

<div class="input-group">
  <div class="input-group-prepend">
    <div class="input-group-text">
    <input type="radio" aria-label="Botão radio para acompanhar input text">
    </div>
  </div>
  <input type="text" class="form-control" aria-label="Input text com botão radio">
</div>
{% endcapture %}
{% include example.html content=example %}

## Múltiplos inputs

Apesar de múltiplos `<input>` serem suportados (visualmente), estilos de validação só estão disponíveis para grupos de input com um único `<input>`.

{% capture example %}
<div class="input-group">
  <div class="input-group-prepend">
    <span class="input-group-text" id="">Nome e sobrenome</span>
  </div>
  <input type="text" class="form-control">
  <input type="text" class="form-control">
</div>
{% endcapture %}
{% include example.html content=example %}

## Múltiplos addons

Múltiplos add-ons são suportados e podem ser misturados com input checkbox e radio.

{% capture example %}
<div class="input-group mb-3">
  <div class="input-group-prepend">
    <span class="input-group-text">R$</span>
    <span class="input-group-text">0.00</span>
  </div>
  <input type="text" class="form-control" aria-label="Quantia">
</div>

<div class="input-group">
  <input type="text" class="form-control" aria-label="Quantia">
  <div class="input-group-append">
    <span class="input-group-text">R$</span>
    <span class="input-group-text">0.00</span>
  </div>
</div>
{% endcapture %}
{% include example.html content=example %}

## Botões addons

{% capture example %}
<div class="input-group mb-3">
  <div class="input-group-prepend">
    <button class="btn btn-outline-secondary" type="button">Botão</button>
  </div>
  <input type="text" class="form-control" placeholder="" aria-label="" aria-describedby="basic-addon1">
</div>

<div class="input-group mb-3">
  <input type="text" class="form-control" placeholder="Recipiente para nickname" aria-label="Recipiente para nickname" aria-describedby="basic-addon2">
  <div class="input-group-append">
    <button class="btn btn-outline-secondary" type="button">Botão</button>
  </div>
</div>

<div class="input-group mb-3">
  <div class="input-group-prepend">
    <button class="btn btn-outline-secondary" type="button">Botão</button>
    <button class="btn btn-outline-secondary" type="button">Botão</button>
  </div>
  <input type="text" class="form-control" placeholder="" aria-label="" aria-describedby="basic-addon1">
</div>

<div class="input-group">
  <input type="text" class="form-control" placeholder="Recipiente para nickname" aria-label="Recipiente para nickname" aria-describedby="basic-addon2">
  <div class="input-group-append">
    <button class="btn btn-outline-secondary" type="button">Botão</button>
    <button class="btn btn-outline-secondary" type="button">Botão</button>
  </div>
</div>
{% endcapture %}
{% include example.html content=example %}

## Botões com dropdowns

{% capture example %}
<div class="input-group mb-3">
  <div class="input-group-prepend">
    <button class="btn btn-outline-secondary dropdown-toggle" type="button" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">Dropdown</button>
    <div class="dropdown-menu">
      <a class="dropdown-item" href="#">Ação</a>
      <a class="dropdown-item" href="#">Outra ação</a>
      <a class="dropdown-item" href="#">Algo mais aqui</a>
      <div role="separator" class="dropdown-divider"></div>
      <a class="dropdown-item" href="#">Link isolado</a>
    </div>
  </div>
  <input type="text" class="form-control" aria-label="Input text com botão dropdown">
</div>

<div class="input-group">
  <input type="text" class="form-control" aria-label="Input text com botão dropdown">
  <div class="input-group-append">
    <button class="btn btn-outline-secondary dropdown-toggle" type="button" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">Dropdown</button>
    <div class="dropdown-menu">
      <a class="dropdown-item" href="#">Ação</a>
      <a class="dropdown-item" href="#">Outra ação</a>
      <a class="dropdown-item" href="#">Algo mais aqui</a>
      <div role="separator" class="dropdown-divider"></div>
      <a class="dropdown-item" href="#">Link isolado</a>
    </div>
  </div>
</div>
{% endcapture %}
{% include example.html content=example %}

## Botões segmentados

{% capture example %}
<div class="input-group mb-3">
  <div class="input-group-prepend">
    <button type="button" class="btn btn-outline-secondary">Ação</button>
    <button type="button" class="btn btn-outline-secondary dropdown-toggle dropdown-toggle-split" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
      <span class="sr-only">Dropdown</span>
    </button>
    <div class="dropdown-menu">
      <a class="dropdown-item" href="#">Ação</a>
      <a class="dropdown-item" href="#">Outra ação</a>
      <a class="dropdown-item" href="#">Algo mais aqui</a>
      <div role="separator" class="dropdown-divider"></div>
      <a class="dropdown-item" href="#">Link isolado</a>
    </div>
  </div>
  <input type="text" class="form-control" aria-label="Input dropdown com botão dropdown segmentado">
</div>

<div class="input-group">
  <input type="text" class="form-control" aria-label="Input dropdown com botão dropdown segmentado">
  <div class="input-group-append">
    <button type="button" class="btn btn-outline-secondary">Ação</button>
    <button type="button" class="btn btn-outline-secondary dropdown-toggle dropdown-toggle-split" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
      <span class="sr-only">Dropdown</span>
    </button>
    <div class="dropdown-menu">
      <a class="dropdown-item" href="#">Ação</a>
      <a class="dropdown-item" href="#">Outra ação</a>
      <a class="dropdown-item" href="#">Algo mais aqui</a>
      <div role="separator" class="dropdown-divider"></div>
      <a class="dropdown-item" href="#">Link isolado</a>
    </div>
  </div>
</div>
{% endcapture %}
{% include example.html content=example %}

## Formulários personalizados

Grupos de input possuem suporte para selects e inputs de arquivos personalizados. As versões padrões de browsers deles não é suportada.

### Select personalizado

{% capture example %}
<div class="input-group mb-3">
  <div class="input-group-prepend">
    <label class="input-group-text" for="inputGroupSelect01">Opções</label>
  </div>
  <select class="custom-select" id="inputGroupSelect01">
    <option selected>Escolher...</option>
    <option value="1">Um</option>
    <option value="2">Dois</option>
    <option value="3">Três</option>
  </select>
</div>

<div class="input-group mb-3">
  <select class="custom-select" id="inputGroupSelect02">
    <option selected>Escolher...</option>
    <option value="1">Um</option>
    <option value="2">Dois</option>
    <option value="3">Três</option>
  </select>
  <div class="input-group-append">
    <label class="input-group-text" for="inputGroupSelect02">Opções</label>
  </div>
</div>

<div class="input-group mb-3">
  <div class="input-group-prepend">
    <button class="btn btn-outline-secondary" type="button">Botão</button>
  </div>
  <select class="custom-select" id="inputGroupSelect03">
    <option selected>Escolher...</option>
    <option value="1">Um</option>
    <option value="2">Dois</option>
    <option value="3">Três</option>
  </select>
</div>

<div class="input-group">
  <select class="custom-select" id="inputGroupSelect04">
    <option selected>Escolher...</option>
    <option value="1">Um</option>
    <option value="2">Dois</option>
    <option value="3">Três</option>
  </select>
  <div class="input-group-append">
    <button class="btn btn-outline-secondary" type="button">Botão</button>
  </div>
</div>
{% endcapture %}
{% include example.html content=example %}

### Input de arquivo personalizado

{% capture example %}
<div class="input-group mb-3">
  <div class="input-group-prepend">
    <span class="input-group-text">Upload</span>
  </div>
  <div class="custom-file">
    <input type="file" class="custom-file-input" id="inputGroupFile01">
    <label class="custom-file-label" for="inputGroupFile01">Escolher arquivo</label>
  </div>
</div>

<div class="input-group mb-3">
  <div class="custom-file">
    <input type="file" class="custom-file-input" id="inputGroupFile02">
    <label class="custom-file-label" for="inputGroupFile02">Escolher arquivo</label>
  </div>
  <div class="input-group-append">
    <span class="input-group-text" id="">Upload</span>
  </div>
</div>

<div class="input-group mb-3">
  <div class="input-group-prepend">
    <button class="btn btn-outline-secondary" type="button">Botão</button>
  </div>
  <div class="custom-file">
    <input type="file" class="custom-file-input" id="inputGroupFile03">
    <label class="custom-file-label" for="inputGroupFile03">Escolher arquivo</label>
  </div>
</div>

<div class="input-group">
  <div class="custom-file">
    <input type="file" class="custom-file-input" id="inputGroupFile04">
    <label class="custom-file-label" for="inputGroupFile04">Escolher arquivo</label>
  </div>
  <div class="input-group-append">
    <button class="btn btn-outline-secondary" type="button">Botão</button>
  </div>
</div>
{% endcapture %}
{% include example.html content=example %}

## Acessibilidade

Leitores de telas vão ter problemas com seus formulários se você não incluir um `<label>` para cada input. Para estes grupos de input, se assegure de que qualquer label ou funcionalidade extra seja percebida pelas tecnologias assistivas.

A melhor técnica (elementos `<label>` escondidos usando a classe `.sr-only` ou o uso dos atributos `aria-label` e `aria-labelledby`, possivelmente, acompanhados do `aria-describedby`) e informação a ser transmitida vai variar, dependendo do tipo de interface que você está implementando. Os exemplos, nesta seção, dão algumas sugestões, para casos diferentes.

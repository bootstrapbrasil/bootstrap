---
layout: docs
title: Formulários
description: Exemplos, instruções para estilizar campos de formulários, opções de layout e componentes personalizados para criar uma grande variedade de formulários.
group: components
toc: true
---

## Visão geral

Campos de formulários Bootstrap extendem os [estilos herdados do Reboot]({{ site.baseurl }}/docs/{{ site.docs_version }}/content/reboot/#forms), graças a classes. Use estas classes para conseguir uma exibição personalizada e, portanto, uma renderização nos browsers e dispositivos, mais consistentes.

Se assegure de usar um atributo `type` adequado em todos inputs (`email` em campos de email, por exemplo) para conseguir se aproveitar dos novos inputs, como seletores de números, verificadores de emails, etc.

Aqui está um rápido exemplo para demonstrar os estilos de formulário Bootstrap. Continue lendo a documentação para descobrir sobre classes obrigatórias, layout de formulários e muito mais.

{% capture example %}
<form>
  <div class="form-group">
    <label for="exampleInputEmail1">Endereço de email</label>
    <input type="email" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp" placeholder="Seu email">
    <small id="emailHelp" class="form-text text-muted">Nunca vamos compartilhar seu email, com ninguém.</small>
  </div>
  <div class="form-group">
    <label for="exampleInputPassword1">Senha</label>
    <input type="password" class="form-control" id="exampleInputPassword1" placeholder="Senha">
  </div>
  <div class="form-group form-check">
    <input type="checkbox" class="form-check-input" id="exampleCheck1">
    <label class="form-check-label" for="exampleCheck1">Clique em mim</label>
  </div>
  <button type="submit" class="btn btn-primary">Enviar</button>
</form>
{% endcapture %}
{% include example.html content=example %}

## Campos de formulário

Campos de formulário textuais como `<input>`, `<select>` e `<textarea>` são estilizados com a classe `.form-control`. Ela possui estilos para aparência, estado de foco e muito mais.

Tenha certeza de explorar nossos [formulários personalizados](#custom-forms) para estilos de `<select>`.

{% capture example %}
<form>
  <div class="form-group">
    <label for="exampleFormControlInput1">Endereço de email</label>
    <input type="email" class="form-control" id="exampleFormControlInput1" placeholder="nome@exemplo.com">
  </div>
  <div class="form-group">
    <label for="exampleFormControlSelect1">Select de exemplo</label>
    <select class="form-control" id="exampleFormControlSelect1">
      <option>1</option>
      <option>2</option>
      <option>3</option>
      <option>4</option>
      <option>5</option>
    </select>
  </div>
  <div class="form-group">
    <label for="exampleFormControlSelect2">Exemplo de select múltiplo</label>
    <select multiple class="form-control" id="exampleFormControlSelect2">
      <option>1</option>
      <option>2</option>
      <option>3</option>
      <option>4</option>
      <option>5</option>
    </select>
  </div>
  <div class="form-group">
    <label for="exampleFormControlTextarea1">Exemplo de textarea</label>
    <textarea class="form-control" id="exampleFormControlTextarea1" rows="3"></textarea>
  </div>
</form>
{% endcapture %}
{% include example.html content=example %}

Para inputs de arquivo, troque o `.form-control` por `.form-control-file`.

{% capture example %}
<form>
  <div class="form-group">
    <label for="exampleFormControlFile1">Exemplo de input de arquivo</label>
    <input type="file" class="form-control-file" id="exampleFormControlFile1">
  </div>
</form>
{% endcapture %}
{% include example.html content=example %}

### Tamanhos

Defina alturas, usando classes como `.form-control-lg` e `.form-control-sm`.

{% capture example %}
<input class="form-control form-control-lg" type="text" placeholder=".form-control-lg">
<input class="form-control" type="text" placeholder="Input padrão">
<input class="form-control form-control-sm" type="text" placeholder=".form-control-sm">
{% endcapture %}
{% include example.html content=example %}

{% capture example %}
<select class="form-control form-control-lg">
  <option>Select grande</option>
</select>
<select class="form-control">
  <option>Select padrão</option>
</select>
<select class="form-control form-control-sm">
  <option>Select pequeno</option>
</select>
{% endcapture %}
{% include example.html content=example %}

### Input só de leitura

Use o atributo booleano `readonly` em um input para evitar alterações no valor dele. Inputs `readonly` são mais esmaecidos (como os desativados), mas preservam o cursor padrão.

{% capture example %}
<input class="form-control" type="text" placeholder="Input só de leitura, aqui..." readonly>
{% endcapture %}
{% include example.html content=example %}

### Input só de leitura em texto

Se você quiser elementos `<input readonly>` em seu formuláro, mas no estilo de texto, use a classe `.form-control-plaintext` para remover os estilos padrões do campo, preservando margem e padding.

{% capture example %}
<form>
  <div class="form-group row">
    <label for="staticEmail" class="col-sm-2 col-form-label">Email</label>
    <div class="col-sm-10">
      <input type="text" readonly class="form-control-plaintext" id="staticEmail" value="email@exemplo.com">
    </div>
  </div>
  <div class="form-group row">
    <label for="inputPassword" class="col-sm-2 col-form-label">Senha</label>
    <div class="col-sm-10">
      <input type="password" class="form-control" id="inputPassword" placeholder="Senha">
    </div>
  </div>
</form>
{% endcapture %}
{% include example.html content=example %}

{% capture example %}
<form class="form-inline">
  <div class="form-group mb-2">
    <label for="staticEmail2" class="sr-only">Email</label>
    <input type="text" readonly class="form-control-plaintext" id="staticEmail2" value="email@exemplo.com">
  </div>
  <div class="form-group mx-sm-3 mb-2">
    <label for="inputPassword2" class="sr-only">Senha</label>
    <input type="password" class="form-control" id="inputPassword2" placeholder="Senha">
  </div>
  <button type="submit" class="btn btn-primary mb-2">Confirmar identidade</button>
</form>
{% endcapture %}
{% include example.html content=example %}

## Inputs range

Crie um input range, usando `.form-control-range`.

{% capture example %}
<form>
  <div class="form-group">
    <label for="formControlRange">Exemplo de input range</label>
    <input type="range" class="form-control-range" id="formControlRange">
  </div>
</form>
{% endcapture %}
{% include example.html content=example %}

## Checkboxes e radios

Checkboxes e radios padrões são aprimorados com ajuda da `.form-check`, **uma classe para os dois tipos de input que melhora o layout e comportamento de seus elementos HTML**. Checkboxes são para selecionar várias opções em uma lista, enquanto radios são para selecionar uma em muitas.

Checkboxes e radios desativados são suportados, mas para se ter um cursor `not-allowed` quando passá-lo sobre o `<label>` pai, você precisará adicionar o atributo `disabled` no elemento com `.form-check-input`. O atributo disabled vai aplicar um cor mais clara para indicar o estado do input.

Checkboxes e radios são feitos para terem suporte a validação de formulário HTML e prover labels consisos e acessíveis. Assim, nossos `<input>` e `<label>` são elementos irmãos, diferente de um `<input>` dentro de uma `<label>`. Isso é um pouco mais massante, já que você precisa especificar atributos `id` e `for` para vincular o `<input>` a `<label>`.

### Padrão (empilhados)

Por padrão, qualquer número de checkboxes e radios, que são irmãos imediatos, vão se empilhar e receber espaçamento apropriado com a classe `.form-check`.

{% capture example %}
<div class="form-check">
  <input class="form-check-input" type="checkbox" value="" id="defaultCheck1">
  <label class="form-check-label" for="defaultCheck1">
    Checkbox padrão
  </label>
</div>
<div class="form-check">
  <input class="form-check-input" type="checkbox" value="" id="defaultCheck2" disabled>
  <label class="form-check-label" for="defaultCheck2">
    Checkbox desativado
  </label>
</div>
{% endcapture %}
{% include example.html content=example %}

{% capture example %}
<div class="form-check">
  <input class="form-check-input" type="radio" name="exampleRadios" id="exampleRadios1" value="opcao1" checked>
  <label class="form-check-label" for="exampleRadios1">
    Radio padrão
  </label>
</div>
<div class="form-check">
  <input class="form-check-input" type="radio" name="exampleRadios" id="exampleRadios2" value="opcao2">
  <label class="form-check-label" for="exampleRadios2">
    Segundo radio padrão
  </label>
</div>
<div class="form-check">
  <input class="form-check-input" type="radio" name="exampleRadios" id="exampleRadios3" value="option3" disabled>
  <label class="form-check-label" for="exampleRadios3">
    Radio desativado
  </label>
</div>
{% endcapture %}
{% include example.html content=example %}

### Inline

Crie grupos de checkboxes ou radios, na mesma linha horizontal, usando `.form-check-inline` em qualquer `.form-check`.

{% capture example %}
<div class="form-check form-check-inline">
  <input class="form-check-input" type="checkbox" id="inlineCheckbox1" value="opcao1">
  <label class="form-check-label" for="inlineCheckbox1">1</label>
</div>
<div class="form-check form-check-inline">
  <input class="form-check-input" type="checkbox" id="inlineCheckbox2" value="opcao2">
  <label class="form-check-label" for="inlineCheckbox2">2</label>
</div>
<div class="form-check form-check-inline">
  <input class="form-check-input" type="checkbox" id="inlineCheckbox3" value="opcao3" disabled>
  <label class="form-check-label" for="inlineCheckbox3">3 (desativado)</label>
</div>
{% endcapture %}
{% include example.html content=example %}

{% capture example %}
<div class="form-check form-check-inline">
  <input class="form-check-input" type="radio" name="inlineRadioOptions" id="inlineRadio1" value="opcao1">
  <label class="form-check-label" for="inlineRadio1">1</label>
</div>
<div class="form-check form-check-inline">
  <input class="form-check-input" type="radio" name="inlineRadioOptions" id="inlineRadio2" value="opcao2">
  <label class="form-check-label" for="inlineRadio2">2</label>
</div>
<div class="form-check form-check-inline">
  <input class="form-check-input" type="radio" name="inlineRadioOptions" id="inlineRadio3" value="opcao3" disabled>
  <label class="form-check-label" for="inlineRadio3">3 (desativado)</label>
</div>
{% endcapture %}
{% include example.html content=example %}

### Sem labels

Use `.position-static` em inputs dentro de `.form-check`, os quais não possuem qualquer texto de label. Lembre-se de, ainda assim, criar algum tipo de label para tecnologias assistivas (usando `aria-label`, por exemplo).

{% capture example %}
<div class="form-check">
  <input class="form-check-input position-static" type="checkbox" id="blankCheckbox" value="opcao1" aria-label="...">
</div>
<div class="form-check">
  <input class="form-check-input position-static" type="radio" name="blankRadio" id="blankRadio1" value="opcao1" aria-label="...">
</div>
{% endcapture %}
{% include example.html content=example %}

## Layout

Já que Bootstrap aplica `display: block` e `width: 100%` em quase todos campos de formulários, eles vão se empilhar, por padrão. Classes adicionais podem ser usadas para variar este layout.

### Grupos de formulários

A classe `.form-group` é o jeito mais fácil de adicionar alguma estrutura aos formulários. Ela cria uma base para o agrupamento apropriado de labels, controles, textos de ajuda e mensagens de validação de formulário. Por padrão, ela só aplica `margin-bottom`, mas usa alguns estilos adicionais de `form-inline`, sempre que necessário. Use-a em `<fieldset>`, `<div>` ou quase qualquer outro elemento.

{% capture example %}
<form>
  <div class="form-group">
    <label for="formGroupExampleInput">Label exemplo</label>
    <input type="text" class="form-control" id="formGroupExampleInput" placeholder="Input exemplo">
  </div>
  <div class="form-group">
    <label for="formGroupExampleInput2">Outra label</label>
    <input type="text" class="form-control" id="formGroupExampleInput2" placeholder="Outro input">
  </div>
</form>
{% endcapture %}
{% include example.html content=example %}

### Grid de formulário

Formulários mais complexos podem ser feitos usando classes do grid. Use-as para fazer layouts de formulários que precisam de várias colunas, larguras e outras opções de alinhamento.

{% capture example %}
<form>
  <div class="row">
    <div class="col">
      <input type="text" class="form-control" placeholder="Nome">
    </div>
    <div class="col">
      <input type="text" class="form-control" placeholder="Sobrenome">
    </div>
  </div>
</form>
{% endcapture %}
{% include example.html content=example %}

#### Form row

Você também pode trocar `.row` por `.form-row`, uma variação de nosso grid row padrão, a qual sobrescreve as gutters padrões das colunas para conseguir layouts mais compactos.

{% capture example %}
<form>
  <div class="form-row">
    <div class="col">
      <input type="text" class="form-control" placeholder="Nome">
    </div>
    <div class="col">
      <input type="text" class="form-control" placeholder="Sobrenome">
    </div>
  </div>
</form>
{% endcapture %}
{% include example.html content=example %}

Layouts mais complexos também podem ser criados com o sistema grid.

{% capture example %}
<form>
  <div class="form-row">
    <div class="form-group col-md-6">
      <label for="inputEmail4">Email</label>
      <input type="email" class="form-control" id="inputEmail4" placeholder="Email">
    </div>
    <div class="form-group col-md-6">
      <label for="inputPassword4">Senha</label>
      <input type="password" class="form-control" id="inputPassword4" placeholder="Senha">
    </div>
  </div>
  <div class="form-group">
    <label for="inputAddress">Endereço</label>
    <input type="text" class="form-control" id="inputAddress" placeholder="Rua dos Bobos, nº 0">
  </div>
  <div class="form-group">
    <label for="inputAddress2">Endereço 2</label>
    <input type="text" class="form-control" id="inputAddress2" placeholder="Apartamento, hotel, casa, etc.">
  </div>
  <div class="form-row">
    <div class="form-group col-md-6">
      <label for="inputCity">Cidade</label>
      <input type="text" class="form-control" id="inputCity">
    </div>
    <div class="form-group col-md-4">
      <label for="inputEstado">Estado</label>
      <select id="inputEstado" class="form-control">
        <option selected>Escolher...</option>
        <option>...</option>
      </select>
    </div>
    <div class="form-group col-md-2">
      <label for="inputCEP">CEP</label>
      <input type="text" class="form-control" id="inputCEP">
    </div>
  </div>
  <div class="form-group">
    <div class="form-check">
      <input class="form-check-input" type="checkbox" id="gridCheck">
      <label class="form-check-label" for="gridCheck">
        Clique em mim
      </label>
    </div>
  </div>
  <button type="submit" class="btn btn-primary">Entrar</button>
</form>
{% endcapture %}
{% include example.html content=example %}

#### Formulário horizontal

Crie formulários horizontais com o grid, usando a classe `.row` em grupos de formulários e as classes `.col-*-*` para especificar a largura de seus labels e controles. Também, se assegure de usar `.col-form-label` no seu `<label>`, para que ele se centralize verticalmente com seus campos de formulário.

As vezes, você pode precisar usar utilitários de margem ou padding para criar o alinhamento perfeito que precisa. Por exemplo, nós removemos `padding-top` em nossos inputs radios empilhados para melhorar o alinhamento da baseline do texto.

{% capture example %}
<form>
  <div class="form-group row">
    <label for="inputEmail3" class="col-sm-2 col-form-label">Email</label>
    <div class="col-sm-10">
      <input type="email" class="form-control" id="inputEmail3" placeholder="Email">
    </div>
  </div>
  <div class="form-group row">
    <label for="inputPassword3" class="col-sm-2 col-form-label">Senha</label>
    <div class="col-sm-10">
      <input type="password" class="form-control" id="inputPassword3" placeholder="Senha">
    </div>
  </div>
  <fieldset class="form-group">
    <div class="row">
      <legend class="col-form-label col-sm-2 pt-0">Radios</legend>
      <div class="col-sm-10">
        <div class="form-check">
          <input class="form-check-input" type="radio" name="gridRadios" id="gridRadios1" value="opcao1" checked>
          <label class="form-check-label" for="gridRadios1">
            Primeiro radio
          </label>
        </div>
        <div class="form-check">
          <input class="form-check-input" type="radio" name="gridRadios" id="gridRadios2" value="opcao2">
          <label class="form-check-label" for="gridRadios2">
            Segundo radio
          </label>
        </div>
        <div class="form-check disabled">
          <input class="form-check-input" type="radio" name="gridRadios" id="gridRadios3" value="opcao3" disabled>
          <label class="form-check-label" for="gridRadios3">
            Terceiro radio desativado
          </label>
        </div>
      </div>
    </div>
  </fieldset>
  <div class="form-group row">
    <div class="col-sm-2">Checkbox</div>
    <div class="col-sm-10">
      <div class="form-check">
        <input class="form-check-input" type="checkbox" id="gridCheck1">
        <label class="form-check-label" for="gridCheck1">
          Checkbox exemplo
        </label>
      </div>
    </div>
  </div>
  <div class="form-group row">
    <div class="col-sm-10">
      <button type="submit" class="btn btn-primary">Entrar</button>
    </div>
  </div>
</form>
{% endcapture %}
{% include example.html content=example %}

##### Dimensionamento horizontal de labels

Tenha certeza de usar `.col-form-label-sm` ou `.col-form-label-lg` em um `<label>` ou `<legend>` para, adequadamente, seguir o tamanho de `.form-control-lg` e `.form-control-sm`.

{% capture example %}
<form>
  <div class="form-group row">
    <label for="colFormLabelSm" class="col-sm-2 col-form-label col-form-label-sm">Email</label>
    <div class="col-sm-10">
      <input type="email" class="form-control form-control-sm" id="colFormLabelSm" placeholder="col-form-label-sm">
    </div>
  </div>
  <div class="form-group row">
    <label for="colFormLabel" class="col-sm-2 col-form-label">Email</label>
    <div class="col-sm-10">
      <input type="email" class="form-control" id="colFormLabel" placeholder="col-form-label">
    </div>
  </div>
  <div class="form-group row">
    <label for="colFormLabelLg" class="col-sm-2 col-form-label col-form-label-lg">Email</label>
    <div class="col-sm-10">
      <input type="email" class="form-control form-control-lg" id="colFormLabelLg" placeholder="col-form-label-lg">
    </div>
  </div>
</form>
{% endcapture %}
{% include example.html content=example %}

#### Tamanho de colunas

Como mostrado nos exemplos anteriores, nosso sistema de grid permite que você use qualquer número de `.col`, dentro de um `.row` ou `.form-row`. Elas vão dividir a largura disponível, igualmente, entre si. Você também pode escolher se um subconjunto de colunas pode tomar mais ou menos espaço, enquanto as `.col` restantes dividem o resto do espaço, usando classes de colunas como `.col-7`.

{% capture example %}
<form>
  <div class="form-row">
    <div class="col-7">
      <input type="text" class="form-control" placeholder="Cidade">
    </div>
    <div class="col">
      <input type="text" class="form-control" placeholder="Estado">
    </div>
    <div class="col">
      <input type="text" class="form-control" placeholder="CEP">
    </div>
  </div>
</form>
{% endcapture %}
{% include example.html content=example %}

#### Auto dimensionamento

O exemplo abaixo usa utilitário flexbox para centralizar verticalmente os conteúdos e troca `.col` por `.col-auto` para que suas colunas só usem o espaço necessário. Em outras palavras, a coluna vai crescer sozinha, baseando-se no tamanho de seus conteúdos.

{% capture example %}
<form>
  <div class="form-row align-items-center">
    <div class="col-auto">
      <label class="sr-only" for="inlineFormInput">Nome</label>
      <input type="text" class="form-control mb-2" id="inlineFormInput" placeholder="Fulano">
    </div>
    <div class="col-auto">
      <label class="sr-only" for="inlineFormInputGroup">Usuário</label>
      <div class="input-group mb-2">
        <div class="input-group-prepend">
          <div class="input-group-text">@</div>
        </div>
        <input type="text" class="form-control" id="inlineFormInputGroup" placeholder="Usuário">
      </div>
    </div>
    <div class="col-auto">
      <div class="form-check mb-2">
        <input class="form-check-input" type="checkbox" id="autoSizingCheck">
        <label class="form-check-label" for="autoSizingCheck">
          Lembrar de mim
        </label>
      </div>
    </div>
    <div class="col-auto">
      <button type="submit" class="btn btn-primary mb-2">Enviar</button>
    </div>
  </div>
</form>
{% endcapture %}
{% include example.html content=example %}

Você também pode repetir isso, mas com classes de colunas de tamanhos específicos.

{% capture example %}
<form>
  <div class="form-row align-items-center">
    <div class="col-sm-3 my-1">
      <label class="sr-only" for="inlineFormInputName">Nome</label>
      <input type="text" class="form-control" id="inlineFormInputName" placeholder="Fulano">
    </div>
    <div class="col-sm-3 my-1">
      <label class="sr-only" for="inlineFormInputGroupUsername">Usuário</label>
      <div class="input-group">
        <div class="input-group-prepend">
          <div class="input-group-text">@</div>
        </div>
        <input type="text" class="form-control" id="inlineFormInputGroupUsername" placeholder="Usuário">
      </div>
    </div>
    <div class="col-auto my-1">
      <div class="form-check">
        <input class="form-check-input" type="checkbox" id="autoSizingCheck2">
        <label class="form-check-label" for="autoSizingCheck2">
          Lembrar de mim
        </label>
      </div>
    </div>
    <div class="col-auto my-1">
      <button type="submit" class="btn btn-primary">Enviar</button>
    </div>
  </div>
</form>
{% endcapture %}
{% include example.html content=example %}

E, é claro, [campos de formulário personalizados](#custom-forms) são suportados.

{% capture example %}
<form>
  <div class="form-row align-items-center">
    <div class="col-auto my-1">
      <label class="mr-sm-2 sr-only" for="inlineFormCustomSelect">Preferência</label>
      <select class="custom-select mr-sm-2" id="inlineFormCustomSelect">
        <option selected>Escolher...</option>
        <option value="1">Um</option>
        <option value="2">Dois</option>
        <option value="3">Três</option>
      </select>
    </div>
    <div class="col-auto my-1">
      <div class="custom-control custom-checkbox mr-sm-2">
        <input type="checkbox" class="custom-control-input" id="customControlAutosizing">
        <label class="custom-control-label" for="customControlAutosizing">Lembrar preferências</label>
      </div>
    </div>
    <div class="col-auto my-1">
      <button type="submit" class="btn btn-primary">Enviar</button>
    </div>
  </div>
</form>
{% endcapture %}
{% include example.html content=example %}

### formulários inline

Use a classe `.form-inline` pora mostrar vários labels, controles e botões, em uma única linha. Campos dentro de formulários inline são um pouco diferente de seus estados padrões.

- Controles usam `display: flex`, colapsando qualquer espaço HTML em branco e permitindo que você tenha controle de alinhamento com utilitários de [espaçamento]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/spacing/) e [flexbox]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/flex/);
- Grupos de controles e inputs recebem `width: auto` para sobrescrever o padrão do Bootstrap `width: 100%`;
- Controles **só aparecem inline em viewports que possuem, pelo menos, 576px de largura**, levando em conta viewports estreitas em dispositivos móveis.

Você pode precisar definir a largura e alinhamento individual dos campos, usando [utilitários de espaçamento]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/spacing/) (como mostrado abaixo). Por último, se assegure de sempre usar uma `<label>` em cada controle, mesmo se você precisar escondê-lo de usuários sem leitores de telas, usando `.sr-only`.

{% capture example %}
<form class="form-inline">
  <label class="sr-only" for="inlineFormInputName2">Nome</label>
  <input type="text" class="form-control mb-2 mr-sm-2" id="inlineFormInputName2" placeholder="Fulano">

  <label class="sr-only" for="inlineFormInputGroupUsername2">Usuário</label>
  <div class="input-group mb-2 mr-sm-2">
    <div class="input-group-prepend">
      <div class="input-group-text">@</div>
    </div>
    <input type="text" class="form-control" id="inlineFormInputGroupUsername2" placeholder="Usuário">
  </div>

  <div class="form-check mb-2 mr-sm-2">
    <input class="form-check-input" type="checkbox" id="inlineFormCheck">
    <label class="form-check-label" for="inlineFormCheck">
      Lembrar de mim
    </label>
  </div>

  <button type="submit" class="btn btn-primary mb-2">Enviar</button>
</form>
{% endcapture %}
{% include example.html content=example %}

Controles de formuários e selects personalizados são suportados, também.

{% capture example %}
<form class="form-inline">
  <label class="my-1 mr-2" for="inlineFormCustomSelectPref">Preferência</label>
  <select class="custom-select my-1 mr-sm-2" id="inlineFormCustomSelectPref">
    <option selected>Escolher...</option>
    <option value="1">Um</option>
    <option value="2">Dois</option>
    <option value="3">Três</option>
  </select>

  <div class="custom-control custom-checkbox my-1 mr-sm-2">
    <input type="checkbox" class="custom-control-input" id="customControlInline">
    <label class="custom-control-label" for="customControlInline">Lembrar preferências</label>
  </div>

  <button type="submit" class="btn btn-primary my-1">Enviar</button>
</form>
{% endcapture %}
{% include example.html content=example %}

{% capture callout %}
##### Opções para esconder labels

Tecnologias assistivas como leitores de telas sempre vão ter problemas nos formulários, se você não colocar um label em cada input. Nesses formulários inline, você pode esconder as labels usando a classe `.sr-only`. Também há outros métodos de criar uma label para tecnologias assistivas, como os atributos `aria-label`, `aria-labelledby` e `title`. Se nenhum deles é usado, tecnologias assistivas podem recorrer ao atributo `placeholder` (se existir), mas perceba que o uso de `placeholder` como substituto não é aconselhável, nesses casos.
{% endcapture %}
{% include callout.html content=callout type="warning" %}

## Texto de ajuda

Textos de ajuda block-level em formulários podem ser criado usando `.form-text` (anteriormente, conhecido como `.help-block`, na v3). Textos de ajuda inline podem ser implementados, sem problemas, usando qualquer elemento HTML inline e classes utilitárias como `.text-muted`.

{% capture callout %}
##### Associando textos de ajuda com campos de formulário

Textos de ajuda devem ser, explicitamente, associados aos campos de formulário que eles remetem, usando o atributo `aria-describedby`. Isso vai garantir que tecnologias assistivas (como leitores de telas) mostrem esse texto de ajuda, quando o usuário foca ou entra no campo.
{% endcapture %}
{% include callout.html content=callout type="warning" %}

Textos de ajuda abaixo podem ser estilizados com `.form-text`. Essa classe possui `display: block` e adiciona alguma margem no topo para fácil distanciamento dos inputs acima.

{% capture example %}
<label for="inputPassword5">Senha</label>
<input type="password" id="inputPassword5" class="form-control" aria-describedby="passwordHelpBlock">
<small id="passwordHelpBlock" class="form-text text-muted">
  Sua senha deve ter entre 8 e 20 caracteres, os quais devem ser letras e números, sem espaços, caracteres especiais ou emojis.
</small>
{% endcapture %}
{% include example.html content=example %}

Textos inline devem usar qualquer elemento HTML inline, seja `<small>`, `<span>` ou qualquer outra coisa, além de classes utilitárias.

{% capture example %}
<form class="form-inline">
  <div class="form-group">
    <label for="inputPassword6">Senha</label>
    <input type="password" id="inputPassword6" class="form-control mx-sm-3" aria-describedby="passwordHelpInline">
    <small id="passwordHelpInline" class="text-muted">
      Deve ter entre 8 e 20 caracteres.
    </small>
  </div>
</form>
{% endcapture %}
{% include example.html content=example %}

## Desativar formulários

Use o atributo booleano `disabled` em um input para evitar interações e fazê-lo parecer mais esmaecido.

{% highlight html %}
<input class="form-control" id="disabledInput" type="text" placeholder="Input desativado..." disabled>
{% endhighlight %}

Use o atributo `disabled` em um `<fieldset>` para desativar todos os campos dentro dele.

{% capture example %}
<form>
  <fieldset disabled>
    <div class="form-group">
      <label for="disabledTextInput">Input desativado</label>
      <input type="text" id="disabledTextInput" class="form-control" placeholder="Input desativado">
    </div>
    <div class="form-group">
      <label for="disabledSelect">Menu select desativado</label>
      <select id="disabledSelect" class="form-control">
        <option>Select desativado</option>
      </select>
    </div>
    <div class="form-check">
      <input class="form-check-input" type="checkbox" id="disabledFieldsetCheck" disabled>
      <label class="form-check-label" for="disabledFieldsetCheck">
        Não é possível clicar aqui
      </label>
    </div>
    <button type="submit" class="btn btn-primary">Enviar</button>
  </fieldset>
</form>
{% endcapture %}
{% include example.html content=example %}

{% capture callout %}
##### Probleminha com âncoras

Por padrão, navegadores vão tratar todo campo de formulário nativo (`<input>`, `<select>` e `<button>`), dentro de um `<fieldset disabled>`, como desativado. Dessa maneira, não será possível haver interação de teclado ou mouse, neles. No entanto, se seu formulário também possui elementos `<a ... class="btn btn-*">`, estes só vão receber o estilo `pointer-events: none`. Como falado na seção sobre [estado desativado de botões]({{ site.baseurl }}/docs/{{ site.docs_version }}/components/buttons/#disabled-state) (e na sub-seção de elementos âncoras, especialmente), esta propriedade CSS ainda não foi padronizada e não é suportada, totalmente, no Internet Explorer 10, além não evitar que usuários de teclado de serem capazes de ativarem estes links. Portanto, para ter segurança, use JavaScript personalizado  para desativar tais links.
{% endcapture %}
{% include callout.html content=callout type="warning" %}

{% capture callout %}
#### Compatibilidade cross-browser

Apesar do Bootstrap aplicar estes estilos em todos os browsers, Internet Explorer 11 e versões anteriores não vão suportar o atributo `disabled` em `<fieldset>`, totalmente. Use JavaScript personalizado para desativar o fieldset, nesses browsers.
{% endcapture %}
{% include callout.html content=callout type="danger" %}

## Validação

Dê um feedback significativo e acionável aos seus usuários, usando validação de formulário HTML5 ([disponível em todos os nossos browsers suportados](https://caniuse.com/#feat=form-validation)). Escolha entre o feedback de validação padrão do browser ou implemente mensagens personalizadas com nossas classes integradas e JavaScript.

{% capture callout %}
Atualmente, recomendamos usar estilos de validação personalizados, já que mensagens de validação padrões não são, totalmente, expostas a tecnologias assistivas, em todos browsers (no Chrome desktop e mobile, mais notavelmente).
{% endcapture %}
{% include callout.html content=callout type="warning" %}

### Como funciona

Aqui está como validação de formulário funciona, usando Bootstrap:

- A validação de formulário HTML é aplicada usando duas pseudo-classes CSS: `:invalid` e `:valid`;
  - Ela é aplicada em `<input>`, `<select>` e `<textarea>`.
- Bootstrap limita o scopo de `:invalid` e `:valid` a classe pai `.was-validated`, usualmente, aplicada no `<form>`;
  - Caso contrário, qualquer campo obrigatório sem um valor será mostrado como inválido, ao carregar a página;
  - Assim, você pode escolher quando ativá-los (tipicamente, depois do envio de formulário).
- Para resetar a aparência do formulário (no caso de envio de dados dinâmico, via AJAX, por exemplo), remova a classe `.was-validated` do `<form>`, depois de cada envio;
- Como um fallback, as classes `is-invalid` e `.is-valid` podem ser usadas, invés das pseudo-classes para [validação server side](#server-side);
  - Não exigem uma classe pai `.was-validated`.
- Devido as limitações do CSS, não podemos (no momento) aplicar estilos em uma `<label>` que venha antes de um campo de formulário (no DOM), sem a ajuda de JavaScript;
- Todos browsers modernos suportam a [constraint validation API](https://www.w3.org/TR/html5/sec-forms.html#the-constraint-validation-api), uma série de métodos JavaScript para validar campos de formulário;
- Mensagens de feedback podem usar os [padrões do browser](#browser-defaults) (diferente em cada e não estilizável, via CSS) ou nossos estilos de feedback personalizados, com HTML e CSS extra;
- Você pode prover mensagens de validação personalizadas com `setCustomValidity`, no JavaScript.

Com isso em mente, preste atenção nas seguintes demonstrações de nossos estilos de validação de formulários personalizados, classes server-side opcionais e padrões dos browsers.

### Estilos personalizados

Para mensagens de validação Bootstrap personalizadas, você precisará colocar o atributo booleano `novalidate` em seu `<form>`. Isso desativa as dicas padrões do browser, mas continua tendo acesso as APIs de validação de formulário, no JavaScript. Tente enviar o formulário abaixo e veja que nosso JavaScript irá interceptar o botão "Enviar" e retornar um feedback a você. Quando tentando enviar o formulário, verá os estilos `:invalid` e `:valid` aplicados em seus campos de formulário.

Estilos de feedback customizados aplicam cores, bordas, estilos de foco e ícones de background personalizados, para melhor transmitir o feedback. Ícones de background para `<select>`s só estão disponíveis com `.custom-select` e não `form-control`.

{% capture example %}
<form class="needs-validation" novalidate>
  <div class="form-row">
    <div class="col-md-4 mb-3">
      <label for="validationCustom01">Primeiro nome</label>
      <input type="text" class="form-control" id="validationCustom01" placeholder="Nome" value="Mark" required>
      <div class="valid-feedback">
        Tudo certo!
      </div>
    </div>
    <div class="col-md-4 mb-3">
      <label for="validationCustom02">Sobrenome</label>
      <input type="text" class="form-control" id="validationCustom02" placeholder="Sobrenome" value="Otto" required>
      <div class="valid-feedback">
        Tudo certo!
      </div>
    </div>
    <div class="col-md-4 mb-3">
      <label for="validationCustomUsername">Usuário</label>
      <div class="input-group">
        <div class="input-group-prepend">
          <span class="input-group-text" id="inputGroupPrepend">@</span>
        </div>
        <input type="text" class="form-control" id="validationCustomUsername" placeholder="Usuário" aria-describedby="inputGroupPrepend" required>
        <div class="invalid-feedback">
          Por favor, escolha um nome de usuário.
        </div>
      </div>
    </div>
  </div>
  <div class="form-row">
    <div class="col-md-6 mb-3">
      <label for="validationCustom03">Cidade</label>
      <input type="text" class="form-control" id="validationCustom03" placeholder="Cidade" required>
      <div class="invalid-feedback">
        Por favor, informe uma cidade válida.
      </div>
    </div>
    <div class="col-md-3 mb-3">
      <label for="validationCustom04">Estado</label>
      <input type="text" class="form-control" id="validationCustom04" placeholder="Estado" required>
      <div class="invalid-feedback">
        Por favor, informe um estado válido.
      </div>
    </div>
    <div class="col-md-3 mb-3">
      <label for="validationCustom05">CEP</label>
      <input type="text" class="form-control" id="validationCustom05" placeholder="CEP" required>
      <div class="invalid-feedback">
        Por favor, informe um CEP válido.
      </div>
    </div>
  </div>
  <div class="form-group">
    <div class="form-check">
      <input class="form-check-input" type="checkbox" value="" id="invalidCheck" required>
      <label class="form-check-label" for="invalidCheck">
        Concordo com os termos e condições
      </label>
      <div class="invalid-feedback">
        Você deve concordar, antes de continuar.
      </div>
    </div>
  </div>
  <button class="btn btn-primary" type="submit">Enviar</button>
</form>

<script>
// Exemplo de JavaScript inicial para desativar envios de formulário, se houver campos inválidos.
(function() {
  'use strict';
  window.addEventListener('load', function() {
    // Pega todos os formulários que nós queremos aplicar estilos de validação Bootstrap personalizados.
    var forms = document.getElementsByClassName('needs-validation');
    // Faz um loop neles e evita o envio
    var validation = Array.prototype.filter.call(forms, function(form) {
      form.addEventListener('submit', function(event) {
        if (form.checkValidity() === false) {
          event.preventDefault();
          event.stopPropagation();
        }
        form.classList.add('was-validated');
      }, false);
    });
  }, false);
})();
</script>
{% endcapture %}
{% include example.html content=example %}

### Padrões dos browsers

Não tem interesse em feedback de validação personalizado ou em escrever JavaScript para mudar os comportamentos do formulário? Tudo bem! Use os padrões dos navegadores.

Tente enviar o formulário abaixo. Dependendo do seu browser e SO, verá um estilo de feedback pouco diferente.

Apesar destes estilos não poderem serem estilizados com CSS, você ainda pode personalizar o texto de feedback, usando JavaScript.

{% capture example %}
<form>
  <div class="form-row">
    <div class="col-md-4 mb-3">
      <label for="validationDefault01">Primeiro nome</label>
      <input type="text" class="form-control" id="validationDefault01" placeholder="Nome" value="Mark" required>
    </div>
    <div class="col-md-4 mb-3">
      <label for="validationDefault02">Sobrenome</label>
      <input type="text" class="form-control" id="validationDefault02" placeholder="Sobrenome" value="Otto" required>
    </div>
    <div class="col-md-4 mb-3">
      <label for="validationDefaultUsername">Usuário</label>
      <div class="input-group">
        <div class="input-group-prepend">
          <span class="input-group-text" id="inputGroupPrepend2">@</span>
        </div>
        <input type="text" class="form-control" id="validationDefaultUsername" placeholder="Usuário" aria-describedby="inputGroupPrepend2" required>
      </div>
    </div>
  </div>
  <div class="form-row">
    <div class="col-md-6 mb-3">
      <label for="validationDefault03">Cidade</label>
      <input type="text" class="form-control" id="validationDefault03" placeholder="Cidade" required>
    </div>
    <div class="col-md-3 mb-3">
      <label for="validationDefault04">Estado</label>
      <input type="text" class="form-control" id="validationDefault04" placeholder="Estado" required>
    </div>
    <div class="col-md-3 mb-3">
      <label for="validationDefault05">CEP</label>
      <input type="text" class="form-control" id="validationDefault05" placeholder="CEP" required>
    </div>
  </div>
  <div class="form-group">
    <div class="form-check">
      <input class="form-check-input" type="checkbox" value="" id="invalidCheck2" required>
      <label class="form-check-label" for="invalidCheck2">
        Concordo com os termos e condições
      </label>
    </div>
  </div>
  <button class="btn btn-primary" type="submit">Enviar</button>
</form>
{% endcapture %}
{% include example.html content=example %}

### Server-side

Recomendamos usar validação client-side, mas se precisar de server-side, poderá indicar campos de formulário válidos e invalidos com as classes `.is-invalid` and `.is-valid`. Perceba que `.invalid-feedback` também pode ser usada com essas classes.

{% capture example %}
<form>
  <div class="form-row">
    <div class="col-md-4 mb-3">
      <label for="validationServer01">Primeiro nome</label>
      <input type="text" class="form-control is-valid" id="validationServer01" placeholder="Nome" value="Mark" required>
      <div class="valid-feedback">
        Tudo certo!
      </div>
    </div>
    <div class="col-md-4 mb-3">
      <label for="validationServer02">Sobrenome</label>
      <input type="text" class="form-control is-valid" id="validationServer02" placeholder="Sobrenome" value="Otto" required>
      <div class="valid-feedback">
        Tudo certo!
      </div>
    </div>
    <div class="col-md-4 mb-3">
      <label for="validationServerUsername">Usuário</label>
      <div class="input-group">
        <div class="input-group-prepend">
          <span class="input-group-text" id="inputGroupPrepend3">@</span>
        </div>
        <input type="text" class="form-control is-invalid" id="validationServerUsername" placeholder="Usuário" aria-describedby="inputGroupPrepend3" required>
        <div class="invalid-feedback">
          Por favor, escolha um nome de usuário.
        </div>
      </div>
    </div>
  </div>
  <div class="form-row">
    <div class="col-md-6 mb-3">
      <label for="validationServer03">Cidade</label>
      <input type="text" class="form-control is-invalid" id="validationServer03" placeholder="Cidade" required>
      <div class="invalid-feedback">
        Por favor, informe uma cidade válida.
      </div>
    </div>
    <div class="col-md-3 mb-3">
      <label for="validationServer04">Estado</label>
      <input type="text" class="form-control is-invalid" id="validationServer04" placeholder="Estado" required>
      <div class="invalid-feedback">
        Por favor, informe um estado válido.
      </div>
    </div>
    <div class="col-md-3 mb-3">
      <label for="validationServer05">CEP</label>
      <input type="text" class="form-control is-invalid" id="validationServer05" placeholder="CEP" required>
      <div class="invalid-feedback">
        Por favor, informe um CEP válido.
      </div>
    </div>
  </div>
  <div class="form-group">
    <div class="form-check">
      <input class="form-check-input is-invalid" type="checkbox" value="" id="invalidCheck3" required>
      <label class="form-check-label" for="invalidCheck3">
        Concordo com os termos e condições
      </label>
      <div class="invalid-feedback">
        Você deve concordar, antes de continuar.
      </div>
    </div>
  </div>
  <button class="btn btn-primary" type="submit">Enviar</button>
</form>
{% endcapture %}
{% include example.html content=example %}

### Elementos suportados

Nossos formulários de exemplo mostram `<input>` textuais nativos, abaixo, mas estilos de validação de formulário estão disponíveis para `<textarea>`s e nossos controles de formulários personalizados, também.

{% capture example %}
<form class="was-validated">
  <div class="mb-3">
    <label for="validationTextarea">Textarea</label>
    <textarea class="form-control is-invalid" id="validationTextarea" placeholder="Required example textarea" required></textarea>
    <div class="invalid-feedback">
      Please enter a message in the textarea.
    </div>
  </div>

  <div class="custom-control custom-checkbox mb-3">
    <input type="checkbox" class="custom-control-input" id="customControlValidation1" required>
    <label class="custom-control-label" for="customControlValidation1">Olha só, esse checkbox personalizado</label>
    <div class="invalid-feedback">Exemplo de texto para feedback inválido</div>
  </div>

  <div class="custom-control custom-radio">
    <input type="radio" class="custom-control-input" id="customControlValidation2" name="radio-stacked" required>
    <label class="custom-control-label" for="customControlValidation2">Clique neste radio personalizado</label>
  </div>
  <div class="custom-control custom-radio mb-3">
    <input type="radio" class="custom-control-input" id="customControlValidation3" name="radio-stacked" required>
    <label class="custom-control-label" for="customControlValidation3">Ou clique neste outro radio personalizado</label>
    <div class="invalid-feedback">Mais exemplo de texto para feedback inválido</div>
  </div>

  <div class="form-group">
    <select class="custom-select" required>
      <option value="">Abra este menu select</option>
      <option value="1">Um</option>
      <option value="2">Dois</option>
      <option value="3">Três</option>
    </select>
    <div class="invalid-feedback">Exemplo de feedback invalido para o select</div>
  </div>

  <div class="custom-file">
    <input type="file" class="custom-file-input" id="validatedCustomFile" required>
    <label class="custom-file-label" for="validatedCustomFile">Escolher arquivo...</label>
    <div class="invalid-feedback">Exemplo de feedback inválido para input file</div>
  </div>
</form>
{% endcapture %}
{% include example.html content=example %}

### Tooltips

Se o layout do seu formulário permite, você pode trocar as classes `.{valid|invalid}-feedback` pelas `.{valid|invalid}-tooltip` para mostrar o feedback de validação em um tooltip. Se assegure de ter um elemento pai com `position: relative` para o posicionamento do tooltip. No exemplo abaixo, nossas classes de coluna já possuem isso, mas seu projeto pode ter uma estrutura diferente.

{% capture example %}
<form class="needs-validation" novalidate>
  <div class="form-row">
    <div class="col-md-4 mb-3">
      <label for="validationTooltip01">Primeiro nome</label>
      <input type="text" class="form-control" id="validationTooltip01" placeholder="Nome" value="Mark" required>
      <div class="valid-tooltip">
        Tudo certo!
      </div>
    </div>
    <div class="col-md-4 mb-3">
      <label for="validationTooltip02">Sobrenome</label>
      <input type="text" class="form-control" id="validationTooltip02" placeholder="Sobrenome" value="Otto" required>
      <div class="valid-tooltip">
        Tudo certo!
      </div>
    </div>
    <div class="col-md-4 mb-3">
      <label for="validationTooltipUsername">Usuário</label>
      <div class="input-group">
        <div class="input-group-prepend">
          <span class="input-group-text" id="validationTooltipUsernamePrepend">@</span>
        </div>
        <input type="text" class="form-control" id="validationTooltipUsername" placeholder="Usuário" aria-describedby="validationTooltipUsernamePrepend" required>
        <div class="invalid-tooltip">
          Por favor, escolha um usuário válido e único.
        </div>
      </div>
    </div>
  </div>
  <div class="form-row">
    <div class="col-md-6 mb-3">
      <label for="validationTooltip03">Cidade</label>
      <input type="text" class="form-control" id="validationTooltip03" placeholder="Cidade" required>
      <div class="invalid-tooltip">
        Por favor, informe uma cidade válida.
      </div>
    </div>
    <div class="col-md-3 mb-3">
      <label for="validationTooltip04">Estado</label>
      <input type="text" class="form-control" id="validationTooltip04" placeholder="Estado" required>
      <div class="invalid-tooltip">
        Por favor, informe um estado válido.
      </div>
    </div>
    <div class="col-md-3 mb-3">
      <label for="validationTooltip05">CEP</label>
      <input type="text" class="form-control" id="validationTooltip05" placeholder="CEP" required>
      <div class="invalid-tooltip">
        Por favor, informe um CEP válido.
      </div>
    </div>
  </div>
  <button class="btn btn-primary" type="submit">Enviar</button>
</form>
{% endcapture %}
{% include example.html content=example %}

## Formulários personalizados

Para mais customização ainda e consistência cross-browser, use nossos elementos de formulário personalizados para substituir os padrões dos browsers. Eles são feitos com base em marcação semântica e acessível, então, são substituições sólidas para qualquer campo de formulário padrão.

### Checkboxes e radios

Cada checkbox e radio é envolto em uma `<div>` com um `<span>` irmão para criar nosso campo personalizado e um `<label>` para acompanhar o texto. Estruturalmente, esta é a mesma abordagem que nossa `.form-check` padrão.

Nós usamos o seletor de irmão (`~`) para todos os nossos estados de `inputs` (`:checked`, por exemplo) para, adequadamente, estilizar nosso indicador de formulário personalizado. Quando combinado com a classe `.custom-control-label`, também podemos estilizar o texto em cada item, baseando-se no estado do `<input>`.

Nós escondemos o `<input>` padrão com `opacity` e usamos a `.custom-control-label` para fazer um novo indicador de formulário, em seu lugar, com `::before` e `::after`. Infelizmente, não podemos fazer um personalizado só a partir do `<input>`, porque a propriedade CSS `content` não funciona no elemento.

Nos estados `:checked`, usamos **ícones SVG base64 embutidos** do [Open Iconic](https://useiconic.com/open). Ele nos dá o melhor controle para estilizar e posicionar, através dos browsers e dispositivos.

#### Checkboxes

{% capture example %}
<div class="custom-control custom-checkbox">
  <input type="checkbox" class="custom-control-input" id="customCheck1">
  <label class="custom-control-label" for="customCheck1">Olha só, esse checkbox personalizado</label>
</div>
{% endcapture %}
{% include example.html content=example %}

Checkboxes personalizados também podem usar a pseudo-classe `:indeterminate`, quando, manualmente, definida via JavaScript (não existe nenhum atributo HTML para defini-la).

<div class="bd-example bd-example-indeterminate">
  <div class="custom-control custom-checkbox">
    <input type="checkbox" class="custom-control-input" id="customCheck2">
    <label class="custom-control-label" for="customCheck2">Olha só, esse checkbox personalizado</label>
  </div>
</div>

Se você está usando jQuery, algo como isso deve servir:

{% highlight js %}
$('.seu-checkbox').prop('indeterminate', true)
{% endhighlight %}

#### Radios

{% capture example %}
<div class="custom-control custom-radio">
  <input type="radio" id="customRadio1" name="customRadio" class="custom-control-input">
  <label class="custom-control-label" for="customRadio1">Clique neste radio personalizado</label>
</div>
<div class="custom-control custom-radio">
  <input type="radio" id="customRadio2" name="customRadio" class="custom-control-input">
  <label class="custom-control-label" for="customRadio2">Ou clique neste outro radio personalizado</label>
</div>
{% endcapture %}
{% include example.html content=example %}

#### Inline

{% capture example %}
<div class="custom-control custom-radio custom-control-inline">
  <input type="radio" id="customRadioInline1" name="customRadioInline1" class="custom-control-input">
  <label class="custom-control-label" for="customRadioInline1">Clique neste radio personalizado</label>
</div>
<div class="custom-control custom-radio custom-control-inline">
  <input type="radio" id="customRadioInline2" name="customRadioInline1" class="custom-control-input">
  <label class="custom-control-label" for="customRadioInline2">Ou clique neste outro radio personalizado</label>
</div>
{% endcapture %}
{% include example.html content=example %}

#### Desativado

Checkboxes e radios também podem ser desativados. Coloque o atributo booleano `disabled` em um `<input>` e o indicador personalizado e a descrição da label vão ser estilizados, automaticamente.

{% capture example %}
<div class="custom-control custom-checkbox">
  <input type="checkbox" class="custom-control-input" id="customCheckDisabled" disabled>
  <label class="custom-control-label" for="customCheckDisabled">Olha só, esse checkbox personalizado</label>
</div>

<div class="custom-control custom-radio">
  <input type="radio" id="radio3" name="radioDisabled" id="customRadioDisabled" class="custom-control-input" disabled>
  <label class="custom-control-label" for="customRadioDisabled">Clique neste radio personalizado</label>
</div>
{% endcapture %}
{% include example.html content=example %}

### Menu select

Menus de `<select>` personalizados só precisam de uma classe personalizada `.custom-select`, para ativar os estilos personalizados. Custom styles are limited to the `<select>`'s initial appearance and cannot modify the `<option>`s due to browser limitations.

{% capture example %}
<select class="custom-select">
  <option selected>Abra este menu select</option>
  <option value="1">Um</option>
  <option value="2">Dois</option>
  <option value="3">Três</option>
</select>
{% endcapture %}
{% include example.html content=example %}

Você também pode escolher entre `selects` personalizados pequenos ou grandes, para combinar com nossos inputs estilizados similarmente.

{% capture example %}
<select class="custom-select custom-select-lg mb-3">
  <option selected>Abra este menu select</option>
  <option value="1">Um</option>
  <option value="2">Dois</option>
  <option value="3">Três</option>
</select>

<select class="custom-select custom-select-sm">
  <option selected>Abra este menu select</option>
  <option value="1">Um</option>
  <option value="2">Dois</option>
  <option value="3">Três</option>
</select>
{% endcapture %}
{% include example.html content=example %}

O atributo `multiple` também é suportado:

{% capture example %}
<select class="custom-select" multiple>
  <option selected>Abra este menu select</option>
  <option value="1">Um</option>
  <option value="2">Dois</option>
  <option value="3">Três</option>
</select>
{% endcapture %}
{% include example.html content=example %}

Assim como o atributo `size`:

{% capture example %}
<select class="custom-select" size="3">
  <option selected>Abra este menu select</option>
  <option value="1">Um</option>
  <option value="2">Dois</option>
  <option value="3">Três</option>
</select>
{% endcapture %}
{% include example.html content=example %}

### Range

Crie um `<input type="range">` personalizado, usando `.custom-range`. A trilha e o valor são ambos estilizados para aparecerem da mesma maneira, nos diferentes browsers. Já que só o IE e o Firefox suportam preencher a trilha (da esquerda para a direita), como um indicador visual de progresso, nós não suportamos isso, ainda.

{% capture example %}
<label for="customRange1">Range exemplo</label>
<input type="range" class="custom-range" id="customRange1">
{% endcapture %}
{% include example.html content=example %}

Inputs range possuem valores padrões inplícitos para `min` e `max`, sendo eles `0` and `100`, respectivamente. Você pode especificar novos valores para os inputs que estiverem usando os atributos `min` and `max`.

{% capture example %}
<label for="customRange2">Range exemplo</label>
<input type="range" class="custom-range" min="0" max="5" id="customRange2">
{% endcapture %}
{% include example.html content=example %}

Por padrão, inputs range pulam por valores inteiros. Para mudar isso, você pode especificar a quantia de pulos. No exemplo abaixo, dobramos a quantia de pulos, usando `step="0.5"`.

{% capture example %}
<label for="customRange3">Range exemplo</label>
<input type="range" class="custom-range" min="0" max="5" step="0.5" id="customRange3">
{% endcapture %}
{% include example.html content=example %}

### Explorador de arquivos

O input de arquivos é o mais cabuloso de todos e exige JavaScript adicional, se você quiser ter um *Escolher arquivo...*  e nome de arquivo selecionado funcional.

{% capture example %}
<div class="custom-file">
  <input type="file" class="custom-file-input" id="customFile">
  <label class="custom-file-label" for="customFile">Escolher arquivo</label>
</div>
{% endcapture %}
{% include example.html content=example %}

- Nós escondemos o `<input>` de arquivo via `opacity` e, pelo contrário, estilizamos o `<label>`;
- O botão é gerado e posicionado com `::after`;
- Por último, nós declaramos `width` e `height` no `<input>` para espaçamento em volta do conteúdo, apropriado.

#### Traduzindo ou customizando as strings

A [pseudo-classe `:lang()`](https://developer.mozilla.org/en-US/docs/Web/CSS/:lang) é usada para permitir a tradução do texto "Browse", em outras linguagens. Sobrescreva ou adicione valores na variável `$custom-file-text` com uma [tag de linguagem](https://en.wikipedia.org/wiki/IETF_language_tag) e a string referente ao local. Por exemplo, assim é como você pode adicionar tradução para o espanhol (a tag de linguagem do espanhol é `es`):

{% highlight scss %}
$custom-file-text: (
  en: "Browse",
  es: "Elegir"
);
{% endhighlight %}

Aqui está a `lang(es)`, em ação, no input de arquivo personalizado para a tradução espanhol:

{% capture example %}
<div class="custom-file">
  <input type="file" class="custom-file-input" id="customFileLang" lang="es">
  <label class="custom-file-label" for="customFileLang">Seleccionar Archivo</label>
</div>
{% endcapture %}
{% include example.html content=example %}

Você precisará definir a linguagem de seu documento, corretamente, para que o texto correto seja mostrado. Isso pode ser feito usando o [atributo `lang`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/lang) no elemento `<html>` ou [`Content-Language` HTTP header](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.12), junto com os outros métodos.

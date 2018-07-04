---
layout: docs
title: Navs
description: Documentação e exemplos de como usar os componentes de navegação Bootstrap.
group: components
toc: true
---

## Nav: a base de tudo

A navegação disponível no Bootstrap compartilha várias marcações e estilos, desde a classe base `.nav` até os estados ativo e desativo. Troque de classes modificadoras para mudar de estilo.

O componente `.nav` é feito com flexbox e provê uma forte fundação para construir todo tipo de componente de navegação. Ela possui sobrescrição de alguns estilos para trabalhar com listas, padding em links para criar áreas de clique maiores e estilo desativado básico.

{% capture callout %}
O componente base `.nav` não inclui qualquer estado `.active`. Os exemplos seguintes possuem a  classe, principalmente, para demonstrar que esta classe não aciona nenhum estilo, em específico.
{% endcapture %}
{% include callout.html content=callout type="info" %}

{% capture example %}
<ul class="nav">
  <li class="nav-item">
    <a class="nav-link active" href="#">Ativo</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" href="#">Link</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" href="#">Link</a>
  </li>
  <li class="nav-item">
    <a class="nav-link disabled" href="#">Desativado</a>
  </li>
</ul>
{% endcapture %}
{% include example.html content=example %}

As classes são usadas por toda parte, então, sua marcação consegue ser muito flexível. Use um `<ul>` como acima ou faça seu próprio, com um elemento `<nav>`. Devido o `.nav` usar `display: flex`, os links navs se comportam da mesma forma que os itens nav, mas sem marcação HTML a mais.

{% capture example %}
<nav class="nav">
  <a class="nav-link active" href="#">Ativo</a>
  <a class="nav-link" href="#">Link</a>
  <a class="nav-link" href="#">Link</a>
  <a class="nav-link disabled" href="#">Desativado</a>
</nav>
{% endcapture %}
{% include example.html content=example %}

## Estilos disponíveis

Mude o estilo do componente `.nav` com modificadores e utilitários. Você também pode misturar e combinar, assim como construir seu próprio nav.

### Alinhamento horizontal

Altere o alinhamento horizontal de seu nav com [utilitários flexbox]({{ site.baseurl }}/docs/{{ site.docs_version }}/layout/grid/#horizontal-alignment). Por padrão, navs são alinhados a esquerda, mas você pode modificá-los para serem centralizados ou alinhados a direita, facilmente.

Centralizado, usando `.justify-content-center`:

{% capture example %}
<ul class="nav justify-content-center">
  <li class="nav-item">
    <a class="nav-link active" href="#">Ativo</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" href="#">Link</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" href="#">Link</a>
  </li>
  <li class="nav-item">
    <a class="nav-link disabled" href="#">Desativado</a>
  </li>
</ul>
{% endcapture %}
{% include example.html content=example %}

Alinhado a direita, usando `.justify-content-end`:

{% capture example %}
<ul class="nav justify-content-end">
  <li class="nav-item">
    <a class="nav-link active" href="#">Ativo</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" href="#">Link</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" href="#">Link</a>
  </li>
  <li class="nav-item">
    <a class="nav-link disabled" href="#">Desativado</a>
  </li>
</ul>
{% endcapture %}
{% include example.html content=example %}

### Alinhamento vertical

Empilhe sua navegação, modificando a direção flex item com o utilitário `.flex-column`. 

Precisa empilhar eles, em algumas viewports, mas não em outras? Use variações responsivas, como `.flex-sm-column`.

{% capture example %}
<ul class="nav flex-column">
  <li class="nav-item">
    <a class="nav-link active" href="#">Ativo</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" href="#">Link</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" href="#">Link</a>
  </li>
  <li class="nav-item">
    <a class="nav-link disabled" href="#">Desativado</a>
  </li>
</ul>
{% endcapture %}
{% include example.html content=example %}

Navegação vertical é possível sem `<ul>`, também.

{% capture example %}
<nav class="nav flex-column">
  <a class="nav-link active" href="#">Ativo</a>
  <a class="nav-link" href="#">Link</a>
  <a class="nav-link" href="#">Link</a>
  <a class="nav-link disabled" href="#">Desativado</a>
</nav>
{% endcapture %}
{% include example.html content=example %}

### Abas

Use o nav básico acima e coloque a classe `.nav-tabs` para gerar uma interface de abas. Use isso para criar regiões de abas com nosso [plugin JavaScript tab](#javascript-behavior).

{% capture example %}
<ul class="nav nav-tabs">
  <li class="nav-item">
    <a class="nav-link active" href="#">Ativo</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" href="#">Link</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" href="#">Link</a>
  </li>
  <li class="nav-item">
    <a class="nav-link disabled" href="#">Desativado</a>
  </li>
</ul>
{% endcapture %}
{% include example.html content=example %}

### Pílulas

Pegue o mesmo HTML, mas use `.nav-pills` e obtenha o seguinte:

{% capture example %}
<ul class="nav nav-pills">
  <li class="nav-item">
    <a class="nav-link active" href="#">Ativo</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" href="#">Link</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" href="#">Link</a>
  </li>
  <li class="nav-item">
    <a class="nav-link disabled" href="#">Desativado</a>
  </li>
</ul>
{% endcapture %}
{% include example.html content=example %}

### Fill e justify

Force o conteúdo do seu `.nav` se extender por toda largura disponível com uma das duas classes modificadoras. Para preencher, proporcionalmente, todo espaço disponível com seus `.nav-item`, use `.nav-fill`. Perceba que todo espaço horizontal é ocupado, mas nem todo item nav tem a mesma largura.

{% capture example %}
<ul class="nav nav-pills nav-fill">
  <li class="nav-item">
    <a class="nav-link active" href="#">Ativo</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" href="#">Link nav muito mais longo</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" href="#">Link</a>
  </li>
  <li class="nav-item">
    <a class="nav-link disabled" href="#">Desativado</a>
  </li>
</ul>
{% endcapture %}
{% include example.html content=example %}

Quando usando uma navegação baseada em `<nav>`, se assegure de usar `.nav-item`, nas âncoras.

{% capture example %}
<nav class="nav nav-pills nav-fill">
  <a class="nav-item nav-link active" href="#">Ativo</a>
  <a class="nav-item nav-link" href="#">Link</a>
  <a class="nav-item nav-link" href="#">Link</a>
  <a class="nav-item nav-link disabled" href="#">Desativado</a>
</nav>
{% endcapture %}
{% include example.html content=example %}

Para ter elementos com larguras idênticas, use `.nav-justified`. Todo espaço horizontal será ocupado por links nav, mas diferente do `.nav-fill` acima, todo item nav terá a mesma largura.

{% capture example %}
<nav class="nav nav-pills nav-justified">
  <a class="nav-link active" href="#">Ativo</a>
  <a class="nav-link" href="#">Link nav muito mais longo</a>
  <a class="nav-link" href="#">Link</a>
  <a class="nav-link disabled" href="#">Desativado</a>
</nav>
{% endcapture %}
{% include example.html content=example %}

Similar ao exemplo `.nav-fill` usando uma navegação baseada em `<nav>`, se assegure de incluir `.nav-item`, nas âncoras.

{% capture example %}
<nav class="nav nav-pills nav-justified">
  <a class="nav-item nav-link active" href="#">Ativo</a>
  <a class="nav-item nav-link" href="#">Link</a>
  <a class="nav-item nav-link" href="#">Link</a>
  <a class="nav-item nav-link disabled" href="#">Desativado</a>
</nav>

{% endcapture %}
{% include example.html content=example %}
## Trabalhando com utilitários flex

Se precisar de variações nav responsivas, considere usar [utilitários flexbox]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/flex/). Apesar de ser mais massante, estes utilitários oferecem melhor customização, nos direntes breakpoints. No exemplo abaixo, nosso nav irá se empilhar no menor breakpoint, então, voltar ao layout horizontal que preenche a toda largura disponível, a partir do breakpoint _small_ (sm).

{% capture example %}
<nav class="nav nav-pills flex-column flex-sm-row">
  <a class="flex-sm-fill text-sm-center nav-link active" href="#">Ativo</a>
  <a class="flex-sm-fill text-sm-center nav-link" href="#">Link</a>
  <a class="flex-sm-fill text-sm-center nav-link" href="#">Link</a>
  <a class="flex-sm-fill text-sm-center nav-link disabled" href="#">Desativado</a>
</nav>
{% endcapture %}
{% include example.html content=example %}

## Acessibilidade

Se você está usando navs para prover uma barra de navegação, se assegure de usar `role="navigation"` no container pai mais lógico do `<ul>` ou envolva um elemento `<nav>` em toda navegação. Não adicione o `role` no `<ul>`, porque isso evitaria que ele fosse transmitido como uma lista, de fato, para as tecnologias assistivas.

Perceba que barras de navegação, mesmo que visualmente estilizadas como abas com a classe `.nav-tabs`, **não** devem receber os atributos `role="tablist"`, `role="tab"` ou `role="tabpanel"`. Eles só são adequados para interfaces com abas dinâmicas, como descrito em [<abbr title="Web Accessibility Initiative">WAI</abbr> <abbr title="Accessible Rich Internet Applications">ARIA</abbr> Authoring Practices](https://www.w3.org/TR/wai-aria-practices/#tabpanel). Leia sobre o [comportamento JavaScript](#javascript-behavior) para aprender sobre interfaces de abas dinâmicas.

## Usando dropdowns

Use menus dropdown com uma marcação HTML extra e o [plugin JavaScript dropdown]({{ site.baseurl }}/docs/{{ site.docs_version }}/components/dropdowns/#usage).

### Abas com dropdowns

{% capture example %}
<ul class="nav nav-tabs">
  <li class="nav-item">
    <a class="nav-link active" href="#">Ativo</a>
  </li>
  <li class="nav-item dropdown">
    <a class="nav-link dropdown-toggle" data-toggle="dropdown" href="#" role="button" aria-haspopup="true" aria-expanded="false">Dropdown</a>
    <div class="dropdown-menu">
      <a class="dropdown-item" href="#">Ação</a>
      <a class="dropdown-item" href="#">Outra ação</a>
      <a class="dropdown-item" href="#">Algo mais aqui</a>
      <div class="dropdown-divider"></div>
      <a class="dropdown-item" href="#">Link isolado</a>
    </div>
  </li>
  <li class="nav-item">
    <a class="nav-link" href="#">Link</a>
  </li>
  <li class="nav-item">
    <a class="nav-link disabled" href="#">Desativado</a>
  </li>
</ul>
{% endcapture %}
{% include example.html content=example %}

### Pílulas com dropdowns

{% capture example %}
<ul class="nav nav-pills">
  <li class="nav-item">
    <a class="nav-link active" href="#">Ativo</a>
  </li>
  <li class="nav-item dropdown">
    <a class="nav-link dropdown-toggle" data-toggle="dropdown" href="#" role="button" aria-haspopup="true" aria-expanded="false">Dropdown</a>
    <div class="dropdown-menu">
      <a class="dropdown-item" href="#">Ação</a>
      <a class="dropdown-item" href="#">Outra ação</a>
      <a class="dropdown-item" href="#">Algo mais aqui</a>
      <div class="dropdown-divider"></div>
      <a class="dropdown-item" href="#">Link isolado</a>
    </div>
  </li>
  <li class="nav-item">
    <a class="nav-link" href="#">Link</a>
  </li>
  <li class="nav-item">
    <a class="nav-link disabled" href="#">Desativado</a>
  </li>
</ul>
{% endcapture %}
{% include example.html content=example %}

## Comportamento JavaScript

Use o plugin JavaScript tab (inclua-o individualmente ou através do arquivo compilado `bootstrap.js`) para aprimorar nossas abas ou pílulas navegacionais e criar paineis dinâmicos com conteúdo local, até mesmo usando menus dropdown.

Se você está montando nosso JavaScript a partir da fonte, vai precisar do [`util.js`]({{ site.baseurl }}/docs/{{ site.docs_version }}/getting-started/javascript/#util).

Interfaces de abas dinâmicas, como descritas em [<abbr title="Web Accessibility Initiative">WAI</abbr> <abbr title="Accessible Rich Internet Applications">ARIA</abbr> Authoring Practices](https://www.w3.org/TR/wai-aria-practices/#tabpanel), precisam de `role="tablist"`, `role="tab"`, `role="tabpanel"` e atributos `aria-` extras, para transmitir sua estrutura, funcionalidade e atual estado para os usuários de tecnologias assistivas.

Perceba que interfaces de abas dinâmicas <em>não</em> devem conter menus dropdowns, já que isso causa problemas de usabilidade e acessibilidade. De uma perspectiva de usabilidade, o fato do elemento gatilho da aba atualmente exibida não estar visível (já que está dentro do menu dropdown fechado) pode causar confusão. Do ponto de vista de acessibilidade, atualmente, não há maneira sensata de mapear este tipo de construção em um padrão WAI ARIA, significando que isso não pode ser, facilmente, indendido por usuários de tecnologias assistivas.

<div class="bd-example bd-example-tabs">
  <ul class="nav nav-tabs" id="myTab" role="tablist">
    <li class="nav-item">
      <a class="nav-link active" id="home-tab" data-toggle="tab" href="#home" role="tab" aria-controls="home" aria-selected="true">Home</a>
    </li>
    <li class="nav-item">
      <a class="nav-link" id="profile-tab" data-toggle="tab" href="#perfil" role="tab" aria-controls="profile" aria-selected="false">Perfil</a>
    </li>
    <li class="nav-item">
      <a class="nav-link" id="contact-tab" data-toggle="tab" href="#contato" role="tab" aria-controls="contact" aria-selected="false">Contato</a>
    </li>
  </ul>
  <div class="tab-content" id="myTabContent">
    <div class="tab-pane fade show active" id="home" role="tabpanel" aria-labelledby="home-tab">
      <p>Raw denim you probably haven't heard of them jean shorts Austin. Nesciunt tofu stumptown aliqua, retro synth master cleanse. Mustache cliche tempor, williamsburg carles vegan helvetica. Reprehenderit butcher retro keffiyeh dreamcatcher synth. Cosby sweater eu banh mi, qui irure terry richardson ex squid. Aliquip placeat salvia cillum iphone. Seitan aliquip quis cardigan american apparel, butcher voluptate nisi qui.</p>
    </div>
    <div class="tab-pane fade" id="perfil" role="tabpanel" aria-labelledby="profile-tab">
      <p>Food truck fixie locavore, accusamus mcsweeney's marfa nulla single-origin coffee squid. Exercitation +1 labore velit, blog sartorial PBR leggings next level wes anderson artisan four loko farm-to-table craft beer twee. Qui photo booth letterpress, commodo enim craft beer mlkshk aliquip jean shorts ullamco ad vinyl cillum PBR. Homo nostrud organic, assumenda labore aesthetic magna delectus mollit. Keytar helvetica VHS salvia yr, vero magna velit sapiente labore stumptown. Vegan fanny pack odio cillum wes anderson 8-bit, sustainable jean shorts beard ut DIY ethical culpa terry richardson biodiesel. Art party scenester stumptown, tumblr butcher vero sint qui sapiente accusamus tattooed echo park.</p>
    </div>
    <div class="tab-pane fade" id="contato" role="tabpanel" aria-labelledby="contact-tab">
      <p>Etsy mixtape wayfarers, ethical wes anderson tofu before they sold out mcsweeney's organic lomo retro fanny pack lo-fi farm-to-table readymade. Messenger bag gentrify pitchfork tattooed craft beer, iphone skateboard locavore carles etsy salvia banksy hoodie helvetica. DIY synth PBR banksy irony. Leggings gentrify squid 8-bit cred pitchfork. Williamsburg banh mi whatever gluten-free, carles pitchfork biodiesel fixie etsy retro mlkshk vice blog. Scenester cred you probably haven't heard of them, vinyl craft beer blog stumptown. Pitchfork sustainable tofu synth chambray yr.</p>
    </div>
  </div>
</div>

{% highlight html %}
<ul class="nav nav-tabs" id="myTab" role="tablist">
  <li class="nav-item">
    <a class="nav-link active" id="home-tab" data-toggle="tab" href="#home" role="tab" aria-controls="home" aria-selected="true">Home</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" id="profile-tab" data-toggle="tab" href="#perfil" role="tab" aria-controls="profile" aria-selected="false">Perfil</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" id="contact-tab" data-toggle="tab" href="#contato" role="tab" aria-controls="contact" aria-selected="false">Contato</a>
  </li>
</ul>
<div class="tab-content" id="myTabContent">
  <div class="tab-pane fade show active" id="home" role="tabpanel" aria-labelledby="home-tab">...</div>
  <div class="tab-pane fade" id="perfil" role="tabpanel" aria-labelledby="profile-tab">...</div>
  <div class="tab-pane fade" id="contato" role="tabpanel" aria-labelledby="contact-tab">...</div>
</div>
{% endhighlight %}

Para ajudar em suas necessidades, isso funciona com uma marcação baseada em `<ul>` ou feita por você mesmo. Perceba que se você está usando `<nav>`, não deveria usar `role="tablist"` diretamente nele, já que isso sobrescreveria o `role` nativo do elemento, que é uma referência de navegação. Por isso, escolha um elemento alternativo (um `<div>`, no exemplo abaixo) e o envolva com o `<nav>`.

<div class="bd-example bd-example-tabs">
  <nav>
    <div class="nav nav-tabs" id="nav-tab" role="tablist">
      <a class="nav-item nav-link active" id="nav-home-tab" data-toggle="tab" href="#nav-home" role="tab" aria-controls="nav-home" aria-selected="true">Home</a>
      <a class="nav-item nav-link" id="nav-profile-tab" data-toggle="tab" href="#nav-profile" role="tab" aria-controls="nav-profile" aria-selected="false">Perfil</a>
      <a class="nav-item nav-link" id="nav-contact-tab" data-toggle="tab" href="#nav-contact" role="tab" aria-controls="nav-contact" aria-selected="false">Contato</a>
    </div>
  </nav>
  <div class="tab-content" id="nav-tabContent">
    <div class="tab-pane fade show active" id="nav-home" role="tabpanel" aria-labelledby="nav-home-tab">
      <p>Et et consectetur ipsum labore excepteur est proident excepteur ad velit occaecat qui minim occaecat veniam. Fugiat veniam incididunt anim aliqua enim pariatur veniam sunt est aute sit dolor anim. Velit non irure adipisicing aliqua ullamco irure incididunt irure non esse consectetur nostrud minim non minim occaecat. Amet duis do nisi duis veniam non est eiusmod tempor incididunt tempor dolor ipsum in qui sit. Exercitation mollit sit culpa nisi culpa non adipisicing reprehenderit do dolore. Duis reprehenderit occaecat anim ullamco ad duis occaecat ex.</p>
    </div>
    <div class="tab-pane fade" id="nav-profile" role="tabpanel" aria-labelledby="nav-profile-tab">
      <p>Nulla est ullamco ut irure incididunt nulla Lorem Lorem minim irure officia enim reprehenderit. Magna duis labore cillum sint adipisicing exercitation ipsum. Nostrud ut anim non exercitation velit laboris fugiat cupidatat. Commodo esse dolore fugiat sint velit ullamco magna consequat voluptate minim amet aliquip ipsum aute laboris nisi. Labore labore veniam irure irure ipsum pariatur mollit magna in cupidatat dolore magna irure esse tempor ad mollit. Dolore commodo nulla minim amet ipsum officia consectetur amet ullamco voluptate nisi commodo ea sit eu.</p>
    </div>
    <div class="tab-pane fade" id="nav-contact" role="tabpanel" aria-labelledby="nav-contact-tab">
      <p>Sint sit mollit irure quis est nostrud cillum consequat Lorem esse do quis dolor esse fugiat sunt do. Eu ex commodo veniam Lorem aliquip laborum occaecat qui Lorem esse mollit dolore anim cupidatat. Deserunt officia id Lorem nostrud aute id commodo elit eiusmod enim irure amet eiusmod qui reprehenderit nostrud tempor. Fugiat ipsum excepteur in aliqua non et quis aliquip ad irure in labore cillum elit enim. Consequat aliquip incididunt ipsum et minim laborum laborum laborum et cillum labore. Deserunt adipisicing cillum id nulla minim nostrud labore eiusmod et amet. Laboris consequat consequat commodo non ut non aliquip reprehenderit nulla anim occaecat. Sunt sit ullamco reprehenderit irure ea ullamco Lorem aute nostrud magna.</p>
    </div>
  </div>
</div>

{% highlight html %}
<nav>
  <div class="nav nav-tabs" id="nav-tab" role="tablist">
    <a class="nav-item nav-link active" id="nav-home-tab" data-toggle="tab" href="#nav-home" role="tab" aria-controls="nav-home" aria-selected="true">Home</a>
    <a class="nav-item nav-link" id="nav-profile-tab" data-toggle="tab" href="#nav-profile" role="tab" aria-controls="nav-profile" aria-selected="false">Perfil</a>
    <a class="nav-item nav-link" id="nav-contact-tab" data-toggle="tab" href="#nav-contact" role="tab" aria-controls="nav-contact" aria-selected="false">Contato</a>
  </div>
</nav>
<div class="tab-content" id="nav-tabContent">
  <div class="tab-pane fade show active" id="nav-home" role="tabpanel" aria-labelledby="nav-home-tab">...</div>
  <div class="tab-pane fade" id="nav-profile" role="tabpanel" aria-labelledby="nav-profile-tab">...</div>
  <div class="tab-pane fade" id="nav-contact" role="tabpanel" aria-labelledby="nav-contact-tab">...</div>
</div>
{% endhighlight %}

O plugin tab também funciona com pílulas.

<div class="bd-example bd-example-tabs">
  <ul class="nav nav-pills mb-3" id="pills-tab" role="tablist">
    <li class="nav-item">
      <a class="nav-link active" id="pills-home-tab" data-toggle="pill" href="#pills-home" role="tab" aria-controls="pills-home" aria-selected="true">Home</a>
    </li>
    <li class="nav-item">
      <a class="nav-link" id="pills-profile-tab" data-toggle="pill" href="#pills-profile" role="tab" aria-controls="pills-profile" aria-selected="false">Perfil</a>
    </li>
    <li class="nav-item">
      <a class="nav-link" id="pills-contact-tab" data-toggle="pill" href="#pills-contact" role="tab" aria-controls="pills-contact" aria-selected="false">Contato</a>
    </li>
  </ul>
  <div class="tab-content" id="pills-tabContent">
    <div class="tab-pane fade show active" id="pills-home" role="tabpanel" aria-labelledby="pills-home-tab">
      <p>Consequat occaecat ullamco amet non eiusmod nostrud dolore irure incididunt est duis anim sunt officia. Fugiat velit proident aliquip nisi incididunt nostrud exercitation proident est nisi. Irure magna elit commodo anim ex veniam culpa eiusmod id nostrud sit cupidatat in veniam ad. Eiusmod consequat eu adipisicing minim anim aliquip cupidatat culpa excepteur quis. Occaecat sit eu exercitation irure Lorem incididunt nostrud.</p>
    </div>
    <div class="tab-pane fade" id="pills-profile" role="tabpanel" aria-labelledby="pills-profile-tab">
      <p>Ad pariatur nostrud pariatur exercitation ipsum ipsum culpa mollit commodo mollit ex. Aute sunt incididunt amet commodo est sint nisi deserunt pariatur do. Aliquip ex eiusmod voluptate exercitation cillum id incididunt elit sunt. Qui minim sit magna Lorem id et dolore velit Lorem amet exercitation duis deserunt. Anim id labore elit adipisicing ut in id occaecat pariatur ut ullamco ea tempor duis.</p>
    </div>
    <div class="tab-pane fade" id="pills-contact" role="tabpanel" aria-labelledby="pills-contact-tab">
      <p>Est quis nulla laborum officia ad nisi ex nostrud culpa Lorem excepteur aliquip dolor aliqua irure ex. Nulla ut duis ipsum nisi elit fugiat commodo sunt reprehenderit laborum veniam eu veniam. Eiusmod minim exercitation fugiat irure ex labore incididunt do fugiat commodo aliquip sit id deserunt reprehenderit aliquip nostrud. Amet ex cupidatat excepteur aute veniam incididunt mollit cupidatat esse irure officia elit do ipsum ullamco Lorem. Ullamco ut ad minim do mollit labore ipsum laboris ipsum commodo sunt tempor enim incididunt. Commodo quis sunt dolore aliquip aute tempor irure magna enim minim reprehenderit. Ullamco consectetur culpa veniam sint cillum aliqua incididunt velit ullamco sunt ullamco quis quis commodo voluptate. Mollit nulla nostrud adipisicing aliqua cupidatat aliqua pariatur mollit voluptate voluptate consequat non.</p>
    </div>
  </div>
</div>

{% highlight html %}
<ul class="nav nav-pills mb-3" id="pills-tab" role="tablist">
  <li class="nav-item">
    <a class="nav-link active" id="pills-home-tab" data-toggle="pill" href="#pills-home" role="tab" aria-controls="pills-home" aria-selected="true">Home</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" id="pills-profile-tab" data-toggle="pill" href="#pills-profile" role="tab" aria-controls="pills-profile" aria-selected="false">Perfil</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" id="pills-contact-tab" data-toggle="pill" href="#pills-contact" role="tab" aria-controls="pills-contact" aria-selected="false">Contato</a>
  </li>
</ul>
<div class="tab-content" id="pills-tabContent">
  <div class="tab-pane fade show active" id="pills-home" role="tabpanel" aria-labelledby="pills-home-tab">...</div>
  <div class="tab-pane fade" id="pills-profile" role="tabpanel" aria-labelledby="pills-profile-tab">...</div>
  <div class="tab-pane fade" id="pills-contact" role="tabpanel" aria-labelledby="pills-contact-tab">...</div>
</div>
{% endhighlight %}

Ele também funciona com pílulas verticais.

<div class="bd-example bd-example-tabs">
  <div class="row">
    <div class="col-3">
      <div class="nav flex-column nav-pills" id="v-pills-tab" role="tablist" aria-orientation="vertical">
        <a class="nav-link active" id="v-pills-home-tab" data-toggle="pill" href="#v-pills-home" role="tab" aria-controls="v-pills-home" aria-selected="true">Home</a>
        <a class="nav-link" id="v-pills-profile-tab" data-toggle="pill" href="#v-pills-profile" role="tab" aria-controls="v-pills-profile" aria-selected="false">Perfil</a>
        <a class="nav-link" id="v-pills-messages-tab" data-toggle="pill" href="#v-pills-messages" role="tab" aria-controls="v-pills-messages" aria-selected="false">Mensagens</a>
        <a class="nav-link" id="v-pills-settings-tab" data-toggle="pill" href="#v-pills-settings" role="tab" aria-controls="v-pills-settings" aria-selected="false">Configurações</a>
      </div>
    </div>
    <div class="col-9">
      <div class="tab-content" id="v-pills-tabContent">
        <div class="tab-pane fade show active" id="v-pills-home" role="tabpanel" aria-labelledby="v-pills-home-tab">
          <p>Cillum ad ut irure tempor velit nostrud occaecat ullamco aliqua anim Lorem sint. Veniam sint duis incididunt do esse magna mollit excepteur laborum qui. Id id reprehenderit sit est eu aliqua occaecat quis et velit excepteur laborum mollit dolore eiusmod. Ipsum dolor in occaecat commodo et voluptate minim reprehenderit mollit pariatur. Deserunt non laborum enim et cillum eu deserunt excepteur ea incididunt minim occaecat.</p>
        </div>
        <div class="tab-pane fade" id="v-pills-profile" role="tabpanel" aria-labelledby="v-pills-profile-tab">
          <p>Culpa dolor voluptate do laboris laboris irure reprehenderit id incididunt duis pariatur mollit aute magna pariatur consectetur. Eu veniam duis non ut dolor deserunt commodo et minim in quis laboris ipsum velit id veniam. Quis ut consectetur adipisicing officia excepteur non sit. Ut et elit aliquip labore Lorem enim eu. Ullamco mollit occaecat dolore ipsum id officia mollit qui esse anim eiusmod do sint minim consectetur qui.</p>
        </div>
        <div class="tab-pane fade" id="v-pills-messages" role="tabpanel" aria-labelledby="v-pills-messages-tab">
          <p>Fugiat id quis dolor culpa eiusmod anim velit excepteur proident dolor aute qui magna. Ad proident laboris ullamco esse anim Lorem Lorem veniam quis Lorem irure occaecat velit nostrud magna nulla. Velit et et proident Lorem do ea tempor officia dolor. Reprehenderit Lorem aliquip labore est magna commodo est ea veniam consectetur.</p>
        </div>
        <div class="tab-pane fade" id="v-pills-settings" role="tabpanel" aria-labelledby="v-pills-settings-tab">
          <p>Eu dolore ea ullamco dolore Lorem id cupidatat excepteur reprehenderit consectetur elit id dolor proident in cupidatat officia. Voluptate excepteur commodo labore nisi cillum duis aliqua do. Aliqua amet qui mollit consectetur nulla mollit velit aliqua veniam nisi id do Lorem deserunt amet. Culpa ullamco sit adipisicing labore officia magna elit nisi in aute tempor commodo eiusmod.</p>
        </div>
      </div>
    </div>
  </div>
</div>

{% highlight html %}
<div class="row">
  <div class="col-3">
    <div class="nav flex-column nav-pills" id="v-pills-tab" role="tablist" aria-orientation="vertical">
      <a class="nav-link active" id="v-pills-home-tab" data-toggle="pill" href="#v-pills-home" role="tab" aria-controls="v-pills-home" aria-selected="true">Home</a>
      <a class="nav-link" id="v-pills-profile-tab" data-toggle="pill" href="#v-pills-profile" role="tab" aria-controls="v-pills-profile" aria-selected="false">Perfil</a>
      <a class="nav-link" id="v-pills-messages-tab" data-toggle="pill" href="#v-pills-messages" role="tab" aria-controls="v-pills-messages" aria-selected="false">Mensagens</a>
      <a class="nav-link" id="v-pills-settings-tab" data-toggle="pill" href="#v-pills-settings" role="tab" aria-controls="v-pills-settings" aria-selected="false">Configurações</a>
    </div>
  </div>
  <div class="col-9">
    <div class="tab-content" id="v-pills-tabContent">
      <div class="tab-pane fade show active" id="v-pills-home" role="tabpanel" aria-labelledby="v-pills-home-tab">...</div>
      <div class="tab-pane fade" id="v-pills-profile" role="tabpanel" aria-labelledby="v-pills-profile-tab">...</div>
      <div class="tab-pane fade" id="v-pills-messages" role="tabpanel" aria-labelledby="v-pills-messages-tab">...</div>
      <div class="tab-pane fade" id="v-pills-settings" role="tabpanel" aria-labelledby="v-pills-settings-tab">...</div>
    </div>
  </div>
</div>
{% endhighlight %}

### Usando atributos data

Você pode ativar uma navegação em aba ou pílula sem escrever qualquer JavaScript, simplesmente, especificando `data-toggle="tab"` ou `data-toggle="pill"`, em um elemento. Use estes atributos data em `.nav-tabs` ou `.nav-pills`.

{% highlight html %}
<!-- Abas nav -->
<ul class="nav nav-tabs" id="myTab" role="tablist">
  <li class="nav-item">
    <a class="nav-link active" id="home-tab" data-toggle="tab" href="#home" role="tab" aria-controls="home" aria-selected="true">Home</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" id="profile-tab" data-toggle="tab" href="#perfil" role="tab" aria-controls="profile" aria-selected="false">Perfil</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" id="messages-tab" data-toggle="tab" href="#messages" role="tab" aria-controls="messages" aria-selected="false">Mensagens</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" id="settings-tab" data-toggle="tab" href="#settings" role="tab" aria-controls="settings" aria-selected="false">Configurações</a>
  </li>
</ul>

<!-- Painel de abas -->
<div class="tab-content">
  <div class="tab-pane active" id="home" role="tabpanel" aria-labelledby="home-tab">...</div>
  <div class="tab-pane" id="perfil" role="tabpanel" aria-labelledby="profile-tab">...</div>
  <div class="tab-pane" id="messages" role="tabpanel" aria-labelledby="messages-tab">...</div>
  <div class="tab-pane" id="settings" role="tabpanel" aria-labelledby="settings-tab">...</div>
</div>
{% endhighlight %}

### Usando JavaScript

Ative abas dinâmicas, usando JavaScript (cada aba precisa ser ativada, individualmente):

{% highlight js %}
$('#minhaAba a').on('click', function (e) {
  e.preventDefault()
  $(this).tab('show')
})
{% endhighlight %}

Você pode ativar abas individuais, em diversas maneiras:

{% highlight js %}
$('#minhaAba a[href="#perfil"]').tab('show') // Por ID
$('#minhaAba li:first-child a').tab('show') // Ativar o primeiro elemento filho
$('#minhaAba li:last-child a').tab('show') // Ativar o último elemento filho
$('#minhaAba li:nth-child(3) a').tab('show') // Selecionar um filho específico (terceiro, neste caso)
{% endhighlight %}

### Efeito fade

Para fazer as abas terem o efeito fade in, use `.fade` em cada `.tab-pane`. O primeiro `.tab-pane` também deve ter `.show` para fazer o conteúdo inicial vísivel.

{% highlight html %}
<div class="tab-content">
  <div class="tab-pane fade show active" id="home" role="tabpanel" aria-labelledby="home-tab">...</div>
  <div class="tab-pane fade" id="perfil" role="tabpanel" aria-labelledby="profile-tab">...</div>
  <div class="tab-pane fade" id="messages" role="tabpanel" aria-labelledby="messages-tab">...</div>
  <div class="tab-pane fade" id="settings" role="tabpanel" aria-labelledby="settings-tab">...</div>
</div>
{% endhighlight %}

### Métodos

{% include callout-danger-async-methods.md %}

#### $().tab

Ativa uma aba e o container de conteúdo. Abas devem ter um `data-target` ou um `href`, remetenado a um container presente no DOM.

{% highlight html %}
<ul class="nav nav-tabs" id="myTab" role="tablist">
  <li class="nav-item">
    <a class="nav-link active" id="home-tab" data-toggle="tab" href="#home" role="tab" aria-controls="home" aria-selected="true">Home</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" id="profile-tab" data-toggle="tab" href="#perfil" role="tab" aria-controls="profile" aria-selected="false">Perfil</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" id="messages-tab" data-toggle="tab" href="#messages" role="tab" aria-controls="messages" aria-selected="false">Mensagens</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" id="settings-tab" data-toggle="tab" href="#settings" role="tab" aria-controls="settings" aria-selected="false">Configurações</a>
  </li>
</ul>

<div class="tab-content">
  <div class="tab-pane active" id="home" role="tabpanel" aria-labelledby="home-tab">...</div>
  <div class="tab-pane" id="perfil" role="tabpanel" aria-labelledby="profile-tab">...</div>
  <div class="tab-pane" id="messages" role="tabpanel" aria-labelledby="messages-tab">...</div>
  <div class="tab-pane" id="settings" role="tabpanel" aria-labelledby="settings-tab">...</div>
</div>

<script>
  $(function () {
    $('#myTab li:last-child a').tab('show')
  })
</script>
{% endhighlight %}

#### .tab('show')

Seleciona uma aba específica e mostra seu painel associado. Qualquer outra aba que foi, anteriormente, selecionada, é desselecionada e o seu painel oculto. **Retorna ao invocador, antes da aba do painel ter sido exibida, de fato** (antes do evento `shown.bs.tab` ocorrer).

{% highlight js %}
$('#algumaAba').tab('show')
{% endhighlight %}

#### .tab('dispose')

Destrói a aba de um elemento.

### Eventos

Quando mostrando uma nova aba, os eventos são acionados, na seguinte ordem:

1. `hide.bs.tab` (na aba ativa, no momento);
2. `show.bs.tab` (na aba que está para ser exibida);
3. `hidden.bs.tab` (na aba anteriormente ativa, a mesma do evento `hide.bs.tab`);
4. `shown.bs.tab` (na aba recém ativa e exibida, a mesma do evento `show.bs.tab`).

Se nenhuma aba já estava ativa, então, os eventos `hide.bs.tab` e `hidden.bs.tab` não serão acionados.

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
      <td>Este evento é acionado na exibição de aba, mas antes da nova aba ser exibida. Use <code>event.target</code> e <code>event.relatedTarget</code> para atingir a aba ativa e anteriormente ativa (se disponível), respectivamente.</td>
    </tr>
    <tr>
      <td>shown.bs.tab</td>
      <td>Este evento é acionado na exibição de aba, mas depois da exibição.  Use <code>event.target</code> e <code>event.relatedTarget</code> para atingir a aba ativa e anteriormente ativa (se disponível), respectivamente.</td>
    </tr>
    <tr>
      <td>hide.bs.tab</td>
      <td>Este evento é acionado quando uma nova aba está para ser exibida e a aba ativa, anteriormente, está para ser oculta. Use <code>event.target</code> e <code>event.relatedTarget</code> para atingir a aba, atualmente, ativa e a que está para ser ativada, respectivamente.</td>
    </tr>
    <tr>
      <td>hidden.bs.tab</td>
      <td>Este evento é acionado depois que uma nova aba é exibida e, portanto, a aba ativa anteriormente é oculta. Use <code>event.target</code> e <code>event.relatedTarget</code> para atingir a aba, anteriormente, ativa e a nova aba ativa, respectivamente.</td>
    </tr>
  </tbody>
</table>

{% highlight js %}
$('a[data-toggle="tab"]').on('shown.bs.tab', function (e) {
  e.target // aba que acabou de ser ativada
  e.relatedTarget // aba, anteriormente, ativa
})
{% endhighlight %}

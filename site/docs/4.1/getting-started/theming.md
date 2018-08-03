---
layout: docs
title: Customização de temas Bootstrap
description: Utilize variáveis Sass do Bootstrap 4 para construir, fácilmente, temas e componentes customizados.
group: getting-started
toc: true
redirect_from: "/docs/4.1/getting-started/options/"
---

## Introdução

No Bootstrap 3, tematizações foram amplamente feitas com sobrescrição de variáveis LESS, CSS customizado e uma folha de estilos separada que nós incluíamos nos nossos arquivos `dist`. Com algum esforço, qualquer um podia redesenhar o visual do Bootstrap 3, sem tocar em seus principais arquivos. Já o Bootstrap 4 tem uma abordagem familiar, mas um pouco diferente.

Agora, tematizações são feitas com variáveis e mapas Sass, além de CSS customizado. Não existe mais, uma folha de estilos tema dedicada.

## Sass

Utilize nossos arquivos fonte Sass para aproveitar as variáveis, mapas, mixins e muito mais.

### Estrutura de arquivos

Sempre que possível, evite modificar os arquivos principais do Bootstrap. No Sass, isso significa que precisará criar sua própria folha de estilos e importar o Bootstrap, para que você possa modificar e extendê-lo. Assumindo que você usa um gerenciador de pacotes como o npm, terá uma estrutura de arquivos parecida com essa:

{% highlight plaintext %}
seu-projeto/
├── scss
│   └── custom.scss
└── node_modules/
    └── bootstrap
        ├── js
        └── scss
{% endhighlight %}

Se você baixou nossos arquivos fonte e não está usando um gerenciador de pacotes, vai querer fazer algo semelhante a essa estrutura, manualmente, mantendo os arquivos fontes separados dos seus.

{% highlight plaintext %}
seu-projeto/
├── scss
│   └── custom.scss
└── bootstrap/
    ├── js
    └── scss
{% endhighlight %}

### Importando

No seu `custom.scss`, você vai importar os arquivos Sass Bootstrap. Nesse sentido, você terá duas opções: incluir todo o Bootstrap ou apenas as partes que você precisa. Nós encorajamos que pegue somente aquilo que necessite, mas fique atento que há alguns requisitos e dependências, nos componentes. Você também vai precisar adicionar alguns JavaScripts para nossos plugins.

{% highlight scss %}
// Custom.scss
// Opção A: Importa todo o Bootstrap

@import "../node_modules/bootstrap/scss/bootstrap";
{% endhighlight %}

{% highlight scss %}
// Custom.scss
// Opção B: Importa partes do Bootstrap

Partes obrigatórias
@import "../node_modules/bootstrap/scss/functions";
@import "../node_modules/bootstrap/scss/variables";
@import "../node_modules/bootstrap/scss/mixins";

// Partes opcionais
@import "../node_modules/bootstrap/scss/reboot";
@import "../node_modules/bootstrap/scss/type";
@import "../node_modules/bootstrap/scss/images";
@import "../node_modules/bootstrap/scss/code";
@import "../node_modules/bootstrap/scss/grid";
{% endhighlight %}

Com essa configuração, você pode começar a modificar quaisquer variáveis e mapas Sass, no seu `custom.scss`. Você também pode começar a adicionar partes do Bootstrap, abaixo do comentário "`// Partes adicionais`", sempre que necessário. Nós sugerimos usar toda a pilha de importação do nosso arquivo `bootstrap.scss`, como seu ponto inicial.

### Variáveis padrão

Toda variável Sass no Bootstrap 4 possui uma _flag_ `!default`, permitindo que você sobrescreva o valor da variável padrão, no seu próprio Sass, sem modificar o código fonte Bootstrap. Copie, cole e modifique os valores das variáveis, sempre que precisar. Sem falar que você também pode remover a flag `!default` de variáveis. Se uma variável já recebeu um valor, então, ela não vai ter uma nova atribuição de valores padrões Bootstrap.

Você vai achar uma lista completa das variáveis Bootstrap, no diretório `scss/_variables.scss`.

Sobrescrição de variáveis dentro do mesmo arquivo Sass pode acontecer antes ou depois das variáveis padrões. Contudo, quando for fazer sobrescrições em arquivos Sass, suas sobrescrições devem vir antes de você importar arquivos Sass do Bootstrap.

Aqui vai um exemplo que muda as propriedades `background-color` e `color` do `<body>`, quando for importar e compilar Bootstrap via npm:

{% highlight scss %}
// Suas sobrescrições de variáveis
$body-bg: #000;
$body-color: #111;

//Bootstrap e suas variáveis padrões
@import "../node_modules/bootstrap/scss/bootstrap";
{% endhighlight %}

Faça isso o quanto quiser, para qualquer variável Bootstrap, incluindo a opção global abaixo.

### Mapas e loops

Bootstrap 4 possui um punhado de mapas Sass, os quais são pares de chave-valor que facilitam gerar famílias de CSS relacionados. Nós usamos mapas Sass para nossas cores, breakpoints grid e etc. Assim como as variáveis Sass, todos os mapas Sass possuem a _flag_ `!default` e podem ser sobrescritos e extendidos.

Alguns de nossos mapas Sass são fundidos em outros vazios, por padrão. Isto é feito para permitir uma fácil expansão de um dado mapa Sass, apesar de, consequentemente, ser um pouco mais difícil remover ítens de um mapa.

#### Alterando o mapa

Para modificar uma cor existente no nosso mapa `$theme-colors`, você pode adicionar o seguinte ao seu arquivo Sass customizado:

{% highlight scss %}
$theme-colors: (
  "primary": #0074d9,
  "danger": #ff4136
);
{% endhighlight %}

#### Adicionando ao mapa

para adicionar uma nova cor ao `$theme-colors`, adicione a nova chave e valor:

{% highlight scss %}
$theme-colors: (
  "custom-color": #900
);
{% endhighlight %}

#### Removendo do mapa

Para remover cores do `$theme-colors` ou qualquer outro mapa, use `map-remove`. No entanto, certifique-se de inserir isso entre as partes obrigatórias e opcionais:

{% highlight scss %}
// Partes obrigatórias
@import "../node_modules/bootstrap/scss/functions";
@import "../node_modules/bootstrap/scss/variables";
@import "../node_modules/bootstrap/scss/mixins";

$theme-colors: map-remove($theme-colors, "info", "light", "dark");

// Partes adicionais
@import "../node_modules/bootstrap/scss/root";
@import "../node_modules/bootstrap/scss/reboot";
@import "../node_modules/bootstrap/scss/type";
...
{% endhighlight %}

#### Chaves obrigatórias

Bootstrap espera que existam algumas chaves específicas, já que usamos e extendemos elas para construírmos o framework, nós mesmos. Por isso, assim que você for customizando os mapas, pode encontrar erros em que uma chave específica está sendo usada.

Por exemplo, nós usamos as chaves `primary`, `success` e `danger` do mapa `$theme-colors`, para links, botões e estados de formulários. Substituir os valores dessas chaves não deve apresentar problemas, mas removê-las pode causar problemas na compilação Sass. Nesses casos, você precisará modificar o código Sass que faz uso destes valores.

### Funções

Bootstrap usa diversas funções Sass, mas só algumas delas são aplicáveis em tematização. Nós usamos três funções para obter valores dos mapas de cores:

{% highlight scss %}
@function color($key: "blue") {
  @return map-get($colors, $key);
}

@function theme-color($key: "primary") {
  @return map-get($theme-colors, $key);
}

@function gray($key: "100") {
  @return map-get($grays, $key);
}
{% endhighlight %}

Isso permite que obtenha uma cor de um mapa Sass, da mesma maneira que você usava uma variável de cor, na versão 3.

{% highlight scss %}
.elemento-personalizado {
  color: gray("100");
  background-color: theme-color("dark");
}
{% endhighlight %}

Nós também temos outra função para recuperar um nível de cor específico do mapa `$theme-colors`. Níveis com valores negativos vão esclarecer a cor, enquanto níveis maiores vão escurecer.

{% highlight scss %}
@function theme-color-level($color-name: "primary", $level: 0) {
  $color: theme-color($color-name);
  $color-base: if($level > 0, #000, #fff);
  $level: abs($level);

  @return mix($color-base, $color, $level * $theme-color-interval);
}
{% endhighlight %}

Na prática, você chamaria a função e passaria dois argumentos: o nome da cor do `$theme-colors` (ex: primary e danger) e um valor numérico.

{% highlight scss %}
.elemento-personalizado {
  color: theme-color-level(primary, -10);
}
{% endhighlight %}

Outras funções podem ser adicionadas, futuramente, ou use seu próprio Sass para criar funções de nível para outros mapas Sass.

### Contraste de cor

Uma outra função que temos no Bootstrap é aquela para contraste de cores: `color-yiq`. Ela usa o [YIQ color space](https://en.wikipedia.org/wiki/YIQ) para, automaticamente, retornar um contraste de cores claras (`#fff`) ou escuras (`#111`), baseado na cor especificada. Esta função é, especialmente, útil para mixins ou loops quando for gerar múltiplas classes.

Por exemplo, para gerar amostras de cores a partir do nosso mapa `$theme-colors`, use isso:

{% highlight scss %}
@each $color, $value in $theme-colors {
  .swatch-#{$color} {
    color: color-yiq($value);
  }
}
{% endhighlight %}

Ela também pode ser usada para retornar o contraste de uma única cor:

{% highlight scss %}
.elemento-personalizado {
  color: color-yiq(#000); // retorna `color: #fff`
}
{% endhighlight %}

Você também pode especificar uma cor base, com nossas funções de mapa de cores:

{% highlight scss %}
.elemento-personalizado {
  color: color-yiq(theme-color("dark")); // retorna `color: #fff`
}
{% endhighlight %}

## Opções do Sass

Personalize o Bootstrap 4 com nosso arquivo customizado de variáveis e, facilmente, alterne configurações CSS globais com as novas variáveis Sass `$enable-*`. Sobrescreva o valor da variável e recompile com `npm run test`, sempre que precisar.

Você pode achar e personalizar estas variáveis para opções globais, no arquivo Bootstrap `scss/_variables.scss`.

| Variável                    | Valores                             | Descrição                                                                            |
| --------------------------- | ---------------------------------- | -------------------------------------------------------------------------------------- |
| `$spacer`                   | `1rem` é o padrão, mas também pode-se utilizar valores maior que 0. | Especifíca o valor padrão para gerar os [utilitário de espaçamento]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/spacing/), programaticamente. |
| `$enable-rounded`           | `true` (padrão) ou `false`        | Ativa estilos `border-radius` pré-definidos, em vários componentes. |
| `$enable-shadows`           | `true` ou `false` (padrão)        | Ativa estilos `box-shadow` pré-definidos, em vários componentes. |
| `$enable-gradients`         | `true` ou `false` (padrão)        | Ativa gradientes pré-definidos via estilos `background-image`, em vários componentes. |
| `$enable-transitions`       | `true` (padrão) ou `false`        | Ativa `transições` pré-definidas, em vários componentes. |
| `$enable-hover-media-query` | `true` ou `false` (padrão)        | **Defasado** |
| `$enable-grid-classes`      | `true` (padrão) ou `false`        | Ativa a geração de classes CSS para o grid (ex: `.container`, `.row`, `.col-md-1`, etc). |
| `$enable-caret`             | `true` (padrão) ou `false`        | Ativa a setinha do `.dropdown-toggle` usando pseudo-elementos. |
| `$enable-print-styles`      | `true` (padrão) ou `false`        | Ativa estilos para otimizar impressões. |
| `$enable-validation-icons`  | `true` (default) or `false`       | Enables `background-image` icons within textual inputs and some custom forms for validation states. |

## Cor

Muitos dos componentes e utilitários Bootstrap são construídos com uma série de cores definidas em mapas Sass. Estes mapas podem ser iterados para, rapidamente, gerar vários blocos de regras.

### Todas as cores

Todas as cores disponíveis no Bootstrap 4 também estão disponíveis nas variáveis e no mapa Sass, dentro do arquivo `scss/_variables.scss`. Isso será expandido, nos próximos pequenos releases com tons adicionais, como a [escala de cores cinzas](#grays) que já incluímos.

<div class="row">
  {% for color in site.data.colors %}
    {% unless color.name == "white" or color.name == "gray" or color.name == "gray-dark" %}
    <div class="col-md-4">
        <div class="p-3 mb-3 swatch-{{ color.name }}">{{ color.name | capitalize }}</div>
    </div>
    {% endunless %}
  {% endfor %}
</div>

É assim que você pode usar isso, no seu Sass:

{% highlight scss %}
// Com variáveis
.alpha { color: $purple; }

// Usando o mapa Sass, com nossa função `color()`
.beta { color: color("purple"); }
{% endhighlight %}

[Classes utilitárias de cores]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/colors/) também estão disponíveis para definir o valor de `color` e `background-color`.

{% capture callout %}
No futuro, vamos se concentrar em prover mapas e variáveis Sass para os tons de cada cor, assim como fizemos com a escala de cinza abaixo.
{% endcapture %}
{% include callout.html content=callout type="info" %}

### Cores do tema

Usamos um subconjunto de todas as cores para criar uma paleta de cores menor e gerar um esquemas de cores, também disponíveis em variáveis e mapas Sass, no arquivo Bootstrap `scss/_variables.scss`.

<div class="row">
  {% for color in site.data.theme-colors %}
    <div class="col-md-4">
      <div class="p-3 mb-3 swatch-{{ color.name }}">{{ color.name | capitalize }}</div>
    </div>
  {% endfor %}
</div>

### Tons de cinza

Um grande conjunto de variáveis e mapas Sass, no arquivo `scss/_variables.scss`, para tons de cinzas consistentes nos seus projetos.

<div class="row mb-3">
  <div class="col-md-4">
    {% for color in site.data.grays %}
      <div class="p-3 swatch-{{ color.name }}">{{ color.name | capitalize }}</div>
    {% endfor %}
  </div>
</div>

Dentro do arquivo  `scss/_variables.scss`, você vai achar as variáveis e mapas de cores Bootstrap. Aqui está um exemplo do mapa `$colors`:

{% highlight scss %}
$colors: (
  "blue": $blue,
  "indigo": $indigo,
  "purple": $purple,
  "pink": $pink,
  "red": $red,
  "orange": $orange,
  "yellow": $yellow,
  "green": $green,
  "teal": $teal,
  "cyan": $cyan,
  "white": $white,
  "gray": $gray-600,
  "gray-dark": $gray-800
) !default;
{% endhighlight %} 

Adicione, remova ou modifique valores dentro do mapa, para atualizar o uso deles em outros componentes. Infelizmente, atualmente, _nem todos_ componentes utiliza este mapa Sass. Futuras atualizações vão tentar melhorar essa situação. No entanto, até lá, planeje o uso deste mapa e de variáveis de cores.

## Componentes

Muitos componentes e utilitários Bootstrap são construídos com loops `@each`, os quais iteram sobre um mapa Sass. Isso é, especialmente, útil para gerar variantes de um componente com nosso `$theme-colors` e criando variantes responsivos para cada breakpoint. Assim que você personalizar estes mapas Sass e recompilar, verá suas mudanças refletidas nestes loops, automaticamente.

### Modificadores

Muitos dos componentes Bootstrap são construídos com uma abordagem de classe-modificadora. Isso significa que o grosso da estilização está em uma classe base (ex: `.btn`), enquanto variações de estilos estão em classes modificadoras, como `.btn-danger`. Estas classes modificadoras são feitas a partir do mapa `$theme-colors`, para personalizar a quantidade e nomes delas.

Aqui está dois exemplos de como nós iteramos o mapa `$theme-colors` para gerar modificadores do componente `.alert` e todos nossos utilitários de background `.bg-*`.

{% highlight scss %}
// Gera classes modificadoras de alertas
@each $color, $value in $theme-colors {
  .alert-#{$color} {
    @include alert-variant(theme-color-level($color, -10), theme-color-level($color, -9), theme-color-level($color, 6));
  }
}

// Gera utilitários de cores para `.bg-*`
@each $color, $value in $theme-colors {
  @include bg-variant('.bg-#{$color}', $value);
}
{% endhighlight %}

### Responsivo

Estes loops Sass não são limitados a mapas de cores. Você também pode gerar variações responsivas de seus componentes e utilitários. Por exemplo, pegue nossos utilitários para alinhamento de texto, onde nós misturamos um loop `@each` para o mapa Sass `$grid-breakpoins`, o qual possui integrações de media queries.

{% highlight scss %}
@each $breakpoint in map-keys($grid-breakpoints) {
  @include media-breakpoint-up($breakpoint) {
    $infix: breakpoint-infix($breakpoint, $grid-breakpoints);

    .text#{$infix}-left   { text-align: left !important; }
    .text#{$infix}-right  { text-align: right !important; }
    .text#{$infix}-center { text-align: center !important; }
  }
}
{% endhighlight %}

Se precisar alterar seu `$grid-breakpoints`, suas modificações serão aplicadas a todos os loops iterando neste mapa.

## Variáveis CSS

Bootstrap 4 inclui cerca de duas dúzias de [propriedades CSS personalizadas (variáveis)](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_variables), em seu CSS compilado. Elas provêm fácil acsso a valores comumente usados, como nossas cores de tema, breakpoints e pilhas de fontes primárias (para quando estiver trabalhando no inspetor do browser, sandbox de código ou uma prototipagem qualquer).

### Variáveis disponíveis

Aqui estão as variáveis que incluímos (perceba que o `:root` é obrigatório). Elas estão localizadas no nosso arquivo `_root.scss`.

{% highlight css %}
:root {
  --blue: #007bff;
  --indigo: #6610f2;
  --purple: #6f42c1;
  --pink: #e83e8c;
  --red: #dc3545;
  --orange: #fd7e14;
  --yellow: #ffc107;
  --green: #28a745;
  --teal: #20c997;
  --cyan: #17a2b8;
  --white: #fff;
  --gray: #6c757d;
  --gray-dark: #343a40;
  --primary: #007bff;
  --secondary: #6c757d;
  --success: #28a745;
  --info: #17a2b8;
  --warning: #ffc107;
  --danger: #dc3545;
  --light: #f8f9fa;
  --dark: #343a40;
  --breakpoint-xs: 0;
  --breakpoint-sm: 576px;
  --breakpoint-md: 768px;
  --breakpoint-lg: 992px;
  --breakpoint-xl: 1200px;
  --font-family-sans-serif: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol";
  --font-family-monospace: SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", "Courier New", monospace;
}
{% endhighlight %}

### Exemplos

Variáveis CSS oferecem uma flexibilidade similar as do Sass, mas sem precisar compilar antes de usar no navegador. Por exemplo, com isso estamos resetando os estilos de fonte e links de nossa página, com variáveis CSS:

{% highlight css %}
body {
  font: 1rem/1.5 var(--font-family-sans-serif);
}
a {
  color: var(--blue);
}
{% endhighlight %}

### Variáveis de breakpoint

Apesar de, originalmente, termos incluídos breakpoints em nossas variáveis CSS (ex: `--breakpoint-md`), **elas não são suportadas dentro de media queries**, mas ainda podem ser usadas dentro de bloco de regras, nas media queries. Estas variáveis de breakpoint permanecem no CSS compilado, para retro-compatibilidade (dado que podem ser utilizadas pelo JavaScript). [Leia mais na especificação](https://www.w3.org/TR/css-variables-1/#using-variables)!

Aqui está um exemplo de **oquê não é suportado:**

{% highlight css %}
@media (min-width: var(--breakpoint-sm)) {
  ...
}
{% endhighlight %}

E aqui está um exemplo de **oquê é suportado:**

{% highlight css %}
@media (min-width: 768px) {
  .elemento-personalizado {
    color: var(--primary);
  }
}
{% endhighlight %}

---
layout: docs
title: Browsers e dispositivos
description: Aprenda sobre os browsers e dispositivos (dos modernos até os antigos) que suportam o Bootstrap, incluindo quirks e bugs conhecidos, em cada.
group: getting-started
toc: true
---

## Suporte de browsers

Bootstrap é suportado pelas versões mais **recentes e estáveis** dos maiores navegadores e plataformas. No Windows, somos suportados pelo **Internet Explorer 10, 11 e Microsoft Edge**.

Navegadores alternativos que usam a versão mais recente do WebKit, Blink ou Gecko (tanto diretamente, quanto através da API web view da plataforma) não suportam explicitamente o Bootstrap. Contudo, o framework funciona normalmente (na maioria dos casos) nesses browsers. Informações mais específicas a respeito estão abaixo.

Você pode consultar nosso leque de browsers com suporte e suas versões no nosso [`package.json`]({{ site.repo }}/blob/v4-dev/package.json):

```json
"browserslist": [
  "last 1 major version",
  ">= 1%",
  "Chrome >= 45",
  "Firefox >= 38",
  "Edge >= 12",
  "Explorer >= 10",
  "iOS >= 9",
  "Safari >= 9",
  "Android >= 4.4",
  "Opera >= 30"
]
```

Nós usamos o [Autoprefixer](https://github.com/postcss/autoprefixer) para obter o suporte esperado (usando prefixos CSS), o qual usa [Browserslist](https://github.com/browserslist/browserslist) para gerenciar as versões destes navegadores.

### Dispositivos móveis

No geral, Bootstrap é suportado pelas versões mais recentes das maiores plataformas padrões dos browsers. No entanto, lembre-se que _proxy browsers_ (como o Opera Mini, modo turbo do Opera Mobile, UC Browser Mini, Amazon Silk) não são suportados.

<table class="table table-bordered table-striped">
  <thead>
    <tr>
      <td></td>
      <th>Chrome</th>
      <th>Firefox</th>
      <th>Safari</th>
      <th>Android Browser &amp; WebView</th>
      <th>Microsoft Edge</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">Android</th>
      <td class="text-success">Suportado</td>
      <td class="text-success">Suportado</td>
      <td class="text-muted">N/A</td>
      <td class="text-success">Android v5.0+ Suportado</td>
      <td class="text-success">Suportado</td>
    </tr>
    <tr>
      <th scope="row">iOS</th>
      <td class="text-success">Suportado</td>
      <td class="text-success">Suportado</td>
      <td class="text-success">Suportado</td>
      <td class="text-muted">N/A</td>
      <td class="text-success">Suportado</td>
    </tr>
    <tr>
      <th scope="row">Windows 10 Móvel</th>
      <td class="text-muted">N/A</td>
      <td class="text-muted">N/A</td>
      <td class="text-muted">N/A</td>
      <td class="text-muted">N/A</td>
      <td class="text-success">Suportado</td>
    </tr>
  </tbody>
</table>

### Browsers desktop

De forma parecida, as versões mais recentes da maioria dos navegadores desktops são suportadas.

<table class="table table-bordered table-striped">
  <thead>
    <tr>
      <td></td>
      <th>Chrome</th>
      <th>Firefox</th>
      <th>Internet Explorer</th>
      <th>Microsoft Edge</th>
      <th>Opera</th>
      <th>Safari</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">Mac</th>
      <td class="text-success">Suportado</td>
      <td class="text-success">Suportado</td>
      <td class="text-muted">N/A</td>
      <td class="text-muted">N/A</td>
      <td class="text-success">Suportado</td>
      <td class="text-success">Suportado</td>
    </tr>
    <tr>
      <th scope="row">Windows</th>
      <td class="text-success">Suportado</td>
      <td class="text-success">Suportado</td>
      <td class="text-success">Suportado, IE10+</td>
      <td class="text-success">Suportado</td>
      <td class="text-success">Suportado</td>
      <td class="text-danger">Not Suportado</td>
    </tr>
  </tbody>
</table>

No Firefox, em adição ao release mais recente e estável, nós também temos suporte da recente versão "[Extended Support Release (ESR)](https://www.mozilla.org/en-US/firefox/organizations/#faq)".

Não oficialmente, Bootstrap vai se apresentar e comportar bem no Chromium, Chrome e Firefox para Linux, além do Internet Explorer 9 (apesar de não termos suporte oficial).

Para consultar alguns bugs que o Bootstrap enfrenta, veja nosso [Mural de bugs]({{ site.baseurl }}/docs/{{ site.docs_version }}/browser-bugs/).

## Internet Explorer

Do Internet Explorer 10 acima, nós temos suporte. No entanto, do IE9 para baixo, não temos. Portanto, esteja atento que algumas propriedades CSS3 e elementos HTML5 não são, totalmente, suportadas no IE10 ou requerem prefixos para compatilidade. Visite o site [Can I use...](https://caniuse.com/) para detalhes sobre suporte CSS3 em browsers e recursos HTML5.

**Se você precisa de suporte no IE8 ou 9, use o Bootstrap 3**. É a versão mais estável do nosso código e nosso time ainda dá suporte para reparar bugs críticos e alterar a documentação. Contudo, nem um recurso novo será adicionado a ela.

## Modais e dropdowns em dispositivos móveis

### Overflow e rolagem

Suporte para `overflow: hidden;` no elemento `<body>` é um pouco limitado, no iOS e Android. Nesse sentido, quando você rola perto da parte superior ou inferior do modal (em algum dos browsers destes dispositivos), o conteúdo do `<body>` vai começar a rolar. Veja o [bug do Chrome #175502](https://bugs.chromium.org/p/chromium/issues/detail?id=175502) (reparado no Chrome v40) e o [bug Webkit #153852](https://bugs.webkit.org/show_bug.cgi?id=153852).

### Campos de texto e rolagem no iOS

A partir do iOS 9.2, enquanto o modal está aberto, se o toque inicial do gesto de rolagem está dentro dos limites de um `<input>` de texto ou `<textarea>`, o conteúdo do `<body>` abaixo do modal vai ser rolado, invés do modal. Veja o [bug Webkit #153856](https://bugs.webkit.org/show_bug.cgi?id=153856).

### Dropdowns navbar

O elemento `.dropdown-backdrop` não é usando no iOS, por causa da complexidade do z-index. Portanto, para fechar dropdowns em navbars, você deve clicar diretamente no elemento dropdown ou [qualquer outro elemento que vai acionar o evento de clique no iOS](https://developer.mozilla.org/en-US/docs/Web/Events/click#Safari_Mobile)).

## Zoom em browsers

Dar zoom em páginas irá mostrar, inevitavelmente, artefatos de renderização em alguns componentes, tanto no Bootstrap quando no resto da web. Dependendo do problema, poderemos consertá-lo, bastando pesquisar antes e depois abrir um issue (se necessário). Contudo, nós tendemos a ignorar estes problemas, já que eles não possuem soluções diretas, aléms de hacks, normalmente.

## Sticky `:hover`/`:focus` no iOS

Enquanto o `:hover` não é possível na maioria dos dispositivos de toque, o iOS emula este comportamento, resultando em estilos que persistem depois de soltar um elemento. Estes estilos hover só são interrompidos quando o usuário toca outro elemento. Este comportamento é considerado, largamente, indesejável e aparenta não ser um problema nos dispositivos Android ou Windows.

Durante nossos realeases v4 alpha e beta, nós incluímos códigos incompletos e comentados para dar a opção de usar uma media query que desativaria estilos hover em dispositivos de toque que emulam estes estilos. Isto nunca foi finalizado ou ativado, mas para evitar quebra total, nós optamos em defazar [isto](https://github.com/twbs/mq4-hover-shim) e manter os mixins como atalhos para as pseudo-classes.

## Impressão

Mesmo em alguns browsers modernos, imprimir pode ser bem chatinho.

A partir do Safari v8.0, o uso da classe `.container` pode levar o Safari a usar pequenos tamanhos de fontes, quando imprimindo. Veja o [issue #14868]({{ site.repo }}/issues/14868) e [WebKit bug #138192](https://bugs.webkit.org/show_bug.cgi?id=138192), para mais detalhes. Uma possível solução alternativa é o seguinte CSS:

{% highlight css %}
@media print {
  .container {
    width: auto;
  }
}
{% endhighlight %}

## Browser padrão do Android

O Android 4.1 e algumas versões mais recentes são lançadas com um app Browser padrão, que não é o Chrome. Infelizmente, o app Browser tem muitos bugs e inconsistências com CSS.

#### Menu Select

Em elementos `<select>`, o app Browser não irá mostrar os controles laterais se houver `border-radius` ou `border` aplicadas (veja [esta questão no StackOverflow](https://stackoverflow.com/questions/14744437/html-select-box-not-showing-drop-down-arrow-on-android-version-4-0-when-set-with), para mais detalhes). Use o snippet abaixo para remover o CSS problemático e renderizar o `<select>` como um elemento não estilizado, no app Browser do Android. O sniffer do user agent evita interferência com o Chrome, Safari e navegadores Mozilla.

{% highlight html %}
<script>
$(function () {
  var nua = navigator.userAgent
  var isAndroid = (nua.indexOf('Mozilla/5.0') > -1 && nua.indexOf('Android ') > -1 && nua.indexOf('AppleWebKit') > -1 && nua.indexOf('Chrome') === -1)
  if (isAndroid) {
    $('select.form-control').removeClass('form-control').css('width', '100%')
  }
})
</script>
{% endhighlight %}

Quer ver um exemplo? [Veja esta demo no JS Bin](http://jsbin.com/OyaqoDO/2).

## Validação

Pensando em dar a melhor experiência para os antigos e bugados browsers, Bootstrap usa [hacks CSS](http://browserhacks.com/) em diversos locais para conseguir um CSS único em algumas versões de browsers e, consequentemente, trabalhar em cima dos próprios bugs. Estes hacks, compreensivelmente, levam os validadores CSS a falarem que o código está inválido. Em outros locais, nós também usamos recursos CSS inovadores que ainda não foram padronizados. No entanto, eles são usados puramente para _progressive enhancement_.

Estes avisos de validação não significam nada na prática, já que a parte sem hacks valida normalmente e a parte com hacks não interfere no funcionamente da parte sem hacks. Portanto, se ignorarmos estes avisos, a parte com hacks é usada em _progressive enhancement_.

Nossa documentação HTML, da mesma forma tem alguns avisos de validação triviais e inconsequentes, devido a inclusão de uma solução para um certo [bug no Firefox](https://bugzilla.mozilla.org/show_bug.cgi?id=654072).

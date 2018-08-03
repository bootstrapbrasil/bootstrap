---
layout: docs
title: Carousel
description: Um componente de slideshow para fazer um giro através de elementos (imagens ou slides de texto), como se fosse um carrosel.
group: components
toc: true
---

## Como funciona

O carousel é um slideshow para fazer um giro em vários coteúdos, construído com CSS 3D transforms e um pouco de JavaScript. Ele funciona com o uso de imagens, texto ou marcação personalizada. Também possui suporte para controles anterior, próximo e indicadores.

Nos navegadores onde a [API Page Visibility](https://www.w3.org/TR/page-visibility/) é suportada, o carousel vai evitar deslizar quando a página não está visível para o usuário (como quando o browser está inativo, janela minimizada, etc).

Por favor, esteja atento que carousels aninhados não são suportados e não são, geralmente, amigáveis aos padrões de acessibilidades.

Por último, se você está construindo nosso JavaScript a partir da fonte, vai precisar do [`util.js`]({{ site.baseurl }}/docs/{{ site.docs_version }}/getting-started/javascript/#util).

## Exemplo

Carousels não normalizam dimensões, automaticamente. Assim, você pode precisar usar utilitários adicionais ou estilos personalizados para dimensionar conteúdos, apropriadamente. Apesar de carousels suportarem controles anterior, próximo e indicadores, eles não são obrigatórios, necessariamente. Use e abuse, como quiser.

**A classe `.active` precisa ser usada em um dos slides,** caso contrário, o carousel não ficará visível. Também, se assegure de definir um único ID no `.carousel` para os controles opcionais, especialmente, se você está usando múltiplos carousels em uma página. Elementos de controle e indicador devem ter um atributo `data-target` (ou links `href`) que combinam com o ID do elemento `.carousel`.

### Só slides

Aqui está um carousel só com slides. Perceba a presença do `.d-block` e `.w-100` nas imagens do carousel para evitar alinhamento padrão de imagens do navegador.

{% capture example %}
<div id="carouselExampleSlidesOnly" class="carousel slide" data-ride="carousel">
  <div class="carousel-inner">
    <div class="carousel-item active">
      <img class="d-block w-100" data-src="holder.js/800x400?auto=yes&bg=777&fg=555&text=Primeiro Slide" alt="Primeiro Slide">
    </div>
    <div class="carousel-item">
      <img class="d-block w-100" data-src="holder.js/800x400?auto=yes&bg=666&fg=444&text=Segundo Slide" alt="Segundo Slide">
    </div>
    <div class="carousel-item">
      <img class="d-block w-100" data-src="holder.js/800x400?auto=yes&bg=555&fg=333&text=Terceiro Slide" alt="Terceiro Slide">
    </div>
  </div>
</div>
{% endcapture %}
{% include example.html content=example %}

### Com controles

Adicionando os controles anterior e próximo, temos isso:

{% capture example %}
<div id="carouselExampleControls" class="carousel slide" data-ride="carousel">
  <div class="carousel-inner">
    <div class="carousel-item active">
      <img class="d-block w-100" data-src="holder.js/800x400?auto=yes&bg=777&fg=555&text=Primeiro Slide" alt="Primeiro Slide">
    </div>
    <div class="carousel-item">
      <img class="d-block w-100" data-src="holder.js/800x400?auto=yes&bg=666&fg=444&text=Segundo Slide" alt="Segundo Slide">
    </div>
    <div class="carousel-item">
      <img class="d-block w-100" data-src="holder.js/800x400?auto=yes&bg=555&fg=333&text=Terceiro Slide" alt="Terceiro Slide">
    </div>
  </div>
  <a class="carousel-control-prev" href="#carouselExampleControls" role="button" data-slide="prev">
    <span class="carousel-control-prev-icon" aria-hidden="true"></span>
    <span class="sr-only">Anterior</span>
  </a>
  <a class="carousel-control-next" href="#carouselExampleControls" role="button" data-slide="next">
    <span class="carousel-control-next-icon" aria-hidden="true"></span>
    <span class="sr-only">Próximo</span>
  </a>
</div>
{% endcapture %}
{% include example.html content=example %}

### Com indicadores

Você também pode adicionar indicadores ao carousel, além dos controles.

{% capture example %}
<div id="carouselExampleIndicators" class="carousel slide" data-ride="carousel">
  <ol class="carousel-indicators">
    <li data-target="#carouselExampleIndicators" data-slide-to="0" class="active"></li>
    <li data-target="#carouselExampleIndicators" data-slide-to="1"></li>
    <li data-target="#carouselExampleIndicators" data-slide-to="2"></li>
  </ol>
  <div class="carousel-inner">
    <div class="carousel-item active">
      <img class="d-block w-100" data-src="holder.js/800x400?auto=yes&bg=777&fg=555&text=Primeiro Slide" alt="Primeiro Slide">
    </div>
    <div class="carousel-item">
      <img class="d-block w-100" data-src="holder.js/800x400?auto=yes&bg=666&fg=444&text=Segundo Slide" alt="Segundo Slide">
    </div>
    <div class="carousel-item">
      <img class="d-block w-100" data-src="holder.js/800x400?auto=yes&bg=555&fg=333&text=Terceiro Slide" alt="Terceiro Slide">
    </div>
  </div>
  <a class="carousel-control-prev" href="#carouselExampleIndicators" role="button" data-slide="prev">
    <span class="carousel-control-prev-icon" aria-hidden="true"></span>
    <span class="sr-only">Anterior</span>
  </a>
  <a class="carousel-control-next" href="#carouselExampleIndicators" role="button" data-slide="next">
    <span class="carousel-control-next-icon" aria-hidden="true"></span>
    <span class="sr-only">Próximo</span>
  </a>
</div>
{% endcapture %}
{% include example.html content=example %}

### Com legenda

Adicione legendas nos seus slides, facilmente, usando o elemento `.carousel-caption` dentro de qualquer `.carousel-item`. Eles podem ser escondidos, facilmente, em qualquer viewport menor, como mostrado é mostrado abaixo, usando [utilitários display]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/display/). Escondemos eles, inicialmente, com `.d-none` e trazemos de volta em dispositivos de tamanho mediano, usando `.d-md-block`.

<div class="bd-example">
  <div id="carouselExampleCaptions" class="carousel slide" data-ride="carousel">
    <ol class="carousel-indicators">
      <li data-target="#carouselExampleCaptions" data-slide-to="0" class="active"></li>
      <li data-target="#carouselExampleCaptions" data-slide-to="1"></li>
      <li data-target="#carouselExampleCaptions" data-slide-to="2"></li>
    </ol>
    <div class="carousel-inner">
      <div class="carousel-item active">
        <img class="d-block w-100" data-src="holder.js/800x400?auto=yes&bg=777&fg=555&text=Primeiro Slide" alt="Primeiro Slide">
        <div class="carousel-caption d-none d-md-block">
          <h5>Título do primeiro slide</h5>
          <p>Nulla vitae elit libero, a pharetra augue mollis interdum.</p>
        </div>
      </div>
      <div class="carousel-item">
        <img class="d-block w-100" data-src="holder.js/800x400?auto=yes&bg=666&fg=444&text=Segundo Slide" alt="Segundo Slide">
        <div class="carousel-caption d-none d-md-block">
          <h5>Título do segundo slide</h5>
          <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
        </div>
      </div>
      <div class="carousel-item">
        <img class="d-block w-100" data-src="holder.js/800x400?auto=yes&bg=555&fg=333&text=Terceiro Slide" alt="Terceiro Slide">
        <div class="carousel-caption d-none d-md-block">
          <h5>Título do terceiro slide</h5>
          <p>Praesent commodo cursus magna, vel scelerisque nisl consectetur.</p>
        </div>
      </div>
    </div>
    <a class="carousel-control-prev" href="#carouselExampleCaptions" role="button" data-slide="prev">
      <span class="carousel-control-prev-icon" aria-hidden="true"></span>
      <span class="sr-only">Anterior</span>
    </a>
    <a class="carousel-control-next" href="#carouselExampleCaptions" role="button" data-slide="next">
      <span class="carousel-control-next-icon" aria-hidden="true"></span>
      <span class="sr-only">Próximo</span>
    </a>
  </div>
</div>

{% highlight html %}
<div class="carousel-item">
  <img src="..." alt="...">
  <div class="carousel-caption d-none d-md-block">
    <h5>...</h5>
    <p>...</p>
  </div>
</div>
{% endhighlight %}

### Crossfade

Use `.carousel-fade` no seu carousel para animar os slides com uma transição esmaecida, invés de um simples slide.

{% capture example %}
<div id="carouselExampleFade" class="carousel slide carousel-fade" data-ride="carousel">
  <div class="carousel-inner">
    <div class="carousel-item active">
      <img class="d-block w-100" data-src="holder.js/800x400?auto=yes&bg=777&fg=555&text=Primeiro Slide" alt="Primeiro Slide">
    </div>
    <div class="carousel-item">
      <img class="d-block w-100" data-src="holder.js/800x400?auto=yes&bg=666&fg=444&text=Segundo Slide" alt="Segundo Slide">
    </div>
    <div class="carousel-item">
      <img class="d-block w-100" data-src="holder.js/800x400?auto=yes&bg=555&fg=333&text=Terceiro Slide" alt="Terceiro Slide">
    </div>
  </div>
  <a class="carousel-control-prev" href="#carouselExampleFade" role="button" data-slide="prev">
    <span class="carousel-control-prev-icon" aria-hidden="true"></span>
    <span class="sr-only">Anterior</span>
  </a>
  <a class="carousel-control-next" href="#carouselExampleFade" role="button" data-slide="next">
    <span class="carousel-control-next-icon" aria-hidden="true"></span>
    <span class="sr-only">Próximo</span>
  </a>
</div>
{% endcapture %}
{% include example.html content=example %}


## Modo de uso

### Via atributos data

Use atributos data para, facilmente, controlar a posição do carousel. O `data-slide` aceita as palavras-chaves `prev` ou `next`, as quais alteram a posição do slide, de acordo com sua atual posição. Opcionalmente, use `data-slide-to` para passar um index ao carousel, o qual muda a posição do slide para o index específico, com valores começando em `0` (ex: `data-slide-to="2"`).

O atributo `data-ride="carousel"` é usado para declarar que o carousel vai começar a animação assim que a página carregar. **Este atributo não pode ser usado em combinação com uma (redundante e desnecessária) inicialização JavaScript explícita, do mesmo carousel.**

### Via JavaScript

Invoque o carousel, manualmente, usando:

{% highlight js %}
$('.carousel').carousel()
{% endhighlight %}

### Opções

Opções podem ser passadas via atributos data ou JavaScript. Para atributos data, anexe o nome da opção no prefixo `data-`, como acontece em `data-interval=""`.

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
      <td>interval</td>
      <td>number</td>
      <td>5000</td>
      <td>A quantidade de tempo de espera entre a troca de slides. Se o valor é false, o carousel não vai girar, automaticamente.</td>
    </tr>
    <tr>
      <td>keyboard</td>
      <td>booleano</td>
      <td>true</td>
      <td>Diz se o carousel deve reagir aos eventos de teclado.</td>
    </tr>
    <tr>
      <td>pause</td>
      <td>string | booleano</td>
      <td>"hover"</td>
      <td><p>Se tiver definido como <code>"hover"</code>, pausa o ciclo do carousel no evento <code>mouseenter</code> e volta o ciclo no <code>mouseleave</code>. Se definido para <code>false</code>, passar o mouse sobre o carousel não irá pausá-lo.</p>
      <p>Em dispositivos com touch, quando tiver definido o valor <code>"hover"</code>, o ciclo vai pausar no evento <code>touchend</code> (uma vez que o usuário parar de interagir com o carousel) por dois intervalos, antes de voltar sozinho, novamente. Perceba que isso acontece devido ao comportamento de mouse, mencionado acima.</p></td>
    </tr>
    <tr>
      <td>ride</td>
      <td>string</td>
      <td>false</td>
      <td>Auto inicia o carousel, depois do usuário clicar no primeiro item, manualmente. Se definido com o valor "carousel", o carousel começa assim que carrega.</td>
    </tr>
    <tr>
      <td>wrap</td>
      <td>boolean</td>
      <td>true</td>
      <td>Diz se o carousel deve girar continuamente ou ter paradas bruscas.</td>
    </tr>
  </tbody>
</table>

### Métodos

{% include callout-danger-async-methods.md %}

#### `.carousel(options)`

Inicializa o carousel com um `object` de opções opcional e inicia o ciclo dos itens.

{% highlight js %}
$('.carousel').carousel({
  interval: 2000
})
{% endhighlight %}

#### `.carousel('cycle')`

Gira pelos itens do carousel, da esquerda para direita.

#### `.carousel('pause')`

Impede o carousel de girar pelos itens.

#### `.carousel(Número)`

Gira o carousel para um frame particular (começa em 0, como uma array). **Retorna ao invocador, antes do item alvo ser mostrado** (antes do evento `slid.bs.carousel` ocorrer).

#### `.carousel('prev')`

Gira para o item anterior. **Retorna ao invocador, antes do item anterior ser mostrado** (antes do evento `slid.bs.carousel` ocorrer).

#### `.carousel('next')`

Gira para o próximo item. **Retorna ao invocador, antes do próximo item ser mostrado** (antes do evento `slid.bs.carousel` ocorrer).

#### `.carousel('dispose')`

Destroi um elemento do carousel.

### Eventos

A classe carousel do Bootstrap tem dois evento para serem ligados a funcionalidade do carousel. Ambos eventos possuem as seguintes propriedades adicionais:

- `direction`: a direção na qual o carousel está deslizando (tanto `"left"` quanto `"right"`);
- `relatedTarget`: o elemento DOM que está sendo deslizado para o lugar do item ativo;
- `from`: o index do atual item;
- `to`: o index do próximo item.

Todos eventos carousel são acionados no próprio carousel (acionados no elemento `<div class="carousel">`).

<table class="table table-bordered table-striped">
  <thead>
    <tr>
      <th style="width: 150px;">Tipo de evento</th>
      <th>Descrição</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>slide.bs.carousel</td>
      <td>Este evento aciona, imediatamente, quando o método <code>slide</code> é invocado.</td>
    </tr>
    <tr>
      <td>slid.bs.carousel</td>
      <td>Este evento é acionado quando o carousel acabou de finalizar sua transição.</td>
    </tr>
  </tbody>
</table>

{% highlight js %}
$('#myCarousel').on('slide.bs.carousel', function () {
  // Faça algo...
})
{% endhighlight %}

### Mude a duração da transição

A duração da transição do `.carousel-item` pode ser alterada na variável Sass `$carousel-transition`, antes de compilar ou em estilos personalizados (se você está usando CSS compilado). Se várias transições são aplicadas, se assegure da transição `transform` ser declarada primeiro (ex: `transition: transform 2s ease, opacity .5s ease-out`).

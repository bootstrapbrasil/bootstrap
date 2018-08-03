---
layout: docs
title: Ferramentas de build
description: Aprenda a usar os scripts npm incluídos no Bootstrap para construir nossa documentação, compilar o código fonte, realizar testes, entre outras coisas.
group: getting-started
toc: true
---

## Setup de ferramentas

Bootstrap usa [scripts NPM](https://docs.npmjs.com/misc/scripts) no seu sistema de build. Nosso [package.json]({{ site.repo }}/blob/v{{ site.current_version }}/package.json) possui métodos convenientes ao nosso framework, incluindo compilação de código, realização de testes e outras coisas.

Para usar nossa build e executar a documentação localmente, você vai precisar de uma cópia dos arquivos fontes Bootstrap e do Node.js.

1. [Baixe e instale o Node.js](https://nodejs.org/download/), o qual usamos para gerenciar nossas dependências;
2. Vá até o diretório raiz `/bootstrap` e execute o comando `npm install`, para instalar nossas dependências locais listadas no [package.json]({{ site.repo }}/blob/v{{ site.current_version }}/package.json);
3. Primeiro, instale o [Ruby][install-ruby]. Depois, instale o [Bundler][gembundler] com o comando `gem install bundler` e execute `bundle install`. Assim, você vai instalar todas as dependências Ruby, como Jekyll e plugins.
  - **Usuários de Windows:** leiam [este guia](https://jekyllrb.com/docs/windows/) para conseguir rodar o jekyll, tranquilamente.

Quando fizer isso, você será capaz de executar diversos comandos disponíveis em cli.

[install-ruby]: https://www.ruby-lang.org/en/documentation/installation/
[gembundler]: https://bundler.io/

## Usando scripts NPM

Nosso [package.json]({{ site.repo }}/blob/v{{ site.current_version }}/package.json) possui os seguintes comandos e tarefas:

| Comando | Tarefa |
| --- | --- |
| `npm run dist` | cria o diretório `/dist`, o qual tem arquivos compilados (**usa [Sass](https://sass-lang.com/), [Autoprefixer][autoprefixer] e [UglifyJS](https://github.com/mishoo/UglifyJS2).**). |
| `npm test` | é a mesma coisa que `npm run dist`, com a diferença que ele excuta os testes localmente.|
| `npm run docs` | Constrói e formata o CSS e JavaScript para documentos. Assim, depois você pode rodar a documentação localmente, usando `npm run docs-serve` |

Execute `npm run` para ver todos os scripts npm.

## Autoprefixer

Boostrap usa o [Autoprefixer][autoprefixer] (incluído na build) para, automaticamente, adicionar prefixos de fabricantes em algumas propriedades CSS. Deste modo, poupamos código e tempo porque nos ocupamos só em escrever as partes chaves do nosso CSS uma vez, sem precisar de mixins para adicionar prefixos (como aqueles da v3).

Nós mantemos uma lista de browsers suportados no Autoprefixer em um arquivo separado, em um repositório do GitHub. Veja [/package.json]({{ site.repo }}/blob/v{{ site.current_version }}/package.json), para mais detalhes.

## Documentação local

Rodar nossa documentação, localmente, requer o uso do Jekyll. Ele é um gerador flexível de sites estáticos, o qual provê: includes básicos, arquivos em Markdown, templates, entre outras coisas. Para se familiarizar, faça o seguinte:

1. Leia sobre o [setup de ferramentas](#tooling-setup), acima, para instalar o Jekyll e outras dependências Ruby com `bundle-install`;
2. Dentro do diretório raiz `/bootstrap`, execute `npm run docs-serve` na linha de comando;
3. Abra `http://localhost:9001` no seu browser e voilà.

Aprenda mais sobre o uso do Jekyll, lendo sua [documentação](https://jekyllrb.com/docs/home/).

## Solução de problemas

Se você encontrar problemas para instalar dependências, desinstale todas as versões anteriores das dependências (global e localmente), então, re-execute `npm install`.

[autoprefixer]: https://github.com/postcss/autoprefixer

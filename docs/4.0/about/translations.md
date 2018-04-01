---
layout: docs
title: Traduções
description: Links para sites da documentação traduzida do Boostrap pela comunidade.
group: about
---

Os membros da comunidade traduziram a documentação do Bootstrap para vários idiomas. Nenhuma é oficialmente suportada e nem sempre está atualizada.

<ul>
{% for language in site.data.translations %}
  <li><a href="{{ language.url }}" hreflang="{{ language.code }}">{{ language.description }} ({{ language.name }})</a></li>
{% endfor %}
</ul>

{% capture callout %}
Perceba: já que browsers não suportam, atualmente, [range context queries](https://www.w3.org/TR/mediaqueries-4/#range-context), nós contornamos as limitações dos [prefixos `min-` e `max-`](https://www.w3.org/TR/mediaqueries-4/#mq-min-max) e viewports com larguras fracionais (pode ocorrer em algumas circunstâncias, em dispositivos de alta dpi), usando valores com precisão maior para estas comparações.
{% endcapture %}
{% include callout.html content=callout type="info" %}

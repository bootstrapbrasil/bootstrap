{% capture callout %}
#### Métodos é transições assíncronas

Todos métodos API são **assíncronos** e iniciam a **transição**. Eles retornam ao invocador, assim que a transição é iniciada, mas **que ela finalize**. Além do mais, uma chamada de método em um **componente transicionando é ignorada**.

[Veja nossa documentação JavaScript, para mais informação.]({{ site.baseurl }}/docs/{{ site.docs_version }}/getting-started/javascript/)
{% endcapture %}
{% include callout.html content=callout type="danger" %}

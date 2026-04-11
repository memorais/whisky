---
layout: base
title: Minha Adega Digital
---

# 🥃 Minha Adega Digital

Aqui estão todas as notas de degustação da minha coleção:

{% assign whiskies = site.collections | where: "label", "degustacoes" | first %}
{% if whiskies %}
  <ul>
  {% for whisky in whiskies.docs %}
    <li>
      <a href="{{ whisky.url | relative_url }}">
        🥃 {{ whisky.data.title | default: whisky.title | default: whisky.basename }}
      </a>
    </li>
  {% endfor %}
  </ul>
{% else %}
  <p>Nenhuma degustação encontrada.</p>
{% endif %}

Meus próprios blends:

{% assign blends = site.collections | where: "label", "blends" | first %}
{% if blends %}
  <ul>
  {% for blend in blends.docs %}
    <li>
      <a href="{{ blend.url | relative_url }}">
        🧪 {{ blend.data.title | default: blend.title | default: blend.basename }}
      </a>
    </li>
  {% endfor %}
  </ul>
{% else %}
  <p>Nenhuma Blend ainda disponível.</p>
{% endif %}


---

*Total: {{ whiskies.docs | size }} whiskies*

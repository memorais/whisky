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

---

*Total: {{ whiskies.docs | size }} whiskies*

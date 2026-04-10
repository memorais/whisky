---
layout: default
title: Minha Adega Digital
---

# 🥃 Minha Adega Digital

Aqui estão todas as notas de degustação da minha coleção:

<ul>
{% for file in site.static_files %}
  {% if file.path contains "/degustacoes/" and file.extname == ".md" %}
    {% assign nome = file.basename | replace: "-", " " | capitalize %}
    <li>
      <a href="{{ file.path | replace: ".md", ".html" | relative_url }}">
        🥃 {{ nome }}
      </a>
    </li>
  {% endif %}
{% endfor %}
</ul>

---

*Total de whiskies:
{% assign count = 0 %}
{% for file in site.static_files %}
  {% if file.path contains "/degustacoes/" and file.extname == ".md" %}
    {% assign count = count | plus: 1 %}
  {% endif %}
{% endfor %}
{{ count }}*

---
layout: default
title: Minha Adega Digital
---

# 🥃 Minha Adega Digital

Aqui estão todas as notas de degustação da minha coleção:

<ul>
  {% for file in site.static_files %}
    {% if file.path contains "/degustacoes/" and file.extname == ".md" %}
      <li>
        <a href="{{ file.path | replace: ".md", ".html" | relative_url }}">
          🥃 {{ file.basename | replace: "-", " " | capitalize }}
        </a>
      </li>
    {% endif %}
  {% endfor %}
</ul>

---

*Total: {{ site.static_files | where_exp: "file", "file.path contains '/degustacoes/' and file.extname == '.md'" | size }} whiskies*

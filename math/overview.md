---
title: "Math"
---

Mostly recovering everything I failed to absorb in school and building a base for other interests...

<ul>
{% for note in site["6-042"] %}
  <li><a href="{{ note.url | relative_url }}">{{ note.title }}</a></li>
{% endfor %}
</ul>

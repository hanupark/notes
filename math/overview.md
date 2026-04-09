Mostly recovering everything I failed to absorb in school and building a base for other interests...

<ul>
{% for note in site.collections["6-042"].docs %}
  <li><a href="{{ note.url | relative_url }}">{{ note.title }}</a></li>
{% endfor %}
</ul>

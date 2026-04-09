---
title: "Computer Graphics"
---

I got interested in computer graphics because it's related to shaders, gaming, art, 3D software, etc. Let's see where it goes...

<ul>
{% for note in site["shadertoy-tutorial"] %}
  <li><a href="{{ note.url | relative_url }}">{{ note.title }}</a></li>
{% endfor %}
{% for note in site["utah-video-course"] %}
  <li><a href="{{ note.url | relative_url }}">{{ note.title }}</a></li>
{% endfor %}
</ul>
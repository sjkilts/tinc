---
layout: page
title: notes
url: notes/
---
{% for notes in site.notes %}
  {{ notes.user }}
  {% for client in notes.client %}
    - {{ client.client }}
  {% endfor %}
  {% for project in notes.project %}
    {{ project.project }}
    {{ project.description }}
    {% for todo in project.todo %}
      - {{ todo.todo }}
    {% endfor %}
    {% for notes in project.notes %}
      - {{ notes.notes }}
    {% endfor %}
  {% endfor %}
  {% for minutes in notes.minutes %}
    - {{ minutes.minutes }}
  {% endfor %}
{% endfor %}

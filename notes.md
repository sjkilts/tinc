---
layout: page
title: notes
url: notes/
---
{% for note in site.data.notes %}
  {{ note.user }}
  {% for client in note.client %}
    - {{ client.client }}
  {% endfor %}
  {% for project in note.project %}
    {{ project.project }}
    {{ project.description }}
    {% for todo in project.todo %}
      - {{ todo.todo }}
    {% endfor %}
    {% for notes in project.notes %}
      - {{ notes.notes }}
    {% endfor %}
  {% endfor %}
  {% for minutes in note.minutes %}
    - {{ minutes.minutes }}
  {% endfor %}
{% endfor %}

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
  
{% for project in note.projects %}  
{{ project.project }}  
{{ project.client }}  
{{ project.description }}  
{% for todo in project.todo %}  
  - {{ todo.todo }}  
{% endfor %}  
{% endfor %}  
  
{% for minutes in note.minutes %}  
  - {{ minutes.minutes }}  
{% endfor %}  
  
{% for note in project.notes %}  
- date: {{ note.date }}  
- project: {{ note.project }}  
- note: {{ note.note }}  
  
{% endfor %}  
{% endfor %}  

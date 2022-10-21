---
layout: page
title: notes
url: notes/
---
# notes
{% for note in site.data.notes %}  
## users  
{{ note.user }}  
## clients  
{% for client in note.client %}  
- {{ client.client }}  
{% endfor %}  
## projects  
{% for project in note.projects %}  
{{ project.project }}  
{{ project.client }}  
{{ project.description }}  
{% for todo in project.todo %}  
  - {{ todo.todo }}  
{% endfor %}  
{% endfor %}  
## hours  
{% for hours in note.minutes %}  
  - {{ hours.minutes }}  
{% endfor %}  
## notes  
{% for note in project.notes %}  
- date: {{ note.date }}  
- project: {{ note.project }}  
- note: {{ note.note }}  
  
{% endfor %}  
{% endfor %}  

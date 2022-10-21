---
layout: default
title: notes
url: notes/
---
{% for foo in site.data.notes %}  
## users  
{{ foo.user }}  
## clients  
- {{ foo.client }}    
## projects  
{% for project in foo.projects %}  
{{ project.project }}  
{{ project.client }}  
{{ project.description }}  
{% for todo in project.todo %}  
- {{ todo.todo }}  
{% endfor %}  
{% endfor %}  
## hours  
{% for hours in foo.minutes %}  
- {{ hours.name }}, {{ hours.date }}, {{ hours.hours }}, {{ hours.description }}  
{% endfor %}
## notes  
{% for thought in foo.thoughts %}  
- date: {{ thought.date }}  
- project: {{ thought.project }}  
- note: {{ thought.note }}  
{% endfor %}  
{% endfor %}  

---
published: true
layout: default
url: /note
---
{% for project in site.notes.projects %}  
{% capture project %}{{ project.project }}{% encapture %}
{% capture client %}{{ project.client }}{% encapture %}
{% capture description %}{{ project.description }}{% encapture %}
{% capture todo %}{{ project.todo }}{% encapture %}

project: {{ project.project }}  
client: {{ project.client }}  
description: {{ project.description }}  
todo:  
{{ project.todo | markdownify }}  
notes:    
{{ content }}  
  
{% endfor %}

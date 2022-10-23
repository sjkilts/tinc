---
published: true
layout: default
url: /note
---
{% for project in site.notes.projects %}
project: {{ project.project }}  
client: {{ project.client }}  
description: {{ project.description }}  
todo:  
{{ project.todo | markdownify }}  
notes:    
{{ content }}  
{% endfor %}

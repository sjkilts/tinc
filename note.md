---
published: true
layout: default
url: /note
---
{% assign project = site.posts %}  
{% for project in site.posts %}   
{% if project.path contains project %}  
  
project: {{ project.project }}  
client: {{ project.client }}  
description: {{ project.description }}  
todo:  
{{ project.todo | markdownify }}  
notes:    
{{ content }}  
  
{% endif %}  
{% endfor %}

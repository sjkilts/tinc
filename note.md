---
published: true
layout: default
url: /note
---
{% assign project = site.posts %}
{% for project in site.posts %}   
{% if project.path contains projects %}  
  
project: {{ project.project }}  
client: {{ project.client }}  
description: {{ project.description }}  
todo:  
{{ project.todo | markdownify }}  
notes:    
{{ content }}  
  
{% endif %}  
{% endfor %}

---
published: true
layout: default
url: /note
---
{% for p in site.posts %}   
{% if p.path contains 'project' %}  
  
project: {{ p.project }}  
client: {{ p.client }}  
description: {{ p.description }}  
todo:  
{{ p.todo | markdownify }}  
notes:    
{{ content }}  
  
{% endif %}  
{% endfor %}

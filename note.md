---
published: true
layout: default
url: /note
---
{% for project in site.posts %}   
{% if project.path contains 'projects' %}  
{% capture project %}{{ project.project }}{% endcapture %}  
{% capture client %}{{ project.client }}{% endcapture %}  
{% capture description %}{{ project.description }}{% endcapture %}  
{% capture todo %}{{ project.todo }}{% endcapture %}  
  
project: {{ project.project }}  
client: {{ project.client }}  
description: {{ project.description }}  
todo:  
{{ project.todo | markdownify }}  
notes:    
{{ content }}  
  
{% endif %}  
{% endfor %}

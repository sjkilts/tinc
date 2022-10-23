---
published: true
layout: default
url: /note
---
{% for p in site.notes %}   
{% if p.project %}

  project: {{ p.project }}  
  client: {{ p.client }}  
  description: {{ p.description }}  
  todo:  
  {{ p.todo }}  
  notes:    
  {{ content }}  

{% endif %}
{% endfor %}

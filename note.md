---
published: true
layout: default
url: /note
---
{% for p in site.note %}   

  project: {{ p.project }}  
  client: {{ p.client }}  
  description: {{ p.description }}  
  todo:  
  {{ p.todo }}  
  notes:    
  {{ content }}  

{% endfor %}

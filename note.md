---
published: true
layout: default
url: /note
---
{% for p in site.notes %}   
{% if p.path contains 'project' %}  
  {% capture %}{{ p.project }}{% endcapture %}
  {% capture %}{{ p.client }}{% endcapture %}
  {% capture %}{{ p.description }}{% endcapture %}
  {% capture %}{{ p.todo | markdownify }}{% endcapture %}

  project: {{ p.project }}  
  client: {{ p.client }}  
  description: {{ p.description }}  
  todo:  
  {{ p.todo }}  
  notes:    
  {{ content }}  

{% endif %}  
{% endfor %}

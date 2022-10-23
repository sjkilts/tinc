---
published: true
layout: default
url: /note
---
{% comment %}
{% for p in site.notes %}   
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

{% endfor %}
{% comment %}

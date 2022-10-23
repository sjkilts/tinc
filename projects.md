---
published: true
layout: default
---

{% for p in site.notes %}   
<div style="font-family: courier new" class="col12 pad1">
  {% if p.path contains 'projects' %}
  <ul>
    <li>project: {{ p.project }}</li>  
    <li>client: {{ p.client }}</li>  
    <li>description: {{ p.description }}</li>  
    <li>todo:</li>  
    <li>{{ p.todo }}</li>  
    <li>notes:</li>    
    <li>{{ p.content | markdownify }}</li>  
  </ul>
  {% endif %}
</div>  
{% endfor %}

---
published: true
layout: default
url: /notes
---

{% for p in site.note %}   
<div>
  <ul>
    <li>project: {{ p.project }}</li>  
    <li>client: {{ p.client }}</li>  
    <li>description: {{ p.description }}</li>  
    <li>todo:</li>  
    <li>{{ p.todo }}</li>  
    <li>notes:</li>    
    <li>{{ p.content | markdownify }}</li>  
  </ul>
</div>  
{% endfor %}

---
layout: default
title: notes
url: notes/
---
{% for foo in site.data.notes %}  
<div class="fr">
   <h3>users</h3>  
   {{ foo.user }}  
</div>   
<div class="fl">
   <h3>clients</h3>  
   {% for client in foo.client %}
   - {{ client }}    
   {% endfor %}     
</div>   
### projects  
<ul>
{% for project in foo.projects %}  
<details>   
   <summary>   
      <li><i>{{ project.project }} </i>{{ project.client }}<span class='date'> {{ project.description }}</span></li>      
   </summary>   
   {% for todo in project.todo %}  
   <li>{{ todo }}</li>  
   {% endfor %}     
</details>  
{% endfor %}  
</ul>   
### notes  
<ul>
{% for thought in foo.thoughts %}  
<details>
   <summary>
      <li>{{ thought.date }}<i> {{ thought.project }}</i></li>  
   </summary>
   <li>{{ thought.note }}</li>  
   <br>    
</details>   
{% endfor %}  
</ul>
{% endfor %}    
### hours  
{% for hours in foo.minutes %}  
{{ hours }}   
<br>  
{% endfor %}  

---
layout: default
title: notes
url: notes/
---
{% for foo in site.data.notes %}  
<div class="fl">
   ### users  
   {{ foo.user }}  
</div>   
<div class="fr">
   ### clients  
   <p>
   {% for client in foo.client %}
   - {{ client }}    
   {% endfor %}   
   </p>  
</div>   
### projects  
{% for project in foo.projects %}  
<details>   
   <summary>   
      - <i>{{ project.project }} </i>{{ project.client }}<span class='date'> {{ project.description }}</span>      
   </summary>   
   {% for todo in project.todo %}  
      - {{ todo }}  
   {% endfor %}     
</details>  
{% endfor %}  
### notes  
{% for thought in foo.thoughts %}  
<details>
   <summary>
      - {{ thought.date }}<i> {{ thought.project }}</i>  
   </summary>
   {{ thought.note }}  
   <br>    
</details>   
{% endfor %}  
{% endfor %}    
### hours  
{% for hours in foo.minutes %}  
{{ hours }}   
<br>  
{% endfor %}  

---
layout: default
title: notes
url: notes/
---
{% for foo in site.data.notes %}  
### users  
{{ foo.user }}  
### clients  
<p>
{% for client in foo.client %}
- {{ client }}    
{% endfor %}   
</p>  
### projects  
{% for project in foo.projects %}  
<details>   
   <summary>   
      - *{{ project.project }} *{{ project.client }}<span class='date'> {{ project.description }}</span>      
   </summary>   
   <p>
   {% for todo in project.todo %}  
   - {{ todo }}  
   {% endfor %}  
   </p>   
</details>  
{% endfor %}  
### notes  
{% for thought in foo.thoughts %}  
<details>
   <summary>
   - {{ thought.date }}  *{{ thought.project }}*  
   </summary>
   <p>
   {{ thought.note }}  
   </p>
   <br>    
</details>   
{% endfor %}  
{% endfor %}    
### hours  
{% for hours in foo.minutes %}  
{{ hours }}   
<br>  
{% endfor %}  

---
layout: default
title: notes
url: notes/
---
{% for foo in site.data.notes %}  

- users:
- *{{ foo.user }}*  
- clients:
{% for client in foo.client %}
- *{{ client }}*
{% endfor %}      


<div>
   <h3>projects</h3>  
   <ul>
   {% for project in foo.projects %}  
   <details>   
      <summary>
         <li><strong>{{ project.project }}</strong><span class='date'>&nbsp;{{ project.client }}&nbsp;</span><em>{{ project.description }}</em></li>      
      </summary>   
      {% for todo in project.todo %}  
      <li>{{ todo }}</li>
      {% endfor %}     
      <br>
   </details>  
   {% endfor %} 
   </ul>    
</div> 

<ul>
   <li>notes:</li>
   {% for thought in foo.thoughts %}  
   <details>
      <summary>
         <li><span class='date'>{{ thought.date }}</span><em>&nbsp;{{ thought.project }}</em></li>  
      </summary>
         - {{ thought.note }}  
      <br>    
   </details>   
   {% endfor %}  
</ul>
 

hours:  
{% for hours in foo.minutes %}  
{{ hours }}   
{% endfor %}   
{% endfor %}

---
layout: default
title: notes
url: notes/
---
{% for foo in site.data.notes %}  
users:   {{ foo.user }}  
clients:
<ul>
{% for client in foo.client %}
<li>{{ client }}</li>    
{% endfor %}      
</ul>    

<div>
   <h3>projects</h3>  
   <ul>
   {% for project in foo.projects %}  
   <details>   
      <summary>
         <br>
         <li>{{ project.project }}<span class='date'>&nbsp;{{ project.client }}</span></li>
         <li><span style="font-style: italic;">{{ project.description }}</span></li>      
         <br>
      </summary>   
      {% for todo in project.todo %}  
      <li>{{ todo }}</li>  
      {% endfor %}     
   </details>  
   {% endfor %} 
   </ul>    
</div> 

<div>   
   <h3>notes</h3>  
   <ul>
   {% for thought in foo.thoughts %}  
   <details>
      <summary>
         <li>{{ thought.date }}<i style="font-style: italic;"> {{ thought.project }}</i></li>  
      </summary>
      <p>{{ thought.note }}</p>  
      <br>    
   </details>   
   {% endfor %}  
   </ul>
</div>    

hours:  
{% for hours in foo.minutes %}  
{{ hours }}   
<br>  
{% endfor %}   
{% endfor %}

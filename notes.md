---
layout: default
title: notes
url: notes/
---
{% for foo in site.data.notes %}  
<div class="fl">
   <h3>users</h3>  
   {{ foo.user }}  
</div>   
<div>
   <h3>clients</h3>  
   <ul>
   {% for client in foo.client %}
   <li>{{ client }}<li>    
   {% endfor %}     
   </ul>   
</div>   
<div>
   <h3>projects</h3>  
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
</div>   
<div>   
   <h3>notes</h3>  
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
</div>   
<div>   
   <h3>hours</h3>  
   {% for hours in foo.minutes %}  
   {{ hours }}   
   <br>  
   {% endfor %}
</div>   
{% endfor %}

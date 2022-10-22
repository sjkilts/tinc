---
layout: default
title: notes
url: notes/
---
{% for foo in site.data.notes %}  
<div>
   <h3>users</h3>  
   {{ foo.user }}  
</div> <!-- /divusers -->   
<div class="fr">
   <h3>clients</h3>  
   <ul>
   {% for client in foo.client %}
   <li>{{ client }}</li>    
   {% endfor %} <!-- /forclients -->     
   </ul> <!-- /listclients -->   
</div> <!-- /divclients -->   
<div>
   <h3>projects</h3>  
   <ul>
   {% for project in foo.projects %}  
   <details>   
      <summary>   
         <li><i style="font-style: italic;">{{ project.project }} </i>{{ project.client }}<span class='date'> {{ project.description }}</span></li>      
      </summary>   
      {% for todo in project.todo %}  
      <li>{{ todo }}</li>  
      {% endfor %} <!-- /fortodo -->     
   </details>  
   {% endfor %} <!-- /forprojects -->
   </ul> <!-- /projectslist -->   
</div> <!-- /divprojects -->
<div>   
   <h3>notes</h3>  
   <ul>
   {% for thought in foo.thoughts %}  
   <details>
      <summary>
         <li>{{ thought.date }}<i style="font-style: italic;"> {{ thought.project }}</i></li>  
      </summary>
      <li>{{ thought.note }}</li>  
      <br>    
   </details>   
   {% endfor %}  
   </ul>
</div> <!-- /notes -->   
<div>   
   <h3>hours</h3>  
   {% for hours in foo.minutes %}  
   {{ hours }}   
   <br>  
   {% endfor %}
</div>   
{% endfor %}

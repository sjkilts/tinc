---
layout: default
title: notes
url: notes/
---
{% for foo in site.data.notes %}  
<div style="font-family: courier new">
  <div> <!--users, clients-->
    <ul>
      <li>
          <strong>users</strong>
          <em> {{ foo.user }} </em>
          <strong>clients</strong> 
          {% for client in foo.client %}
          <em> * {{ client }} </em>
          {% endfor %}       
      </li>
    </ul>
  </div>
  <div> <!--projects-->
    <strong>projects</strong>   
    {% for project in foo.projects %}  
    <details>     
      <summary>  
        <li>
          <strong>{{ project.project }}</strong>
          &nbsp;{{ project.client }}&nbsp;
          <em>{{ project.description }}</em>
        </li>      
      </summary>   
      <ul>
        {% for todo in project.todo %}  
        <li>° {{ todo }}</li>  
        {% endfor %}     
      </ul>  
    </details>  
    {% endfor %}   
  </div>
  <div> <!--notes-->
    <strong>notes</strong>      
      {% for thought in foo.thoughts %}  
      <details>  
        <summary>  
          <span>{{ thought.date }}</span>&nbsp;<em>{{ thought.project }}</em>  
        </summary>
        <span>{{ thought.note }}</span>   
      </details>    
      {% endfor %}    
  </div>
  <div> <!--hours-->  
    <strong>hours</strong>    
    <ul>
      {% for hours in foo.minutes %}    
      <li>{{ hours.hours }}, {{ hours.date }}, {{ hours.client }}, {{ hours.project }}, {{ hours.description }}</li>
      {% endfor %}   
    </ul>
  </div>    
{% endfor %}  
</div>

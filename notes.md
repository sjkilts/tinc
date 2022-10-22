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
          <em> {{ client }} </em>
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
    <strong>notes</notes>      
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
    {% for hours in foo.minutes %}    
    <span>{{ hours.name }}, {{ hours.date }}, {{ hours.client }}, {{ hours.project }}, {{ hours.hours }}, {{ hours.description }}</span>  
    {% endfor %}   
  </div>    
{% endfor %}  
</div>

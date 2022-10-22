---
layout: default
title: notes
url: notes/
---
{% for foo in site.data.notes %}  
<div style="font-family: courier new" class="col10 pad1">
  <div> <!--users, clients-->
    <ul>
      <li><strong>users</strong></li>
      <li><em>&nbsp;{{ foo.user }}</em></li>
    </ul>
    <ul>
      <li><strong>clients</strong></li>
      {% for client in foo.client %}
      <li><em>&nbsp;* {{ client }}</em></li>
      {% endfor %}  
    </ul>
  </div>
  <br>
  <div> <!--projects-->
    <strong>projects</strong>   
    {% for project in foo.projects %}  
    <details>     
      <summary>  
        <li>
          &nbsp;
          <strong>{{ project.project }}</strong>
          &nbsp;{{ project.client }}&nbsp;
          <em>{{ project.description }}</em>
        </li>      
      </summary>   
      <ul>
        {% for todo in project.todo %}  
        <li>&nbsp;&nbsp;&nbsp;° {{ todo }}</li>  
        {% endfor %}     
      </ul>  
    </details>  
    {% endfor %}   
  </div>
  <br>
  <div> <!--notes-->
    <strong>notes</strong>      
      {% for thought in foo.thoughts %}  
      <details>  
        <summary>  
          <span>&nbsp;&nbsp;{{ thought.date }}</span>&nbsp;<em>{{ thought.project }}</em>  
        </summary>
        <span>{{ thought.note }}</span>   
      </details>    
      {% endfor %}    
  </div> 
{% endfor %}  
</div>

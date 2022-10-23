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
    &nbsp;<strong>{{ project.project }}</strong><span class="date fr">&nbsp;{{ project.client }}&nbsp;</span>
    <details>     
      <summary>  
        <li>
          <em>>&nbsp;{{ project.description }}</em>
        </li>      
      </summary>   
      <ul>
        {% for todo in project.todo %}  
        <li>&nbsp;&nbsp;&nbsp;° {{ todo }}</li>  
        {% endfor %}     
      </ul>  
      <br>
    </details>  
    {% endfor %}   
  </div>
  <br>
  <div> <!--notes-->
    <strong>notes</strong>      
      {% for thought in foo.thoughts %}  
      <details>  
        <summary>  
          <span class="date">&nbsp;&nbsp;{{ thought.date }}</span>&nbsp;<em class="fr">{{ thought.project }}</em>  
        </summary>
        <span>{{ thought.note }}<br></span>   
      </details>    
      {% endfor %}    
  </div> 
{% endfor %}  
</div>

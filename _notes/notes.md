---
layout: default
title: notes
url: notes/
---
{% for foo in site.data.notes %}  

<div style="font-family: courier new" class="col12 pad1">
  
  <div> <!--users, clients-->
    <ul>
      <li><strong>users</strong></li>
      <li><em>&nbsp;{{ foo.user }}</em></li>
    </ul>
    <br>
    
    <ul>
      <li><strong>clients</strong></li>
      {% for client in foo.client %}
      <li><em>&nbsp;* {{ client }}</em></li>
      {% endfor %}  
    </ul>
  </div>
  <br>
  
  <div> <!--projects-->
    <ul>
      <strong>projects</strong>   
      {% for project in foo.projects %}  
      <li>&nbsp;<strong>{{ project.project }}</strong><span class="date fr">&nbsp;{{ project.client }}&nbsp;</span></li>
      <details>     
        <summary>  
          <li>
            <em>&nbsp;>&nbsp;{{ project.description }}</em>
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
    </ul>  
  </div>
  <br>
 
  <div> <!--notes-->
    <strong>notes</strong>
    {% for thought in foo.thoughts %}  
    <details>  
      <summary>  
        <span class="date">&nbsp;&nbsp;{{ thought.date }}</span>&nbsp;<em class="fr">{{ thought.project }}</em>  
      </summary>
      <span markdown="1">
    
      {{ thought.note }}
      
      </span>
    <br>
  </details>    
  {% endfor %}    
  
</div>
  
{% endfor %}  

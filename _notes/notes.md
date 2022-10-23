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
    <strong>projects</strong>   
    <div>
      {% for project in foo.projects %}  
      <span>>&nbsp;<strong>{{ project.project }}</strong><span class="date fr">&nbsp;{{ project.client }}&nbsp;</span></span>>
      <details>     
        <summary>
          <em>&nbsp;>&nbsp;{{ project.description }}</em>      
        </summary>   
        {% for todo in project.todo %}  
        <span markdown="1">{{ todo }}</span>  
        {% endfor %}     
        <br>
      </details>  
      {% endfor %}   
    </div>  
  </div>
  <br>
 
  <div> <!--notes-->
    <strong>notes</strong>
    {% for thought in foo.thoughts %}  
    <details>  
      <summary>  
        <span class="date">&nbsp;&nbsp;{{ thought.date }}</span>&nbsp;<em class="fr">{{ thought.project }}</em>  
      </summary>
      <span markdown="1">{{ thought.note }}</span>
    <br>
  </details>    
  {% endfor %}    
  
</div>
  
{% endfor %}  

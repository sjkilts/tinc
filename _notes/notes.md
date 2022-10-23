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
      {% for project in foo.projects %}  
      <details>     
        <span>&nbsp;<strong>{{ project.project }}</strong><span class="date fr">&nbsp;{{ project.client }}&nbsp;</span></span>
        <summary>
          <em>&nbsp;>&nbsp;{{ project.description }}</em>      
        </summary>   
        <br>
        <span markdown="1">{{ project.todo }}</span>      
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
        <strong>&nbsp;{{ thought.date }}</strong>&nbsp;<em class="fr">{{ thought.project }}&nbsp;</em>  
      </summary>
      <br>
      <span markdown="1">{{ thought.note }}</span>
      <br>
    </details>    
    {% endfor %}    
  </div>
  
</div>  
{% endfor %}  

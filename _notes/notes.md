---
layout: default
title: notes
url: notes/
---
{% for foo in site.data.notes.notes %}  

<div style="font-family: courier new" class="col12 pad1">
  
  <div> <!--users-->
    <ul>
      <li><strong>users</strong></li>
      <li><em>&nbsp;{{ foo.user }}</em></li>
    </ul>
    <br>
  </div>  
  
  <div> <!--clients-->
    <ul>
      <li><strong>clients</strong></li>
      {% for client in foo.client %}
      <li><em>&nbsp;* {{ client }}</em></li>
      {% endfor %}  
    </ul>
    <br>
  </div>
  
  <div> <!--projects-->
    <strong>projects</strong>   
    {% for project in foo.projects %}  
    <details>     
      <summary>
        &nbsp;{{ project.client }}
        &nbsp;{{ project.project }}&nbsp;<em>/&nbsp;{{ project.description }}</em>
      </summary>   
      <br>
      {{ project.todo | markdownify }}
      <br>
      <hr>
    </details>  
    {% endfor %}   
  </div>
  <br>
 
  <div> <!--notes-->
    <strong>notes</strong>
      {% for thought in foo.thoughts %}  
      <details>  
        <summary>  
          &nbsp;{{ thought.date }}
          &nbsp;<em class="fr">{{ thought.project }}&nbsp;</em>  
        </summary>
        <br>
        <hr>
        {{ thought.note | markdownify }}
        <br>
      </details>    
      {% endfor %}    
  </div>
  
</div>  
{% endfor %}  

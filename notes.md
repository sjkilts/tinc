---
layout: default
title: notes
url: notes/
---
{% for foo in site.data.notes %}  
- **users** *{{ foo.user }}* **clients** {% for client in foo.client %}*{{ client }}*{% endfor %}**       
- projects:   
  {% for project in foo.projects %}  

  <ul>
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
        <li>{{ todo }}</li>  
        {% endfor %}     
      </ul>  
    </details>  
  </ul>
  
  {% endfor %}   
  
- notes:      
  {% for thought in foo.thoughts %}  
  
  <ul>
    <details>  
      <summary>  
        <li>{{ thought.date }}&nbsp;<em>{{ thought.project }}</em></li>  
      </summary>  
      <ul>
        <li>{{ thought.note }}</li>    
      </ul>
    </details>    
  </ul>
  
  {% endfor %}    
    
- hours:    
  {% for hours in foo.minutes %}    
  
  <ul>
    <li><em>{{ hours }}<em></li>
  </ul>
      
{% endfor %}   
      
{% endfor %}  

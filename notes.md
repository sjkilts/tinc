---
layout: default
title: notes
url: notes/
---
{% for foo in site.data.notes %}  
- users:  
- *{{ foo.user }}*  
- clients:  
{% for client in foo.client %}  
- *{{ client }}*  
{% endfor %}       
- projects:  
{% for project in foo.projects %}  
  
<details>   
<summary>  
  
- **{{ project.project }}** {{ project.client }} *{{ project.description }}*      
         
</summary>   
      
{% for todo in project.todo %}  
- {{ todo }}  
{% endfor %}     
   
</details>  
  
{% endfor %}   
  
- notes:  
{% for thought in foo.thoughts %}  
   
<details>  
<summary>  
         
- {{ thought.date }} *{{ thought.project }}*  
  
</summary>  
  
- {{ thought.note }}    
  
</details>    
  
{% endfor %}    
- hours:    
{% for hours in foo.minutes %}    
- *{{ hours }}*    
{% endfor %}   
{% endfor %}  

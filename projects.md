---
published: true
layout: default
--- 
<div style="font-family: courier new" class="col12 pad1">
  
{% for foo in site.data.notes.notes %}    
  
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

{% endfor %}  
  
  <div> <!--projects-->
    <strong>projects</strong>
    {% for p in site.notes %}
    {% if p.path contains 'projects' %}
    <details>     
      <summary>
        <ul>
          <li>&nbsp;<em>{{ p.client }}</em></li>   
          <li>&nbsp;&nbsp;{{ p.project }}&nbsp;<em>/&nbsp;{{ p.description }}</em></li>
        </ul>
      </summary>   
      <br>
      {{ p.todo | markdownify }}
      <br>
      <details>
        <summary>
          <strong>notes:</strong>
        </summary
          {{ p.content | markdownify }}
      </details>
      <hr>
    </details>
    {% endif %}
    {% endfor %}
  </div>  

</div>      

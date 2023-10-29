---
published: true
layout: default
sitemap: false
title: notes
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
          <li>&nbsp;{{ p.project }}&nbsp;/<strong><em>&nbsp;{{ p.description }}</em></strong>&nbsp;<em class='fr'>{{ p.client }}&nbsp;</em></li>
        </ul>
      </summary>   
      <br>
      {{ p.todo | markdownify }}
      <br>
      {% if p.content.size > 10 %}
      <details>
        <summary>
          <span>&nbsp;&nbsp;<strong>notes</strong>&nbsp;></span><span class='fr'>*&nbsp;</span>
        </summary>
          <br>
          {{ p.content | markdownify }}
      </details>
      {% endif %}
      <br>
      <hr>
    </details>
    {% endif %}
    {% endfor %}
  </div>
  
  
  {% for t in site.notes %}
  {% if t.path contains 'hours' %}
  <br>
  <br>
  <div>
    <strong>hours</strong>
    <br>  
    {{ t.content | sort_natural | join: ", " }}
  </div>
  {% endif%}
  {% endfor %}
  
</div>

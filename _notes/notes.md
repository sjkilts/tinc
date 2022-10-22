---
layout: default
title: notes
url: notes/
---
{% for foo in site.data.notes %}  
<div style="font-family: courier new">
  <div> <!--users, clients-->
    <ul>
      <li>
          <strong>users</strong>
          <em> {{ foo.user }} </em>
          <strong>clients</strong> 
          {% for client in foo.client %}
          <em> * {{ client }} </em>
          {% endfor %}       
      </li>
    </ul>
  </div>
  <div> <!--projects-->
    <strong>projects</strong>   
    {% for project in foo.projects %}  
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
        <li>° {{ todo }}</li>  
        {% endfor %}     
      </ul>  
    </details>  
    {% endfor %}   
  </div>
  <div> <!--notes-->
    <strong>notes</strong>      
      {% for thought in foo.thoughts %}  
      <details>  
        <summary>  
          <span>{{ thought.date }}</span>&nbsp;<em>{{ thought.project }}</em>  
        </summary>
        <span>{{ thought.note }}</span>   
      </details>    
      {% endfor %}    
  </div> {{ comment }} <!--
  <div> <!--hours- ->  
    <strong>hours</strong>    
    {% capture now %}{{'now' | date: '%Y-%m-%d' | plus: 0 }}{% endcapture %}
    {% for hours in foo.minutes %}    
      {% capture day %}{{ hours.date | date: '%Y-%m-%d' | plus: 0 }}{% endcapture %}
      {% capture time %}{{ hours.hours | plus: 0 }}{% endcapture %}
      {% capture project %}{{ hours.project | plus: 0 }}{% endcapture %}
    <details>
      <summary>
        {% for day in hours.date %}
          {% if day == hours.date %}
            <li>
            {{ day | limit: 1 }}            <!-- date - ->
            {{ time | plus: hours.hours }}  <!-- total hours for date? - ->
            {{ project }}                   <!-- contributions on date - ->
            </li>
          {% endif %}
      </summary>
          <li>{{ hours.hours }}, {{ hours.date }}, {{ hours.client }}, {{ hours.project }}, {{ hours.description }}</li>
        {% endfor %}
    </details>      
    < !--
    hours worked in past two weeks, hours in past month, total hours
    three most recently contributed to projects
    stale project(s) (longest time between now and past contribution)
    <ul>
      {% for hours in foo.minutes %}    
      <li>{{ hours.hours }}, {{ hours.date }}, {{ hours.client }}, {{ hours.project }}, {{ hours.description }}</li>
      {% endfor %}   
    </ul>
  </div> -->{{ comment }}
{% endfor %}  
</div>

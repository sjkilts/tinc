---
published: false
title: admin
project: admin
description: organize projects & data
todo: |
  - [ ] gitea heroku  
  - [ ] killer stack, gitea heroku fleek jekyll prose  
  - [ ] jekyll template  
  - [ ] detailed prose setup  
  - [ ] update essentials via jekyll or theme?  
  - [ ] css baseline template  
  - [ ] heroku form backend app  
  - [ ] consolidate and organize files  
  - [ ] secure notes  
  - [ ] time tracking web app
client:
  - scott j kilts
---
---   
   
*scottkilts.com*  
---  
  
stack ? :
- server (heroku)
- version control (gitea/heroku)
	- backed up securly (dropbox?)
- web3.0 (fleek)
- api based headless cms (sanity?)
	- needs to integrate with dropshippers (printify, book publishers, etc)
	- gui notes backend (jekyll/sanity?)
- frontend (jekyll)(hugo?)
- store functions (snipcart?)
	- needs to manage worldwide taxes
  
  
---  
  
*2022-20-21*  
---  
   
working code for hours    
would like to display a line item with the date, total number of hours worked, and projects worked on   
this can drop open to show the line items from that day  
  
pulled not-quite-working code:  

```
{% comment %}
<div> <!--hours-->  
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
          {{ day | limit: 1 }}            <!-- date -->
          {{ time | plus: hours.hours }}  <!-- total hours for date? -->
          {{ project }}                   <!-- contributions on date -->
          </li>
          {% endif %}
        </summary>
        <li>{{ hours.hours }}, {{ hours.date }}, {{ hours.client }}, {{ hours.project }}, {{ hours.description }}</li>
        {% endfor %}
      </details>      
      <!--
      hours worked in past two weeks, hours in past month, total hours
      three most recently contributed to projects
      stale project(s) (longest time between now and past contribution)
      -->
      <ul>
        {% for hours in foo.minutes %}    
        <li>{{ hours.hours }}, {{ hours.date }}, {{ hours.client }}, {{ hours.project }}, {{ hours.description }}</li>
        {% endfor %}   
      </ul>
</div>
{% comment %}
```
  
   
---  
  
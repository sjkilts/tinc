---
published: true
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
   
*sites*  
---  
  
webapp as localhost:	¿heroku server?  
  
version control:		gitea hosted on heroku backed up [somewhere]  
  
frontend:				jekyll or hugo base theme / framework  
						manage themes/framework/skins with [storybook?]  
						minimal skin for each site  
                    	store managed with [snipcart?]  
                    	products and content managed with [sanity? netlify?]  
                    	hosted on fleek with #hash and web3.0  
                          
backend:				products and content managed with headless cms api  
						backed up to cloud and gitea  
                    	managed on localhost web app  
						notes plugin [thanks Hieu Pham](https://medium.com/ionic-prototyping/my-journey-to-sanity-io-fe0a6576a417)  
                          
sales channels: 		jekyll/hugo site snipcart  
						printify  
                        etsy  
  						sellfy?  
                        market ionic? -themes  
                        gumroad?  
                        
analytics:				find a google alternative

marketing: 				heroku server app for email list management
						should be able to write a plug-in for sanity to manage email lists
                        alert email list with new products
                        alert socials when content is pushed to sales channel
  
---   
   
*scottkilts.com*  
---  
  
you need a localhost web app (heroku?)
- it's nice to set this up on the mac, but can you run a local host on ipad etc? haven't seen a good way.
- keeping the mac up to date over cell connection is a true barrier to local development and shouldn't be necessary for the simple things we are doing here
  
stack ? :
- server (heroku)
- version control (gitea/heroku)
	- backed up securly (dropbox?)
- web3.0 (fleek)
- api based headless cms (sanity?)
	- needs to integrate with dropshippers (printify, book publishers, etc)
	- gui notes backend (jekyll/sanity?)
- frontend (jekyll)(hugo?)
- store functions (snipcart? sellfy? more research needed)
	- needs to manage worldwide taxes
  
  
[this person has solved many of our problems for his digital projects using Sanity.io](https://medium.com/ionic-prototyping/my-journey-to-sanity-io-fe0a6576a417)
  
  
---  
  
*2022-20-21*  
---  
   
working code for hours    
would like to display a line item with the date, total number of hours worked, and projects worked on   
this can drop open to show the line items from that day  
  
pulled not-quite-working code:  

```html

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

```
  
   
---

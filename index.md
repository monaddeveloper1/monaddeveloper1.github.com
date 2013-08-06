---
layout: page
title: Home 
tagline: 
---
{% include JB/setup %}
---

<table class="posts">
   <!-- Get 7 most recent entries by date (asc) -->
   {% for post in site.posts limit:5 offset:0 %}
   <tr>
      <th align="left" style="color:white">{{ post.date | date: "%A , %B %d, %Y" }} </th>
   </tr>
   <tr>
      <td>
         <span style="color:white"> {{ post.title }} </span>
         <p>{{ post.excerpt }}
            <a href="{{ BASE_PATH }}{{ post.url }}"> More... </a>				
         </p>
         <br/>
         <hr/>
      </td>
   </tr>
   {% endfor %} 
</table>




---
layout: page
permalink: /resources/
---

# Resources

CS 88

Guides
<!-- had to use HTML here, markdown loop gave weird spacing -->
<ul>
{% for post in site.resources %}
  <li>
    <a href="{{ post.url | relative_url }}">{{ post.title | escape }}</a>
  </li>
{% endfor %}
</ul>

Slides
* [Dictionaries, ADTs Slides](https://docs.google.com/a/berkeley.edu/presentation/d/1eUxUG0tQFFLIVEX1P9lGjsqGFPgkDZDtiPiOTNZJPps/edit?usp=sharing)
* [Midterm Review Slides](https://docs.google.com/a/berkeley.edu/presentation/d/1ohSibp_BEO8pj36xbSjtUyVz8YS6oO17RbGtNNHkda4/edit?usp=sharing)
* [Sequences, Generators Slides](https://docs.google.com/a/berkeley.edu/presentation/d/16AWlaNHD838EB8gfOBkHTVptAfDNEmMU0gdDbGPmjmQ/edit?usp=sharing)
* [Mutability, Nonlocal, Exceptions Slides](https://docs.google.com/a/berkeley.edu/presentation/d/1kUVhqoKJPD3VK2DCCYXJvw4Ec4oWhvSU4yoUiBnoHMY/edit?usp=sharing)
* [Exceptions, SQL Slides](https://docs.google.com/a/berkeley.edu/presentation/d/1odF4la9odxTEwPLRvsOrScZHWeB0Ht5zcvGceByKifc/edit?usp=sharing)

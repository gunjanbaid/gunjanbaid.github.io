---
layout: page
title: All Pages
---

## Pages

<!-- had to use HTML here, markdown loop gave weird spacing -->
<ul>
{% for page in site.pages %}
	{% if page.title != 'All Pages' %}
	 	<li>
    		<a href="{{ page.url | relative_url }}">{{ page.title | escape }}</a>
  		</li>
  	{% endif %}
{% endfor %}
</ul>

{% comment %}
	Linear weighted tag cloud for Jeykll
	
	Author: Sebastian Teumert (<http://www.teumert.net>, <http://www.github.com/NetzwergX>)
	
	This tag cloud uses a quite simple linear progression in order to weight tags. 
	For greater tag cloud, a logarithmic approach will give better results. In this tag cloud,
	100% is the base, and every tag gets additional wheight according to the number of times it 
	is used in posts.
	
	Calculating more complex equasions is made difficult by the fact that Liquid does not support
	math very well and you have to use filters.
	
	For more Jekyll widgets, see <http://www.github.com/NetzwergX/jekyll-template-toolkit>.
{% endcomment %}
<section class="tags">
	<h3>Tags</h3>		
	<ul>
	   {% for tag in site.tags %}      
	   <li>
	   	<a href="/tag/#{{ tag | first | cgi_encode }}">
		{{ tag | first }}</a>
		{% unless forloop.last %} {% endunless %}
	</li>
	{% endfor %}    
	</ul>
</section>
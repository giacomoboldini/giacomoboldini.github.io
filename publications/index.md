---
layout: secondary
---

# All publications

You can find all available PDFs for the publications in this page [here]({{ site.baseurl }}/papers/). Each individual publication's page will contain a direct link to the corresponding manuscript when available.

{% assign first_publication = site.categories.publications | first %}
{% assign year = first_publication.date | date: "%Y" %}

<h3>{{ year }}</h3>
<ul class="fa-ul talk-list">
{% for post in site.categories.publications %}
	{% assign cur_year = post.date | date: "%Y" %}
	{% if cur_year != year %}
</ul>
		{% assign year = cur_year %}
<h3>{{ year }}</h3>
<ul class="fa-ul talk-list">
	{% endif %}
	<li>
		<span class="fa-li"><i class="fas fa-book-open"></i></span>
		{{ post.authors }}. <a href="{{ post.url }}">{{ post.title }}</a><br/>
		{% if post.tags and post.tags.size > 0 %}
		    <a class="topic">{{ post.tags | join: '</a>&nbsp;&nbsp;<a class="topic">' }}</a><br/>
        {% endif %}
		<venue>{{ post.venue }}</venue><br/>
		<small>{{ post.kind }} - {{ post.when }}
		{% if post.location %}
			- {{ post.location }}
		{% endif %}
		{% if post.manuscript %}
			• <i class="fas fa-file-pdf"></i> PDF available
		{% endif %}
		{% if post.presentation %}
			• <i class="fas fa-file-powerpoint"></i> Slides available
		{% endif %}
		</small>
	</li>
{% endfor %}
</ul>
<!--
<h3>PhD Thesis</h3>
<ul class="fa-ul talk-list">
{% assign thesis = site.pages | where: "phdthesis", true %}
{% for post in thesis %}
	<li>
		<span class="fa-li"><i class="fas fa-graduation-cap"></i></span>
		{{ post.authors }}. <a href="{{ post.url }}">{{ post.title }}</a><br/>
		<a class="topic">{{ post.tags | join: '</a>&nbsp;&nbsp;<a class="topic">' }}</a><br/>
		<venue>{{ post.venue }}</venue><br/>
		<small>{{ post.kind }} - {{ post.when }}
		{% if post.location %}
			- {{ post.location }}
		{% endif %}
		{% if post.manuscript %}
			• <i class="fas fa-file-pdf"></i> PDF available
		{% endif %}
		{% if post.presentation %}
			• <i class="fas fa-file-powerpoint"></i> Slides available
		{% endif %}
		</small>
	</li>
{% endfor %}
</ul> -->
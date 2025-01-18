---
layout: secondary
---
# All Experiences
{% assign first_experience = site.categories.experiences | sort: 'start' | last %}
{% assign year = first_experience.start | date: "%Y" %}
<ul class="fa-ul talk-list">
{% assign sorted_experiences = site.categories.experiences | sort: 'start' | reverse %}
{% for post in sorted_experiences %}
	{% assign cur_year = post.start | slice: 0, 4 %}
	{% if cur_year != year %}
</ul>
<h3><strong>{{ cur_year }}</strong></h3>
<ul class="fa-ul talk-list">
	{% assign year = cur_year %}
	{% endif %}
	<li>
		{% if post.end and post.end != "-" %}
		<span class="fa-li">•</span>
		{% else %}
		<span class="fa-li"><i class="fas fa-sync-alt"></i></span>
		{% endif %}
		<a href="{{ post.url }}">{{ post.title }}</a><br/>
		<em>{{ post.employer }}</em>, {{ post.where }}<br/>
		<small>{{ post.start | date: "%Y-%m" }} - {% if post.end and post.end != "-" %}{{ post.end | date: "%Y-%m" }}{% else %}<strong>On Going</strong>{% endif %}</small>
		{% if post.desc %}
			<p>{{ post.desc }}</p>
		{% endif %}
	</li>
{% endfor %}
</ul>

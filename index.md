---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: mylayout
---

I am a Ph.D. student in Computer Science focusing on static analysis,
abstract interpretation, and program verification, with applications to
low-level languages.
My works (academic/personal/small-team) span topics such as parallel
computing, GPU programming, AI applied to source code analysis, and web
development for small to mid-sized websites.
As an Arduino/ESP32/self-hosting enthusiast, I enjoy working on DIY
projects, exploring embedded systems, and delving into network systems.


## Publications

<ul class="fa-ul">
{% for post in site.categories.publications limit: 2 %}
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

[All publications ({{ site.categories.publications.size }}) >>]({{ site.baseurl }}/publications/)

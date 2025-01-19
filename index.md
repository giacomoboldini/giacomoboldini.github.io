---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: mylayout
---

## About me

I am a PhD student in Computer Science focusing on static analysis,
abstract interpretation, and program verification, with applications to
low-level languages.
My works (academic/personal/small-team) span topics such as parallel
computing, GPU programming, AI applied to source code analysis, and web
development for small to mid-sized websites.
As an Arduino/ESP32/self-hosting enthusiast, I enjoy working on DIY
projects, exploring embedded systems, and delving into network systems.

## Education

<ul class="fa-ul">
    <!-- PhD -->
    <li>
        <span class="fa-li"><i class="fas fa-book-open"></i></span>
        <strong>PhD Student</strong>, Computer Science<br/>
        <em>Ca' Foscari University of Venice</em><br/>
        <small>2023 - <strong>On Going</strong></small><br/>
        <p>Static Analysis approaches for improving critical Software Engineering (supervisor: Pietro Ferrara).</p>
            <!-- <li><strong>Member of the Software and System Verification (SSV) research group.</strong></li> -->
    </li>
    <!-- M.S. -->
    <li>
        <span class="fa-li"><i class="fas fa-graduation-cap"></i></span>
        <strong>Master of Science (M.S.)</strong>, Computer Science<br/>
        <em>University of Parma</em><br/>
        <small>2020 - 2023</small><br/>
        <!-- <ul>
            <li><strong>Grade:</strong> 110/110 cum laude.</li>
            <li><strong>Thesis:</strong> Source code clustering via explainable code similarity based on control flow graph features.</li>
        </ul> -->
    </li>
    <!-- B.S. -->
    <li>
        <span class="fa-li"><i class="fas fa-graduation-cap"></i></span>
        <strong>Bachelor of Science (B.S.)</strong>, Computer Science<br/>
        <em>University of Parma</em><br/>
        <small>2016 - 2019</small><br/>
        <!-- <ul>
            <li><strong>Grade:</strong> 105/110.</li>
            <li><strong>Thesis:</strong> DualSPHysics code profiling with Intel Compiler.</li>
        </ul> -->
    </li>
    <!-- Industrial-Technical High School -->
    <li>
        <span class="fa-li"><i class="fas fa-graduation-cap"></i></span>
        <strong>Industrial‑Technical High School Diploma</strong> in Computer Science<br/>
        <em>M.R. Padre Giovanni Bonsignori</em><br/>
        <small>2011 - 2016</small><br/>
        <!-- <ul>
            <li><strong>Grade:</strong> 85/100.</li>
        </ul> -->
    </li>
</ul>

## Experience
<ul class="fa-ul">
{% assign sorted_experiences = site.categories.experiences | sort: 'start' | reverse %}
{% for post in sorted_experiences limit: 2%}
    <li>
        {% if post.end and post.end != "-" %}
        <span class="fa-li">•</span>
        {% else %}
        <span class="fa-li"><i class="fas fa-sync-alt"></i></span>
        {% endif %}
        <a href="{{ post.url }}">{{ post.title }}</a><br/>
        <em>{{ post.employer }}</em>, {{ post.where }}<br/>
        <small>{{ post.start }} - {% if post.end and post.end != "-" %}{{ post.end }}{% else %}<strong>On Going</strong>{% endif %}</small>
        {% if post.desc %}
            <p>{{ post.desc }}</p>
        {% endif %}
    </li>
{% endfor %}
</ul>

[All experiences ({{ site.categories.experiences.size }}) >>]({{ site.baseurl }}/experiences/)

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

## Research Community Activities

<ul class="fa-ul">
    <!-- SSV member -->
    <li>
        <span class="fa-li">•</span>
        <strong>Member</strong>,
        <a href="https://unive-ssv.github.io/" target="_blank">Software and System Verification (SSV)</a> research group @ Ca' Foscari University of Venice<br/>
        <small>09/2024 – On Going</small><br/>
    </li>
    <br />
    <!-- Lipari Summer School on Abstract Interpretation -->
    <li>
        <span class="fa-li">•</span>
        <strong>Attendee</strong>, <em>Lipari Summer School on Abstract Interpretation (ABSINT24)</em><br/>
        <em>Lipari, Italy</em><br/>
        <small>01/09/2024 – 07/09/2024</small><br/>
        <ul>
            <li><a href="https://drive.google.com/file/d/1uhLXjf0C_OeptfQwxXwk_3T8aFOkDMYC/view?pli=1" target="_blank">ABSINT24 program link</a></li>
        </ul>
    </li>
    <!-- PLDI24 + PLMW -->
    <li>
        <span class="fa-li">•</span>
        <strong>Attendee</strong>, <em>PLDI24 + Programming Languages Mentoring Workshop (PLMW)</em><br/>
        <em>Copenhagen, Denmark</em><br/>
        <small>24/06/2024 – 28/06/2024</small><br/>
        <ul>
            <li><a href="https://pldi24.sigplan.org/track/PLMW-PLDI-2024#program" target="_blank">PLMW program link</a> and <a href="https://pldi24.sigplan.org/program/program-pldi-2024/" target="_blank">PLDI24 program link</a></li>
        </ul>
    </li>
    <!-- Challenges of Software Verification Symposium 2024 -->
    <li>
        <span class="fa-li">•</span>
        <strong>Attendee and Session Chair</strong>, <em>Challenges of Software Verification Symposium 2024 (CSV24)</em><br/>
        <em>Venice, Italy</em><br/>
        <small>06/06/2024 – 07/06/2024</small><br/>
        <ul>
            <li><a href="https://unive-ssv.github.io/events/2024/06/06/csv.html" target="_blank">CSV24 program link</a></li>
        </ul>
    </li>
</ul>

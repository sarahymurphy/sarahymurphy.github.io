---
layout: page
title: Find me online
tags: 
date: 2024-02-11
comments: false
---

<div class="findme-page">
	<div class="findme-wrap">
	<p class="findme-intro">One place for all my online profiles.</p>

	<ul class="findme-links">
		{% if site.email %}
			<li><a href="mailto:{{ site.email }}" target="_blank" rel="noopener noreferrer">Email</a></li>
		{% endif %}

		{% if site.github-url %}
			<li><a href="https://github.com/{{ site.github-url }}" target="_blank" rel="noopener noreferrer">GitHub</a></li>
		{% endif %}

		{% if site.linkedin %}
			<li><a href="https://www.linkedin.com/in/{{ site.linkedin }}" target="_blank" rel="noopener noreferrer">LinkedIn</a></li>
		{% endif %}

		{% if site.google-scholar %}
			<li><a href="https://scholar.google.com/citations?user={{ site.google-scholar }}" target="_blank" rel="noopener noreferrer">Google Scholar</a></li>
		{% endif %}

		{% if site.orcid %}
			<li><a href="https://orcid.org/{{ site.orcid }}" target="_blank" rel="noopener noreferrer">ORCID</a></li>
		{% endif %}

		<li><a href="https://sarahymurphy.myportfolio.com/" target="_blank" rel="noopener noreferrer">Portfolio</a></li>
	</ul>
	</div>
</div>


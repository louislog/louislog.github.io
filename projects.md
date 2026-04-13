---
layout: default
title: "Projects"
permalink: /projects/
---

## 项目 Projects

{% assign projects = site.data.public_projects %}

{% if projects and projects.size > 0 %}
<div class="project-grid">
	{% for project in projects %}
	<article class="project-card">
		<h3 class="project-title">
			<a href="{{ project.html_url }}" target="_blank" rel="noopener noreferrer">{{ project.name }}</a>
		</h3>

		<p class="project-desc">
			{% if project.description and project.description != "" %}
				{{ project.description }}
			{% else %}
				暂无项目简介。
			{% endif %}
		</p>

		<div class="project-meta">
			<span>语言: {{ project.language | default: "Unknown" }}</span>
			<span>Star: {{ project.stargazers_count | default: 0 }}</span>
			<span>更新: {{ project.updated_at | date: "%Y-%m-%d" }}</span>
		</div>

		{% if project.homepage and project.homepage != "" %}
		<p class="project-homepage">
			<a href="{{ project.homepage }}" target="_blank" rel="noopener noreferrer">项目主页</a>
		</p>
		{% endif %}
	</article>
	{% endfor %}
</div>
{% else %}
<p class="project-empty">暂无公开项目。</p>
{% endif %}


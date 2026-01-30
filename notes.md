---
layout: default
title: "笔记"
permalink: /notes/
---

## 笔记

这里是我个人记录的笔记，包括 **Code 开发**、**个人分享** 等，会持续更新。

---

<section class="section">
  <h2>Code</h2>
  <ul class="post-list">
    {% for note in site.notes %}
      {% if note.category == "开发" %}
        <li class="post-item">
          <span class="post-date">{{ note.date | date: "%Y-%m-%d" }}</span>
          <a class="post-title" href="{{ note.url | relative_url }}">{{ note.title }}</a>
          {% if note.excerpt %}<span class="post-excerpt"> — {{ note.excerpt | strip_html | truncate: 60 }}</span>{% endif %}
        </li>
      {% endif %}
    {% endfor %}
    {% assign dev_notes = site.notes | where: "category", "开发" %}
    {% if dev_notes.size == 0 %}
      <li class="post-item empty">暂无开发类笔记，后续会在这里更新。</li>
    {% endif %}
  </ul>
</section>

<section class="section">
  <h2>Share</h2>
  <ul class="post-list">
    {% for note in site.notes %}
      {% if note.category == "分享" %}
        <li class="post-item">
          <span class="post-date">{{ note.date | date: "%Y-%m-%d" }}</span>
          <a class="post-title" href="{{ note.url | relative_url }}">{{ note.title }}</a>
          {% if note.excerpt %}<span class="post-excerpt"> — {{ note.excerpt | strip_html | truncate: 60 }}</span>{% endif %}
        </li>
      {% endif %}
    {% endfor %}
    {% assign share_notes = site.notes | where: "category", "分享" %}
    {% if share_notes.size == 0 %}
      <li class="post-item empty">暂无分享类笔记，后续会在这里更新。</li>
    {% endif %}
  </ul>
</section>

<section class="section">
  <h2>全部笔记（按时间）</h2>
  <ul class="post-list">
    {% assign sorted_notes = site.notes | sort: "date" | reverse %}
    {% for note in sorted_notes %}
      <li class="post-item">
        <span class="post-date">{{ note.date | date: "%Y-%m-%d" }}</span>
        <span class="note-category tag">{{ note.category | default: "笔记" }}</span>
        <a class="post-title" href="{{ note.url | relative_url }}">{{ note.title }}</a>
      </li>
    {% endfor %}
    {% if site.notes.size == 0 %}
      <li class="post-item empty">暂无笔记。</li>
    {% endif %}
  </ul>
</section>

---
layout: splash
title: "学术研究笔记"
header:
  overlay_color: "#000"
  overlay_filter: "0.5"
  overlay_image: /assets/images/research-bg.jpg
excerpt: "数学理论探索与计算实现"
---

## 最新内容

{% assign latest_notes = site.notes | sort: 'date' | reverse | limit: 5 %}
{% for note in latest_notes %}
- [{{ note.title }}]({{ note.url }}) {% if note.tags %}<small>{{ note.tags | join: ", " }}</small>{% endif %}
{% endfor %}

## 研究领域

<div class="tag-cloud">
{% assign all_tags = site.notes | map: 'tags' | join: ',' | split: ',' | uniq | sort %}
{% for tag in all_tags %}
  {% if tag != "" %}
    {% assign tag_posts = site.notes | where_exp: "post", "post.tags contains tag" %}
    <a href="{{ site.baseurl }}/tags/#{{ tag | slugify }}" class="tag-link">
      {{ tag }} ({{ tag_posts.size }})
    </a>
  {% endif %}
{% endfor %}
</div>

<style>
.tag-cloud {
  margin: 2rem 0;
}
.tag-link {
  display: inline-block;
  margin: 0.25rem;
  padding: 0.5rem 1rem;
  background: #f1f3f4;
  border-radius: 1rem;
  text-decoration: none;
  color: #333;
  font-size: 0.9rem;
  transition: all 0.3s ease;
}
.tag-link:hover {
  background: #e8eaed;
  color: #1a73e8;
}
</style>

## 关于本站

这是我的个人学术研究平台，记录数学理论学习、研究思考和代码实现。内容涵盖但不限于：

- **理论数学**：从基础到前沿的数学理论
- **应用数学**：数值计算、算法设计
- **代码实现**：理论的程序化实现
- **研究笔记**：学习心得与思考总结

内容会持续更新，研究领域会不断扩展。

---

*"数学是打开科学大门的钥匙"*

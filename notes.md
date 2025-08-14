---
title: "学术笔记"
layout: single
permalink: /notes/
classes: wide
---

# 📚 学术笔记

这里收录我的数学研究笔记和理论探索，按专题系统化组织。

## 🔢 数值分析系列

{% assign numerical_posts = '' | split: '' %}
{% for post in site.notes %}
  {% if post.path contains 'numerical-analysis' %}
    {% assign numerical_posts = numerical_posts | push: post %}
  {% endif %}
{% endfor %}
{% assign numerical_posts = numerical_posts | sort: 'date' %}

{% if numerical_posts.size > 0 %}

{% for post in numerical_posts %}
### [{{ post.title }}]({{ post.url | relative_url }})

{% if post.excerpt %}
{{ post.excerpt | strip_html | truncate: 120 }}
{% endif %}

{% if post.date %}
**发布时间**: {{ post.date | date: "%Y年%m月%d日" }}
{% endif %}

{% if post.tags and post.tags.size > 0 %}
**标签**: {% for tag in post.tags limit: 5 %}{{ tag }}{% unless forloop.last %}, {% endunless %}{% endfor %}
{% endif %}

---
{% endfor %}

{% else %}

<div class="notice--info">
  <h4>数值分析系列</h4>
  <p>从实数理论出发，构建完整的数值分析理论框架</p>
  <p><em>即将开始...</em></p>
</div>

{% endif %}

---

## 📊 概率论系列

{% assign probability_posts = '' | split: '' %}
{% for post in site.notes %}
  {% if post.path contains 'probability-theory' %}
    {% assign probability_posts = probability_posts | push: post %}
  {% endif %}
{% endfor %}
{% assign probability_posts = probability_posts | sort: 'date' %}

{% if probability_posts.size > 0 %}

{% for post in probability_posts %}
### [{{ post.title }}]({{ post.url | relative_url }})

{% if post.excerpt %}
{{ post.excerpt | strip_html | truncate: 120 }}
{% endif %}

{% if post.date %}
**发布时间**: {{ post.date | date: "%Y年%m月%d日" }}
{% endif %}

---
{% endfor %}

{% else %}

<div class="notice--info">
  <h4>概率论系列</h4>
  <p>概率论的严格数学基础与现代发展</p>
  <p><em>计划中...</em></p>
</div>

{% endif %}

---

## 📐 其他数学主题

{% assign other_posts = '' | split: '' %}
{% for post in site.notes %}
  {% assign is_numerical = false %}
  {% assign is_probability = false %}
  
  {% if post.path contains 'numerical-analysis' %}
    {% assign is_numerical = true %}
  {% endif %}
  {% if post.path contains 'probability-theory' %}
    {% assign is_probability = true %}
  {% endif %}
  
  {% unless is_numerical or is_probability %}
    {% assign other_posts = other_posts | push: post %}
  {% endunless %}
{% endfor %}
{% assign other_posts = other_posts | sort: 'date' | reverse %}

{% if other_posts.size > 0 %}

{% for post in other_posts %}
### [{{ post.title }}]({{ post.url | relative_url }})

{% if post.excerpt %}
{{ post.excerpt | strip_html | truncate: 120 }}
{% endif %}

{% if post.date %}
**发布时间**: {{ post.date | date: "%Y年%m月%d日" }}
{% endif %}

---
{% endfor %}

{% else %}

<div class="notice--secondary">
  <h4>更多主题</h4>
  <p>根据研究需要，会不定期添加其他数学主题的内容</p>
</div>

{% endif %}

---

## 📖 阅读指南

### 📚 学习建议
- **系统性学习**：建议按系列顺序阅读，每个系列内部有逻辑递进关系
- **理论与实践**：理论分析配有相应的数值实验和代码实现
- **深度思考**：注重概念的深层理解和数学直觉的培养

### 🎯 内容特色
- **严谨的数学表述**：遵循现代数学的表达规范
- **从基础到前沿**：从基本概念到研究前沿的完整覆盖
- **跨学科视角**：结合计算科学、工程应用等多重视角

### 💬 交流反馈
欢迎通过邮件或GitHub进行学术讨论，指正错误，提出建议。

**统计信息**: 当前共有 {{ site.notes.size }} 篇学术笔记
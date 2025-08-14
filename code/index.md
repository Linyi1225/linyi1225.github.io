---
title: "代码实现"
layout: single
permalink: /code/
author_profile: true
---

# 💻 代码实现

*理论与实践的桥梁 • 数学概念的程序化实现*

## 🚀 最新项目

{% if site.code.size > 0 %}

{% assign latest_code = site.code | sort: 'date' | reverse %}
{% for project in latest_code limit: 3 %}

### [{{ project.title }}]({{ project.url | relative_url }})

{% if project.excerpt %}
{{ project.excerpt | strip_html | truncate: 120 }}
{% endif %}

**发布时间**: {{ project.date | date: "%Y年%m月" }}

{% if project.tags %}
**标签**: {% for tag in project.tags %}{{ tag }}{% unless forloop.last %}, {% endunless %}{% endfor %}
{% endif %}

---

{% endfor %}

{% else %}

**代码项目即将上线**

这里将展示数学理论的程序化实现和算法演示，敬请期待！

{% endif %}

## 📚 按编程语言分类

### Python 项目

{% assign python_posts = '' | split: '' %}
{% for post in site.code %}
  {% if post.tags contains 'Python' or post.tags contains 'python' %}
    {% assign python_posts = python_posts | push: post %}
  {% endif %}
{% endfor %}

{% if python_posts.size > 0 %}
{% for post in python_posts %}
- [{{ post.title }}]({{ post.url | relative_url }}){% if post.date %} ({{ post.date | date: "%Y-%m-%d" }}){% endif %}
{% endfor %}
{% else %}
*暂无 Python 项目，敬请期待*
{% endif %}

### MATLAB 项目

{% assign matlab_posts = '' | split: '' %}
{% for post in site.code %}
  {% if post.tags contains 'MATLAB' or post.tags contains 'matlab' %}
    {% assign matlab_posts = matlab_posts | push: post %}
  {% endif %}
{% endfor %}

{% if matlab_posts.size > 0 %}
{% for post in matlab_posts %}
- [{{ post.title }}]({{ post.url | relative_url }}){% if post.date %} ({{ post.date | date: "%Y-%m-%d" }}){% endif %}
{% endfor %}
{% else %}
*暂无 MATLAB 项目，敬请期待*
{% endif %}

### Julia 项目

{% assign julia_posts = '' | split: '' %}
{% for post in site.code %}
  {% if post.tags contains 'Julia' or post.tags contains 'julia' %}
    {% assign julia_posts = julia_posts | push: post %}
  {% endif %}
{% endfor %}

{% if julia_posts.size > 0 %}
{% for post in julia_posts %}
- [{{ post.title }}]({{ post.url | relative_url }}){% if post.date %} ({{ post.date | date: "%Y-%m-%d" }}){% endif %}
{% endfor %}
{% else %}
*暂无 Julia 项目，敬请期待*
{% endif %}

### R 项目

{% assign r_posts = '' | split: '' %}
{% for post in site.code %}
  {% if post.tags contains 'R' %}
    {% assign r_posts = r_posts | push: post %}
  {% endif %}
{% endfor %}

{% if r_posts.size > 0 %}
{% for post in r_posts %}
- [{{ post.title }}]({{ post.url | relative_url }}){% if post.date %} ({{ post.date | date: "%Y-%m-%d" }}){% endif %}
{% endfor %}
{% else %}
*暂无 R 项目，敬请期待*
{% endif %}

## 📚 使用说明

### 代码组织
- **理论实现**: 数学理论的程序化实现
- **算法演示**: 算法的详细实现和解释  
- **工具函数**: 实用的计算工具
- **可视化**: 数据可视化和图形展示

### 开源协议
所有代码遵循开源原则，欢迎学习使用和改进。

---

*"代码是理论的最佳验证"*

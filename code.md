---
title: "代码实现"
layout: single
permalink: /code/
classes: wide
---

# 💻 代码实现

*理论与实践的桥梁 • 数学概念的程序化实现*

**项目统计**: {{ site.code.size }} 个项目

## 🚀 最新项目

{% assign latest_code = site.code | sort: 'date' | reverse | limit: 3 %}
{% if latest_code.size > 0 %}

{% for project in latest_code %}
### [{{ project.title }}]({{ project.url | relative_url }})

{% if project.excerpt %}
{{ project.excerpt | strip_html | truncate: 120 }}
{% endif %}

**发布时间**: {{ project.date | date: "%Y年%m月%d日" }}

{% if project.tags %}
**标签**: {% for tag in project.tags %}{{ tag }}{% unless forloop.last %}, {% endunless %}{% endfor %}
{% endif %}

{% if project.github %}
[**GitHub源码**]({{ project.github }}){: .btn .btn--primary}
{% endif %}

---
{% endfor %}

{% else %}

<div class="notice--info">
  <h4>代码项目即将上线</h4>
  <p>这里将展示数学理论的程序化实现和算法演示，敬请期待！</p>
</div>

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
- **[{{ post.title }}]({{ post.url | relative_url }})**{% if post.date %} - {{ post.date | date: "%Y-%m-%d" }}{% endif %}
  {% if post.excerpt %}<br>*{{ post.excerpt | strip_html | truncate: 100 }}*{% endif %}
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
- **[{{ post.title }}]({{ post.url | relative_url }})**{% if post.date %} - {{ post.date | date: "%Y-%m-%d" }}{% endif %}
  {% if post.excerpt %}<br>*{{ post.excerpt | strip_html | truncate: 100 }}*{% endif %}
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
- **[{{ post.title }}]({{ post.url | relative_url }})**{% if post.date %} - {{ post.date | date: "%Y-%m-%d" }}{% endif %}
  {% if post.excerpt %}<br>*{{ post.excerpt | strip_html | truncate: 100 }}*{% endif %}
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
- **[{{ post.title }}]({{ post.url | relative_url }})**{% if post.date %} - {{ post.date | date: "%Y-%m-%d" }}{% endif %}
  {% if post.excerpt %}<br>*{{ post.excerpt | strip_html | truncate: 100 }}*{% endif %}
{% endfor %}
{% else %}
*暂无 R 项目，敬请期待*
{% endif %}

---

## 📚 按应用领域分类

### 数值分析

{% assign numerical_code = '' | split: '' %}
{% for post in site.code %}
  {% if post.path contains 'numerical-analysis' or post.tags contains '数值分析' %}
    {% assign numerical_code = numerical_code | push: post %}
  {% endif %}
{% endfor %}

{% if numerical_code.size > 0 %}
{% for post in numerical_code %}
- **[{{ post.title }}]({{ post.url | relative_url }})**{% if post.date %} - {{ post.date | date: "%Y-%m-%d" }}{% endif %}
{% endfor %}
{% else %}
*数值分析代码实现即将发布*
{% endif %}

### 概率统计

{% assign prob_code = '' | split: '' %}
{% for post in site.code %}
  {% if post.path contains 'probability' or post.tags contains '概率论' or post.tags contains '统计' %}
    {% assign prob_code = prob_code | push: post %}
  {% endif %}
{% endfor %}

{% if prob_code.size > 0 %}
{% for post in prob_code %}
- **[{{ post.title }}]({{ post.url | relative_url }})**{% if post.date %} - {{ post.date | date: "%Y-%m-%d" }}{% endif %}
{% endfor %}
{% else %}
*概率统计代码实现计划中*
{% endif %}

---

## 📚 使用说明

### 代码特色
- **理论实现**: 数学概念的程序化表达
- **算法演示**: 详细的实现过程和性能分析
- **工具函数**: 实用的计算工具和辅助函数
- **可视化**: 数据可视化和图形化展示

### 运行环境
大部分代码基于以下环境开发和测试：
- **Python**: 3.8+ (NumPy, SciPy, Matplotlib, Jupyter)
- **MATLAB**: R2020a+
- **Julia**: 1.6+
- **R**: 4.0+

### 开源协议
所有代码遵循开源原则，欢迎学习使用和改进。商业使用请事先联系。

---

*"代码是理论的最佳验证"*
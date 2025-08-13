---
title: "代码实现"
layout: single
permalink: /code/
author_profile: true
sidebar:
  nav: "code_nav"
---

# 代码实现

这里收录理论的程序化实现、算法演示和计算工具。

## 按编程语言分类

{% assign all_tags = site.code | map: 'tags' | join: ',' | split: ',' | uniq | sort %}
{% assign languages = "python,r,julia,matlab,cpp,javascript" | split: "," %}

{% for lang in languages %}
  {% if all_tags contains lang %}
    {% assign lang_posts = site.code | where_exp: "post", "post.tags contains lang" %}
    {% if lang_posts.size > 0 %}
### {{ lang | capitalize }}
{% for post in lang_posts %}
- [{{ post.title }}]({{ post.url }}) 
  <small>{{ post.date | date: "%Y-%m-%d" }}</small>
  {% if post.excerpt %}<br><em>{{ post.excerpt }}</em>{% endif %}
{% endfor %}
    {% endif %}
  {% endif %}
{% endfor %}

## 按应用领域分类

{% assign domains = "numerical-methods,monte-carlo,optimization,machine-learning,statistics,visualization" | split: "," %}

{% for domain in domains %}
  {% if all_tags contains domain %}
    {% assign domain_posts = site.code | where_exp: "post", "post.tags contains domain" %}
    {% if domain_posts.size > 0 %}
### {{ domain | replace: "-", " " | capitalize }}
{% for post in domain_posts %}
- [{{ post.title }}]({{ post.url }})
  {% if post.tags %}
    <small>{{ post.tags | join: ", " }}</small>
  {% endif %}
{% endfor %}
    {% endif %}
  {% endif %}
{% endfor %}

## 最新代码

{% assign latest_code = site.code | sort: 'date' | reverse | limit: 5 %}
{% if latest_code.size > 0 %}
{% for post in latest_code %}
- **{{ post.date | date: "%m-%d" }}** [{{ post.title }}]({{ post.url }})
  {% if post.tags %}<small>Tags: {{ post.tags | join: ", " }}</small>{% endif %}
  {% if post.excerpt %}<br><em>{{ post.excerpt }}</em>{% endif %}
{% endfor %}
{% else %}
<p><em>暂无代码内容，即将更新...</em></p>
{% endif %}

## 使用说明

### 代码组织
- **理论实现**：数学理论的程序化实现
- **算法演示**：经典算法的详细实现和解释
- **工具函数**：常用的计算工具和辅助函数
- **可视化**：数据可视化和图形展示代码

### 环境要求
大部分代码基于以下环境：
- **Python**: 3.8+ (NumPy, SciPy, Matplotlib)
- **R**: 4.0+ 
- **Julia**: 1.6+

### 许可说明
所有代码遵循学术共享原则，欢迎学习使用，商业用途请联系。

---

*"代码是理论的最佳验证"*
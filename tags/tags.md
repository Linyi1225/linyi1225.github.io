---
title: "标签索引"
layout: single
permalink: /tags/
author_profile: true
classes: wide
toc: true
toc_label: "快速导航"
toc_icon: "tags"
---

<div class="page__hero--overlay" style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); padding: 2rem 0; margin-bottom: 2rem; border-radius: 10px;">
  <div class="wrapper">
    <h1 style="color: white; text-align: center; margin: 0; font-size: 2.5rem;">🏷️ 标签导航</h1>
    <p style="color: rgba(255,255,255,0.9); text-align: center; margin: 0.5rem 0 0 0; font-size: 1.1rem;">通过标签快速定位您感兴趣的内容</p>
  </div>
</div>

## 📊 标签统计

{% assign tags = site.tags | sort %}
{% assign tag_count = site.tags | size %}

<div class="notice--info">
  <h4><i class="fas fa-chart-bar"></i> 当前统计</h4>
  <p><strong>标签总数：</strong>{{ tag_count }} 个 | <strong>文章总数：</strong>{{ site.posts.size }} 篇</p>
</div>

## 🎯 标签分类

### 📚 学科领域标签

<div class="tag-category">
  <div class="tags-grid">
    {% for tag in tags %}
      {% assign tag_name = tag[0] %}
      {% assign tag_posts = tag[1] %}
      {% if tag_name contains '代数' or tag_name contains '几何' or tag_name contains '分析' or tag_name contains '概率' or tag_name contains '统计' or tag_name contains '拓扑' or tag_name contains '数论' %}
        <a href="#{{ tag_name | slugify }}" class="tag-item subject-tag">
          <span class="tag-name">{{ tag_name }}</span>
          <span class="tag-count">{{ tag_posts.size }}</span>
        </a>
      {% endif %}
    {% endfor %}
    <!-- 如果没有匹配的标签，显示示例 -->
    {% if tag_count == 0 %}
      <div class="tag-item subject-tag example">
        <span class="tag-name">线性代数</span>
        <span class="tag-count">0</span>
      </div>
      <div class="tag-item subject-tag example">
        <span class="tag-name">微积分</span>
        <span class="tag-count">0</span>
      </div>
      <div class="tag-item subject-tag example">
        <span class="tag-name">概率论</span>
        <span class="tag-count">0</span>
      </div>
    {% endif %}
  </div>
</div>

### 💻 技术工具标签

<div class="tag-category">
  <div class="tags-grid">
    {% for tag in tags %}
      {% assign tag_name = tag[0] %}
      {% assign tag_posts = tag[1] %}
      {% if tag_name contains 'Python' or tag_name contains 'MATLAB' or tag_name contains 'R' or tag_name contains 'Julia' or tag_name contains 'LaTeX' or tag_name contains '编程' %}
        <a href="#{{ tag_name | slugify }}" class="tag-item tech-tag">
          <span class="tag-name">{{ tag_name }}</span>
          <span class="tag-count">{{ tag_posts.size }}</span>
        </a>
      {% endif %}
    {% endfor %}
    <!-- 示例标签 -->
    {% if tag_count == 0 %}
      <div class="tag-item tech-tag example">
        <span class="tag-name">Python</span>
        <span class="tag-count">0</span>
      </div>
      <div class="tag-item tech-tag example">
        <span class="tag-name">MATLAB</span>
        <span class="tag-count">0</span>
      </div>
    {% endif %}
  </div>
</div>

### 🎓 难度级别标签

<div class="tag-category">
  <div class="tags-grid">
    {% for tag in tags %}
      {% assign tag_name = tag[0] %}
      {% assign tag_posts = tag[1] %}
      {% if tag_name contains '基础' or tag_name contains '进阶' or tag_name contains '高级' or tag_name contains '入门' %}
        <a href="#{{ tag_name | slugify }}" class="tag-item level-tag">
          <span class="tag-name">{{ tag_name }}</span>
          <span class="tag-count">{{ tag_posts.size }}</span>
        </a>
      {% endif %}
    {% endfor %}
    <!-- 示例标签 -->
    {% if tag_count == 0 %}
      <div class="tag-item level-tag example">
        <span class="tag-name">基础理论</span>
        <span class="tag-count">0</span>
      </div>
      <div class="tag-item level-tag example">
        <span class="tag-name">进阶应用</span>
        <span class="tag-count">0</span>
      </div>
    {% endif %}
  </div>
</div>

## 📋 完整标签列表

{% if site.tags.size > 0 %}
  {% for tag in tags %}
    {% assign tag_name = tag[0] %}
    {% assign tag_posts = tag[1] %}
    
    <div class="tag-section" id="{{ tag_name | slugify }}">
      <h3 class="tag-title">
        <i class="fas fa-tag"></i> {{ tag_name }}
        <span class="tag-badge">{{ tag_posts.size }} 篇</span>
      </h3>
      
      <div class="tag-posts">
        {% for post in tag_posts %}
          <article class="tag-post-item">
            <h4><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h4>
            {% if post.date %}
              <time class="post-date">{{ post.date | date: "%Y年%m月%d日" }}</time>
            {% endif %}
            {% if post.excerpt %}
              <p class="post-excerpt">{{ post.excerpt | strip_html | truncate: 100 }}</p>
            {% endif %}
          </article>
        {% endfor %}
      </div>
    </div>
  {% endfor %}
{% else %}
  <div class="notice--warning">
    <h4><i class="fas fa-exclamation-triangle"></i> 暂无标签</h4>
   
  </div>
{% endif %}

---

## 💡 标签使用指南

### 🏷️ 推荐标签规范

为了更好地组织内容，建议使用以下标签规范：

**学科分类标签**
- `线性代数`、`微积分`、`概率论`、`数理统计`
- `数值分析`、`优化理论`、`图论`、`数论`

**内容类型标签**  
- `理论推导`、`应用实例`、`算法实现`、`习题解析`
- `研究心得`、`学习笔记`、`工具教程`

**技术工具标签**
- `Python`、`MATLAB`、`R语言`、`Mathematica`
- `LaTeX`、`Jupyter`、`可视化`

**难度级别标签**
- `入门基础`、`中等难度`、`进阶内容`、`专业研究`

### 📝 如何添加标签

在文章的前置元数据中添加标签：

```yaml
---
title: "你的文章标题"
tags:
  - 线性代数
  - Python
  - 基础理论
---
```

<style>
.tag-category {
  margin: 1.5rem 0;
}

.tags-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
  gap: 0.8rem;
  margin: 1rem 0;
}

.tag-item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0.6rem 1rem;
  border-radius: 8px;
  text-decoration: none;
  transition: all 0.3s ease;
  border: 2px solid transparent;
}

.tag-item:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 8px rgba(0,0,0,0.1);
  text-decoration: none;
}

.subject-tag {
  background: linear-gradient(135deg, #e3f2fd, #bbdefb);
  color: #1565c0;
}

.subject-tag:hover {
  border-color: #1565c0;
  color: #0d47a1;
}

.tech-tag {
  background: linear-gradient(135deg, #f3e5f5, #e1bee7);
  color: #7b1fa2;
}

.tech-tag:hover {
  border-color: #7b1fa2;
  color: #4a148c;
}

.level-tag {
  background: linear-gradient(135deg, #e8f5e8, #c8e6c9);
  color: #2e7d32;
}

.level-tag:hover {
  border-color: #2e7d32;
  color: #1b5e20;
}

.tag-item.example {
  opacity: 0.6;
  pointer-events: none;
}

.tag-name {
  font-weight: 600;
  font-size: 0.9rem;
}

.tag-count {
  background: rgba(255,255,255,0.9);
  padding: 0.2rem 0.5rem;
  border-radius: 12px;
  font-size: 0.8rem;
  font-weight: bold;
  min-width: 20px;
  text-align: center;
}

.tag-section {
  margin: 2rem 0;
  padding: 1.5rem;
  background: #f8f9fa;
  border-radius: 10px;
  border-left: 4px solid #007bff;
}

.tag-title {
  margin-bottom: 1rem;
  color: #333;
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.tag-badge {
  background: #007bff;
  color: white;
  padding: 0.2rem 0.6rem;
  border-radius: 12px;
  font-size: 0.8rem;
  font-weight: normal;
}

.tag-post-item {
  margin: 1rem 0;
  padding: 1rem;
  background: white;
  border-radius: 6px;
  border-left: 3px solid #28a745;
}

.tag-post-item h4 {
  margin: 0 0 0.5rem 0;
}

.tag-post-item h4 a {
  color: #333;
  text-decoration: none;
}

.tag-post-item h4 a:hover {
  color: #007bff;
}

.post-date {
  color: #666;
  font-size: 0.9rem;
  margin-right: 1rem;
}

.post-excerpt {
  color: #666;
  font-size: 0.9rem;
  margin: 0.5rem 0 0 0;
  line-height: 1.4;
}
</style>

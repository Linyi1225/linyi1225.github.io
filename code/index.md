---
title: "代码实现"
layout: single
permalink: /code/
author_profile: true
classes: wide
toc: true
toc_label: "代码导航"
toc_icon: "code"
---

<div class="code-hero">
  <div class="hero-content">
    <h1><i class="fas fa-code"></i> 代码实现</h1>
    <p>理论与实践的桥梁 • 数学概念的程序化实现</p>
    <div class="hero-stats">
      <div class="stat-item">
        <span class="stat-number">{{ site.code.size }}</span>
        <span class="stat-label">代码项目</span>
      </div>
      <div class="stat-item">
        {% assign all_tags = site.code | map: 'tags' | join: ',' | split: ',' | uniq %}
        <span class="stat-number">{{ all_tags.size }}</span>
        <span class="stat-label">技术标签</span>
      </div>
    </div>
  </div>
</div>

## 🚀 最新项目

{% assign latest_code = site.code | sort: 'date' | reverse | limit: 3 %}
{% if latest_code.size > 0 %}
<div class="featured-projects">
  {% for project in latest_code %}
  <div class="project-card featured">
    <div class="project-header">
      <h3><a href="{{ project.url | relative_url }}">{{ project.title }}</a></h3>
      {% if project.tags %}
        <div class="project-tags">
          {% for tag in project.tags limit: 3 %}
            <span class="tag {{ tag | downcase }}">{{ tag }}</span>
          {% endfor %}
        </div>
      {% endif %}
    </div>
    <div class="project-content">
      {% if project.excerpt %}
        <p>{{ project.excerpt | strip_html | truncate: 120 }}</p>
      {% endif %}
      <div class="project-meta">
        <span class="date"><i class="fas fa-calendar"></i> {{ project.date | date: "%Y年%m月" }}</span>
        {% if project.github %}
          <a href="{{ project.github }}" class="github-link" target="_blank">
            <i class="fab fa-github"></i> 源码
          </a>
        {% endif %}
      </div>
    </div>
  </div>
  {% endfor %}
</div>
{% else %}
<div class="empty-state-hero">
  <div class="empty-icon"><i class="fas fa-code"></i></div>
  <h3>代码项目即将上线</h3>
  <p>这里将展示数学理论的程序化实现和算法演示</p>
</div>
{% endif %}

## 💻 按编程语言分类

<div class="language-tabs">
  <div class="tab-nav">
    <button class="tab-btn active" data-tab="python"><i class="fab fa-python"></i> Python</button>
    <button class="tab-btn" data-tab="matlab"><i class="fas fa-calculator"></i> MATLAB</button>
    <button class="tab-btn" data-tab="julia"><i class="fas fa-rocket"></i> Julia</button>
    <button class="tab-btn" data-tab="r"><i class="fab fa-r-project"></i> R</button>
    <button class="tab-btn" data-tab="others"><i class="fas fa-code"></i> 其他</button>
  </div>
  
  <div class="tab-content">
    <!-- Python -->
    <div class="tab-pane active" id="python">
      {% assign python_posts = site.code | where_exp: "post", "post.tags contains 'Python' or post.tags contains 'python'" %}
      {% if python_posts.size > 0 %}
        <div class="projects-grid">
          {% for post in python_posts %}
            <div class="project-card">
              <h4><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h4>
              {% if post.excerpt %}
                <p>{{ post.excerpt | strip_html | truncate: 100 }}</p>
              {% endif %}
              <div class="project-footer">
                <span class="date">{{ post.date | date: "%Y-%m-%d" }}</span>
                {% if post.tags %}
                  <div class="mini-tags">
                    {% for tag in post.tags limit: 2 %}
                      {% unless tag == 'Python' or tag == 'python' %}
                        <span class="mini-tag">{{ tag }}</span>
                      {% endunless %}
                    {% endfor %}
                  </div>
                {% endif %}
              </div>
            </div>
          {% endfor %}
        </div>
      {% else %}
        <div class="empty-state">
          <div class="empty-icon"><i class="fab fa-python"></i></div>
          <h4>Python 项目</h4>
          <p>暂无内容，敬请期待</p>
        </div>
      {% endif %}
    </div>
    
    <!-- MATLAB -->
    <div class="tab-pane" id="matlab">
      {% assign matlab_posts = site.code | where_exp: "post", "post.tags contains 'MATLAB' or post.tags contains 'matlab'" %}
      {% if matlab_posts.size > 0 %}
        <div class="projects-grid">
          {% for post in matlab_posts %}
            <div class="project-card">
              <h4><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h4>
              {% if post.excerpt %}
                <p>{{ post.excerpt | strip_html | truncate: 100 }}</p>
              {% endif %}
              <div class="project-footer">
                <span class="date">{{ post.date | date: "%Y-%m-%d" }}</span>
              </div>
            </div>
          {% endfor %}
        </div>
      {% else %}
        <div class="empty-state">
          <div class="empty-icon"><i class="fas fa-calculator"></i></div>
          <h4>MATLAB 项目</h4>
          <p>暂无内容，敬请期待</p>
        </div>
      {% endif %}
    </div>
    
    <!-- Julia -->
    <div class="tab-pane" id="julia">
      {% assign julia_posts = site.code | where_exp: "post", "post.tags contains 'Julia' or post.tags contains 'julia'" %}
      {% if julia_posts.size > 0 %}
        <div class="projects-grid">
          {% for post in julia_posts %}
            <div class="project-card">
              <h4><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h4>
              {% if post.excerpt %}
                <p>{{ post.excerpt | strip_html | truncate: 100 }}</p>
              {% endif %}
              <div class="project-footer">
                <span class="date">{{ post.date | date: "%Y-%m-%d" }}</span>
              </div>
            </div>
          {% endfor %}
        </div>
      {% else %}
        <div class="empty-state">
          <div class="empty-icon"><i class="fas fa-rocket"></i></div>
          <h4>Julia 项目</h4>
          <p>暂无内容，敬请期待</p>
        </div>
      {% endif %}
    </div>
    
    <!-- R -->
    <div class="tab-pane" id="r">
      {% assign r_posts = site.code | where_exp: "post", "post.tags contains 'R' or post.tags contains 'r-lang'" %}
      {% if r_posts.size > 0 %}
        <div class="projects-grid">
          {% for post in r_posts %}
            <div class="project-card">
              <h4><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h4>
              {% if post.excerpt %}
                <p>{{ post.excerpt | strip_html | truncate: 100 }}</p>
              {% endif %}
              <div class="project-footer">
                <span class="date">{{ post.date | date: "%Y-%m-%d" }}</span>
              </div>
            </div>
          {% endfor %}
        </div>
      {% else %}
        <div class="empty-state">
          <div class="empty-icon"><i class="fab fa-r-project"></i></div>
          <h4>R 项目</h4>
          <p>暂无内容，敬请期待</p>
        </div>
      {% endif %}
    </div>
    
    <!-- Others -->
    <div class="tab-pane" id="others">
      {% assign other_posts = site.code | where_exp: "post", "post.tags contains 'C++' or post.tags contains 'JavaScript' or post.tags contains 'cpp'" %}
      {% if other_posts.size > 0 %}
        <div class="projects-grid">
          {% for post in other_posts %}
            <div class="project-card">
              <h4><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h4>
              {% if post.excerpt %}
                <p>{{ post.excerpt | strip_html | truncate: 100 }}</p>
              {% endif %}
              <div class="project-footer">
                <span class="date">{{ post.date | date: "%Y-%m-%d" }}</span>
              </div>
            </div>
          {% endfor %}
        </div>
      {% else %}
        <div class="empty-state">
          <div class="empty-icon"><i class="fas fa-code"></i></div>
          <h4>其他语言项目</h4>
          <p>暂无内容，敬请期待</p>
        </div>
      {% endif %}
    </div>
  </div>
</div>

## 📚 使用说明

### 代码组织
- **理论实现**：数学理论的程序化实现
- **算法演示**：算法的详细实现和解释  
- **工具函数**：实用的计算工具
- **可视化**：数据可视化和图形展示

### 开源协议
所有代码遵循开源原则，欢迎学习使用和改进。

---

<script>
document.addEventListener('DOMContentLoaded', function() {
  const tabBtns = document.querySelectorAll('.tab-btn');
  const tabPanes = document.querySelectorAll('.tab-pane');
  
  tabBtns.forEach(btn => {
    btn.addEventListener('click', function() {
      const targetTab = this.getAttribute('data-tab');
      
      // 移除所有活动状态
      tabBtns.forEach(b => b.classList.remove('active'));
      tabPanes.forEach(p => p.classList.remove('active'));
      
      // 激活当前标签
      this.classList.add('active');
      document.getElementById(targetTab).classList.add('active');
    });
  });
});
</script>

<style>
.code-hero {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  padding: 3rem 0;
  margin: -2rem -2rem 2rem -2rem;
  border-radius: 0 0 20px 20px;
  color: white;
  text-align: center;
}

.hero-content h1 {
  margin: 0 0 1rem 0;
  font-size: 2.5rem;
  font-weight: 700;
}

.hero-content p {
  margin: 0 0 2rem 0;
  font-size: 1.2rem;
  opacity: 0.9;
}

.hero-stats {
  display: flex;
  justify-content: center;
  gap: 2rem;
  flex-wrap: wrap;
}

.stat-item {
  text-align: center;
}

.stat-number {
  display: block;
  font-size: 2rem;
  font-weight: bold;
  color: #ffd700;
}

.stat-label {
  font-size: 0.9rem;
  opacity: 0.8;
}

.empty-state-hero {
  text-align: center;
  padding: 3rem 2rem;
  background: #f8f9fa;
  border-radius: 15px;
  margin: 2rem 0;
}

.empty-state-hero .empty-icon {
  font-size: 4rem;
  color: #6c757d;
  margin-bottom: 1rem;
}

.empty-state-hero h3 {
  color: #495057;
  margin-bottom: 1rem;
}

.empty-state-hero p {
  color: #6c757d;
  font-size: 1.1rem;
}

.featured-projects {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 1.5rem;
  margin: 2rem 0;
}

.project-card {
  background: white;
  border-radius: 12px;
  padding: 1.5rem;
  box-shadow: 0 2px 10px rgba(0,0,0,0.1);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  border: 1px solid #e9ecef;
}

.project-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 8px 25px rgba(0,0,0,0.15);
}

.project-card.featured {
  border-left: 4px solid #007bff;
}

.project-header {
  margin-bottom: 1rem;
}

.project-header h3,
.project-card h4 {
  margin: 0 0 0.5rem 0;
  color: #333;
}

.project-header h3 a,
.project-card h4 a {
  color: #333;
  text-decoration: none;
}

.project-header h3 a:hover,
.project-card h4 a:hover {
  color: #007bff;
}

.project-tags {
  display: flex;
  gap: 0.5rem;
  flex-wrap: wrap;
}

.tag {
  padding: 0.3rem 0.6rem;
  border-radius: 20px;
  font-size: 0.8rem;
  font-weight: 500;
  background: #e9ecef;
  color: #495057;
}

.project-content p {
  color: #666;
  line-height: 1.6;
  margin-bottom: 1rem;
}

.project-meta {
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-size: 0.9rem;
  color: #6c757d;
}

.github-link {
  color: #333;
  text-decoration: none;
}

.github-link:hover {
  color: #007bff;
}

.language-tabs {
  margin: 2rem 0;
}

.tab-nav {
  display: flex;
  gap: 0.5rem;
  margin-bottom: 2rem;
  flex-wrap: wrap;
}

.tab-btn {
  padding: 0.8rem 1.5rem;
  border: 2px solid #dee2e6;
  background: white;
  color: #495057;
  border-radius: 25px;
  cursor: pointer;
  transition: all 0.3s ease;
  font-weight: 500;
}

.tab-btn:hover,
.tab-btn.active {
  background: #007bff;
  color: white;
  border-color: #007bff;
}

.tab-pane {
  display: none;
}

.tab-pane.active {
  display: block;
}

.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 1.5rem;
}

.empty-state {
  text-align: center;
  padding: 3rem 2rem;
  color: #6c757d;
}

.empty-state .empty-icon {
  font-size: 3rem;
  margin-bottom: 1rem;
  opacity: 0.5;
}

.empty-state h4 {
  margin-bottom: 0.5rem;
  color: #495057;
}

.project-footer {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-top: 1rem;
  padding-top: 1rem;
  border-top: 1px solid #eee;
  font-size: 0.9rem;
  color: #6c757d;
}

.mini-tags {
  display: flex;
  gap: 0.3rem;
}

.mini-tag {
  padding: 0.2rem 0.5rem;
  background: #f8f9fa;
  border-radius: 12px;
  font-size: 0.8rem;
  color: #495057;
}

@media (max-width: 768px) {
  .code-hero {
    margin: -1rem -1rem 2rem -1rem;
    padding: 2rem 1rem;
  }
  
  .hero-content h1 {
    font-size: 2rem;
  }
  
  .hero-stats {
    gap: 1rem;
  }
  
  .tab-nav {
    justify-content: center;
  }
  
  .tab-btn {
    padding: 0.6rem 1rem;
    font-size: 0.9rem;
  }
}
</style>

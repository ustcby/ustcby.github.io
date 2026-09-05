---
layout: default
permalink: /digest/
title: 电子资讯
nav: true
nav_order: 2
---

<div class="post">

  <div class="header-bar">
    <h1>电子资讯梳理</h1>
    <h2>搬运值得收藏的好东西——论文、工具、课程、文章，附我的判断</h2>
  </div>

  <div class="tag-category-list">
    <ul class="p-0 m-0">
      <li><i class="fa-solid fa-tag fa-sm"></i> <a href="{{ '/blog/category/电子资讯/' | relative_url }}">电子资讯</a></li>
    </ul>
  </div>

  {% assign digest_posts = site.posts | where_exp: "post", "post.categories contains '电子资讯'" | sort: "date" | reverse %}

  {% if digest_posts.size == 0 %}
    <p style="color: var(--global-text-color-light); margin-top: 2rem;">还没有资讯，正在整理中……</p>
  {% else %}

  <ul class="post-list">
    {% for post in digest_posts %}
    {% assign read_time = post.content | number_of_words | divided_by: 180 | plus: 1 %}
    {% assign year = post.date | date: "%Y" %}
    {% assign tags = post.tags | join: "" %}

    <li>
      <h3>
        {% if post.redirect == blank %}
          <a class="post-title" href="{{ post.url | relative_url }}">{{ post.title }}</a>
        {% elsif post.redirect contains '://' %}
          <a class="post-title" href="{{ post.redirect }}" target="_blank">{{ post.title }}</a>
          <svg width="2rem" height="2rem" viewBox="0 0 40 40" xmlns="http://www.w3.org/2000/svg">
            <path d="M17 13.5v6H5v-12h6m3-3h6v6m0-6-9 9" class="icon_svg-stroke" stroke="#999" stroke-width="1.5" fill="none" fill-rule="evenodd" stroke-linecap="round" stroke-linejoin="round"></path>
          </svg>
        {% else %}
          <a class="post-title" href="{{ post.redirect | relative_url }}">{{ post.title }}</a>
        {% endif %}
      </h3>
      <p>{{ post.description }}</p>
      <p class="post-meta">
        {{ read_time }} min read &nbsp; &middot; &nbsp;
        {{ post.date | date: '%B %d, %Y' }}
        {% if post.source %}
        &nbsp; &middot; &nbsp; 来源：{{ post.source }}
        {% endif %}
      </p>
      <p class="post-tags">
        <a href="{{ year | prepend: '/blog/' | prepend: site.baseurl}}">
          <i class="fa-solid fa-calendar fa-sm"></i> {{ year }} </a>
        {% if tags != "" %}
          &nbsp; &middot; &nbsp;
          {% for tag in post.tags %}
          <a href="{{ tag | slugify | prepend: '/blog/tag/' | prepend: site.baseurl}}">
            <i class="fa-solid fa-hashtag fa-sm"></i> {{ tag }}</a>
            {% unless forloop.last %}
              &nbsp;
            {% endunless %}
          {% endfor %}
        {% endif %}
      </p>
    </li>
    {% endfor %}
  </ul>

  {% endif %}

</div>

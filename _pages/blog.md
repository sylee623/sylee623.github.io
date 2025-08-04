---
layout: default
permalink: /blog
title: blog
nav: true
nav_order: 5
pagination:
  enabled: true
  collection: posts
  permalink: /page/:num/
  per_page: 5
  sort_field: date
  sort_reverse: true
  trail:
    before: 1 # The number of links before the current page
    after: 3 # The number of links after the current page
---
<div class="post">
  <div class="header-bar">
    <h1>{{ site.blog_name }}</h1>
    <h2>{{ site.blog_description }}</h2>
  </div>

  <iframe src="/garden/" width="100%" height="1000px" style="border: none;"></iframe>
</div>


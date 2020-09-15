---
layout: default
title: What This MUSIC!
permalink: /tags/
content-type: eg
---

<style>
.category-content a {
    text-decoration: none;
    color: #4183c4;
}

.category-content a:hover {
    text-decoration: underline;
    color: #4183c4;
}
</style>

<main>
  {% include site_tags_cloud.html %}

  {% for tag in site.tags %}
    {% capture tag_name %}{{ tag | first }}{% endcapture %}
    <h2 class="tag-headline" id="{{ tag_name }}">
	  <i class="fa fa-tags"></i>&nbsp;Tag: <code class="tag">{{ tag_name }}</code>
	</h2>
	<ul>
      {% for post in tag.last %}
        <li class="tag-list">
	      <a href="{{ post.url }}">{{ post.title }}</a>
	      <span class="post-meta">
		    <small>{{ post.date | date: '%B %d, %Y' }} by {{ post.author }}</small>
		  </span>
	    </li>
      {% endfor %}
    </ul>
  {% endfor %}
</main>

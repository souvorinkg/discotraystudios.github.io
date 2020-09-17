---
layout: page
title: Blog
#background_style: bg-info
background_image: url('assets/img/sparkle.jpg')
# Add a link to the the top menu
background_style: bg-dark text-primary
menus:
  header:
    title: Blog
    weight: 2

sections:
---

{%- if site.posts.size > 0 -%}
    {%- for post in site.posts -%}
		{%- assign date_format = site.minima.date_format | default: "on %b %-d, %Y" -%}
<div class="row">
	<div class="col-md-4">
		<div class="blog-image"><img src="{{site.baseurl}}{{ post.image }}" alt="Blog Image"></div>
	</div>
	<div class="col-md-6">
		<div class="blog-info">
			<h2 class="title">
				<a class="post-link" href="{{ post.url | relative_url }}">
					<b>{{ post.title | escape }}</b>
				</a>
			</h2>
			<p>{%- if site.show_excerpts -%}
				{{ post.content | markdownify | strip_html | truncatewords: 40 }}
				<!--{{ post.excerpt }} -->
				{%- endif -%}
			</p>
		</div>
	</div>
	<div class="col-md-2">
		<div class="avatar-area">
			<a class="avatar" href="{{post.authorhome}}"><img src="{{post.avatar}}" alt="Profile Image"></a>
			<div class="right-area">
				<a class="name" href="{{post.authorhome}}"><b>{{post.author}}</b></a>
				<h6 class="date">{{ post.date | date: date_format }}</h6>
			</div>
		</div>
	</div>
</div>
	{%- endfor -%}
{%- endif -%}

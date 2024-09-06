---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
---

<div class="home">
<!-- section for featured post -->
<section class="site-section site-section-last">
    <div class="wrapper">
        <h1>Featuured articles</h1>
            {%  assign count = 0 %}
            {% for post in site.posts reversed  %}
                {% if post.featured == true and count < 2 %}
                    <div class="post post-featured"> 
                        <span class="post-meta">{{ post.date | date: "%b %-d, %Y" }}</span>
                        <h2>{{ post.title }}</h2>
                        <p>{{ post.content |  strip_html |  strip_newlines |  truncate: 200 }}</p>
                        <p class="post-read-more-link">
                            <a href="#">read more...</a>
                        </p>
                    </div>
                    {%  assign count = count | plus: 1 %}
                {% endif %}
            {% endfor %}
    </div>
</section>
<!-- section for featured projects -->
<!-- section for the latest articles -->
<section class="site-section site-section-last">
    <div class="wrapper">
        <h1>latest articles</h1>
        <ul class="post-list">
            {% for post in site.posts reversed | limit: 4 %}
                <li class="post"> 
                    <span class="post-meta">{{ post.date | date: "%b %-d, %Y" }}</span>
                    <h2>{{ post.title }}</h2>
                    <p>{{ post.content |  strip_html |  strip_newlines |  truncate: 200 }}</p>
                    <p class="post-read-more-link">
                        <a href="#">read more...</a>
                    </p>
                </li>
            {% endfor %}
        </ul>
    </div>
</section>
</div>
 
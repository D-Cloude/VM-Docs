---
layout: page
title: Documentation
permalink: /installation/
---

# 설치

D-Cloud VM 문서 페이지에 오신 것을 환영합니다! 여기서 특정 페이지로 빠르게 이동할 수 있습니다.

<div class="section-index">
    <hr class="panel-line">
    {% for post in site.docs  %}        
    <div class="entry">
    <h5><a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a></h5>
    <p>{{ post.description }}</p>
    </div>{% endfor %}
</div>

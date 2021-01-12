---
layout: page
pagination:
    enabled: true
    collection: posts
---

<h2>Page {{page.pagination_info.curr_page}} of {{page.pagination_info.total_pages}}</h2>

{% for post in paginator.posts %}
  <h1>{{ post.title }}</h1>
{% endfor %}

{% if paginator.total_pages > 1 %}
<ul>
  {% if paginator.previous_page %}
  <li>
    <a href="{{ paginator.previous_page_path | prepend: site.baseurl }}">Newer</a>
  </li>
  {% endif %}
  {% if paginator.next_page %}
  <li>
    <a href="{{ paginator.next_page_path | prepend: site.baseurl }}">Older</a>
  </li>
  {% endif %}
</ul>
{% endif %}


{% if paginator.next_page %}
  ,"next": "{{ paginator.next_page_path }}"
  {% endif %}
  {% if paginator.last_page %}
  ,"prev": "{{ paginator.last_page_path }}"
  {% endif %}
  {% if paginator.first_page %}
  ,"first": "{{ paginator.first_page_path }}"
  {% endif %}

# https://github.com/sverrirs/jekyll-paginate-v2/blob/master/examples/02-category/_layouts/home.html

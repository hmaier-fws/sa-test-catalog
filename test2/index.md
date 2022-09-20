<style>
  .footer {
    display: none;
  }
</style>

{% assign doclist = site.pages | sort: 'url'  %}
{% assign static_list = site.static_files %}

# json_files
{% assign json_files = site.static_files | where: "json", true %}

{% for cur_file in json_files %}
  <a href="./{{ cur_file.name }}">{{ cur_file.path }}/{{ cur_file.name }}</a>
{% endfor %}

# static files
{% for doc2 in static_list %}
  {% if doc2.name contains '.json' %}
    <a href="{{ site.baseurl }}{{ doc2.url }}">{{ doc2.url }}</a>
  {% endif %}
{% endfor %}


{% if page.url == page.dir %}
   {% assign dn1 = '.' | append: page.url | split: '/' %}
   {%- for each in site.html_pages -%}
      {%- assign dn2 = '.' | append: each.url | split: '/' | pop -%}
      {%- if dn2 == dn1 -%}
         {% if each.url == each.dir %}
      <p>{% octicon file-directory %}
      <a href="{{ each.url | relative_url }}">{{ each.title }}</a></p>
         {% else %}
      <p>{% octicon file %}
      <a href="{{ each.url | relative_url }}">{{ each.title }}</a></p>
         {% endif %}
      {%- endif -%}
   {%- endfor -%}
{% endif %}

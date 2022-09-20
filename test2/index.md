{% assign doclist = site.pages | sort: 'url'  %}
{% assign static_list = site.static_files %}

# json_files
{% assign json_files = site.static_files | where: "json", true %}

{% for cur_file in json_files %}
  <a href="./{{ cur_file.name }}">{{ cur_file.name }}</a>
{% endfor %}

# static files
{% for doc2 in static_list %}
  {% if doc2.name contains '.json' %}
    <a href="{{ site.baseurl }}{{ doc2.url }}">{{ doc2.url }}</a>
  {% endif %}
{% endfor %}

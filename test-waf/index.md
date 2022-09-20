{% assign doclist = site.pages | sort: 'url'  %}
{% assign static_list = site.static_files | sort: 'name'  %}

<ul>
  {% for doc in doclist %}
    {% if doc.name contains '.md' or doc.name contains '.html' %}
      <li><a href="{{ site.baseurl }}{{ doc.url }}">{{ doc.url }}</a></li>
    {% endif %}
  {% endfor %}
</ul>

# json_files
{% assign json_files = site.static_files | where: "json", true %}
{% for cur_file in json_files %}
  <a href="./{{ cur_file.name }}">{{ cur_file.name }}</a></ br>
{% endfor %}

# static files
{% for doc2 in static_list %}
  {% if doc2.name contains '.json' %}
    <li><a href="{{ site.baseurl }}{{ doc2.url }}">{{ doc2.url }}</a></li>
  {% endif %}
{% endfor %}

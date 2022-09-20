{% assign doclist = site.pages | sort: 'url'  %}

<ul>
  {% for doc in doclist %}
    {% if doc.name contains '.md' or doc.name contains '.html' %}
      <li><a href="{{ site.baseurl }}{{ doc.url }}">{{ doc.url }}</a></li>
    {% endif %}
  {% endfor %}
</ul>

{% assign json_files = site.static_files | where: "json", true %}
{% for cur_file in json_files %}
  <a href="./{{ cur_file.name }}">{{ cur_file.name }}</a></ br>
{% endfor %}

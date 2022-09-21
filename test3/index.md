# test3/index.md
## page.name: {{ page.name }}
## page.dir: {{ page.dir }}
## page.path: {{ page.path }}


{% assign doclist = site.pages | sort: 'url'  %}
{% assign doclist2 = site.static_files | where: path, "test3" %}

{% assign json_files = site.static_files | where: "json", true %}

# json files - (file.pat/file.name)
{% for cur_file in json_files %}
  <a href="./{{ cur_file.name }}">{{ cur_file.path }}/{{ cur_file.name }}</a>
{% endfor %}


# static files
{% for doc in doclist %}
  {% if doc.name contains '.json' %}
    <a href="{{ site.baseurl }}{{ doc.url }}">{{ site.baseurl }}{{ doc.url }}</a>
  {% endif %}
{% endfor %}


# all docs
{% for doc in doclist %}
    {{ doc.dir }} - {{ doc.name }}

    <a href="{{ site.baseurl }}{{ doc.url }}">{{ site.baseurl }}{{ doc.url }}</a>
{% endfor %}

# all docs in test3
{% for doc in doclist %}
    {{ doc.dir }} - {{ doc.name }}

    <a href="{{ site.baseurl }}{{ doc.url }}">{{ site.baseurl }}{{ doc.url }}</a>
{% endfor %}

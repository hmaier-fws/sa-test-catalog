# test3/index.md
## page.name: {{ page.name }}
## page.dir: {{ page.dir }}
## page.path: {{ page.path }}


{% assign json_files = site.static_files | where: "json", true %}
{% assign sa_files = site.static_files | where: "sa-catalog", true %}
{% assign wh_files = site.static_files | where: "warehouse", true %}


# json files - (file.path/file.name)
{% for cur_file in json_files %}
  {{ cur_file.path }}: <a href="{{ site.baseurl }}{{ cur_file.path }}">{{ cur_file.name }}</a>
{% endfor %}

# sa-catalog files - (file.path/file.name)
{% for cur_file in wh_files %}
  {% if cur_file.name contains '.json' %}
  {{ cur_file.path }}: <a href="{{ site.baseurl }}{{ cur_file.path }}"> {{ cur_file.name }} </a>
  {% endif %}
{% endfor %}

# sa-catalog files - (file.path, file.dir, file.name)
{% for cur_file in wh_files %}
  {% if cur_file.name contains '.json' %}
  file.path = {{ cur_file.path }} - file.dir = {{ cur_file.dir }} - file.name = {{ cur_file.name }}
  {% endif %}
{% endfor %}

# Split paths
{% for cur_file in wh_files %}
  {% if cur_file.name contains '.json' %}
  file.path: {{ cur_file.path }}, file.name: {{ cur_file.name }}, {% file.path | split "/" | first %}
  {% endif %}
{% endfor %}

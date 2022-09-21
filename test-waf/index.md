{% assign json_files = site.static_files | where: "json", true %}
{% assign sa_files = site.static_files | where: "sa-catalog", true %}


# json files - (file.path/file.name)
{% for cur_file in json_files %}
  <a href="{{ cur_file.path }}">{{ cur_file.name }}</a>
{% endfor %}

# sa-catalog files - (file.path/file.name)
{% for cur_file in sa_files %}
  {% if cur_file.name contains '.json' %}
    <a href="{{ cur_file.path }}">{{ cur_file.path }}</a>
  {% endif %}
{% endfor %}

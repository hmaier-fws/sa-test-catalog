{% assign sa_files = site.static_files | where: "sa-catalog", true %}


{% for cur_file in sa_files %}
  {% if cur_file.name contains '.json' %}
  <a href="{{ site.baseurl }}{{ cur_file.path }}"> {{ cur_file.name }} </a>
  {% endif %}
{% endfor %}

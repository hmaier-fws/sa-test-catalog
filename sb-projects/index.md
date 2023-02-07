{% assign selectedFiles = site.static_files | where: "warehouse", true %}


{% for curFile in selectedFiles %}
  {% if curFile.name contains '.json' %}
  <a href="{{ site.baseurl }}{{ curFile.path }}"> {{ curFile.name }} </a>
  {% endif %}
{% endfor %}

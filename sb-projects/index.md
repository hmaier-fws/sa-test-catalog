{% assign wh_files = site.static_files | where: "warehouse", true %}


{% for cur_file in wh_files %}
  {% if curFile.name contains '.json' and curFile.name contains '/sb-projects/'%}
    
    <a href="{{ site.baseurl }}{{ curFile.path }}"> {{ curFile.name }} </a>
  {% endif %}
{% endfor %}

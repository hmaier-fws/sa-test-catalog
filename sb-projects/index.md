{% assign wh_files = site.static_files | where: "warehouse", true %}


{% for cur_file in wh_files %}
  {% if cur_file.name contains '.json' %}
  
    <a href="{{ site.baseurl }}{{ cur_file.path }}"> {{ cur_file.name }} </a>
    
  {% endif %}
{% endfor %}

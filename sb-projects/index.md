{% assign wh_files = site.static_files | where: "warehouse", true %}


{% for cur_file in wh_files %}
-- {{% cur_file.name %}} --
  {% if cur_file.name contains '.json' and cur_file.name contains '/sb-projects/' %}
  <a href="{{ site.baseurl }}{{ cur_file.path }}"> {{ cur_file.name }} </a>
  {% endif %}
{% endfor %}


{% comment %}
  # Split paths
  {% for cur_file in wh_files %}

    {% if cur_file.name contains '.json' %}
      {% capture var1 %}
        {{ cur_file.path }}
      {% endcapture %}
      
    {% assign var2 = var1 | replace: "/", "," | split: "," %}
    var2: {{var2}}, var2[1]: {{var2[1]}}, var2[2]: {{var2[2]}}, var2[3]: {{var2[3]}}
      
      v1replace: {{ var1 | replace: "/", ", "}}
      
      
      ## VAR1
      var1: {{ var1 }}, cleaned: {{ var2[2] }}
      
    {% endif %}
  {% endfor %}
{% endcomment %}
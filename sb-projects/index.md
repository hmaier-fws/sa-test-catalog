{% assign wh_files = site.static_files | where: "warehouse", true %}


{% for cur_file in wh_files %}

  {% capture read_info %}
    file.path = {{ cur_file.path }}, file.dir = {{ cur_file.dir }}, file.name = {{ cur_file.name }} END
  {% endcapture %}
  
  Reading: {{ read_info }}


  {% comment %}
    **
    ** Process only JSON files in currently directory
    **
  {% endcomment %}

  {% if cur_file.name contains '.json' and cur_file.path contains '/sb-projects/' %}
    {% capture output_text %}
      {{% cur_file.path %}}
      <a href="{{ site.baseurl }}{{ cur_file.path }}"> {{ cur_file.name }} </a>
    {% endcapture %}
    
    {{- output_text -}}
    
    
  {% endif %}
  
{% endfor %}


{% comment %}
  **
  ** Extra code for testing
  **
  
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
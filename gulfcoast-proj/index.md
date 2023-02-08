{% assign wh_files = site.static_files | where: "warehouse", true %}


{% for cur_file in wh_files %}

  {% comment %}
    **
    ** Process only JSON files in currently directory
    **
  {% endcomment %}

  {% if cur_file.name contains '.json' and cur_file.path contains page.dir %}
    {% capture output_text %}
<a href="{{ site.baseurl }}{{ cur_file.path }}"> {{ cur_file.name }} </a>
    {% endcapture %}
    {{- output_text -}}
  {% endif %}
  
{% endfor %}

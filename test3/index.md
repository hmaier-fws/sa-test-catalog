<--
{% assign json_files = site.static_files | where: "json", true %}
-->

# hello

{% assign json_files = site.static_files %}

{% for cur_file in json_files %}
  <a href="./{{ cur_file.name }}">{{ cur_file.name }}</a>
{% endfor %}

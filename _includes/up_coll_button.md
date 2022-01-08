{% if include.up_url %}
[Вверх]({{ include.up_url }})
<!--
{% elsif include.up_coll %}
<!-- DO NOT QUESTION IT, IT JUST WORKS -->
{%- assign up_doc = include.up_coll | find: "tags", "navpage" -%}
[\[Вверх\]]({{ up_doc.url }})
-->
{% endif %}

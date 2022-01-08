# {{ page.title }}

{% if include.up_url %}
[Вверх]({{ include.up_url }})
{% elsif include.up_coll %}
<!-- DO NOT QUESTION IT, IT JUST WORKS -->
{%- assign up_doc = include.up_coll | find: "tags", "navpage" -%}
[Вверх]({{ up_doc.url }})
{%- endif -%}

{%- assign items_sorted = include.collection | where_exp: "t","t.draft==null or t.draft==false or site.show_drafts==true" | where_exp: "t","t.published==null or t.published==true or site.unpublished==true" | where_exp: "t","t.date<=site.time or site.future==true" | sort: "slug" -%}
{%- assign items_sorted_size = items_sorted | size -%}
{% if items_sorted_size > 0 %}
{% for item in items_sorted %}
* [{{item.title}}]( {{ item.url }} )
{% if item.draft==true %} (*черновик*){%- endif -%}
{% if item.published==false %} (*не опубликовано*){%- endif -%}
{%- endfor -%}
{% else %}
(тут пусто)
{%- endif -%}

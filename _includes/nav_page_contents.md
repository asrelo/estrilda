# {{ page.title }}

{% include up_coll_button.md up_url=include.up_url up_coll=include.up_coll %}

{%- assign items = include.collection | where_exp: "t","t.draft==null or t.draft==false or site.show_drafts==true" | where_exp: "t","t.published==null or t.published==true or site.unpublished==true" | where_exp: "t","t.date<=site.time or site.future==true" -%}
{%- assign items_size = items | size -%}
<!-- cannot sort an empty -->
{%- if items_size >0 -%}
{%- assign items_sorted = items | sort: "slug" -%}
{% for item in items_sorted %}
* [{{item.title}}]( {{ item.url }} )
{% if item.draft==true %} (*черновик*){%- endif -%}
{% if item.published==false %} (*не опубликовано*){%- endif -%}
{%- endfor -%}
{% else %}
(тут пусто)
{% endif %}

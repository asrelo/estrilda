# {{ page.title }}

{%- assign items_sorted = include.collection | where_exp: "t","t.draft==null or t.draft==false or site.show_drafts==true" | where_exp: "t","t.published==null or t.published==true or site.unpublished==true" | where_exp: "t","t.date<=site.time or site.future==true" | sort: "slug" -%}
{% for item in items_sorted %}
* [{{item.title}}]( {{ item.url }} )
{% if item.draft==true %} (*черновик*){%- endif -%}
{% if item.published==false %} (*не опубликовано*){%- endif -%}
{%- endfor -%}

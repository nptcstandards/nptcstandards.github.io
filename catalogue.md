---
title: Catalogue
layout: page
---
{% assign classification_list = site.data.catalogue | sort: 'bps_full_reference' | group_by : 'primary_classification' %}
{% assign sorted_classification_list = classification_list | sort: 'name' %}
{% assign business_list = sorted_classification_list %}
{% for classification in sorted_classification_list %}
## {{ classification.name | replace: '.', ' > ' }}
<table>
{% for standard in classification.items %}
<tr>
<td><a href="meta/{{ standard.bps_reference }}_meta.html">{{ standard.bps_full_reference }} {{standard.document_title}}</a></td>
</tr>
{% endfor %}
</table>
{% endfor %}
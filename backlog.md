---
title: Backlog
layout: page
---
{% assign classification_list = site.data.backlog | sort: 'bps_full_reference' | group_by : 'primary_classification' %}
{% assign sorted_classification_list = classification_list | sort: 'name' %}
{% for classification in sorted_classification_list %}
## {{ classification.name | replace: '.', ' > ' }}
{% for standard in classification.items %}
### {{standard.document_title}}
<table>
<tr>
<td>Proposed By</td>
<td>{{standard.sponsor}}</td>
</tr>
<tr>
<td>Description</td>
<td>{{standard.document_abstract}}</td>
</tr>
</table>
{% endfor %}
{% endfor %}
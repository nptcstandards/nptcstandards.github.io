---
title: Backlog
layout: page
---
The backlog shows the list of suggested standards which have been submitted to the NPTC Standards Working Group and are potential candidate standards for development and/or inclusion onto the Catalogue.

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
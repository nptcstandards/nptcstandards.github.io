---
title: Catalogue
layout: page
---
The catalogue shows the list of known published standards utilised in policing covering 3 main categories namely, Technical, Security and Business. This list will become richer and more comprehensive over time as the catalogue matures.

There are two main sources for standards:-
+ Internally created standards which have been developed by the NPTC Standards Working Group and their content will be embedded within the page and viewable directly
+ External standards which will be shown in terms of their document detail and an abstract with a link to the relevant standard, including Usage scenarios where assessed.

{% assign classification_list = site.data.catalogue | sort: 'bps_full_reference' | group_by : 'primary_classification' %}
{% assign sorted_classification_list = classification_list | sort: 'name' %}
{% assign business_list = sorted_classification_list %}
{% for classification in sorted_classification_list %}
## {{ classification.name | replace: '.', ' > ' }}
<table>
{% for standard in classification.items %}
<tr>
<td><a href="standards/{{ standard.bps_part_reference }}.html">{{ standard.bps_full_reference }} {{standard.document_title}}</a></td>
</tr>
{% endfor %}
</table>
{% endfor %}
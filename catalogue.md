---
title: Catalogue
layout: page
---
The catalogue shows the list of known published standards utilised in policing covering 3 main categories namely, Technical, Security and Business. This list will become richer and more comprehensive over time as the catalogue matures.

There are two main sources for standards:-
+ Internally created standards which have been developed by the NPTC Standards Working Group and their content will be embedded within the page and viewable directly
+ External standards which will be shown in terms of their document detail and an abstract with a link to the relevant standard, including Usage scenarios where assessed.

{% assign sorted_standards = site.data.catalogue.standards | sort: 'ref_full'  %}
<table>
<tr>
   <th>Reference</th>
   <th>Title</th>
   <th>Status</th>
</tr>
{% for standard in sorted_standards %}
<tr>
<td><a href="{{ standard.permalink }}">{{ standard.ref_full }}</a></td>
<td>{{standard.title}}</td>
<td>{{standard.status.value}}</td>
</tr>
{% endfor %}
</table>

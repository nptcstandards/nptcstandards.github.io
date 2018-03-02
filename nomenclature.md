---
title: NPTS Framework Nomenclature
layout: standard
standard_title: NPTS Framework Nomenclature
bps_reference: bps00001-5
original_reference: 
standard_maturity: Current
project_status: Completed
obsoletes: 
obsoleted_by: 
tags: nomenclature, terms, abbreviations, acronyms
abstract_only:
format_links:
html_link: 
pdf_link: 
docx_link: 
odt_link: 
comments: false
---
{% assign sorted_nomenclature = site.data.nomenclature | sort: 'term' %}
{% for item in sorted_nomenclature %}
## {{ item.term }}
{{ item.definition }}
{% endfor %}

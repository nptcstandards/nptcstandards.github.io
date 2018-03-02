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
comments: true
---
|||
| :------- | ------: |
| **GSC Classification**     | OFFICIAL |
| **Access Policy**          | Open |
| **Reference**              | bps00001-5:2018-02  |
| **Document Maturity**      | Current |
| **Primary Classification** | business.catalogue.terms |
| **ISSN Reference**         |  |
| **Author Organisation**    |NPTC Standards|
| **Sponsor Organisation**   |National Police Technology Council|
| **Trustee**                | NPTC Standards Working Group, <a href="mailto:trustee@standards.police.uk?subject=bps00001-5:2017-06 Npts Framework Nomenclature">trustee@standards.police.uk |

**Copyright Notice**
Copyright (c) 2016 National Police Technology Council (NPTC) group and the persons identified as the document authors. All rights reserved.

## Abstract
This document is the Normative BPS standards reference for acronyms and definitions used by the National Police Technology Standards (NPTS) working group to develop, communicate and manage standards for use in British Policing.

## Usage
Use a reference to the specific term from standards documents.

## Changelog
{% assign sorted_nomenclature = site.data.nomenclature | sort: 'term' %}
{% for item in sorted_nomenclature %}
## {{ item.term }}
{{ item.definition }}
{% endfor %}

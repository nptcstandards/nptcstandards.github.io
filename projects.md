---
layout: page
title: Roadmap
---
The  roadmap section displays a list of standards which are either :
+ under development or
+ scheduled for development or
+ due for assessment for inclusion in the Catalogue

{% for project in site.data.projects %}
## {{project.bps_reference}} : {{ project.name }}
<table>
    <tr>
        <td>Standard Sponsor:</td>
        <td>{{project.std_sponsor}}</td>
    </tr>
    <tr>
        <td>Authoring Organisation:</td>
        <td>{{project.author_org}}</td>
    </tr>
    <tr>
        <td>Project Status:</td>
        <td>{{project.project_status}}</td>
    </tr>
    <tr>
        <td>Abstract:</td>
        <td>{{project.document_abstract}}</td>
    </tr>
{% if project.start_date %}    
    <tr>
        <td>Start Date:</td>
        <td>{{project.start_date}}</td>
    </tr>
{% endif %}
{% if project.estimated_completion_date %}
    <tr>
        <td>Estimated Completion Date:</td>
        <td>{{project.estimated_completion_date}}</td>
    </tr>
{% endif %}
{% if project.url %}
    <tr>
        <td>Project URL:</td>
        <td>
            <a href="{{project.url}}"/>
        </td>
    </tr>
{% endif %}
</table>
  

{% endfor %}



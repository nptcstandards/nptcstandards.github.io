---
layout: default
title: Projects
---

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
        <td><a href="./meta/{{ project.bps_reference }}_meta.html">{{ project.bps_reference }}_meta.html</a></td>
    </tr>
    <tr>
        <td>Start Date:</td>
        <td>{{project.start_date}}</td>
    </tr>
    <tr>
        <td>Estimated Completion Date:</td>
        <td>{{project.estimated_completion_date}}</td>
    </tr>
    <tr>
        <td>Project URL:</td>
        <td>
            <a href="{{project.url}}"/>
        </td>
    </tr>
</table>
{% endfor %}

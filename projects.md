---
layout: page
title: Roadmap
---
The roadmap section shows the list of standards which are either :
+ under development or
+ scheduled for development or
+ due for assessment for inclusion in the Catalogue

<script src="assets/vis/dist/vis.js"></script>
<link href="assets/vis/dist/vis.css" rel="stylesheet" type="text/css" />

<hr>
<div id="visualization"></div>
<hr>

<script type="text/javascript">
  // DOM element where the Timeline will be attached
  var container = document.getElementById('visualization');

  // Create a DataSet (allows two way data-binding)
  var items = new vis.DataSet([
{% for project in site.data.projects %}
    {id:  '{{ project.bps_reference }}', title: '{{ project.bps_reference }}', content: '<a href="projects.html#{{ project.bps_reference }}--{{ project.name | slugify: 'ascii'}}">{{ project.name }}</a>', start: '2018-02-14'},
{% endfor %}
  ]);

  // Configuration for the Timeline
  var options = {};

  // Create a Timeline
  var timeline = new vis.Timeline(container, items, options);
</script>


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



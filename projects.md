---
layout: page
title: Projects
---
The projects section shows the list of standards associated with a project which are either :
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

  var options = {
      width: '100%',
      height: '100%',
      margin: {
        item : {
            horizontal : -1
        }
      },
      verticalScroll: true,
      zoomable: false
    };
    

  // Create a DataSet (allows two way data-binding)
  var items = new vis.DataSet([
{% for project in site.data.catalogue.projects %}
    {id:  '{{ project.bps_reference }}', title: '{{ project.bps_reference }} : {{project.name}}', content: '<a href="projects.html#{{ project.bps_reference }}--{{ project.name | slugify: 'ascii'}}">{{ project.name }}</a>', start: '{{ project.start_date }}', end: '{{ project.due_date }}'},
{% endfor %}
  ]);

  // Configuration for the Timeline
  var options = {};

  // Create a Timeline
  var timeline = new vis.Timeline(container, items, options);
</script>

{% for project in site.data.catalogue.projects %}
{% assign num_docs = 0 %}
## {{ project.name }}

<table>
  <tr>
    <td>Status</td>
    <td>{{project.status.value}}</td>
  </tr>
  {% if project.description %}
    <tr>
      <td>Description:</td>
      <td>{{project.description}}</td>
    </tr>
  {% endif %}
  {% if project.scheduled_date %}
    <tr>
      <td>Scheduled Date:</td>
      <td>{{project.scheduled_date}}</td>
    </tr>
  {% endif %}
  {% if project.start_date %}
    <tr>
      <td>Start Date:</td>
      <td>{{project.start_date}}</td>
    </tr>
  {% endif %}
  {% if project.due_date %}
    <tr>
      <td>Estimated Completion Date:</td>
      <td>{{project.due_date}}</td>
    </tr>
  {% endif %}
  {% if project.completed_date %}
    <tr>
      <td>Completion Date:</td>
      <td>{{project.completed_date}}</td>
    </tr>
  {% endif %}
  {% if project.project_lead %}
    <tr>
      <td>Project Lead:</td>
      <td>{{project.project_lead}}</td>
    </tr>
  {% endif %}
  {% if project.project_org_email %}
    <tr>
      <td>EMail:</td>
      <td><a href="mailto:{{project.project_org_email}}?subject={{project.name}}">{{project.project_org_email}}</a></td>
    </tr>
  {% endif %}
  {% if project.project_url %}
    <tr>
      <td>Project URL:</td>
      <td>
        <a href="{{project.project_url}}">{{project.project_url}}</a>
      </td>
    </tr>
  {% endif %}
  <tr>
    <td>Last Updated:</td>
    <td>{{project.last_updated}}</td>
  </tr>
  <tr>
    <td>Standards:</td>
    <td>
      <table>
        <tr><th>No.</th><th>Reference</th><th>Title</th><th>Status</th></tr>
        {% for standard in site.data.catalogue.standards %}
          {% for standard_project in standard.meta.projects %}
            {% if standard_project.name == project.name %}
              {% assign num_docs = num_docs | plus: 1 %}
              <tr>
                <td>{{ num_docs }}</td>
                <td><a href="{{ standard.permalink }}">{{ standard.ref_full }}</a></td><td>{{ standard.title }}</td>
                <td>{{ standard.status.value }}</td>
              </tr>
            {% endif %}
          {% endfor %}
        {% endfor %}
      </table>
    </td>
  </tr>
</table>
{% endfor %}







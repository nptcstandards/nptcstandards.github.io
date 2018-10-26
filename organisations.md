---
layout: page
title: Organisations
---


{% for org in site.data.catalogue.orgs %}
{% assign num_docs = 0 %}
## {{ org.name }}

<table>
  <tr>
    <td>Type</td>
    <td>{{org.org_type.value}}</td>
  </tr>
  {% if org.parent_org %}
    <tr>
      <td>Parent Org.:</td>
      <td>{{org.parent_org.name}}</td>
    </tr>
  {% endif %}
  {% if org.created %}
    <tr>
      <td>Formed:</td>
      <td>{{org.created}}</td>
    </tr>
  {% endif %}
  {% if org.disolved %}
    <tr>
      <td>Disolved:</td>
      <td>{{org.disolved}}</td>
    </tr>
  {% endif %}
  {% if org.url %}
    <tr>
      <td>URL:</td>
      <td>
        <a href="{{org.url}}">{{org.url}}</a>
      </td>
    </tr>
  {% endif %}
  <tr>
    <td>Standards:</td>
    <td>
      <table>
        <tr><th>No.</th><th>Reference</th><th>Title</th><th>Status</th></tr>
        {% for standard in site.data.catalogue.standards %}
            {% if org.name == standard.author_org.name %}
              {% assign num_docs = num_docs | plus: 1 %}
              <tr>
                <td>{{ num_docs }}</td>
                <td><a href="{{ standard.permalink }}">{{ standard.ref_full }}</a></td><td>{{ standard.title }}</td>
                <td>{{ standard.status.value }}</td>
              </tr>
            {% endif %}
        {% endfor %}
      </table>
    </td>
  </tr>
</table>
{% endfor %}







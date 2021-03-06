---
layout: base/sidebar-none
title: Publications
---

## Journal Articles
{% for item_paper in site.data.journalpapers %}
  {% assign paper = item_paper[1] %}
  <div class="row">
    <div class="publicationheader">
      <div class="col-md-12">
        <div class="row">
            <div class="col-xs-4">
        [{{ paper.pubnum }}]
            </div>
            <div class="col-xs-4 pull-right text-right hidden-md hidden-lg">
                <a href="{{ paper.officialurl }}">official&nbsp;PDF</a>
            </div>
        </div>
      </div>
    </div>
  </div>
  <div class="row">
    <div class="publicationcontent">
      <div class="publicationlinks hidden-xs hidden-sm">
          {% if paper.localpdf %}
            <a href="{{ site.baseurl }}/publications/{{ paper.localpdf }}">local&nbsp;PDF</a>
            <br>
          {% endif %}
          {% if paper.officialurl %}
            <a href="{{ paper.officialurl }}">official&nbsp;PDF</a>
            <br>
          {% endif %}
      </div>
      <div class="publicationimage">
        <a href="{{ site.baseurl }}/publications/{{ paper.localpdf }}">
          <img src="{{ site.baseurl }}/publications/{{ paper.localthumb }}">
        </a>
      </div>
      <div class="publicationcitation">
          {% for id_author in paper.authors %}
            {% assign author = site.data.authors[id_author] %}
              {% for name in author['name'] offset:1 %}
                {% unless name.first %}
                  {{ name }}
                {% endunless %}
              {% endfor %}
            {{ author['name'][0] }}{% if forloop.last %}.{% else %},{% endif %}
          {% endfor %}
          <a href="{{ site.baseurl }}/publications/{{ paper.localpdf }}">{{ paper.title }}</a>.
          {% assign journal = site.data.journals[paper.journal] %}
          <i>{{ journal.longname }}</i>{% if journal.shortname %} ({{ journal.shortname }}){% endif %}.
          Vol.&nbsp;{{ paper.volume }},
          Iss.&nbsp;{{ paper.issue }},
          pp.&nbsp;{{ paper.pages }}.
      </div>
    </div>
  </div>
{% endfor %}

## Conference Articles
{% for item_paper in site.data.conferencepapers %}
  {% assign paper = item_paper[1] %}
  <div class="row">
    <div class="publicationheader">
      <div class="col-md-12">
        <div class="row">
            <div class="col-xs-4">
        [{{ paper.pubnum }}]
            </div>
            <div class="col-xs-4 pull-right text-right hidden-md hidden-lg">
                <a href="{{ paper.officialurl }}">official&nbsp;PDF</a>
            </div>
        </div>
      </div>
    </div>
  </div>
  <div class="row">
    <div class="publicationcontent">
      <div class="publicationlinks hidden-xs hidden-sm">
          {% if paper.localpdf %}
            <a href="{{ site.baseurl }}/publications/{{ paper.localpdf }}">local&nbsp;PDF</a>
            <br>
          {% endif %}
          {% if paper.officialurl %}
            <a href="{{ paper.officialurl }}">official&nbsp;PDF</a>
            <br>
          {% endif %}
      </div>
      <div class="publicationimage">
        <a href="{{ site.baseurl }}/publications/{{ paper.localpdf }}">
          <img src="{{ site.baseurl }}/publications/{{ paper.localthumb }}">
        </a>
      </div>
      <div class="publicationcitation">
          {% for id_author in paper.authors %}
            {% assign author = site.data.authors[id_author] %}
              {% for name in author['name'] offset:1 %}
                {% unless name.first %}
                  {{ name }}
                {% endunless %}
              {% endfor %}
            {{ author['name'][0] }}{% if forloop.last %}.{% else %},{% endif %}
          {% endfor %}
          <a href="{{ site.baseurl }}/publications/{{ paper.localpdf }}">{{ paper.title }}</a>.
          {% assign conference = site.data.conferences[paper.conference] %}
          <i>{{ conference.longname }}</i>{% if conference.shortname %} <span class="text-nowrap">({{ conference.shortname }})</span>{% endif %}.
          {% if paper.pages %}
          <span class="text-nowrap">pp.&nbsp;{{ paper.pages }}</span>.
          {% endif %}
      </div>
    </div>
  </div>
{% endfor %}

## Workshop Papers
{% for item_paper in site.data.workshoppapers %}
  {% assign paper = item_paper[1] %}
  <div class="row">
    <div class="publicationheader">
      <div class="col-md-12">
        <div class="row">
            <div class="col-xs-4">
        [{{ paper.pubnum }}]
            </div>
            <div class="col-xs-4 pull-right text-right hidden-md hidden-lg">
                <a href="{{ site.baseurl }}/publications/{{ paper.localpdf }}">local&nbsp;PDF</a>
            </div>
        </div>
      </div>
    </div>
  </div>
  <div class="row">
    <div class="publicationcontent">
      <div class="publicationlinks hidden-xs hidden-sm">
          {% if paper.localpdf %}
            <a href="{{ site.baseurl }}/publications/{{ paper.localpdf }}">local&nbsp;PDF</a>
            <br>
          {% endif %}
          {% if paper.officialurl %}
            <a href="{{ paper.officialurl }}">official&nbsp;PDF</a>
            <br>
          {% endif %}
      </div>
      <div class="publicationworkshopcitation">
          {% for id_author in paper.authors %}
            {% assign author = site.data.authors[id_author] %}
              {% for name in author['name'] offset:1 %}
                {% unless name.first %}
                  {{ name }}
                {% endunless %}
              {% endfor %}
            {{ author['name'][0] }}{% if forloop.last %}.{% else %},{% endif %}
          {% endfor %}
          <a href="{{ site.baseurl }}/publications/{{ paper.localpdf }}">{{ paper.title }}</a>.
          {% assign workshop = site.data.workshops[paper.workshop] %}
          <i>{{ workshop.longname }}</i>{% if workshop.shortname %} <span class="text-nowrap">({{ workshop.shortname }})</span>{% endif %}.
      </div>
    </div>
  </div>
{% endfor %}

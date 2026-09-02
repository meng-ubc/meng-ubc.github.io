---
layout: page
permalink: /publications/
title: Publications
description:
nav: true
nav_order: 1
hide_page_header: true
---

<!-- _pages/publications.md -->
<div class="publications">

{% comment %}
{% assign highlights = site.data.publication_highlights %}

<section class="publication-highlights" aria-labelledby="publication-highlights-title">
  <div class="publication-highlights__header">
    <div>
      <p class="publication-highlights__eyebrow">Publication snapshot</p>
      <h2 id="publication-highlights-title">Peer-reviewed venue highlights</h2>
    </div>
    <p class="publication-highlights__summary">{{ highlights.summary }}</p>
  </div>

  <div class="publication-highlights__table-wrap">
    <table class="publication-highlights__table">
      <caption class="sr-only">
        Peer-reviewed papers grouped by publication venue
      </caption>
      <thead>
        <tr>
          <th scope="col">Venue</th>
          <th scope="col" class="publication-highlights__count">Papers</th>
          <th scope="col" class="publication-highlights__years">Years</th>
        </tr>
      </thead>
      <tbody>
        {% for venue in highlights.venues %}
          <tr>
            <th scope="row" class="publication-highlights__venue">
              <span class="publication-highlights__venue-label">
                <span class="publication-highlights__venue-code">{{ venue.short_name }}</span>
                <span class="publication-highlights__venue-name">{{ venue.full_name }}</span>
              </span>
            </th>
            <td class="publication-highlights__count">
              {{ venue.papers.size }}
            </td>
            <td class="publication-highlights__years">
              <div class="publication-highlights__year-list">
                {% for paper in venue.papers %}
                  <a
                    class="publication-highlights__year{% if paper.first_author %} publication-highlights__year--first-author{% endif %}"
                    href="#{{ paper.key }}"
                    aria-label="View the {{ paper.year }} {{ venue.short_name }} paper{% if paper.first_author %}; first-author publication{% endif %}"
                  >
                    {{- paper.year -}}
                    {%- if paper.first_author -%}
                      <span class="publication-highlights__year-marker" aria-hidden="true">*</span>
                    {%- endif -%}
                  </a>
                {% endfor %}
              </div>
            </td>
          </tr>
        {% endfor %}
      </tbody>
    </table>
  </div>

  <div class="publication-highlights__notes" aria-label="Publication notes">
    <p class="publication-highlights__first-authorship">
      <span class="publication-highlights__first-author-symbol" aria-hidden="true">*</span>
      <span class="publication-highlights__note-text">
        <span class="sr-only">An asterisk marks</span>
        First-author contributions.
      </span>
    </p>

    <p class="publication-highlights__recognition">
      <span class="publication-highlights__note-label">Recognition</span>
      <span class="publication-highlights__note-text">
        The
        <a href="#{{ highlights.recognition.paper_key }}">{{ highlights.recognition.paper_label }}</a>
        received the {{ highlights.recognition.award }}.
      </span>
    </p>

  </div>
</section>
{% endcomment %}

<section class="publication-category" aria-labelledby="peer-reviewed-publications">
  <h2 id="peer-reviewed-publications">Peer-reviewed</h2>
  {% bibliography --query @*[category=peer_reviewed] %}
</section>

<section class="publication-category" aria-labelledby="preprints-workshops-publications">
  <h2 id="preprints-workshops-publications">Preprints and Workshops</h2>
  {% bibliography --query @*[category=preprints_and_workshops] %}
</section>

</div>

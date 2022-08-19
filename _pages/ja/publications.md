---
layout: page
permalink: /publications/
title: 発表文献
# description: publications by categories in reversed chronological order. generated by jekyll-scholar.
years: [2022, 2021, 2020, 2019, 2018, 2016]
nav: true
nav_order: 1
lang: ja
---
<!-- _pages/publications.md -->

<!-- Filter -->
<script src="{{ '/assets/js/filter.js' | relative_url }}"></script>

<div class="search">
  <div class="form-row mb-4">
    <div class="col-auto">
      <input type="search" id="filter-search" placeholder="Search..." autocapitalize=off autocomplete=off autocorrect=off role=textbox spellcheck=false>
    </div>
    <div class="col-auto">
      <select id="filter-pubtype">
        <option value=".pubtype-all">種類</option>
        <option value=".pubtype-1">原著論文</option>
        <option value=".pubtype-2">講演・口頭発表</option>
        <option value=".pubtype-3">システム説明</option>
        <option value=".pubtype-4">プレプリント</option>
      </select>
    </div>
    <div class="col-auto">
      <select id="filter-year">
        <option value=".year-all">発表年</option>
        {%- for y in page.years %}
          <option value=".year-{{y}}">{{y}}</option>
        {% endfor %}
      </select>
    </div>
  </div>
</div>

<div class="publications">

{%- for y in page.years %}
  <div class="year-all year-{{y}}">
  <h2 class="year">{{y}}</h2>
    <div class="pubtype-all pubtype-1">
    {% bibliography -f journal -q @*[year={{y}}]* %}
    </div>
    <div class="pubtype-all pubtype-2">
    {% bibliography -f conference -q @*[year={{y}}]* %}
    </div>
    <div class="pubtype-all pubtype-3">
    {% bibliography -f competition -q @*[year={{y}}]* %}
    </div>
    <div class="pubtype-all pubtype-4">
    {% bibliography -f preprint -q @*[year={{y}}]* %}
    </div>
  </div>
{% endfor %}

</div>
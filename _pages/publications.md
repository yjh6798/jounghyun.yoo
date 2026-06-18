---
layout: page
permalink: /publications/
title: Publications
nav: true
nav_order: 4
---

<style>
.publications {
  counter-reset: pubnum;
}

.publications ol.bibliography {
  padding-left: 0 !important;
  margin-left: 0 !important;
}

.publications ol.bibliography > li {
  counter-increment: pubnum;
  list-style: none !important;
  display: flex;
  gap: 0.6rem;
  margin-bottom: 1.7rem;
  padding-left: 0 !important;
}

.publications ol.bibliography > li::before {
  content: counter(pubnum) ".";
  font-weight: 400;
  color: inherit;
  flex: 0 0 auto;
}

.publications ol.bibliography > li > .row {
  flex: 1;
  margin-left: 0 !important;
  margin-right: 0 !important;
}

.publications ol.bibliography > li > .row > [class*="col-"] {
  flex: 0 0 100% !important;
  max-width: 100% !important;
  padding-left: 0 !important;
  padding-right: 0 !important;
  margin-left: 0 !important;
}

.publications h2 {
  color: #333 !important;
  font-weight: 600 !important;
  border-bottom: 1px solid #d8d8d8;
  padding-bottom: 0.35rem;
  margin-top: 2rem;
  margin-bottom: 1.2rem;
  text-align: left !important;
}
</style>

<div style="margin-bottom: 1.4rem; font-size: 0.92rem; color: #555;">
<strong>†</strong> Equal contribution &nbsp;&nbsp;&nbsp;
<strong>*</strong> Corresponding author
</div>

<div class="publications">

{% bibliography %}

</div>

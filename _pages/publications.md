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
  max-width: none;
}

/* Contribution note */
.publication-note {
  margin-top: 0;
  margin-bottom: 0;
  font-size: 0.92rem;
  color: #555;
}

/* Year heading */
.publications h2 {
  color: #333 !important;
  font-size: 1.85rem !important;
  font-weight: 600 !important;
  line-height: 1.25 !important;
  border-top: 1px solid #e0e0e0 !important;
  border-bottom: 1px solid #d8d8d8 !important;
  padding-top: 1.0rem !important;
  padding-bottom: 0.35rem !important;
  margin-top: -0.35rem !important;
  margin-bottom: 1.5rem !important;
  text-align: left !important;
}

.publications ol.bibliography {
  padding-left: 0 !important;
  margin-left: 0 !important;
  width: 100% !important;
}

.publications ol.bibliography > li {
  counter-increment: pubnum;
  list-style: none !important;
  display: flex;
  align-items: flex-start;
  gap: 0.8rem;
  margin-bottom: 2rem;
  padding-left: 0 !important;
  max-width: 100%;
  min-width: 0;
}

.publications ol.bibliography > li::before {
  content: counter(pubnum) ".";
  flex: 0 0 22px;
  width: 22px;
  text-align: right;
  font-size: 1.05rem;
  font-weight: 500;
  line-height: 1.45;
  padding-top: 0;
  margin-top: 0;
  color: #222;
}

.publications ol.bibliography > li > .row {
  flex: 1 1 auto;
  min-width: 0;
  margin: 0 !important;
  width: 100% !important;
}

.publications ol.bibliography > li > .row > [class*="col-"] {
  flex: 0 0 100% !important;
  max-width: 100% !important;
  min-width: 0 !important;
  padding: 0 !important;
  margin: 0 !important;
}

.publications ol.bibliography .title {
  margin-top: 0 !important;
  margin-bottom: 0.08rem !important;
  padding-top: 0 !important;
  line-height: 1.45 !important;
  font-weight: 500 !important;
  overflow-wrap: anywhere;
  word-break: normal;
}

.publications ol.bibliography .author,
.publications ol.bibliography .authors {
  line-height: 1.45 !important;
  overflow-wrap: anywhere;
  word-break: normal;
}

/* Highlight my name subtly */
.publications ol.bibliography .author em,
.publications ol.bibliography .authors em {
  font-style: normal !important;
  font-weight: 400 !important;
  color: #8a0078 !important;
}

.publications ol.bibliography .periodical {
  margin-top: 0.15rem !important;
  line-height: 1.35 !important;
  overflow-wrap: anywhere;
  word-break: normal;
}

/* DOI / link buttons */
.publications ol.bibliography .links {
  margin-top: 0.38rem !important;
}

.publications ol.bibliography .links .btn {
  padding: 0.08rem 0.42rem !important;
  font-size: 0.62rem !important;
  line-height: 1.15 !important;
  font-weight: 500 !important;
  border: 1px solid #aaa !important;
  border-radius: 2px !important;
  color: #333 !important;
  background: transparent !important;
  box-shadow: none !important;
  text-transform: uppercase !important;
  letter-spacing: 0.02em !important;
}

.publications ol.bibliography .links .btn:hover {
  color: #000 !important;
  border-color: #666 !important;
  background: #f7f7f7 !important;
  text-decoration: none !important;
}

@media (max-width: 768px) {
  .publications ol.bibliography > li {
    gap: 0.65rem;
  }

  .publications ol.bibliography > li::before {
    flex: 0 0 20px;
    width: 20px;
    font-size: 1rem;
    padding-top: 0;
    margin-top: 0;
  }
}
</style>

<div class="publication-note">
<strong>†</strong> Equal contribution
&nbsp;&nbsp;&nbsp;
<strong>*</strong> Corresponding author
</div>

<div class="publications">

{% bibliography %}

</div>

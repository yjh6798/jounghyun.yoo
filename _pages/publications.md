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
  margin: 0 0 1.2rem 0;
  font-size: 0.92rem;
  color: #555;
}

/* Year heading */
.publications h2 {
  color: #333 !important;
  font-size: 1.85rem !important;
  font-weight: 600 !important;
  line-height: 1.25 !important;
  text-align: left !important;
  border-top: 1px solid #e0e0e0 !important;
  border-bottom: 1px solid #d8d8d8 !important;
  padding: 1rem 0 0.35rem 0 !important;
  margin: -0.35rem 0 1.5rem 0 !important;
}

.publications ol.bibliography {
  width: 100% !important;
  padding-left: 0 !important;
  margin-left: 0 !important;
}

/* Each publication item */
.publications ol.bibliography > li {
  counter-increment: pubnum;
  list-style: none !important;
  display: flex !important;
  align-items: flex-start !important;
  gap: 0.8rem !important;
  margin-bottom: 2rem !important;
  padding-left: 0 !important;
  max-width: 100% !important;
  min-width: 0 !important;
}

/* Publication number */
.publications ol.bibliography > li::before {
  content: counter(pubnum) ".";
  flex: 0 0 22px;
  width: 22px;
  text-align: right;
  font-size: 1.05rem;
  font-weight: 500;
  line-height: 1.45;
  color: #222;
}

/* Full-width bibliography content */
.publications ol.bibliography > li > .row {
  flex: 1 1 auto !important;
  width: 100% !important;
  min-width: 0 !important;
  margin: 0 !important;
}

.publications ol.bibliography > li > .row > [class*="col-"] {
  flex: 0 0 100% !important;
  max-width: 100% !important;
  min-width: 0 !important;
  padding: 0 !important;
  margin: 0 !important;
}

/* Title */
.publications ol.bibliography .title {
  display: block !important;
  margin: 0 0 0.08rem 0 !important;
  padding: 0 !important;
  line-height: 1.45 !important;
  font-weight: 600 !important;
  color: #111 !important;
  overflow-wrap: anywhere;
}

/* Authors */
.publications ol.bibliography .author,
.publications ol.bibliography .authors {
  display: block !important;
  line-height: 1.45 !important;
  color: #222 !important;
  overflow-wrap: anywhere;
}

/* Highlight my name */
.publications .my-name {
  color: #8a0078 !important;
  font-weight: 400 !important;
}

/* Journal line: hidden first to prevent year flicker */
.publications ol.bibliography .periodical {
  display: block !important;
  visibility: hidden;
  margin: 0.15rem 0 0 0 !important;
  line-height: 1.35 !important;
  color: #222 !important;
  overflow-wrap: anywhere;
}

.publications ol.bibliography .periodical.pub-ready {
  visibility: visible;
}

.publications ol.bibliography .periodical em,
.publications ol.bibliography .periodical i {
  font-style: italic !important;
}

/* Hide unnecessary expandable elements */
.publications ol.bibliography .abbr,
.publications ol.bibliography .abstract,
.publications ol.bibliography .award,
.publications ol.bibliography .bibtex,
.publications ol.bibliography .hidden {
  display: none !important;
}

/* DOI / link buttons */
.publications ol.bibliography .links {
  display: block !important;
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
    gap: 0.65rem !important;
  }

  .publications ol.bibliography > li::before {
    flex-basis: 20px;
    width: 20px;
    font-size: 1rem;
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

<script>
document.addEventListener("DOMContentLoaded", function () {
  /* Highlight my name automatically */
  document
    .querySelectorAll(".publications ol.bibliography .author, .publications ol.bibliography .authors")
    .forEach(function (block) {
      block.innerHTML = block.innerHTML.replace(
        /Jounghyun Yoo([†*])?/g,
        '<span class="my-name">Jounghyun Yoo$1</span>'
      );
    });

  /* Automatically remove year from every bibliography-generated journal line */
  document
    .querySelectorAll(".publications ol.bibliography .periodical")
    .forEach(function (periodical) {
      let html = periodical.innerHTML;

      html = html
        /* remove years such as 2024, (2024), , 2024 */
        .replace(/\(\s*20\d{2}\s*\)/g, "")
        .replace(/,\s*20\d{2}(?=[,.\s<]|$)/g, "")
        .replace(/\s+20\d{2}(?=[,.\s<]|$)/g, "")

        /* clean punctuation and spaces */
        .replace(/\s*,\s*/g, ", ")
        .replace(/,\s*,+/g, ",")
        .replace(/,\s*\./g, ".")
        .replace(/,\s*$/g, "")
        .replace(/\s{2,}/g, " ")
        .trim();

      periodical.innerHTML = html;
      periodical.classList.add("pub-ready");
    });
});
</script>

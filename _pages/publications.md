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
.publications .my-name {
  color: #8a0078 !important;
  font-weight: 400 !important;
}

.publications ol.bibliography .periodical {
  margin-top: 0.15rem !important;
  line-height: 1.35 !important;
  overflow-wrap: anywhere;
  word-break: normal;
}

.publications ol.bibliography .periodical em {
  font-style: italic !important;
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

<script>
document.addEventListener("DOMContentLoaded", function () {
  /* Highlight my name */
  const authorBlocks = document.querySelectorAll(
    ".publications ol.bibliography .author, .publications ol.bibliography .authors"
  );

  authorBlocks.forEach(function (block) {
    block.innerHTML = block.innerHTML.replace(
      /Jounghyun Yoo([†*])?/g,
      '<span class="my-name">Jounghyun Yoo$1</span>'
    );
  });

  /* Published papers: journal in italic + volume + first page/article number */
  const publicationInfo = {
    "Enzymatic microbubble robots": "<em>Nature Nanotechnology</em>, 21, 397",
    "Directed and rapid intracellular delivery of CRISPR/Cas9 ribonucleoproteins using charge-reversible fusogenic nanoparticles for therapeutic genome editing": "<em>Small</em>, 22, e11362",
    "Surface-engineered nanobeads for regioselective antibody binding: A robust immunoassay platform leveraging catalytic signal amplification": "<em>Biosensors and Bioelectronics</em>, 281, 117463",
    "Imaging-guided deep tissue in vivo sound printing": "<em>Science</em>, 388, 616",
    "All-printed chip-less wearable neuromorphic system for multimodal physiochemical heath monitoring": "<em>Nature Communications</em>, 16, 5689",
    "Sustained release of HIF-2α inhibitors using biodegradable porous silicon carriers for enhanced immunogenic cell death of malignant Merkel cell carcinoma": "<em>ACS Applied Materials & Interfaces</em>, 17, 7449",
    "Sustained release of HIF-2{\\alpha} inhibitors using biodegradable porous silicon carriers for enhanced immunogenic cell death of malignant Merkel cell carcinoma": "<em>ACS Applied Materials & Interfaces</em>, 17, 7449",
    "Photonic control of ligand nanospacing in self-assembly regulates stem cell fate": "<em>Bioactive Materials</em>, 34, 164",
    "Imaging-guided bioresorbable acoustic hydrogel microrobots": "<em>Science Robotics</em>, 9, eadp3593",
    "Bacterial outer membrane vesicle nanorobot": "<em>Proceedings of the National Academy of Sciences</em>, 121, e2403460121",
    "Room-temperature phosphorescence of defect-engineered silica nanoparticles for high-contrast afterglow bioimaging": "<em>Chemical Engineering Journal</em>, 493, 152529",
    "Micro- and nanorobots for biomedical applications in the brain": "<em>Nature Reviews Bioengineering</em>, 1, 308",
    "Tailored polyethylene glycol grafting on porous nanoparticles for enhanced targeting and intracellular siRNA delivery": "<em>Nanoscale</em>, 14, 14482",
    "Multifunction-harnessed afterglow nanosensor for molecular imaging of acute kidney injury in vivo": "<em>Small</em>, 18, 2200245",
    "Metal complexation-mediated stable and biocompatible nanoformulation of clinically approved near-infrared absorber for improved tumor targeting and photonic theranostics": "<em>Nano Convergence</em>, 8, 1",
    "Photoswitchable microgels for dynamic macrophage modulation": "<em>Advanced Materials</em>, 34, 2205498",
    "Direct deposition of anatase TiO2 on thermally unstable gold nanobipyramid: Morphology-conserved plasmonic nanohybrid for combinational photothermal and photocatalytic cancer therapy": "<em>Applied Materials Today</em>, 27, 101472",
    "Photoechogenic inflatable nanohybrids for upconversion-mediated sonotheranostics": "<em>ACS Nano</em>, 15, 18394",
    "Superoxide-responsive fluorogenic molecular probes for optical bioimaging of neurodegenerative events in Alzheimer's disease": "<em>Analyst</em>, 146, 4748",
    "Biocompatible organosilica nanoparticles with self-encapsulated phenyl motifs for effective UV protection": "<em>ACS Applied Materials & Interfaces</em>, 12, 9062",
    "A multi-dye containing MOF for the ratiometric detection and simultaneous removal of Cr2O7(2-) in the presence of interfering ions": "<em>Sensors and Actuators B: Chemical</em>, 283, 426",
    "Photoluminescent and biodegradable porous silicon nanoparticles for biomedical imaging": "<em>Journal of Materials Chemistry B</em>, 7, 6271",
    "Controlled growth of silica nanoparticles using two-phase orthogonal solvents for bioimaging": "<em>Journal of Luminescence</em>, 214, 116529",
    "Formation of TiO2@carbon core/shell nanocomposites from single molecular layer of aromatic compounds for photocatalytic hydrogen peroxide generation": "<em>ACS Applied Materials & Interfaces</em>, 11, 41196",
    "Defect-induced fluorescence of silica nanoparticles for bioimaging applications": "<em>ACS Applied Materials & Interfaces</em>, 10, 44247",
    "In vivo photoacoustic imaging of livers using biodegradable hyaluronic acid-conjugated silica nanoparticles": "<em>Advanced Functional Materials</em>, 28, 1800941",
    "Tailoring nanocrystalline metal-organic frameworks as fluorescent dye carriers for bioimaging": "<em>Inorganic Chemistry</em>, 56, 12859",
    "Improving functionality of carbon nanodots: Doping and surface functionalization": "<em>Journal of Materials Chemistry A</em>, 4, 11582"
  };

  const publicationItems = document.querySelectorAll(".publications ol.bibliography > li");

  publicationItems.forEach(function (item) {
    const titleBlock = item.querySelector(".title");
    const periodicalBlock = item.querySelector(".periodical");

    if (!titleBlock || !periodicalBlock) return;

    const titleText = titleBlock.textContent.replace(/\s+/g, " ").trim();

    if (publicationInfo[titleText]) {
      periodicalBlock.innerHTML = publicationInfo[titleText];
    } else {
      /* For under revision / in press papers: keep journal italic, remove year */
      periodicalBlock.innerHTML = periodicalBlock.innerHTML
        .replace(/,\s*20\d{2}/g, "")
        .replace(/\s*20\d{2}/g, "")
        .replace(/,\s*$/g, "")
        .trim();
    }
  });
});
</script>

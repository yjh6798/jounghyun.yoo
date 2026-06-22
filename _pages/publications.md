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
      /Jounghyun Yoo/g,
      '<span class="my-name">Jounghyun Yoo</span>'
    );
  });

  /* Replace year-only journal lines with journal, volume, and first page/article number */
  const publicationInfo = {
    "Enzymatic microbubble robots": "Nature Nanotechnology, 21, 397",
    "Directed and rapid intracellular delivery of CRISPR/Cas9 ribonucleoproteins using charge-reversible fusogenic nanoparticles for therapeutic genome editing": "Small, 22, e11362",
    "Surface-engineered nanobeads for regioselective antibody binding: A robust immunoassay platform leveraging catalytic signal amplification": "Biosensors and Bioelectronics, 281, 117463",
    "Imaging-guided deep tissue in vivo sound printing": "Science, 388, 616",
    "All-printed chip-less wearable neuromorphic system for multimodal physiochemical heath monitoring": "Nature Communications, 16, 5689",
    "Sustained release of HIF-2α inhibitors using biodegradable porous silicon carriers for enhanced immunogenic cell death of malignant Merkel cell carcinoma": "ACS Applied Materials & Interfaces, 17, 7449",
    "Sustained release of HIF-2{\\alpha} inhibitors using biodegradable porous silicon carriers for enhanced immunogenic cell death of malignant Merkel cell carcinoma": "ACS Applied Materials & Interfaces, 17, 7449",
    "Photonic control of ligand nanospacing in self-assembly regulates stem cell fate": "Bioactive Materials, 34, 164",
    "Imaging-guided bioresorbable acoustic hydrogel microrobots": "Science Robotics, 9, eadp3593",
    "Bacterial outer membrane vesicle nanorobot": "Proceedings of the National Academy of Sciences, 121, e2403460121",
    "Room-temperature phosphorescence of defect-engineered silica nanoparticles for high-contrast afterglow bioimaging": "Chemical Engineering Journal, 493, 152529",
    "Micro- and nanorobots for biomedical applications in the brain": "Nature Reviews Bioengineering, 1, 308",
    "Tailored polyethylene glycol grafting on porous nanoparticles for enhanced targeting and intracellular siRNA delivery": "Nanoscale, 14, 14482",
    "Multifunction-harnessed afterglow nanosensor for molecular imaging of acute kidney injury in vivo": "Small, 18, 2200245",
    "Metal complexation-mediated stable and biocompatible nanoformulation of clinically approved near-infrared absorber for improved tumor targeting and photonic theranostics": "Nano Convergence, 8, 1",
    "Photoswitchable microgels for dynamic macrophage modulation": "Advanced Materials, 34, 2205498",
    "Direct deposition of anatase TiO2 on thermally unstable gold nanobipyramid: Morphology-conserved plasmonic nanohybrid for combinational photothermal and photocatalytic cancer therapy": "Applied Materials Today, 27, 101472",
    "Photoechogenic inflatable nanohybrids for upconversion-mediated sonotheranostics": "ACS Nano, 15, 18394",
    "Superoxide-responsive fluorogenic molecular probes for optical bioimaging of neurodegenerative events in Alzheimer's disease": "Analyst, 146, 4748",
    "Biocompatible organosilica nanoparticles with self-encapsulated phenyl motifs for effective UV protection": "ACS Applied Materials & Interfaces, 12, 9062",
    "A multi-dye containing MOF for the ratiometric detection and simultaneous removal of Cr2O7(2-) in the presence of interfering ions": "Sensors and Actuators B: Chemical, 283, 426",
    "Photoluminescent and biodegradable porous silicon nanoparticles for biomedical imaging": "Journal of Materials Chemistry B, 7, 6271",
    "Controlled growth of silica nanoparticles using two-phase orthogonal solvents for bioimaging": "Journal of Luminescence, 214, 116529",
    "Formation of TiO2@carbon core/shell nanocomposites from single molecular layer of aromatic compounds for photocatalytic hydrogen peroxide generation": "ACS Applied Materials & Interfaces, 11, 41196",
    "Defect-induced fluorescence of silica nanoparticles for bioimaging applications": "ACS Applied Materials & Interfaces, 10, 44247",
    "In vivo photoacoustic imaging of livers using biodegradable hyaluronic acid-conjugated silica nanoparticles": "Advanced Functional Materials, 28, 1800941",
    "Tailoring nanocrystalline metal-organic frameworks as fluorescent dye carriers for bioimaging": "Inorganic Chemistry, 56, 12859",
    "Improving functionality of carbon nanodots: Doping and surface functionalization": "Journal of Materials Chemistry A, 4, 11582"
  };

  const publicationItems = document.querySelectorAll(".publications ol.bibliography > li");

  publicationItems.forEach(function (item) {
    const titleBlock = item.querySelector(".title");
    const periodicalBlock = item.querySelector(".periodical");

    if (!titleBlock || !periodicalBlock) return;

    const titleText = titleBlock.textContent.replace(/\s+/g, " ").trim();

    Object.keys(publicationInfo).forEach(function (title) {
      if (titleText === title) {
        periodicalBlock.innerHTML = publicationInfo[title];
      }
    });
  });
});
</script>

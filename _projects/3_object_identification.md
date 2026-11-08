---
layout: page
title: Object Identification for Amazon's Sparrow Robot
description: The production perception model behind a warehouse picking robot (ICRA 2024).
img: assets/img/projects/cards/object-identification.jpg
importance: 3
category: industry
featured: true
related_publications: true
---

<p class="project-meta"><strong>Amazon Robotics</strong> · 2022 – 2024 · Applied Scientist II</p>

## The problem

A picking robot in a fulfillment center has to recognize which item it is holding, out of an open-ended catalog of products. The reference images for an item are often incomplete, and items arrive occluded, deformed, or in changed packaging.

## What I did

I developed a multimodal object-identification model that matches a camera crop against several partial reference sources at once: photos taken during fulfillment, the catalog image, and the catalog title text. A DINO vision transformer gives domain-invariant image embeddings, catalog titles are aligned to the same space with CLIP-style contrastive fine-tuning, and a gradient-boosted model fuses the per-source matches while tolerating missing sources.

<div class="row justify-content-sm-center">
  <div class="col-sm-10 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/projects/object-identification.jpg" class="img-fluid rounded z-depth-1" zoomable=true %}
  </div>
</div>
<div class="caption">Matching object segments in a bin against multiple partial reference sources.</div>

## Results

On ARMBench (190K+ objects) extended with these reference sources, the fused model identified 92–97% of objects across reference-coverage scenarios, holding up where nearest-neighbor matching lost precision. In production it shipped to Sparrow stations across U.S. fulfillment centers and raised identification accuracy from about 80% to 98.5%.

## Paper

Published at ICRA 2024 {% cite mitash2024scaling %}.

**Tools:** vision transformers · DINO · CLIP · contrastive learning · multimodal retrieval

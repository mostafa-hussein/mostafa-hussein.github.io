---
layout: page
title: Robust Behavior Cloning
description: Learning multi-step tasks when some human demonstrations are wrong (CoRL 2022, IROS 2021).
img: assets/img/projects/cards/robust-bc.jpg
importance: 3
category: research
related_publications: true
---

<p class="project-meta"><strong>University of New Hampshire (CARL)</strong> · 2018 – 2022 · PhD research</p>

## The problem

Behavior cloning assumes every demonstration is correct, but real human demonstrations include mistakes and even unsafe actions, and a cloned policy copies them. My PhD thesis, *Robust Behavior Cloning for Multi-Step Sequential Task Learning by Robots*, addresses this.

## What I did

**R-MaxEnt** (NeurIPS 2020 workshop, IROS 2021) learns a policy by matching feature expectations under the maximum-entropy principle while learning a weight for each demonstration. A min-max formulation drives the weight of any demonstration that disagrees with the rest toward zero, with no simulator and only a handful of demonstrations.

**Detecting incorrect visual demonstrations** (CoRL 2022) moves the idea to raw video. Each video is split into sub-tasks, temporally aware visual features are extracted per segment, and a min-max entropy problem gives low weight to videos whose sub-task sequence is inconsistent with the rest, such as forgetting the tea bag.

**A hierarchical approach** (manuscript) learns the high-level sub-task policy from video over only the visual features that best capture the task's temporal structure, while the robot learns each sub-task's motor skill kinesthetically.

<div class="row justify-content-sm-center">
  <div class="col-sm-10 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/projects/robust-behavior-cloning.jpg" class="img-fluid rounded z-depth-1" zoomable=true %}
  </div>
</div>
<div class="caption">Kinesthetic demonstrations of the tea-making task on the ABB YuMi.</div>

## Results

In Mountain-Car and Acrobot, R-MaxEnt kept its accuracy as adversarial demonstrations were added, while behavior cloning, GAIL, and IRL baselines degraded. On a real ABB YuMi tea-making task it stayed accurate until adversarial demonstrations outnumbered correct ones. The video method caught every incorrect video on a tea-making dataset and on 50-Salads, even when they made up about 40% of the demonstrations. Temporally grounded features reached 100% sub-task policy accuracy from 15 tea-making demonstrations, where spatial-only features needed 30.

## Papers, code, and videos

Published at CoRL 2022, IROS 2021, and a NeurIPS 2020 workshop {% cite hussein2022detecting hussein2021robust hussein2021maxent hussein2021hierarchical %}. The full story is in my PhD thesis {% cite hussein2023robust %}. Code: [R-MaxEnt](https://github.com/mostafa-hussein/max-ent), [hierarchical learner](https://github.com/AssistiveRoboticsUNH/hierarchical_learner).

<div class="row justify-content-sm-center">
  <div class="col-sm-10 mt-3 mt-md-0">
    {% include video.liquid path="/assets/video/iros2021.mp4" class="img-fluid rounded z-depth-1" controls=true %}
  </div>
</div>
<div class="caption">IROS 2021 video: robust behavior cloning with adversarial demonstration detection.</div>

<div class="row justify-content-sm-center">
  <div class="col-sm-10 mt-3 mt-md-0">
    {% include video.liquid path="/assets/video/iros2021-talk.mp4" class="img-fluid rounded z-depth-1" controls=true %}
  </div>
</div>
<div class="caption">IROS 2021 talk (15 min).</div>

**Tools:** behavior cloning · maximum-entropy methods · learning from demonstration · ABB YuMi

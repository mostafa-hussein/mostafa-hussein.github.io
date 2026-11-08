---
layout: page
title: Trajectory-Consistent Flow Matching
description: Flow-matching policies that stay on track over long-horizon tasks (IROS 2026).
img: assets/img/projects/cards/flow-matching.jpg
importance: 1
category: research
featured: true
related_publications: true
---

<p class="project-meta"><strong>University of New Hampshire (CARL)</strong> · 2025 – 2026 · Co-advisor</p>

## The problem

Flow-matching policies are trained point by point on the velocity field, but at run time the robot follows the whole integrated trajectory. Over long, multi-phase tasks the two drift apart and small errors pile up.

## What we did

Trajectory-Consistent Flow Matching trains at the trajectory level instead: rectified-flow regression over the whole time interval, a multi-step consistency loss on the integrated displacement, and a velocity-smoothness penalty, with fourth-order Runge–Kutta (RK4) integration at inference. The policy sees two point-cloud views of the scene. I co-advised the project and shaped the method and the real-robot evaluation.

<div class="row justify-content-sm-center">
  <div class="col-sm-10 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/projects/trajectory-flow-matching.jpg" class="img-fluid rounded z-depth-1" zoomable=true %}
  </div>
</div>
<div class="caption">Pointwise flow matching drifts; trajectory-level supervision keeps the integrated flow straight and smooth.</div>

## Results

On a Franka FR3 and a Boston Dynamics Spot, it reached 70% and 60% success on two long-horizon tasks where the 3D Diffusion Policy (DP3) and Consistency Flow Matching baselines scored 0%, and 100% on screwdriver placement. Ablations show the parts only work together: keeping RK4 but dropping the smoothness loss cut success from 70% to 10%. It was also evaluated on MetaWorld simulation tasks.

## Paper

Published at IROS 2026 {% cite ahmed2026trajectory %}. Preprint on [arXiv](https://arxiv.org/abs/2605.08511).

**Tools:** flow matching · DP3 · PointNet · Franka FR3 · Boston Dynamics Spot · MetaWorld

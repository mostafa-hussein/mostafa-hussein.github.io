---
layout: page
title: Inverse RL for Human–Robot Interaction
description: Learning interaction policies from demonstrations, applied to autism therapy (ICRA 2019).
img: assets/img/projects/cards/interaction-irl.jpg
importance: 4
category: research
related_publications: true
---

<p class="project-meta"><strong>University of New Hampshire (CARL)</strong> · 2018 – 2019 · PhD research</p>

## The problem

A robot that runs structured teaching sessions, such as Applied Behavior Analysis interventions for children with autism, needs a reward function. Hand-crafting one over noisy human cues gives brittle policies, and inverse RL directly on a POMDP is expensive.

## What I did

This work models the session as a small POMDP, reduces it to an MDP (by mapping combinations of observed cues such as gaze, speech, and gesture to states, or by discretizing the belief), learns the reward there with standard inverse RL, and plugs it back into the POMDP.

<div class="row justify-content-sm-center">
  <div class="col-sm-10 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/projects/interaction-irl.jpg" class="img-fluid rounded z-depth-1" zoomable=true %}
  </div>
</div>
<div class="caption">Reducing the POMDP to an MDP to learn the reward with inverse RL.</div>

## Results

Running autonomously on a NAO robot in a user study, the learned reward reproduced the demonstrator's actions 100% of the time for social greeting and 90% for object naming, ahead of hand-crafted rewards and two existing POMDP inverse-RL methods.

## Paper and video

Published at ICRA 2019 {% cite hussein2019inverse %}.

<div class="row justify-content-sm-center">
  <div class="col-sm-10 mt-3 mt-md-0">
    {% include video.liquid path="/assets/video/icra2019.mp4" class="img-fluid rounded z-depth-1" controls=true %}
  </div>
</div>
<div class="caption">ICRA 2019 video: learning interaction dynamics from demonstrations.</div>

**Tools:** inverse reinforcement learning · POMDPs · CNN-LSTM cue detection · NAO

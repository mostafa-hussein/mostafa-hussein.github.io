---
layout: page
title: Policy Learning for Industrial Humanoids
description: Dual-arm and whole-body manipulation policies for humanoid robots at Persona AI.
img: assets/img/projects/cards/persona.jpg
importance: 1
category: industry
---

<p class="project-meta"><strong>Persona AI</strong> · 2026 – present · Senior Deep Learning Manipulation Engineer</p>

At Persona AI I lead policy learning for dual-arm manipulation and whole-body control, on Franka arms and humanoid robots, for industrial tasks that have to succeed reliably over long horizons. The work covers the whole loop: collecting and curating teleoperated demonstrations, fine-tuning vision-language-action models such as GR00T and π0 on them, correcting a deployed policy with DAgger-style on-policy data, adding residual reinforcement learning on top of a frozen base policy, and continual learning that folds new demonstrations and failure cases into the policy without losing earlier skills. I also define how policies are judged (success rate, sample efficiency, trajectory length, motion smoothness, and cycle time on a fixed panel of rollouts), so that every checkpoint is compared the same way.

**Tools:** vision-language-action models (GR00T, π0) · DAgger · residual RL · experience replay · LeRobot · Franka FR3 · humanoids

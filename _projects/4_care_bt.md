---
layout: page
title: "CaRE-BT: Assistive Robots in Real Homes"
description: Care protocols turned into behavior trees, deployed in people's homes for months.
img: assets/img/projects/care-bt.jpg
importance: 2
category: research
related_publications: true
---

**University of New Hampshire (CARL)** · 2025 – 2026 · Team lead and principal researcher

Care robots have to make reliable decisions from noisy perception while people's routines and their homes keep changing. CaRE-BT is an open-source framework that turns symbolic care protocols (medication reminders, exercise, safety checks) into executable behavior trees, so a mobile robot adapts to the people it serves in real time.

It combines a situational-awareness layer, which fuses multi-camera tracking, face re-identification, and smart-home signals, with a two-level planner that replans over a self-healing knowledge base. The planner dispatches navigation, docking, speech, and call services on embedded hardware.

<div class="row justify-content-sm-center">
  <div class="col-sm-10 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/projects/care-bt.jpg" class="img-fluid rounded z-depth-1" zoomable=true %}
  </div>
</div>
<div class="caption">Architecture of the in-home socially assistive robot system (IJERPH 2026, CC BY).</div>

In a 30-day evaluation on a Stretch 3 across two in-home studies, CaRE-BT delivered more than 55 scheduled health prompts; the only failures came from navigation launch issues. In the broader NIH-funded trials, five caregiver and care-recipient couples lived with the robot for one to six months, and monthly interviews with them drove changes to the robot and its care routines through a systematic co-design process.

The system is now being commercialized by [Raha Tech](/projects/2_raha_tech/), which I co-founded (patent pending).

Published at ICSR 2025, Innovation in Aging 2025, and IJERPH 2026 {% cite ghattas2025carebt begum2025technical arthanat2026systematic %}.

**Tools:** ROS 2 · Nav2 · behavior trees · PDDL planning · face re-ID · activity recognition · Stretch 3

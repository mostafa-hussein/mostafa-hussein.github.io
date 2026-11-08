---
layout: page
title: Teaching a Robot to Write in English and Arabic
description: Learning perceptual and motion primitives from demonstration.
importance: 5
category: research
related_publications: true
---

**Assiut University, Egypt** · 2013 – 2017 · M.Sc. research

Most learning-from-demonstration methods assume each demonstration arrives neatly separated. A robot watching people instead sees a continuous stream that mixes intended and incidental demonstrations.

**COLD** (ICMA 2017) is a modular, robot-independent ROS framework that learns from such continuous streams: motif discovery finds the repeated actions (here, strokes and letters) inside them. The motion primitives are Gaussian mixture models whose number of components is chosen by variational Bayesian inference (IEA/AIE 2015), rather than by costly model selection.

By watching people write, the robot learned the basic strokes of English and Arabic, two scripts with very different stroke structure, and then wrote new words that never appeared in the demonstrations, on a physical NAO and a parallel-robot simulator.

Published at ICMA 2017 and IEA/AIE 2015 {% cite hussein2017cold hussein2015learning %}.

**Tools:** ROS · Gaussian mixture models · variational Bayes · motif discovery · NAO

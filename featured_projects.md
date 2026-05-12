---
layout: default
title: Projects
description: Selection of relevant research projects and coursework
---
[Home](/index) | [Research/Projects](/featured_projects) | [Geopolitical Strategy](/geopolitics)| [Mentorship](/mentorship)
---
### Spacecraft Position Estimation in LEO using Terrain Relative Kalman Filtering
Accurate vision-based Kalman Filtering framework for spacecraft position estimation in GNSS-denied orbit scenarios.

<p align="center">
  <img src="/assets/images/(70km; 100m_s) 3D error.png" width="600">
</p>


**Problem**:
Accurate knowledge of a spacecraft's position is critical for mission success; however, there are a number of circumstances that may cause GNSS (Global Navigation Satellite System) services to be unavailable, potentially for extended periods of time. In these instances, the ability to leverage vision-based estimation can be critical to the successful execution of the spacecraft's mission.

**Approach**: 
Employ Extended and Unscented Kalman Filters with novel terrain-relative residuals to achieve sub-kilometer position estimates for a simulated spacecraft in LEO.

**Results**
We achieve a 90% reduction in initial position error over the duration of the 7-second flyover of Lake Seneca. We achieve sub-kilometer estimates with both the EKF and UKF, but we ultimately discover the UKF is most effective with a lowest error of 424 m from the true position.
<div style="
  display: flex;
  justify-content: center;
  gap: 20px;
  flex-wrap: wrap;
">

<img src="/assets/images/(15km; 1m_s) x error.png"
     width="300">

<img src="/assets/images/(15km; 1m_s) y error.png"
     width="300">

<img src="/assets/images/(15km; 1m_s) z error.png"
     width="300">

</div>


Technical details
Links (code, paper, demo)

## A Deep Semantic Segmentation Network for Mars Rover Traversibility

## Interactive Orbital Mechanics Simulator

## 2D formation controller for fish-like bio-robots

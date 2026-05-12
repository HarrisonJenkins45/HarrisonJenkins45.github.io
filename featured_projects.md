---
layout: default
title: Projects
description: Selection of relevant research projects and coursework
---
[Home](/index) | [Research/Projects](/featured_projects) | [Geopolitical Strategy](/geopolitics)| [Mentorship](/mentorship)
---
<h3>
Spacecraft Position Estimation in LEO using Terrain Relative Kalman Filtering
<span style="font-size: 0.3em; font-weight: normal;">
  <a href="/assets/pdfs/AE_6505_Final_Project_Manuscript.pdf">
    [Download Manuscript]
  </a>
</span>
</h3>
_An accurate, vision-based, Kalman Filtering framework for spacecraft position estimation in GNSS-denied orbit scenarios._

<p align="center">
  <img src="/assets/images/(70km; 100m_s) 3D error.png" width="600">
</p>


**Problem:**
Accurate knowledge of a spacecraft's position is critical for mission success; however, there are a number of circumstances that may cause GNSS (Global Navigation Satellite System) services to be unavailable, potentially for extended periods of time. In these instances, the ability to leverage vision-based estimation can be critical to the successful execution of the spacecraft's mission.

**Approach:**
Employ Extended and Unscented Kalman Filters (EKF and UKF) with novel terrain-relative residuals to achieve sub-kilometer position estimates for a simulated spacecraft in LEO.

**Results:**
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


**Technical details:**
- We simulate the true trajectory with two-body motion equations + the J2 perturbation and atmospheric drag (nominal trajectory intentionally excludes perturbations)
- Leverage OpenCV and pyproj to create a physically consistent orbital flyover and generate measurement residuals
- Use MATLAB's native Python interface to run the filtering loop in MATLAB while leveraging key Python libraries to develop residuals from the data.


**Demo:**
See the project repository's [README](https://github.com/HarrisonJenkins45/Terrain-Relative-Spacecraft-Position-Estimation) for setup instructions.

## A Deep Semantic Segmentation Network for Mars Rover Traversibility

## Interactive Orbital Mechanics Simulator

## 2D formation controller for fish-like bio-robots

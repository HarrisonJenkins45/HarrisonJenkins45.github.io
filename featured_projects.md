---
layout: default
title: Projects
description: Selection of relevant research projects and coursework
---
[Home](/index) | [Research/Projects](/featured_projects) | [Geopolitical Strategy](/geopolitics)| [Mentorship](/mentorship)
---
<h3>
Spacecraft Position Estimation with Terrain Relative Kalman Filtering
<span style="font-size: 0.6em; font-weight: normal;">
  <a href="/assets/pdfs/AE_6505_Final_Project_Manuscript.pdf">
    [View Manuscript]
  </a>
</span>
</h3>


An accurate, vision-based, Kalman Filtering framework for spacecraft position estimation in GNSS-denied orbit scenarios.

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

Semantic Segmentation model for Martian terrain type, trained solely on unlabeled Earth data.

<p align="center">
  <img src="/assets/images/CS7641 Final Tri-panel.png" width="600">
</p>
Tri-panel comparison image

**Problem:**
Current Martian rovers rely on classical (geometry-based) computer vision, lacking semantic understanding of terrain type. This can cause critical mission failures, like​ the 2009 Spirit Rover embedding. Furthermore, when preparing to deploy a rover on unexplored terrain, there may not be labeled data from that environment to train on. The ability to use an accessible Earth environment to train a model to perform on novel terrain is both exciting and challenging.

**Approach:**
We use weakly supervised learning to generate pseudo-labels for the unlabeled Mars analog dataset ([Bardenas Semi-Desert, Spain](https://www.nature.com/articles/s41597-024-03881-1)). These pseudo-labels were then used to train a DeepLabV3 model for semantic segmentation of four specific terrain types on Mars. We then validate these results by testing against the [AI4Mars dataset](https://data.nasa.gov/dataset/ai4mars-a-dataset-for-terrain-aware-autonomous-driving-on-mars).

**Project Pipeline:**
<p align="center">
  <img src="/assets/images/Final_Presentation_Pipeline.png" width="600">
</p>


**Results:**
<div style="
  display: flex;
  justify-content: center;
  gap: 20px;
  flex-wrap: wrap;
">
slide 7 and 8 from final pres
<img src="/assets/images/ai4mars_confusion_matrix.png"
     width="300">

<img src="/assets/images/.png"
     width="300">

<img src="/assets/images/.png"
     width="300">

</div>

**Technical details:**
- Trained a custom multi-layer perceptron (MLP) for DINO ViT-S/14 to learn pseudo masks using just 134 hand-drawn labels.
- Fine-tuned DeepLabV3 (ResNet-50 backbone) with auxiliary loss on the 31,707 images and corresponding pseudo-labels
- Weighted the classes during training to remove bias against less common terrain types

**Acknowledgments:**
This work was done in collaboration with Trisha Singh, Noah Fischer, Steven Baker, and Sameer Panghal. Sincere thanks to them for their hard work on this project.


**Links:**
- [Project GitHub report](https://github.gatech.edu/nfischer30/CS7641-Group-6-Proposal/blob/main/final_report.md) for code and more details.





## Interactive Orbital Mechanics Simulator

## 2D formation controller for fish-like bio-robots

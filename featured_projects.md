---
layout: default
title: Projects
description: Selection of relevant research projects and coursework
---
[Home](/index) | [Research/Projects](/featured_projects) | [Mentorship](/mentorship)| [Geopolitical Strategy](/geopolitics)
---
<div style="
  background-color: #f6f8fa;
  padding: 20px;
  border-radius: 6px;
  margin-bottom: 40px;
  border: 3px solid #d0d7de;

">

<h2 style="margin-top: 0;">
  Directory
</h2>

<ul>

<li>
<a href="#terrain-relative-kalman-filtering">
Spacecraft Position Estimation with Terrain Relative Kalman Filtering
</a>
</li>

<li>
<a href="#mars-segmentation">
Deep Semantic Segmentation for Mars Rover Traversibility
</a>
</li>

<li>
<a href="#orbital-simulator">
Interactive Orbital Mechanics Simulator
</a>
</li>

<li>
<a href="#hydrofoil-controller">
2D Formation Controller for Fish-like Bio-Robots
</a>
</li>


<li>
<a href="#other-projects">
Other Projects
</a>
</li>
</ul>

</div>





<h2 id="terrain-relative-kalman-filtering">
Spacecraft Position Estimation with Terrain Relative Kalman Filtering
<span style="font-size: 0.6em; font-weight: normal;">
  <a href="/assets/pdfs/AE_6505_Final_Project_Manuscript.pdf">
    [View Manuscript]
  </a>
</span>
</h2>


An accurate, vision-based, Kalman Filtering framework for spacecraft position estimation in GNSS-denied orbit scenarios.

<p align="center">
  <img src="/assets/images/(70km; 100m_s) 3D error.png" width="600">
  </p>
<p align="center">
  </p>
<p align="center">
  <strong>Figure 1</strong>. 3D Orbit trajectories for the EKF and UKF compared to true state.

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

<p align="center"><strong>Figure 2</strong>. X, Y, and Z errors for each filter compared.</p>


**Technical details:**
- We simulate the true trajectory with two-body motion equations + the J2 perturbation and atmospheric drag (nominal trajectory intentionally excludes perturbations)
- Leverage OpenCV and pyproj to create a physically consistent orbital flyover and generate measurement residuals
- Use MATLAB's native Python interface to run the filtering loop in MATLAB while leveraging key Python libraries to develop residuals from the data.


**Demo:**
See the project repository's [README](https://github.com/HarrisonJenkins45/Terrain-Relative-Spacecraft-Position-Estimation) for setup instructions.

<h2 id="mars-segmentation">
A Deep Semantic Segmentation Network for Mars Rover Traversibility
</h2>

<p>
Semantic Segmentation model for <strong>Martian</strong> terrain type, trained solely on <strong>unlabeled Earth</strong> imagery.
</p>

<p align="center">
  <img src="/assets/images/CS7641_Final_tripanel.png" width="600">
  </p>
<p align="center">
  <strong>Figure 3</strong>. Final Segmentation output compared with ground truth labels

</p>

**Problem:**
Current Martian rovers rely on classical (geometry-based) computer vision, lacking semantic understanding of terrain type. This can cause critical mission failures, like​ the 2009 Spirit Rover embedding. Furthermore, when preparing to deploy a rover on unexplored terrain, there may not be labeled data from that environment to train on. The ability to use an accessible Earth environment to train a model to perform on novel terrain is both exciting and challenging.

**Approach:**
We use weakly supervised learning to generate pseudo-labels for the unlabeled Mars analog dataset, [BASEPROD](https://www.nature.com/articles/s41597-024-03881-1) (located in the Bardenas Semi-Desert, Spain). These pseudo-labels were then used to train a DeepLabV3 model for semantic segmentation of four specific terrain types on Mars. We then validate these results by testing against the [AI4Mars dataset](https://data.nasa.gov/dataset/ai4mars-a-dataset-for-terrain-aware-autonomous-driving-on-mars).

**Project Pipeline:**
<p align="center">
  <img src="/assets/images/Final_Presentation_Pipeline.png" width="600">
  </p>
<p align="center"><strong>Figure 4</strong>. Overall Training and Deployment Pipeline

</p>


**Results:**
<p align="center">
  <img src="/assets/images/MIoU.png"
       width="600">
  <p><strong>Figure 5</strong>. Mean Area over Union for Pseudo labels compared with hand annotations</p>
</p>

  
<p align="center">
  <img src="/assets/images/Other results.png"
       width="600">

  </p>
<p align="center">
  <strong>Figure 6</strong>. Pseudo Labels Compared with raw BaseProd images
</p>



<p align="center">
  <img src="/assets/images/ai4mars_confusion_matrix.png"
       width="600">

  </p>
<p align="center">
  <strong>Figure 7</strong>. Final Confusion Matrix after deploying on Mars (i.e., testing against AI4Mars)
</p>

**Technical details:**
- Trained a custom multi-layer perceptron (MLP) for DINO ViT-S/14 to learn pseudo masks using just 134 hand-drawn labels.
- Fine-tuned DeepLabV3 (ResNet-50 backbone) with auxiliary loss on the 31,707 images and corresponding pseudo-labels
- Weighted the classes during training to remove bias against less common terrain types

**Acknowledgments:**

This work was done in collaboration with Trisha Singh, Noah Fischer, Steven Baker, and Sameer Panghal. Sincere thanks to them for their hard work on this project.


**Links:**
- [Project GitHub report](https://github.gatech.edu/nfischer30/CS7641-Group-6-Proposal/blob/main/final_report.md) for code and more details.



<h2 id="orbital-simulator">
Interactive Orbital Mechanics Simulator
</h2>

An interactive graphical orbital mechanics simulator based on 2-body Newtonian mechanics. Allows the user to simulate a constellation of spacecraft orbiting Earth and intuitively understand the scale and dynamics.

<div style="
  position: relative;
  padding-bottom: 56.25%;
  height: 0;
  overflow: hidden;
  max-width: 100%;
">

<iframe
        src="https://www.youtube.com/embed/3Q3xwDAv9vE"

        style="
          position: absolute;
          top: 0;
          left: 0;
          width: 100%;
          height: 100%;
        "

        frameborder="0"
        allowfullscreen>
</iframe>

</div>


**Key features**
- Command line arguments to change the following simulation parameters: 
    - The number of spacecraft in the simulated constellation
    - The mass of the spacecraft in the simulation
    - Spacing between spacecraft
    - Initial orbit radius and velocity of each spacecraft
    - Simulation time scale
- Accompanying MATLAB script to plot spacecraft trajectories
- Simulation log to confirm the simulation parameters
- “WASD + Up/Down” controls for changing the camera view

  
<p align="center">
  <img src="/assets/images/Trajectory_plot.png"
       width="500">
</p>
<p align="center">
  <strong>Figure 8</strong>. 3D plot of 2 spacecraft in the simulated constellation
</p>


**Technical Details**
- Leveraged C++ OpenGL for graphics rendering
- Employed custom classes to facilitate the addition of an arbitrary number of spacecraft
- Implemented the Verlet Integrator method to propagate the orbital mechanics

**Links**

- [Project GitHub](https://github.com/HarrisonJenkins45/Orbital_simulation)

<h2 id="hydrofoil-controller">
2D formation controller for fish-like bio-robots
</h2>


Two degree of freedom PD controller for formation control of schooling hydrofoils. Provides closed-loop control to command a pitching hydrofoil to navigate to and hold formation at a target position in the wake of another hydrofoil.

<div style="
  display: flex;
  justify-content: center;
  gap: 30px;
  flex-wrap: wrap;
  text-align: center;
">

  <div>
    <video width="300" controls>
      <source src="/assets/Hydrofoil_tracking.mp4" type="video/mp4">
    </video>

    <p>
      <strong>Video 1:</strong> Simulation of a closed-loop PD hydrofoil tracking
    </p>
  </div>

  <div>
    <img src="/assets/images/hydrofoil tracking.png"
         width="300">

    <p>
      <strong>Figure 9.</strong>
      Trailing hydrofoil position (in chord lengths) over time
    </p>
  </div>

</div>

**Results:**
Enabled the study of the hydrodynamic mechanisms that govern fish schooling in various formations of choice. This tool will enable researchers in the [Lehigh Unsteady Flow Interactions Laboratory](https://wordpress.lehigh.edu/kwm213/) to:
- Understand the most energetically efficient relative positions for fish to school in.
- Learn whether certain formations are physically possible to hold with realistic constraints
- Analyze the feedback control signals and find patterns that may allow for open-loop (feedback-less) control.

<h2 id="other-projects">
Other Projects
</h2>
Portfolio of past projects [here](https://canva.link/muc1xo8a8w28u1h)

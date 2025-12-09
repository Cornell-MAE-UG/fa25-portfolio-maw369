---
layout: project
title: 3270 Materials Final HW
description: ANSYS analysis of a torque wrench
technologies: ANSYS, MATLAB
image: /assets/images/materials-deformation.png
---
This project develops a digitally-instrumented torque wrench using finite-element analysis to determine strain distribution under load and to identify an optimal strain-gauge placement. Digitally instrumented tools like torque wrenches are widely used in aerospace, automotive, and energy, so accurate strain measurement directly affects safety and performance.
ANSYS Static Structural was used to model the wrench geometry, apply realistic boundary conditions, and evaluate normal strain, principal stress, and total deformation for a 600 in-lbf input torque.
<p align="center">
  <img src="/assets/images/materials-principal.png" width="60%">
  *Figure 1 – ANSYS Principal Stress*
</p>

Material selection was performed using published mechanical properties and safety-factor requirements, and several geometry modifications were evaluated to improve strain sensitivity while remaining below allowable stress limits. The final design integrates a bonded strain gauge configured as a half-bridge, enabling electrical output prediction (mV/V) based on FEM strain values.
<p align="center">
  <img src="/assets/images/Materials-graph.jpeg" width="60%">
  *Figure 2 – Material Selection Graph*
</p>

Skills: FEA, ANSYS Static Structural, strain-gauge instrumentation, stress analysis, mechanical design, MATLAB

**My Role:** Designed the digital strain measurement concept, modeled geometry in ANSYS, evaluated stress/strain results, and selected strain-gauge placement.
<p align="center">
  <img src="/assets/images/materials-strain.png" width="60%">
  *Figure 3 – ANSYS strain gauge location*
</p>

[View our full project here](https://docs.google.com/document/d/1r3QO4tW0H9VaC8c4zrUon-J6NAgUSllSU8sCg2zuuzc/edit?usp=sharing)
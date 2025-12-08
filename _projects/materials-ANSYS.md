---
layout: project
title: Spaceship Design
description: Just a spaceship that I designed
technologies: [SolidWorks, Machining]
image: /assets/images/materials.png
---



\\MATLAB Code: 
%Maya Watts Torque Wrench Design
%Hand Calculations

M = 600; %Max torque(lbf)
L = 16; %length(in)
h = 0.87; % width
b = 0.5; % thickness
c = .2; % distance from center of drive to center of strain gauge

%From Granta for specific material
name = 'Ti-12Mo-6Zr-2Fe, Titanium beta alloy'; % material name
E = 9.16e6; % Young's modulus (psi)
nu = 0.31; % Poisson's ratio
su = 135e3; % ultimate tensile strength yield(psi)
sy = 130e3; % yield tensile strength(psi)
KIC = 80.1e3; % fracture toughness (psi sqrt(in))
sfatigue = 70.7e3; % fatigue strength from Granta for 10^6 cycles

GF = 2;
a = .04; %initial crack depth
Y = 1.12;

I = b * h^3 / 12;
y = h/2;
max_stress = M * y / I; %psi

P = M / L;
strain_gauge_stress = (P * (L-c))* y / I;
epsilon = strain_gauge_stress / E;
strain_microstrain = epsilon * 1e6;

voltage_output = (GF * epsilon / 2)*1000;

deflection = P * L^3 / (3 * E * I);

if sy < su
    sigma_allow = sy;
else
    sigma_allow = su;
end

SF_strength = sigma_allow/ max_stress;
K_at_a = Y * max_stress * sqrt(pi * a);
SF_crack = KIC / K_at_a;
SF_fatigue = sfatigue / max_stress;

fprintf('Stress and deflection Analysis: \n');
fprintf('load point deflection = delta = %.3f in\n', deflection);
fprintf('max normal stress = %.2f ksi\n \n', max_stress/1000);

fprintf('Safety Factor results\n');
fprintf('Safety factor for strength, Xo = %.1f\n', SF_strength);
fprintf('Safety factor for crack growth, Xk = %.2f \n', SF_crack);
fprintf('Safety factor for fatigue, Xs = %.2f\n\n' ,SF_fatigue);

fprintf('Strain Gauge Results\n');
fprintf('strain = %.1f microstrain\n', strain_microstrain);
fprintf('output = %.2f mV/V\n', voltage_output);
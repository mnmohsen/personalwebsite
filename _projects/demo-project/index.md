---
layout: post
title: Michigan Aeronautical Science Association
description: Structural system design for MASA’s Citron liquid rocket, including concept architecture, analytical design tooling, structural trade studies, and validation planning.
skills:
  - Mechanical Design
  - Structural Analysis
  - Siemens NX
  - MATLAB
  - ANSYS
  - Finite Element Analysis
  - Aerospace Structures
  - Buckling Analysis
  - System Integration
  - Design for Manufacturability
  - Design Iteration

main-image: /image_rockit.png
---

## Overview

As part of the Michigan Aeronautical Science Association (MASA) Structures team, I have been working on the Thrust Transfer Structure (TTS) for Citron, MASA’s liquid rocket vehicle.

The TTS is the structural subsystem responsible for transferring engine thrust loads into the rocket airframe. While that sounds simple on paper, the design challenge is highly constrained. The structure must carry significant compressive loads while fitting within a crowded engine bay shared with propulsion hardware, plumbing, injector interfaces, and tank structure.

This project has been especially valuable because it blends structural engineering with mechanical design thinking. Rather than simply sizing compression members analytically, we have approached the TTS as a full engineered system requiring architecture decisions, structural validation, packaging awareness, manufacturability, and iterative refinement.

## The Design Challenge

A good thrust transfer structure cannot be optimized for only one metric.

Making members thicker may improve buckling performance, but it increases joint size and creates packaging conflicts. Reducing mass too aggressively may create fragile geometry or difficult manufacturing. Simplifying interfaces can improve reliability, but may reduce alignment flexibility during assembly.

The engineering challenge quickly became balancing competing priorities:

- safely transfer engine thrust into the vehicle structure
- minimize structural mass
- preserve room for propulsion hardware and plumbing
- remain manufacturable with available team resources
- allow inspection, assembly, and future testing
- improve on previous MASA architectures rather than simply inheriting them

This became a systems design problem, not just a structural calculation.

## Early Architecture Exploration

Early in the project, I developed a full conceptual TTS architecture inspired by the <a href="https://www.kegrocket.com/" target="_blank">Keg rocket</a> structural layout.

The design intent was to explore whether manufacturing complexity could be reduced by using standard perforated structural members, sheet metal plates, and circular interfaces rather than relying on more custom joint-heavy architecture.

<img src="/assets/images/tts_conc1.png" alt="Early TTS concept architecture" style="width:100%; max-height:600px; object-fit:contain; margin: 20px 0;">

<p style="font-size: 12px; color: #666; margin-top: 0;">
Early architecture concept exploring sheet-metal construction and standardized structural components.
</p>

The motivation was straightforward: if the structure could be built using simpler standard components, manufacturing and assembly might become significantly easier.

This concept also helped evaluate alternate thrust load paths, packaging strategies, and structural layouts.

However, after team review, two major limitations became clear.

First, the architecture consumed too much valuable space inside an already constrained engine bay.

Second, the propulsion team was understandably uncomfortable with a structural concept where major thrust loads would be transferred through fasteners in shear rather than through cleaner axial load paths.

Even though the concept was not carried forward, it served its purpose. It helped define what the final architecture needed to avoid and reinforced the importance of subsystem integration in structural design.

## Structural Design Tool Development

One of the earliest engineering questions in the project was deceptively simple:

**What structural members actually make sense for this application?**

Initial rod sizing began the traditional way, with hand calculations to estimate axial loads, stress, and Euler buckling behavior for candidate members.

<img src="/assets/images/ttshandcalc1.png" alt="Initial hand calculations for TTS rod sizing" style="width:100%; max-height:500px; object-fit:contain; margin: 20px 0;">

<p style="font-size: 12px; color: #666; margin-top: 0;">
Early hand calculation used to establish first-pass structural sizing assumptions.
</p>

That process worked, but it quickly became obvious how inefficient it was.

Every design change meant recalculating rod forces, stress, buckling behavior, geometry assumptions, and comparing multiple cross sections by hand. Since the design space included changing rod lengths, angles, wall thicknesses, diameters, and cross-sectional geometries, manually iterating through possibilities would have been painfully slow.

That led me to develop a MATLAB-based structural sizing GUI to accelerate early design iteration.

<img src="/assets/images/homepage_gui.png" alt="MATLAB GUI main interface" style="width:100%; max-height:500px; object-fit:contain; margin: 20px 0;">

<img src="/assets/images/gui_results.png" alt="MATLAB GUI analysis results" style="width:100%; max-height:500px; object-fit:contain; margin: 20px 0;">

<img src="/assets/images/fixed_parasweep.png" alt="MATLAB GUI parametric sweep" style="width:100%; max-height:500px; object-fit:contain; margin: 20px 0;">

<p style="font-size: 12px; color: #666; margin-top: 8px;">
MATLAB structural sizing tool developed for rapid structural trade studies, design iteration, and preliminary member validation.
</p>

The tool models each TTS rod as a pin-pin two-force member under axial compression and allows rapid exploration of candidate designs.

Key outputs include:

- axial stress
- reaction forces
- buckling load
- factor of safety
- cross-section comparisons
- parametric design sweeps across geometry variables

This transformed what would have been repetitive manual analysis into a much faster design workflow.

Instead of checking one geometry at a time, we could rapidly explore design trends and identify promising structural directions.

An important engineering lesson came when the original tool relied primarily on Euler buckling assumptions.

That worked well for slender members, but feedback during design review highlighted that Euler buckling becomes less accurate as members become less slender. At lower slenderness ratios, Johnson buckling provides a better approximation.

Rather than ignoring that limitation, I expanded the tool to incorporate Johnson buckling behavior so the analysis better reflected realistic structural conditions across a wider design space.

That evolution was important because it reinforced the actual purpose of engineering analysis tools:

not to generate pretty numbers, but to improve design decisions by becoming more accurate as understanding improves.

## Structural Trade Studies

The structural design space was less obvious than it initially appeared.

For example, larger diameter thin-wall tubes can dramatically improve buckling efficiency while reducing mass. However, that same decision increases joint size, consumes packaging volume, and complicates surrounding interfaces.

Using the sizing tool alongside team design discussions, we evaluated tradeoffs between:

- hollow circular vs hollow square sections
- diameter vs wall thickness
- buckling efficiency vs packaging
- lightweight optimization vs robustness
- theoretical efficiency vs practical manufacturability

This reinforced an important engineering lesson:

**the mathematically optimal component is not always the best system design.**

## Joint and Interface Design

The structural members themselves are only part of the engineering problem.

Joint design became equally important, since connection geometry directly affects load transfer, manufacturability, alignment tolerance, assembly complexity, and structural reliability.

I explored early joint concepts intended to balance structural simplicity with practical assembly needs.

<img src="/assets/images/tts_joint.png" alt="Preliminary joint concept design" style="width:100%; max-height:500px; object-fit:contain; margin: 20px 0;">

<p style="font-size: 12px; color: #666; margin-top: 0;">
Preliminary joint/interface concept exploration focused on manufacturability, alignment, and structural simplicity.
</p>

A recurring design question was how much adjustability should exist in the system.

Too much adjustability introduces unnecessary complexity, additional failure points, and manufacturing burden.

Too little makes alignment and assembly frustrating.

These interface decisions felt much closer to real mechanical product design than purely academic structural analysis.

## Current Development Phase

The project is currently transitioning from preliminary architecture and analytical sizing into higher-fidelity structural validation.

Current work includes:

- refining full CAD geometry
- improving subsystem integration
- evaluating packaging conflicts
- preparing ANSYS finite element analysis
- identifying non-ideal failure modes
- planning physical validation testing

The MATLAB sizing tool was intentionally built as a first-pass design aid, not final structural proof.

Future validation will examine:

- full assembly stress behavior
- joint loading
- local yielding
- local buckling
- Johnson buckling effects
- interface stiffness
- full-system load distribution

## Prototype and Validation Roadmap

A major strength of this project is that it does not end at theoretical design.

The planned engineering workflow includes:

1. CAD refinement
2. ANSYS structural validation
3. prototype fabrication
4. physical load testing
5. iteration based on measured results

That feedback loop is where engineering becomes real.

The most elegant analysis means very little if the hardware disagrees.

## What I Owned

My contributions have focused on concept generation, analytical design tooling, and system-level structural design thinking.

This includes:

- compact clevis-style joint redesign using a clevis pin and retaining ring
- full TTS assembly concept using circular hollow-section struts and annular interface rings
- early TTS architecture concept development
- structural concept iteration
- system-level trade studies
- MATLAB structural sizing GUI development
- axial stress and buckling analysis
- parametric design exploration
- cross-section trade comparisons
- joint/interface concept exploration
- preparation for higher-fidelity validation

### Summer 2026 Redesign and Structural Validation

During Summer 2026, I redesigned the thrust transfer structure around six circular hollow-section aluminum struts connecting the engine and tank interface rings.

The updated architecture uses compact clevis-style connections intended to let each strut behave approximately as a two-force member. A clevis pin and retaining ring connect each tubular strut to its bracket, while two bolts attach the bracket to the corresponding interface ring.

The redesign focused on creating a clearer axial load path while reducing joint size, part count, and assembly complexity.

<img src="/assets/images/tts_summer2026_concept.png" alt="Updated Citron thrust transfer structure concept with six tubular struts and compact clevis joints" style="width:100%; max-height:650px; object-fit:contain; margin:20px 0;">

<p style="font-size:12px; color:#666; margin-top:0;">
Updated six-member TTS concept integrating hollow aluminum struts, compact clevis-style joints, and preliminary engine and tank interface rings.
</p>

The interface rings shown in this model are preliminary geometry used to establish the structural layout, member locations, and overall packaging envelope. Their final thicknesses, mounting features, and local reinforcement will be developed as the surrounding propulsion interfaces mature.

The updated assembly also corrected an earlier overconstrained member arrangement. Reducing the structure to six primary struts created a clearer and more predictable load path without introducing redundant members whose force distribution would depend heavily on manufacturing tolerances and joint stiffness.

The selected struts use 6061-T6 aluminum tubing with:

- 5/8-inch outside diameter
- 1/8-inch wall thickness
- 3/8-inch inside diameter
- approximately 21-inch pin-center-to-pin-center length

Aluminum provided sufficient strength and buckling resistance while remaining lightweight, readily available, weldable, and straightforward to analyze. It can also be treated as approximately isotropic, while a composite tube would require laminate-specific material properties, directional failure criteria, bonded metallic end fittings, and additional joint testing.

#### Static Stress Validation

I first created a simplified ANSYS model of a single tubular strut to validate its basic axial behavior.

The ends were modeled as pinned connections, allowing rotation while restraining the translations needed to represent the clevis interfaces. A compressive load of 2,965 N, or approximately 667 lbf, was applied to represent a conservative 4,000 lbf total thrust load divided equally among six struts.

The analytical axial stress was calculated using:

<div style="text-align:center; font-size:1.2rem; margin:24px 0;">
  σ =
  <span style="display:inline-block; vertical-align:middle; text-align:center; margin-left:6px;">
    <span style="display:block; border-bottom:1px solid currentColor; padding:0 10px;">
      F
    </span>
    <span style="display:block; padding-top:2px;">
      A
    </span>
  </span>
</div>

For the selected tube geometry, the cross-sectional area is approximately 126.7 mm².

<div style="text-align:center; font-size:1.2rem; margin:24px 0;">
  σ =
  <span style="display:inline-block; vertical-align:middle; text-align:center; margin:0 6px;">
    <span style="display:block; border-bottom:1px solid currentColor; padding:0 10px;">
      2,965 N
    </span>
    <span style="display:block; padding-top:2px;">
      126.7 mm²
    </span>
  </span>
  ≈ 23.4 MPa
</div>

<img src="/assets/images/tts_static_stress_fea.png" alt="ANSYS static structural stress result for the TTS aluminum strut" style="width:100%; max-height:650px; object-fit:contain; margin:20px 0;">

<p style="font-size:12px; color:#666; margin-top:0;">
Static structural analysis of one TTS strut under a 2,965 N compressive load. The approximately 23.4 MPa FEA result closely matched the analytical axial-stress calculation.
</p>

ANSYS predicted approximately 23.4 MPa of equivalent stress through the uniform section of the tube, closely matching the analytical result.

This agreement confirmed that the applied loading, material properties, cross-sectional geometry, and boundary conditions were behaving as intended before progressing to buckling analysis.

A separate higher-detail model including the tube and end geometry produced a larger local stress near the load-transfer region. This identified the tube-to-end-fitting interface as an area requiring additional joint-level analysis rather than treating the complete strut as a perfectly uniform member.

#### Eigenvalue Buckling Validation

Because the members carry compression, material yielding was not the only potential failure mode. Global column buckling also needed to be evaluated.

I first estimated the critical load analytically using Euler buckling for a pin-pin column:

<div style="text-align:center; font-size:1.2rem; margin:24px 0;">
  <em>P</em><sub>cr</sub> =
  <span style="display:inline-block; vertical-align:middle; text-align:center; margin-left:6px;">
    <span style="display:block; border-bottom:1px solid currentColor; padding:0 10px;">
      π²EI
    </span>
    <span style="display:block; padding-top:2px;">
      L²
    </span>
  </span>
</div>

The hand calculation predicted a critical buckling load of approximately 1,460 lbf.

I then performed a pre-stressed eigenvalue buckling analysis in ANSYS using the solved static load case. The first buckling mode produced a load multiplier of 2.2485.

Using the 2,965 N reference load:

<div style="text-align:center; font-size:1.2rem; margin:24px 0;">
  <em>P</em><sub>cr</sub> = 2.2485 × 2,965 N
</div>

<div style="text-align:center; font-size:1.2rem; margin:24px 0;">
  <em>P</em><sub>cr</sub> ≈ 6,667 N ≈ 1,499 lbf
</div>

<img src="/assets/images/tts_buckling_fea.png" alt="First eigenvalue buckling mode of the TTS aluminum strut" style="width:100%; max-height:650px; object-fit:contain; margin:20px 0;">

<p style="font-size:12px; color:#666; margin-top:0;">
First global buckling mode of the TTS strut. ANSYS predicted a critical load of approximately 1,499 lbf, within about 3% of the Euler buckling calculation.
</p>

The FEA prediction was within approximately 3% of the analytical result. The first mode also showed the expected smooth lateral bow of a pin-pin column, providing a qualitative check that the model was producing the correct global failure mode.

The deformation displayed in an eigenvalue buckling result is an arbitrary visualization scale. The meaningful outputs are the buckling mode shape and the load multiplier, not the displayed displacement magnitude.

#### Interpretation and Limitations

The static and eigenvalue models validate the first-order axial stress and ideal global buckling behavior of an individual strut.

They do not represent complete flight qualification.

Additional validation is still needed to evaluate:

- unequal load sharing among the six struts
- thrust misalignment and load eccentricity
- clevis pin shear and bending
- bearing stress around the pin holes
- bracket bending and local yielding
- bolt loading at the interface rings
- weld and heat-affected-zone strength
- interface-ring flexibility
- geometric imperfections
- nonlinear buckling behavior
- vibration and dynamic launch loading
- packaging and tool access around propulsion hardware

The next phase will incorporate more detailed joint geometry, realistic interface stiffness, and full-assembly load distribution. Physical testing will ultimately be used to compare the analytical and numerical predictions against actual hardware behavior.

## Key Takeaways

This project progressed from an open-ended structural problem into a traceable engineering workflow:

1. establish the load path and system requirements
2. perform first-pass hand calculations
3. automate design exploration using MATLAB
4. develop the joints and complete CAD architecture
5. validate axial stress using static FEA
6. validate global buckling using hand calculations and eigenvalue FEA
7. identify the limitations requiring higher-fidelity analysis and testing

The strongest lesson was that analysis is most valuable when it is used to build confidence step by step.

The hand calculations provided an independent prediction. The simplified static model verified the loading and boundary conditions. The buckling model reproduced both the expected failure shape and critical load. The remaining uncertainty is now concentrated in the joints, interfaces, imperfections, and full-system behavior rather than the basic compression-member sizing.

That progression from concept development to analytical sizing and numerical validation has made the TTS one of my most complete mechanical engineering projects.

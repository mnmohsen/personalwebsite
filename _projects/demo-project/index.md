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

### Summer 2026 Joint and Architecture Redesign

During Summer 2026, I developed a new compact joint design and integrated it into a complete TTS assembly concept using circular hollow-section struts.

The redesigned joint consolidates the member connection into a compact clevis-style bracket. A clevis pin and retaining ring connect each tubular strut to the bracket, while two hex-head bolts fasten the bracket directly to the upper or lower interface ring.

<img src="/assets/images/tts_joint_redesign.png" alt="Compact clevis-style TTS joint redesign" style="width:100%; max-height:500px; object-fit:contain; margin: 20px 0;">

<p style="font-size: 12px; color: #666; margin-top: 0;">
Compact joint design using a clevis pin and retaining ring for the strut connection and two hex-head bolts for attachment to the interface ring.
</p>

The redesign was developed to:

- reduce the size of each joint
- consolidate the connection into fewer components
- eliminate the need for threaded inserts
- provide a removable and serviceable strut connection
- simplify repeated assembly around the circular interface rings
- create a direct load path between the tubular struts and interface rings

I then used the redesigned joint to create a new full TTS concept consisting of multiple circular hollow-section struts arranged between annular upper and lower interface rings.

<img src="/assets/images/tts_full_concept.png" alt="Full Citron thrust transfer structure concept using circular hollow-section struts" style="width:100%; max-height:650px; object-fit:contain; margin: 20px 0;">

<p style="font-size: 12px; color: #666; margin-top: 0;">
Full Citron TTS concept integrating the compact clevis joints, circular hollow-section struts, and placeholder annular interface rings into a complete structural assembly.
</p>

This concept brought the analytical member sizing, joint design, and full-system architecture together in one CAD assembly.The tank interface ring and rocket engine interface ring shown in this assembly are simplified placeholders used to establish the overall structural layout. Their geometry, mounting features, thicknesses, and interfaces will be developed in future design phases. This concept primarily focuses on the tubular member arrangement and the redesigned clevis-style joints rather than finalized interface-ring design.

Developing the complete assembly also helped identify the next areas requiring detailed analysis, including:

- clevis pin shear
- bearing stress around the pin holes
- bracket bending and local yielding
- bolt loading at the interface rings
- joint stiffness
- interface-ring deformation
- strut buckling
- assembly and tool access
- packaging around propulsion hardware

## Key Takeaways

This project has been one of my strongest engineering experiences because it blends structural analysis with real design iteration.

The biggest lesson has been that engineering is rarely about finding a single correct answer.

It is about balancing performance, manufacturability, packaging, validation strategy, and uncertainty while continuously refining the design.

That mindset translates directly to mechanical product development.



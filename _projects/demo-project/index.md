---
layout: post
title: Michigan Aeronautical Science Association
description: Design and structural validation of the thrust transfer structure for MASA’s Citron liquid rocket.
skills:
  - Mechanical Design
  - Structural Analysis
  - Siemens NX
  - MATLAB
  - ANSYS
  - Finite Element Analysis
  - Aerospace Structures
  - Buckling Analysis
  - Joint Design
  - System Integration
  - Design for Manufacturability
  - Design Iteration

main-image: /assets/images/tts_summer2026_concept.png
---

## Thrust Transfer Structure Design and Validation

I redesigned the structural system that transfers engine thrust into MASA’s Citron liquid rocket, developed a MATLAB sizing tool from first principles, designed compact clevis-style joints, and verified the selected aluminum struts through analytical calculations and ANSYS finite element analysis.

**Current design summary**

- six primary 6061-T6 aluminum struts
- 2,965 N conservative reference load per strut
- static FEA matched the analytical axial-stress result
- global buckling FEA matched Euler buckling within approximately 3%
- local buckling was length- and mesh-converged
- the ideal local-buckling eigenvalue was approximately 2.13 MN, screening local wall buckling out as a governing failure mode

<img src="/assets/images/tts_summer2026_concept.png" alt="Current six-member thrust transfer structure assembly for MASA Citron" style="width:100%; max-height:700px; object-fit:contain; margin:20px 0;">

<p style="font-size:12px; color:#666; margin-top:0;">
Current six-member TTS architecture using hollow aluminum struts, compact clevis-style joints, and preliminary engine and tank interface rings.
</p>

## Where the TTS Sits in the Rocket

<img src="/assets/images/tts_rocket_context_sketch.jpg" alt="Sketch showing the thrust transfer structure relative to the rest of the rocket" style="width:100%; max-height:650px; object-fit:contain; margin:20px 0;">

<p style="font-size:12px; color:#666; margin-top:0;">
The TTS sits between the propulsion system and the vehicle structure, transferring engine thrust through the struts and into the rocket airframe.
</p>

The thrust transfer structure sits inside the lower vehicle between the engine-side and tank-side interfaces.

Its job is to:

- receive engine thrust at the lower interface
- carry that load primarily as axial compression through the struts
- transfer the load into the upper vehicle structure
- fit around propulsion hardware, plumbing, injector interfaces, fasteners, and assembly tooling

This made the project a system-integration and joint-design problem as much as a structural calculation.

## What I Owned

My work included:

- MATLAB structural sizing GUI development
- first-principles reaction-force and member-load calculations
- Euler and Johnson buckling implementation
- cross-section and geometry trade studies
- six-strut TTS architecture development
- compact clevis-style top and bottom joint design
- tube end-fitting and interface development
- static stress verification in ANSYS
- global eigenvalue-buckling analysis
- local wall-buckling analysis
- length- and mesh-convergence studies
- full assembly CAD integration

## Structural Design Tool Development

The first engineering question was:

**What structural members actually make sense for this application?**

Initial sizing began with free-body diagrams and hand calculations for:

- reaction forces
- axial member load
- axial stress
- Euler buckling
- factor of safety

<img src="/assets/images/ttshandcalc1.png" alt="Initial hand calculations for TTS rod sizing" style="width:100%; max-height:500px; object-fit:contain; margin:20px 0;">

<p style="font-size:12px; color:#666; margin-top:0;">
Initial hand calculations used to establish the load path and first-pass structural sizing assumptions.
</p>

That process worked, but every change in rod length, angle, diameter, wall thickness, or cross-section required another full calculation.

I converted the analysis into a MATLAB GUI so candidate designs could be evaluated rapidly.

<img src="/assets/images/homepage_gui.png" alt="MATLAB GUI main interface for TTS member sizing" style="width:100%; max-height:550px; object-fit:contain; margin:20px 0;">

<img src="/assets/images/gui_results.png" alt="MATLAB GUI results for member load, stress, and buckling" style="width:100%; max-height:550px; object-fit:contain; margin:20px 0;">

<img src="/assets/images/fixed_parasweep.png" alt="MATLAB GUI parametric sweep for TTS geometry" style="width:100%; max-height:550px; object-fit:contain; margin:20px 0;">

<p style="font-size:12px; color:#666; margin-top:8px;">
MATLAB structural sizing tool used for rapid load calculations, section comparisons, and parametric design sweeps.
</p>

The tool models each rod as an idealized pin-pin two-force member under axial compression.

Key outputs include:

- axial stress
- reaction forces
- critical buckling load
- factor of safety
- cross-section comparisons
- geometry sweeps
- buckling performance across the design space

The original version relied primarily on Euler buckling. After recognizing that Euler becomes less accurate for lower-slenderness members, I added Johnson buckling so the model changes with the applicable slenderness regime.

The GUI was used as a first-pass design-space filter, not as final structural proof.

## ANSYS Structural Verification

### Static Axial Stress

The selected struts use 6061-T6 aluminum tubing with:

- 5/8-inch outside diameter
- 1/8-inch wall thickness
- 3/8-inch inside diameter
- approximately 21-inch pin-center-to-pin-center length

A conservative 4,000 lbf total engine-thrust case was divided equally among six struts for the simplified member-level analysis, producing a 2,965 N reference load per strut.

The analytical axial stress was:

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
Static structural analysis of one TTS strut under a 2,965 N compressive reference load. The approximately 23.4 MPa FEA result closely matched the analytical axial-stress calculation.
</p>

The close agreement verified that the loading, cross-sectional geometry, material properties, and simplified boundary conditions were behaving as intended.

A higher-detail model including the tube end geometry produced a larger local stress near the load-transfer region. This shifted attention toward the tube-to-end-fitting interface and joint geometry rather than the uniform tube wall.

### Global Eigenvalue Buckling

Global column buckling was first estimated analytically using Euler buckling for an ideal pin-pin member:

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

The hand calculation predicted a critical load of approximately 1,460 lbf.

The first ANSYS global buckling mode produced a load multiplier of 2.2485 using the 2,965 N reference load:

<div style="text-align:center; font-size:1.2rem; margin:24px 0;">
  <em>P</em><sub>cr</sub> = 2.2485 × 2,965 N ≈ 6,667 N ≈ 1,499 lbf
</div>

<img src="/assets/images/tts_buckling_fea.png" alt="First global eigenvalue buckling mode of the TTS aluminum strut" style="width:100%; max-height:650px; object-fit:contain; margin:20px 0;">

<p style="font-size:12px; color:#666; margin-top:0;">
First global buckling mode of the TTS strut. The ANSYS critical load was within approximately 3% of the Euler prediction and showed the expected smooth lateral bow of a pin-pin column.
</p>

The displayed deformation magnitude in an eigenvalue result is arbitrary. The meaningful outputs are the mode shape and load multiplier.

### Local Wall Buckling

I also evaluated whether the tube wall could wrinkle locally before global column buckling or another failure mode became critical.

The local mode family showed repeated helical wall lobing rather than a smooth lateral bow of the complete member.

<img src="/assets/images/tts_local_buckling_refined.png" alt="Refined ANSYS local wall buckling mode showing repeated helical lobing" style="width:100%; max-height:650px; object-fit:contain; margin:20px 0;">

<p style="font-size:12px; color:#666; margin-top:0;">
Refined local wall-buckling mode showing repeated helical lobing. Eigenmode displacement magnitude is arbitrary; the meaningful outputs are the mode shape and load multiplier.
</p>

To verify that the result was not controlled by coupon length, I compared matching local-mode families:

- 2.5-inch coupon: 2.1304 MN
- 5-inch coupon: 2.1235 MN
- difference: approximately 0.32%

To verify that the result was not controlled by mesh density, I compared the baseline and refined meshes:

- baseline mesh: 2.1304 MN
- refined mesh: 2.1293 MN
- difference: approximately 0.052%

The same local-lobing family appeared in each study while the predicted critical load remained essentially unchanged.

The converged linear eigenvalue prediction was approximately 2.13 MN.

Compared with the 2,965 N reference member load, this is roughly 718 times higher.

This ratio is not a real-world factor of safety because linear eigenvalue buckling assumes ideal geometry and linear elastic behavior. However, the separation is large enough to screen local wall buckling out as a governing failure mode for this design.

## Current Joint Design

Once the basic member geometry was established, the main design uncertainty shifted to the joints.

I developed compact clevis-style connections intended to:

- preserve a clear axial load path
- let each strut behave approximately as a two-force member
- reduce joint size
- reduce part count
- simplify assembly
- provide positive pin retention

### Bottom Joint

<img src="/assets/images/tts_bottom_joint_closeup.png" alt="Closeup of the current lower TTS clevis-style joint" style="width:100%; max-height:650px; object-fit:contain; margin:20px 0;">

<p style="font-size:12px; color:#666; margin-top:0;">
Current lower joint concept using a clevis pin and retaining ring at the strut connection, with two bolts attaching the bracket to the engine-side interface.
</p>

### Top Joint

<img src="/assets/images/tts_top_joint_closeup.png" alt="Closeup of the current upper TTS clevis-style joint" style="width:100%; max-height:650px; object-fit:contain; margin:20px 0;">

<p style="font-size:12px; color:#666; margin-top:0;">
Current upper joint concept adapted to the tank-side interface while preserving the same basic axial-member intent.
</p>

The real clevis joint permits rotation primarily about the pin axis. The simplified member-level FEA used idealized constraints to isolate tube stress and buckling behavior rather than claim that the complete joint had already been verified.

Future joint-level analysis will evaluate:

- clevis pin shear and bending
- bearing stress around pin holes
- bracket bending
- local yielding
- bolt loading
- weld and heat-affected-zone strength
- interface stiffness
- eccentric load introduction

## Current Integrated Assembly

<img src="/assets/images/tts_summer2026_concept.png" alt="Complete current six-strut thrust transfer structure assembly" style="width:100%; max-height:700px; object-fit:contain; margin:20px 0;">

<p style="font-size:12px; color:#666; margin-top:0;">
Current integrated TTS assembly with six hollow aluminum struts, compact clevis-style joints, and preliminary engine and tank interface rings.
</p>

The six-member layout replaced an earlier overconstrained arrangement.

Reducing the system to six primary struts produced a clearer and more predictable load path without redundant members whose force distribution would depend heavily on manufacturing tolerances and joint stiffness.

The interface rings remain preliminary. Their final thicknesses, bolt patterns, mounting features, and local reinforcement will be developed as the surrounding propulsion interfaces mature.

## Current Engineering Conclusion

The basic compression-member design is now supported by independent analytical and numerical evidence.

- static stress matched the analytical axial-stress calculation
- global buckling matched Euler within approximately 3%
- local buckling was length-converged
- local buckling was mesh-converged
- local wall buckling was screened out as non-governing

The remaining uncertainty is concentrated in:

- joints
- interfaces
- unequal load sharing
- thrust misalignment
- geometric imperfections
- nonlinear behavior
- full-system dynamics
- physical test correlation

## Background and Earlier Concepts

The current design is the result of several earlier concepts and trade studies. These are included below for readers who want the full development history.

<details>
<summary><strong>Original Sleeve-Bearing and Ball-Joint Concept</strong></summary>

<img src="/assets/images/tts_joint.png" alt="Earlier TTS joint concept using custom sleeve bearings and a ball joint" style="width:100%; max-height:550px; object-fit:contain; margin:20px 0;">

<p style="font-size:12px; color:#666; margin-top:0;">
Earlier joint concept using custom sleeve bearings, a shoulder screw, and a ball-joint interface to provide alignment adjustment.
</p>

This concept explored adjustability and alignment tolerance, but introduced additional custom hardware, manufacturing complexity, and potential failure points.

The later clevis-style design reduced the mechanism to a simpler and more compact load path.

</details>

<details>
<summary><strong>Original Full-System Architecture</strong></summary>

Early in the project, I developed a conceptual TTS architecture inspired by the <a href="https://www.kegrocket.com/" target="_blank">Keg rocket</a> structural layout.

<img src="/assets/images/tts_conc1.png" alt="Early TTS architecture using perforated structural members and sheet metal" style="width:100%; max-height:600px; object-fit:contain; margin:20px 0;">

<p style="font-size:12px; color:#666; margin-top:0;">
Early architecture exploring standardized perforated members, sheet-metal construction, and circular interfaces.
</p>

The concept explored whether standard components could simplify manufacturing.

It was not carried forward because:

- it consumed too much engine-bay volume
- major thrust loads would have passed through fasteners in shear
- the resulting load path was less direct than the later axial-strut architecture

Even though it was rejected, it helped define what the final architecture needed to avoid.

</details>

<details>
<summary><strong>Structural Trade Studies</strong></summary>

Using the MATLAB tool and team design discussions, I evaluated tradeoffs between:

- hollow circular and hollow square sections
- outside diameter and wall thickness
- buckling efficiency and packaging volume
- lightweight optimization and robustness
- theoretical efficiency and practical manufacturability

A larger-diameter thin-wall tube may be mathematically efficient, but it also increases joint size and consumes more packaging volume.

The best member was therefore not simply the geometry with the highest analytical factor of safety. It had to work as part of the complete mechanical system.

</details>

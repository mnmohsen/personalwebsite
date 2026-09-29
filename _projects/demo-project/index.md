---
layout: post
title: Michigan Aeronautical Science Association
description: Designed the thrust transfer structure for MASA's Citron liquid rocket, combining structural sizing, compact joint design, topology-driven ring development, and assembly integration in Siemens NX.
skills:
  - Mechanical Design
  - Siemens NX
  - Structural Analysis
  - ANSYS
  - MATLAB
  - Joint Design
  - Topology Optimization
  - Design for Manufacturability
  - System Integration

main-image: /image_rockit.png
---

## Designing the Structure That Transfers Rocket Thrust

A rocket engine needs a structural connection to push the rest of the vehicle. For MASA's Citron liquid rocket, the **thrust transfer structure (TTS)** carries that force from the engine into the tank-side structure through six aluminum struts, fitting around propulsion hardware and plumbing.

As the **Responsible Engineer**, I developed the strut sizing tools, designed compact joints, refined interface rings, and integrated the assembly in Siemens NX. The central challenge was balancing compression strength and low mass with limited space, practical fabrication, and assembly access.

<img src="/assets/images/newttscover.png" alt="Thrust transfer structure shown within Citron's propulsion bay, connecting the engine-side and tank-side interfaces" style="width:100%; max-height:750px; object-fit:contain; margin:20px 0;">

*TTS within the rocket: six struts carry thrust across the propulsion bay. Interface geometry shown reflects this design iteration.*

## Designing the Joints Around the Hardware

The connections had to fit around propulsion hardware while transferring load from the struts into the mounting interfaces. I designed compact clevis-style brackets and pin connections, then selected **PTFE-lined spherical rod ends to reduce joint play**, coordinating with Timken/Aurora on OEM pricing.

I also revised the pin-retention design to use **Smalley retaining rings with greater circumferential engagement**. Working with Smalley's engineers, I reviewed the groove and pin concept, selected a compatible ring, and obtained samples for prototype evaluation.

<div style="display:grid; grid-template-columns:repeat(auto-fit,minmax(250px,1fr)); gap:20px; align-items:start; margin:24px 0;">
  <div>
    <img src="/assets/images/nxphoto.png" alt="Latest Siemens NX assembly of the six-strut TTS with updated spherical rod ends" style="width:100%; height:480px; object-fit:contain;">
    <p><em>Latest assembly with the updated rod ends and individual engine-side mounting brackets.</em></p>
  </div>
  <div>
    <img src="/assets/images/topjoint.png" alt="Upper clevis joint detail showing the strut connection at the tank-side interface" style="width:100%; height:480px; object-fit:contain;">
    <p><em>Upper joint: compact clevis connection at the tank-side interface.</em></p>
  </div>
</div>

I integrated these connections into the six-strut NX assembly, incorporating the welded tube-end design developed by teammate Gabe Popso.

## Assembly Stress and Buckling Analysis

I refined the ANSYS assembly model with revolute pin connections to represent rotation at the clevis joints. Under the evaluated thrust load, rod midspan stresses of **22.26–22.42 MPa agreed within 0.4%** of my **22.34 MPa** first-principles prediction.

<img src="/assets/images/tts_vm_stress.png" alt="ANSYS assembly stress analysis with rod midspan probes showing approximately 22.26 to 22.42 MPa" style="width:100%; max-height:600px; object-fit:contain; margin:20px 0;">

*Rod midspan von Mises stresses compared with the analytical axial-stress prediction.*

I also compared the assembly's predicted buckling behavior with a pin-ended Euler estimate using the full **24-inch bearing-center spacing**, accounting for the end connections as well as the tube. For matching base and perturbation loads, the assembly result corresponds to a predicted critical load of approximately **1.87 times the reference load**, within **about 6%** of the analytical estimate of **1.76**.

<img src="/assets/images/tts_buckling.png" alt="Predicted eigenvalue buckling mode showing lateral bowing of a strut in the assembly with revolute pin connections" style="width:100%; max-height:600px; object-fit:contain; margin:20px 0;">

*Predicted buckling mode; deformation is scaled for visibility. The displayed 0.871 multiplier represents an additional load increment above the preloaded state, giving a total load ratio of 1.871 when the base and perturbation loads match.*

## Turning Topology Results into Manufacturable Rings

I used ANSYS topology optimization to explore material removal from the interface rings while preserving their mounting regions. In the tank-side ring study, the optimization removed **approximately 40% of the baseline material** with a minimum-compliance objective under the factored design load.

<div style="display:grid; grid-template-columns:repeat(auto-fit,minmax(220px,1fr)); gap:18px; align-items:start; margin:24px 0;">
  <div>
    <img src="/assets/images/topring_old.png" alt="Baseline tank-side interface ring" style="width:100%; height:240px; object-fit:contain;">
    <p><strong>Baseline:</strong> Continuous ring with the required mounting interfaces.</p>
  </div>
  <div>
    <img src="/assets/images/topring_structopt.png" alt="ANSYS topology result indicating material removal from the tank-side ring" style="width:100%; height:240px; object-fit:contain;">
    <p><strong>Optimization:</strong> Approximately 40% material removal in the topology result.</p>
  </div>
  <div>
    <img src="/assets/images/fullynewtopring.png" alt="Refined ring CAD with simplified cutouts and preserved support beneath the joints" style="width:100%; height:240px; object-fit:contain;">
    <p><strong>CAD refinement:</strong> Simplified geometry with material retained beneath the joints.</p>
  </div>
</div>

I translated the optimization into conventional CAD, using the load paths to guide cutouts and preserving contact area beneath the top joints. An earlier engine-side ring study followed the same approach, replacing the raw topology geometry with through-pockets, fillets, and constant plate thickness for machining.

## Sizing the Struts with a MATLAB Design Tool

I built a MATLAB GUI from free-body diagrams and first-principles calculations to compare strut geometries. It calculates member loads, axial stress, and Euler or Johnson buckling predictions, with parameter sweeps for length, angle, cross-section, and wall thickness.

<img src="/assets/images/fixed_parasweep.png" alt="MATLAB sizing tool showing a parameter sweep of strut buckling performance" style="width:100%; max-height:550px; object-fit:contain; margin:20px 0;">

*Parameter sweeps made it possible to compare geometry trends before committing to detailed CAD and FEA.*

My circular-versus-square tube studies supported the team's selection of **6061-T6 round tubing with a 5/8-inch outside diameter and 1/8-inch wall**. The selection balanced buckling resistance with packaging, availability, and fabrication needs.

## Checking Strut Analysis Against First Principles

Earlier member-level studies established the analytical checks used to assess the strut models:

- **Axial stress:** The isolated strut model predicted approximately **23.4 MPa** under a 2,965 N reference load, matching the hand calculation.
- **Global buckling:** The idealized pin-ended strut's eigenvalue prediction agreed with Euler buckling within **approximately 3%**.
- **Local wall buckling:** I compared coupon lengths and mesh densities to check the stability of the predicted local mode.

<div style="display:grid; grid-template-columns:repeat(auto-fit,minmax(250px,1fr)); gap:20px; align-items:start; margin:24px 0;">
  <div>
    <img src="/assets/images/newmeshy.png" alt="ANSYS isolated-strut axial stress result checked against the analytical calculation" style="width:100%; height:360px; object-fit:contain;">
    <p><em>Isolated-strut stress model checked against force divided by cross-sectional area.</em></p>
  </div>
  <div>
    <img src="/assets/images/tts_buckling_fea.png" alt="ANSYS global buckling mode for the idealized pin-ended strut" style="width:100%; height:360px; object-fit:contain;">
    <p><em>Member-level buckling mode compared with the Euler prediction.</em></p>
  </div>
</div>

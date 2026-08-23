---
layout: post
title: Removable Bicycle LED Light Mount
description: Designed, prototyped, and tested a two-fastener PETG bicycle light mount with tool-free lamp removal, indexed angle adjustment, and integrated snap-fit joints.
skills:
  - SolidWorks
  - Mechanical Design
  - Design for Additive Manufacturing
  - 3D Printing
  - Prototyping & Testing
main-image: /assets/images/hero.png
---

<style>
.bike-light-project h2 {
  font-size: 1.85rem;
  font-weight: 700;
  margin-top: 2.5rem;
  margin-bottom: 1rem;
}

.bike-light-project h3 {
  font-size: 1.35rem;
  font-weight: 700;
  margin-top: 2rem;
  margin-bottom: 0.75rem;
}

.bike-light-project p,
.bike-light-project li {
  line-height: 1.65;
}

.bike-light-project .project-image {
  width: 100%;
  max-height: 650px;
  object-fit: contain;
  margin: 1.5rem 0 0.35rem 0;
}

.bike-light-project .caption {
  font-size: 12px;
  color: #666;
  margin-top: 0;
  margin-bottom: 1.5rem;
}

.bike-light-project .image-grid {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 16px;
  margin: 1.5rem 0 0.35rem 0;
}

.bike-light-project .image-grid img {
  width: 100%;
  height: 100%;
  max-height: 480px;
  object-fit: contain;
}

@media (max-width: 700px) {
  .bike-light-project .image-grid {
    grid-template-columns: 1fr;
  }
}
</style>

<div class="bike-light-project" markdown="1">

# Removable Bicycle LED Light Mount

I wanted a substantially brighter light for riding my bicycle at night, but the rechargeable LED lamp I had available was originally designed as a headlamp. Rather than replace it, I designed a dedicated mounting system that could securely integrate the lamp with my bicycle while preserving its original angle adjustment and allowing it to be quickly removed for charging.

The result was a multi-part PETG assembly designed in **SolidWorks**, manufactured with FDM 3D printing, and iterated through physical testing on the bicycle.

The first functional prototype successfully mounted the lamp, retained its adjustable aiming mechanism, reduced the handlebar attachment to only **two fasteners**, and allowed the entire lamp carrier to slide off the bicycle without tools.

<img class="project-image" src="/assets/images/bike-light-mount/hero.jpg" alt="Completed removable LED bicycle light mount installed on bicycle">
<p class="caption">Iteration 1 installed and tested on the bicycle.</p>

## Defining the Problem

The lamp already contained a bright rechargeable LED, battery, controls, and a useful indexed pivot mechanism. The challenge was not designing another light—it was designing the mechanical system needed to turn the existing product into a practical bicycle light.

My primary design goals were to:

- securely mount the lamp to the handlebar,
- retain its existing indexed angle adjustment,
- allow the lamp to be removed easily for charging,
- minimize the number of screws and loose components,
- package the assembly around existing bicycle hardware and cables,
- manufacture the prototype using FDM 3D printing, and
- create a product that looked intentional rather than like a simple adapter bracket.

<div class="image-grid">
  <img src="/assets/images/bike-light-mount/initial-sketch.jpg" alt="Initial hand sketch of bicycle light mounting concept">
  <img src="/assets/images/bike-light-mount/original-headlamp.jpg" alt="LED lamp in its original headlamp configuration">
</div>
<p class="caption">Early concept sketch and the rechargeable LED lamp in its original head-mounted application.</p>

The initial sketches were useful for establishing the overall architecture before committing to detailed CAD: a permanent handlebar interface, a removable lamp carrier, and a mechanism that reused the lamp's existing angular adjustment features.

## Mechanical Architecture

I divided the design into two major assemblies:

1. a **handlebar mount** that remains attached to the bicycle, and
2. a **removable lamp carrier** that interfaces with the light.

The two assemblies connect using integrated T-shaped sliding features. This allows the lamp and its carrier to slide off the fixed bicycle mount for charging without loosening the handlebar clamps.

<img class="project-image" src="/assets/images/bike-light-mount/cad-assembly.jpg" alt="SolidWorks CAD model of bicycle LED light mount assembly">
<p class="caption">SolidWorks assembly showing the handlebar clamps, structural bridge, removable lamp carrier, and sliding interface.</p>

### Removable Sliding Interface

Because charging requires access to the lamp away from the bicycle, I did not want the user to repeatedly remove mounting screws.

Instead, I incorporated mating T-style rails between the two assemblies. The printed sliding surfaces were designed with approximately **0.25 mm of clearance per mating side**, providing enough manufacturing allowance for FDM printing while maintaining controlled alignment of the lamp.

The rail carries and locates the lamp during use, while removal requires only sliding the lamp carrier out of the fixed base.

<img class="project-image" src="/assets/images/bike-light-mount/slider-detail.jpg" alt="CAD detail of removable T rail interface">
<p class="caption">T-style sliding interface used to separate the rechargeable lamp from the permanent handlebar mount.</p>

## Reducing the Fastener Count

A conventional split-clamp design could have used two screws per handlebar clamp, requiring four fasteners across the assembly.

Instead, I designed one side of each C-clamp around an integrated **snap-in locating joint**. The joint constrains the relative motion and rotation of the clamp components while the screw on the opposite side generates the required clamping force.

This reduced the complete handlebar attachment from **four fasteners to two** while also simplifying assembly.

<img class="project-image" src="/assets/images/bike-light-mount/snap-joint-cad.jpg" alt="Snap fit locating joint used in bicycle handlebar clamp">
<p class="caption">Integrated locating joint replaces one conventional fastener location on each C-clamp.</p>

The geometry required physical iteration. Small dimensional differences significantly affected whether the parts could rotate into position, snap together, and remain properly constrained after assembly.

Rather than repeatedly printing the complete mount, I produced smaller test sections containing only the critical joint geometry.

<div class="image-grid">
  <img src="/assets/images/bike-light-mount/snap-test-prototype.jpg" alt="Small 3D printed prototype used to test snap joint">
  <img src="/assets/images/bike-light-mount/snap-final.jpg" alt="Final snap joint incorporated into handlebar clamp">
</div>
<p class="caption">Isolated joint prototype used to refine the snap-fit geometry before incorporating it into the complete assembly.</p>

## Preserving the Lamp's Angle Adjustment

The original headlamp contained indexed features that allowed the light to click between discrete aiming angles. I wanted to retain this functionality rather than replacing it with a fixed-angle mount.

I designed a compliant PETG tab that engages the lamp's existing indexing geometry. The first version was too flexible and susceptible to permanent deformation.

I iterated the feature by:

- increasing its section thickness,
- tapering the section toward the root to improve bending stiffness and distribute stress,
- maintaining enough compliance for repeated engagement with the lamp's indexed positions, and
- changing print orientation so the primary bending loads were carried within continuous printed layers rather than across weaker interlayer bonds.

<img class="project-image" src="/assets/images/bike-light-mount/detent-iterations.jpg" alt="Iterations of PETG angular detent tab">
<p class="caption">Iterations of the compliant indexing feature used to retain discrete lamp angles.</p>

This was an important design-for-additive-manufacturing consideration. FDM parts are anisotropic, so the geometry alone was not sufficient—the orientation of the part on the print bed directly influenced whether the compliant feature could survive repeated bending.

## Designing the Printed Structure

The mount was printed in **PETG** to provide greater toughness and compliance than a more brittle PLA prototype.

The structural bridge incorporates ribs and gussets to increase local stiffness without converting the entire component into a solid section. These features also allowed me to explore geometry more representative of a molded consumer product rather than relying entirely on thick additive-manufactured walls.

<img class="project-image" src="/assets/images/bike-light-mount/rib-detail.jpg" alt="Ribbed structural features on printed bicycle light mount">
<p class="caption">Ribbed bridge geometry provides local stiffness while exploring molded-part design principles.</p>

Threaded connections were created using heat-set inserts rather than relying on printed polymer threads. Early testing showed that insert-hole geometry and installation quality were critical: incorrectly installed inserts could pull out of the surrounding PETG.

I adjusted the insert holes and installation process to achieve more reliable retention before assembling the complete prototype.

<img class="project-image" src="/assets/images/bike-light-mount/heat-set-detail.jpg" alt="Heat set threaded insert installed in PETG bicycle light mount">
<p class="caption">Heat-set inserts provide reusable metal threads at the clamp fasteners.</p>

## Prototype Installation Exposed Real Packaging Constraints

Installing the assembly on the actual bicycle revealed geometry that was easy to underestimate in isolation.

The existing handlebar/stem hardware protrudes into the region occupied by the mount, and cables further constrain the available packaging space. The prototype therefore had to fit the real bicycle rather than an idealized cylindrical handlebar.

<img class="project-image" src="/assets/images/bike-light-mount/bike-installation.jpg" alt="Prototype bicycle mount installed around existing handlebar hardware">
<p class="caption">Physical installation exposed the true packaging environment around the handlebar, stem hardware, and cables.</p>

The clamp diameter also required iteration. Tightening the designed fit improved retention, but the combination of **smooth PETG against glossy painted steel** still created a low-friction interface.

Sanding the PETG contact surface substantially improved grip, confirming that interface friction—not simply structural stiffness—was a significant contributor to rotation of the assembly.

The current prototype remains secure during normal use, although sufficient externally applied torque can still rotate the mount around the handlebar. This remains one of the primary areas identified for the next iteration.

## Functional Prototype

The first complete assembly validated the core architecture:

- the lamp mounts securely enough for real bicycle testing,
- indexed angle adjustment is retained,
- the lamp can be removed from the bicycle without tools,
- the T-style slider repeatedly installs and removes as intended,
- integrated locating joints reduce the system to two clamp fasteners, and
- the complete assembly packages around the actual bicycle controls and hardware.

<img class="project-image" src="/assets/images/bike-light-mount/final-installed.jpg" alt="Completed LED bicycle light mount installed on bicycle">
<p class="caption">Completed Iteration 1 assembly with the rechargeable LED installed.</p>

<img class="project-image" src="/assets/images/bike-light-mount/night-riding.gif" alt="Bicycle light mount operating while bicycle is being ridden at night">
<p class="caption">Functional testing of the mounted LED during bicycle operation.</p>

## What I Learned

Although the product initially appeared to be a relatively simple mounting problem, physical prototyping exposed several interacting mechanical considerations: snap-fit tolerances, compliant-feature stiffness, FDM anisotropy, threaded insert retention, sliding-fit clearances, clamp friction, packaging constraints, assembly sequence, and user serviceability.

The project reinforced the value of using prototypes not simply to confirm that a CAD model can be manufactured, but to discover assumptions that are difficult to capture before the part interacts with the real system.

## Current Status and Next Steps

**Iteration 1 is functional and has been tested on the bicycle.** The main architecture will be retained, while future work will focus on refining rather than replacing the concept.

Planned next steps include:

- increasing friction at the handlebar interface, potentially through an elastomeric liner or integrated high-friction surface,
- refining the clamp diameter and preload,
- further tuning the snap-fit and indexing features for repeatable assembly,
- performing structural FEA on the complete load path and critical compliant features,
- using the analysis to remove unnecessary material from low-stress regions, and
- further developing the geometry toward manufacturable molded-part design practices.

The next iteration will use the lessons from physical testing to reduce mass, improve retention, and refine the product while preserving the removable two-fastener architecture demonstrated by the first prototype.

</div>

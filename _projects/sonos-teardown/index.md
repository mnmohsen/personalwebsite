---
layout: post
title: Lever-Driven Reset for a Magnetic Launcher
description: Designed and bench-tested a lever-driven reset mechanism for the Ann Arbor Hands-On Museum, integrating a dual-purpose spring-steel plate, friction clamp, and serviceable wheeled carriage.
skills:
  - Mechanism Design
  - SolidWorks
  - Rapid Prototyping
  - Experimental Testing
  - Design for Manufacturability
  - Design for Maintainability

main-image: /AAHOM_logo.jpg

---

## The Challenge

A magnetic launcher accelerates steel balls through successive magnet stages. Resetting it requires separating the balls from those magnets, an awkward task for children using a museum exhibit.

For the Ann Arbor Hands-On Museum, **I designed, built, and bench-tested a lever-driven reset mechanism**, alongside launcher and impact-shield prototyping. My responsibility covers the lever, linkage, plate attachment, and carriage. The design must make reset intuitive while allowing museum staff to service parts subjected to repeated use.

## Turning a Handle Motion into Ball Separation

My first reset design used a handwheel and power screw to translate the plate carriage. We built and tested it, but the screw-driven motion made the moment of magnetic separation difficult to feel. Because that interaction is part of the exhibit's educational purpose, I moved to lever actuation to give users a more direct sense of the magnetic resistance.

I designed the lever and connecting linkage in SolidWorks to move spring-steel separator plates along the track. The lever provides mechanical advantage, while the connecting rods transmit motion to the reset carriages. This gives the visitor one handle to operate instead of pulling directly against the magnets.

I built and tested the lever-and-plate mechanism, demonstrating that the plate could separate the ball from the permanent magnet. That bench work informed both the carriage redesign and the way the plate is attached.

Handle length controls the tradeoff between input force and handle travel. We will compare lengths at the museum to assess which feels comfortable and intuitive for children.

## Giving the Spring-Steel Plate Two Jobs

I developed the plate to **protect the magnet during launch and separate the ball during reset**. A replaceable strip takes the repeated ball impacts, while its integration into the carriage makes it part of the reset mechanism.

I compared spring-steel shield configurations through physical testing. A shorter configuration showed the most promising balance of launch performance and durability in those tests.

<img src="/assets/images/platetesting.png" alt="Physical testing of spring-steel impact shield configurations" style="width:100%; max-height:460px; object-fit:contain; margin: 20px 0;">

<div style="text-align:center; margin: 20px 0;">
  <img src="/assets/images/poc_platefull.gif" alt="Early handheld test of the spring-steel plate separating a ball from a magnet" style="max-width:800px; width:100%; height:auto;">
  <p><em>Early separation testing established the plate concept used in the lever mechanism.</em></p>
</div>

I then designed a **friction clamp** to retain the strip without drilling through hardened spring steel. This eliminates a difficult fabrication step and allows the plate to be replaced without fasteners passing through it.

## Making Wear Parts Easier to Replace

I redesigned the shaft-guided carriage around a **two-level 80/20 track**. The upper level carries the balls and magnets; the lower level guides the reset carriage on wheels.

The change replaces sliding contact at the carriage with rolling contact. My intent is to concentrate routine wear in replaceable wheels, making maintenance less involved than replacing a worn carriage. I am currently building this revision.

<div style="display:flex; flex-wrap:wrap; gap:20px; justify-content:center; margin:20px 0;">
  <div style="flex:1 1 280px; min-width:0; text-align:center;">
    <img src="/assets/images/mdp-lever-shaft-concept.png" alt="Earlier lever reset design with a carriage guided by two shafts" style="width:100%; max-height:460px; object-fit:contain;">
    <p><em>Earlier shaft-guided carriage.</em></p>
  </div>
  <div style="flex:1 1 280px; min-width:0; text-align:center;">
    <img src="/assets/images/mdp-wheeled-reset.png" alt="Redesigned lever reset with a wheeled carriage on the lower level of an 80/20 track" style="width:100%; max-height:460px; object-fit:contain;">
    <p><em>Current wheeled carriage and two-level track.</em></p>
  </div>
</div>

## Supporting the Launcher Design

I also helped build and test permanent-magnet launcher prototypes to investigate magnet spacing, ball spacing, and track constraints. Our team selected permanent magnets to keep the launch sequence visible and avoid the powered controls and thermal management associated with electromagnets.

<img src="/assets/images/permalauncher.png" alt="Permanent-magnet launcher prototype showing the magnet, impact surface, and ball path" style="width:100%; max-height:460px; object-fit:contain; margin: 20px 0;">

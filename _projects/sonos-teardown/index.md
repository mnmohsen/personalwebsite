---
layout: post
title: Lever-Driven Reset for a Magnetic Launcher
description: Designed and bench-tested a lever-driven reset mechanism for the Ann Arbor Hands-On Museum, with a dual-purpose spring-steel plate, friction clamp, and redesigned wheeled carriage.
skills:
  - Mechanism Design
  - SolidWorks
  - Rapid Prototyping
  - Experimental Testing
  - Design for Manufacturability
  - Design for Maintainability

main-image: /AAHOM_logo.jpg

---

## Making a Magnetic Museum Exhibit Easier to Reset

A steel ball rolls toward a permanent magnet, accelerates, and strikes it. The collision transfers momentum through the magnet and the balls touching its opposite side, launching the outermost ball down the track. Repeating this process through multiple stages increases the outgoing ball's speed.

Our team is adapting this magnetic launcher into a hands-on exhibit for the Ann Arbor Hands-On Museum, letting children see and feel magnetic forces in action.

<div style="display: flex; justify-content: center; margin: 20px 0;">
  {% include youtube-video.html id="A5auE6Idx-g" autoplay="false" width="500px" %}
</div>
<p style="text-align:center;"><em>Launcher prototype demonstrating the magnetic acceleration and collision sequence.</em></p>

**The challenge is resetting it:** after a launch, steel balls remain strongly attracted to the magnets. Children need a simple way to separate and reposition them for another turn.

**I designed, built, and tested a lever-driven reset mechanism**, owning the lever, linkage, carriage, and spring-steel plate attachment. My work focuses on making that interaction intuitive while keeping wear components easy for museum staff to replace.

## Current Design: A Wheeled Reset Carriage

My latest design combines the lever mechanism with a **two-level 80/20 track**. The upper level supports the balls and magnets; the lower level guides the reset carriage on wheels.

I replaced the earlier sliding-shaft arrangement with rolling contact to improve carriage motion and concentrate routine wear in replaceable wheels. I also designed a **friction clamp** that holds the spring-steel plate without drilling through it, simplifying fabrication and replacement. I am currently building this revision.

<img src="/assets/images/mdp-wheeled-reset.png" alt="Current lever reset design with a wheeled carriage, two-level track, and spring-steel plate attachment" style="width:100%; max-height:460px; object-fit:contain; margin: 20px 0;">
<p><em>Current design: the upper track carries the launch components while the lower track guides the wheeled carriage.</em></p>

## Building and Testing the Lever Mechanism

I developed the lever and connecting linkage in SolidWorks to move the separator plates along the launcher. The lever provides mechanical advantage, and the connecting rods transmit handle motion to the reset carriages.

I built and bench-tested the lever-and-plate mechanism, demonstrating separation of the ball from the permanent magnet. That testing informed the carriage and plate-mounting changes in the current design.

<div style="display: flex; justify-content: center; margin: 20px 0;">
  {% include youtube-video.html id="1jsW6OI1SYc" autoplay="false" width="500px" %}
</div>
<p style="text-align:center;"><em>Bench test of the lever-driven plate separation mechanism.</em></p>

<img src="/assets/images/mdp-lever-shaft-concept.png" alt="Earlier lever-and-linkage design with a carriage guided by two shafts" style="width:100%; max-height:460px; object-fit:contain; margin: 20px 0;">
<p><em>Earlier shaft-guided design, before the move to the wheeled carriage shown above.</em></p>

Handle length affects both input force and travel. Planned museum trials will compare lever lengths to assess comfort and ease of operation for children.

## One Plate, Two Functions

I developed a replaceable spring-steel plate to **protect the magnet during launch and separate the ball during reset**. This lets one component handle repeated impacts and provide the contact surface for the reset mechanism.

I compared shield configurations through physical testing. A shorter configuration showed the most promising balance of launch performance and durability in those tests. Early handheld separation experiments then established the concept I incorporated into the lever assembly.

<div style="text-align:center; margin: 20px 0;">
  <img src="/assets/images/poc_platefull.gif" alt="Early handheld test of the spring-steel plate separating a ball from a magnet" style="max-width:800px; width:100%; height:auto;">
  <p><em>Early testing of the plate's separation function.</em></p>
</div>

## Earlier Iteration: Learning from the Power Screw

My first reset design used a handwheel and power screw to translate the plate carriage. We built and tested it, but the screw-driven motion made magnetic separation difficult to feel.

That feedback changed the design direction. I moved to lever actuation to give visitors a more direct sense of magnetic resistance while retaining mechanical advantage.

<img src="/assets/images/whiteboard.png" alt="Early reset mechanism concept sketches" style="width:100%; max-height:300px; object-fit:contain; margin: 20px 0;">

<div style="display: flex; justify-content: center; margin: 20px 0;">
  {% include youtube-video.html id="mnxXMfzArDM" autoplay="false" width="900px" %}
</div>

## Launcher Development

Alongside the reset work, I helped build and test permanent-magnet launcher prototypes, investigating magnet spacing, ball spacing, and track constraints. Our team selected permanent magnets to preserve the visible launch sequence while avoiding powered controls and thermal-management requirements.

<img src="/assets/images/permalauncher.png" alt="Permanent-magnet launcher prototype showing the magnet, impact surface, and ball path" style="width:100%; max-height:460px; object-fit:contain; margin: 20px 0;">

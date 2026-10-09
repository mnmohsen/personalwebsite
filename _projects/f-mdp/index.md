---
layout: post
title: Multidisciplinary Design Program
description: Designed, built, and tested a lever-driven reset mechanism for the Ann Arbor Hands-On Museum, refining carriage guidance and separator-plate material to improve motion and reduce operating effort.
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

Our team is developing a hands-on magnetic launcher for the Ann Arbor Hands-On Museum. A steel ball accelerates toward a permanent magnet and collides with it, transferring momentum through the magnet and the balls touching its opposite side. The outermost ball launches down the track, with successive stages demonstrating how magnetic attraction can increase its speed.

**The challenge is resetting it:** the balls remain strongly attracted to the magnets after a launch. **I designed, built, and tested a lever-driven reset mechanism**, owning the lever, linkage, carriage, and separator-plate attachment to make that interaction easier for children and simpler to maintain.

<img src="/assets/images/mdp-bearing-pad-reset.png" alt="Latest lever-driven reset assembly with a two-level 80/20 track, bearing-pad carriage, and stainless-steel separator plate" style="width:100%; max-height:600px; object-fit:contain; margin:20px 0;">
<p><em>Latest assembly: the lever and linkage move the separator carriage beneath the launch track.</em></p>

<div style="display:flex; justify-content:center; margin:20px 0;">
  {% include youtube-video.html id="NEW_RESET_VIDEO_ID" autoplay="false" width="700px" %}
</div>
<p style="text-align:center;"><em>Bench demonstration of the latest reset mechanism with bearing-pad guidance and the selected stainless-steel plate.</em></p>

## Smoother Motion with Bearing Pads

The current design uses a **two-level 80/20 track**: the upper level supports the balls and magnets, while the lower level guides the reset carriage. The lever provides mechanical advantage, and connecting rods transmit handle motion to the carriage.

Testing the wheeled version revealed that wheel alignment was difficult to maintain and the wheels often slid instead of rolling. I replaced them with **80/20 bearing pads**, which provided smoother travel with little added resistance and a more rigid carriage in bench testing.

## A Plate That Protects and Releases

The separator plate serves two functions: **protecting the magnet during launch and separating the ball during reset**. The earlier spring-steel strip separated the ball from the magnet, but residual magnetic attraction left the ball sticking to the plate.

I tested **0.015-, 0.024-, and 0.029-inch full-hard 301 stainless-steel strips**, selecting the **0.024-inch thickness** for the current mechanism. In testing, the selected plate released the ball without the sticking seen with the earlier strip and made the lever noticeably easier to pull.

My **friction clamp** retains the plate without drilling through the hardened sheet, simplifying fabrication and allowing the strip to be replaced independently of the carriage.

## Developing the Lever Reset

I developed the lever and connecting linkage in SolidWorks, then built a prototype to test plate separation. That bench work established the lever actuation and guided the later changes to carriage guidance and plate material.

<div style="display:flex; justify-content:center; margin:20px 0;">
  {% include youtube-video.html id="1jsW6OI1SYc" autoplay="false" width="500px" %}
</div>
<p style="text-align:center;"><em>Earlier lever prototype demonstrating separation of the ball from the magnet.</em></p>

<div style="display:grid; grid-template-columns:repeat(auto-fit,minmax(250px,1fr)); gap:20px; align-items:start; margin:24px 0;">
  <div>
    <img src="/assets/images/resetmechanismdiagram2.png" alt="Earlier lever reset concept using two guide shafts" style="width:100%; height:300px; object-fit:contain;">
    <p><em>Initial shaft-guided carriage concept.</em></p>
  </div>
  <div>
    <img src="/assets/images/mdp-wheeled-reset.png" alt="Intermediate wheeled carriage concept on the two-level 80/20 track" style="width:100%; height:300px; object-fit:contain;">
    <p><em>Intermediate wheeled design, followed by the bearing-pad revision shown above.</em></p>
  </div>
</div>

Handle length affects both input force and travel. Planned museum trials will compare lever lengths to assess comfort and ease of operation for children.

## Earlier Iteration: From Power Screw to Lever

My first reset design used a handwheel and power screw to translate the plate carriage. We built and tested it, but the screw-driven motion made magnetic separation difficult to feel. I moved to lever actuation to give visitors a more direct sense of magnetic resistance while retaining mechanical advantage.

<div style="display:flex; justify-content:center; margin:20px 0;">
  {% include youtube-video.html id="mnxXMfzArDM" autoplay="false" width="900px" %}
</div>
<p style="text-align:center;"><em>Earlier power-screw reset prototype.</em></p>

## Launcher Development

Alongside the reset mechanism, I helped build and test permanent-magnet launcher prototypes, investigating magnet spacing, ball spacing, and track constraints. Our team selected permanent magnets to keep the acceleration and collision sequence visible without powered controls.

<div style="display:flex; justify-content:center; margin:20px 0;">
  {% include youtube-video.html id="A5auE6Idx-g" autoplay="false" width="500px" %}
</div>
<p style="text-align:center;"><em>Early launcher testing demonstrating the magnetic acceleration and collision sequence.</em></p>

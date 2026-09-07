---
layout: post
title: Methode Electronics
description: Mechanical and thermal redesign, prototype development, debugging, and validation of a high-intensity LED vehicle spotlight.
skills:
  - Mechanical Design
  - Product Development
  - CATIA V5
  - Thermal Management
  - Design for Manufacturing
  - Prototype Development
  - Thermal Testing
  - Photometric Validation
  - Electrical Debugging
  - Supplier Coordination
  - Design Iteration

main-image: /methode_2.png
---

<style>
.methode-project h2 {
  font-size: 2rem !important;
  font-weight: 700 !important;
  line-height: 1.2 !important;
  margin: 2.4rem 0 1rem !important;
}

.methode-project h3 {
  font-size: 1.5rem !important;
  font-weight: 700 !important;
  line-height: 1.25 !important;
  margin: 2rem 0 0.8rem !important;
}

.methode-project ul,
.methode-project ol {
  margin-top: 0.65rem !important;
  margin-bottom: 1.25rem !important;
  padding-left: 1.5rem !important;
}

.methode-project li {
  font-size: 1.08rem !important;
  line-height: 1.5 !important;
  margin: 0.18rem 0 !important;
}
</style>

<div class="methode-project" markdown="1">

## LED Vehicle Spotlight Product Development

As a Product Development Engineering Intern at Methode Electronics, I worked on the redesign and validation of a high-intensity LED vehicle spotlight.

I had substantial ownership across the development cycle, including mechanical and thermal architecture, CATIA design, DFM, prototype sourcing, hardware debugging, thermal testing, photometric validation, and design iteration.

## Product Context

<div style="display:grid; grid-template-columns:repeat(auto-fit,minmax(280px,1fr)); gap:18px; align-items:start; margin:24px 0;">

  <div>
    <img src="/assets/images/spotlight_assy.jpg"
         alt="Unity vehicle spotlight assembly showing handle, shaft, and spotlight head"
         style="width:100%; height:340px; object-fit:contain;">

    <p style="font-size:12px; color:#666; margin-top:6px;">
      Unity vehicle spotlight assembly.
      <a href="https://www.unityusa.com/assets/images/335V-00026inSpotlight-LED-BlackHead.jpg"
         target="_blank">
        Image: Unity Manufacturing Co.
      </a>
    </p>
  </div>

  <div>
    <img src="/assets/images/Tremor_Spot.jpg"
         alt="Vehicle-mounted spotlight installed near the driver's A-pillar"
         style="width:100%; height:340px; object-fit:cover;">

    <p style="font-size:12px; color:#666; margin-top:6px;">
      Example of a vehicle spotlight installed near the driver's A-pillar.
      <a href="https://www.texasfleetgear.com/Tremor_Spot.JPG"
         target="_blank">
        Image: Texas Fleet Gear
      </a>
    </p>
  </div>

</div>

<p style="font-size:14px; line-height:1.5; margin-top:8px;">
  <strong>Product context only:</strong> These publicly available Unity spotlight images illustrate the type of driver-operated vehicle spotlight discussed in this project and the competitive product category I was benchmarking against. They do not depict my Methode design. Proprietary CAD, hardware photos, drawings, dimensions, and internal product details are intentionally omitted.
</p>

### Results

- redesigned the product around an integrated aluminum structural and thermal architecture
- reduced assembly mass while improving thermal performance
- achieved approximately **46% lower PCB operating temperature** during prototype testing
- diagnosed and resolved unstable LED operation during hardware bring-up
- demonstrated greater than **200,000 cd** peak optical intensity
- supported the design from concept and CAD through prototype manufacturing and physical validation

## What I Owned

My work included:

- mechanical architecture and packaging development in CATIA V5
- housing and thermal-path redesign
- ribbing, interfaces, fastener access, coatings, and production-oriented DFM
- thermal-interface design and heat-transfer evaluation
- prototype supplier coordination
- thermal testing and design iteration
- LED driver troubleshooting during prototype bring-up
- photometric testing and beam-performance evaluation
- integration of mechanical, thermal, electrical, optical, and manufacturing requirements

## Mechanical & Thermal Redesign

The existing product architecture separated the primary structural enclosure and heat-rejection functions.

I redesigned the concept around an aluminum housing that could perform both roles, creating a more direct thermal path from the LED assembly into the exterior structure while reducing mass and component complexity.

The design also had to remain practical to manufacture, requiring tradeoffs between thermal performance, structural stiffness, casting-oriented geometry, exterior regulatory requirements, coatings, assembly access, and surrounding optical and electrical hardware.

<div style="text-align:center; margin:28px 0;">
  <div style="font-size:1.05rem; line-height:2;">
    <strong>LED / PCB</strong>
    &nbsp;→&nbsp;
    <strong>Thermal Interface</strong>
    &nbsp;→&nbsp;
    <strong>Aluminum Housing</strong>
    &nbsp;→&nbsp;
    <strong>Ambient</strong>
  </div>

  <p style="font-size:12px; color:#666; margin-top:8px;">
    Simplified system-level thermal path. Proprietary geometry is intentionally not shown.
  </p>
</div>

## Prototype Bring-Up & Validation

The project continued beyond CAD into physical hardware.

During prototype bring-up, I investigated unstable LED output and traced the issue into the driver current-setting circuit. After correcting the configuration, the hardware operated stably and could proceed through thermal and photometric evaluation.

Testing showed a substantial reduction in PCB operating temperature while maintaining the high optical intensity required of the spotlight.

## Engineering Outcome

The project required treating the spotlight as a coupled mechanical, thermal, electrical, optical, and manufacturing system rather than optimizing any one discipline in isolation.

My work spanned the full development loop:

**architecture → CAD → DFM → prototype → debug → test → iteration**

</div>

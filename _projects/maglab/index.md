---
layout: post
title: UAV Magnetometer Interference Reduction Research
description: NASA-funded sensor system integration and experimental validation exploring compact alternatives to conventional drone magnetometer architectures.
skills:
  - Hardware Integration
  - Sensor Systems
  - MATLAB
  - Python
  - Raspberry Pi
  - Signal Processing
  - Experimental Validation
  - Data Acquisition
  - Embedded Systems
  - Test Engineering

main-image: /magbanner.png
---

## Overview

As part of a NASA-funded undergraduate research project in the University of Michigan Magnetometer Laboratory, I worked on improving drone-based magnetic field measurements by exploring alternatives to conventional boom-mounted magnetometer systems.

Traditional drone magnetometer setups physically separate the sensor from the aircraft using long booms to reduce electromagnetic interference from motors and onboard electronics. While effective, this approach increases mechanical complexity, transport difficulty, weight, and system cost.

Our goal was to investigate whether a more compact body-mounted sensing architecture could become viable through better interference characterization and signal filtering.

This project gave me hands-on experience in hardware integration, experimental test design, sensing systems, and engineering validation.

## The Engineering Problem

Magnetometers are extremely sensitive instruments designed to detect weak magnetic fields.

That sensitivity becomes a challenge when mounted directly to a drone, where brushless motors, ESCs, and onboard electronics generate electromagnetic interference that contaminates measurements.

The conventional engineering solution is mechanical separation: physically move the sensor farther away.

This project explored a different approach.

Instead of avoiding interference purely through mechanical design, we investigated whether better understanding and characterization of the interference could make a simpler sensing architecture practical.

This created an interesting systems engineering tradeoff between hardware complexity and analytical compensation.

## Sensor Integration and Early Validation

A major part of my work involved helping integrate sensing hardware and validating data acquisition behavior before full field testing.

Early testing involved a single PNI magnetometer setup used for calibration and baseline characterization in a controlled environment.

<img src="/assets/images/pni-test-bed.png" alt="Single magnetometer calibration test setup" style="width:100%; max-height:500px; object-fit:contain; margin: 20px 0;">

<p style="font-size: 12px; color: #666; margin-top: 0;">
Early indoor validation setup used for sensor calibration and baseline magnetic characterization.
</p>

This phase was important for establishing confidence in the measurement pipeline before scaling to the full experimental configuration.

## Quad-Magnetometer Experimental Testing

After early validation, the project scaled to a quad-magnetometer sensing system integrated with Raspberry Pi-based synchronized acquisition hardware.

This full setup enabled synchronized magnetic field data collection at 100 Hz during drone interference testing.

<img src="/assets/images/quadmag-test-bed.png" alt="Quad magnetometer drone test setup" style="width:100%; max-height:550px; object-fit:contain; margin: 20px 0;">

<p style="font-size: 12px; color: #666; margin-top: 0;">
Outdoor experimental setup used to characterize drone-induced magnetic interference using the quad-magnetometer platform.
</p>

This phase moved the work from controlled validation into realistic operating conditions where environmental noise, propulsion behavior, and practical testing constraints became part of the engineering challenge.

## Analysis and Experimental Findings

Using MATLAB and Python, I analyzed 37 flight datasets comparing powered and unpowered operating conditions.

Power spectral density analysis revealed distinct frequency-domain interference signatures associated with drone propulsion electronics.

These findings helped determine whether signal filtering could realistically improve measurement quality enough to reduce reliance on mechanically cumbersome boom-mounted architectures.

The most valuable lesson from this work was understanding that solving engineering measurement problems often requires both hardware and analytical solutions.

Mechanical separation solves the problem physically.

Signal analysis solves the problem computationally.

Good engineering comes from understanding when each approach makes sense.

## Research Poster

This work was presented through the University of Michigan Undergraduate Research Opportunity Program.

<img src="/assets/images/magnetometer-poster.png" alt="UAV magnetometer research poster" style="width:100%; margin: 20px 0;">

## What I Contributed

My contributions included:

- sensor hardware integration
- validation test setup support
- quad-magnetometer system integration
- Raspberry Pi synchronized acquisition integration
- MATLAB and Python signal analysis
- power spectral density analysis
- experimental dataset interpretation
- feasibility evaluation of compact sensing architectures

## Key Takeaways

This project broadened my engineering perspective beyond purely mechanical systems.

It reinforced how sensing hardware, embedded systems, testing methodology, and data analysis all interact when building real engineering systems.

That systems-level mindset translates directly to hardware product development, where clean design rarely comes from a single discipline alone.

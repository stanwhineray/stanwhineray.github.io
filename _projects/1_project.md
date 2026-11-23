---
layout: page
title: Power Management System
description: v1.0 & v2.0 for ARES Rocketry's Project Odyssey
img: assets/img/PMB-v2-Front.png
importance: 1
category: Personal / Rocketry
related_publications: false
---

The Power Management System (PMS) is a 4-layer PCB that powers the avionics stack on ARES Rocketry's Project Odyssey. It steps a 2–4S LiPo battery down to the rails the flight electronics need and supplies a 6A avionics stack, including pyro events. The board is tightly size, weight and power (SWaP) constrained. I designed the board, debugged the v1.0 bring-up, and carried the fixes into v2.0.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/PMB-v2-Front.png" title="PMS v2.0 front" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/PMB-v2-Back.png" title="PMS v2.0 back" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Power Management System v2.0, front and back.
</div>

## Design

- **Battery monitoring:** an INA229 (20-bit, SPI) measures battery voltage and current.
- **Launch switchover:** a TPS2121 power mux switches over automatically at launch on the 20V, 6A system, configured using a Zener diode.
- **Regulation:** the 5V and 3.3V rails moved from an MP28167 and TPS62160 in v1.0 to a TPS55285 and TLVM13640 in v2.0 for higher current capacity.
- **Usability:** v2.0 added output switching, mux-bypass and reset jumpers, power-good LEDs, USB-C programming and spare GPIOs.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/PMB-v2-3DModel.png" title="PMS v2.0 3D model" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    3D model of v2.0.
</div>

## v1.0 bring-up and fixes

Bring-up of v1.0 hit over-current faults. I traced them to inrush current caused by insufficient soft-start capacitance, and v2.0 fixes this. v1.0 also had a pin-mapping error on the SPI lines. I worked around it with PIO-based SPI so the board could still be tested, then restored the hardware SPI pinout in v2.0.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/PMB-v1-Front.png" title="PMS v1.0 front" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/PMB-v1-3DModel.png" title="PMS v1.0 3D model" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Power Management System v1.0: the assembled board and its 3D model.
</div>

## Documentation

I wrote a 7,000-word design report covering topology selection, subsystem design and an FMEA. It's now the standard for design reports at ARES.
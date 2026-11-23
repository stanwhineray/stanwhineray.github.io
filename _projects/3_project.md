---
layout: page
title: ASK/OOK Communication System
description: Analogue modulation and demodulation link, validated to 50 kbps
img: assets/img/ASK-comms.png
importance: 2
category: University
related_publications: false
---

An on-off keying (OOK) link, the simplest form of amplitude-shift keying (ASK), designed and built from discrete analogue parts. The transmitter switches a carrier on and off with a MOSFET, and the receiver recovers the data using envelope detection.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/ASK-comms.png" title="ASK/OOK system" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    The ASK/OOK modulation and demodulation system.
</div>

## Overview

- **Modulation:** MOSFET-switched carrier.
- **Demodulation:** envelope detection.
- **Result:** validated to 50 kbps while staying within spec.

I built and tested the full prototype on breadboard and documented the design and test results in a detailed report.

**Skills:** analogue electronics, signal processing, circuit prototyping and test.
---
title: "DNA/RNA & UV                            "
layout: post
date: 2025-01-20
tags: []
author: Dylan Costo
description: "Does lab UV Exposure render DNA useless for amplification? We test varying amounts of UV exposure on unprotected purified DNA."
---

## Background

DNA & RNA is highly sensitive to ultraviolet (UV) radiation, In the lab, the most common form of UV is UV-C (100-280 nm). UV-C damages RNA primarly through pyrimidine dimer formation, crosslinking, photooxidation, and breaks in the strands. While useful for some applications, like inactivation and CLIP-seq, researchers should excersize caution when exposing nucelic acids to UV. 

But how damaging is it really? Let's find out. 

## Experimental Design

10 ul of a synthetic positve (PC) and a human control (HC) were exposed to 4 hours of UV-C. 

10 ul of PC and HC onto parafilm, direct UV-C exposure
10 ul of PC and HC in polyporpylene microcentrifuge tubes, direct UV-C exposure
10 ul of PC and HC in polyporpylene microcentrifuge tubes, no UV-C exposure 

## UV-C Exposure Calculations 

### UV-C dose estimate (25 W, 254 nm lamp, 1 ft distance, 45 ° incidence)

| Parameter | Value | Notes |
|-----------|-------|-------|
| Lamp electrical rating | **25 W** |
| Typical germicidal UV-C output | **≈ 8 W** |
| Lamp length (T5 tube) | **0.56 m** |
| Distance to sample | **0.305 m** |
| Incidence angle | **45 °** (effective irradiance scaled by \(\cos45^{\circ}\)) |

#### 1. Power per unit length  
\[
P_L \;=\; \frac{P_{\text{UVC}}}{L}
     \;=\; \frac{8\ \text{W}}{0.556\ \text{m}}
     \;=\; 14.4\ \text{W·m}^{-1}
\]

#### 2. Irradiance at 0.305 m (line-source model)  
\[
E_{\text{normal}} \;=\;
\frac{P_L}{2\pi r}
=\frac{14.4}{2\pi \times 0.3048}
\approx 7.51\ \text{W·m}^{-2}
= 0.751\ \text{mW·cm}^{-2}
\]

#### 3. Correct for 45 ° incidence  
\[
E_{\text{effective}} \;=\;
E_{\text{normal}}\cos45^{\circ}
\approx 0.751 \times 0.707
\approx 0.53\ \text{mW·cm}^{-2}
\]

#### 4. Dose vs. exposure time  

| Time | Dose \(E \times t\) |
|------|--------------------|
| 1 min | 32 mJ cm\(^{-2}\) |
| 2 min | 64 mJ cm\(^{-2}\) |
| 5 min | 159 mJ cm\(^{-2}\) |
| 10 min| 319 mJ cm\(^{-2}\) |

> **Note:** For critical work verify actual irradiance with a UV-C radiometer; lamp output can vary ±25 %.



### Protective Mechanisms

Organisms have evolved repair mechanisms, such as nucleotide excision repair, to counteract UV damage.

---
title: "RNA & UV                            "
layout: post
usemathjax: true
date: 2025-01-20
tags: []
author: Dylan Costo
description: "Does lab UV Exposure render DNA useless for amplification? We test varying amounts of UV exposure on unprotected purified DNA."
---

## Background

DNA & RNA is highly sensitive to ultraviolet (UV) radiation, In the lab, the most common form of UV is UV-C (100-280 nm). UV-C damages DNA/RNA primarly through pyrimidine dimer formation, crosslinking, photooxidation, and breaks in the strands. While useful for some applications, like inactivation and CLIP-seq, researchers should excersize caution when exposing nucelic acids to UV.

But how damaging is it really? Let's find out by amplyfing common RNA targets in viruses and humans. 

## Experimental Design

10 ul of a synthetic RNA positve (PC) and a human RnaseP control (HC) were exposed to 1 hour of UV-C. 

1. **10 ul of PC and HC onto parafilm, direct UV-C exposure**
2. **10 ul of PC and HC in polypropylene microcentrifuge tubes, direct UV-C exposure**
3. **10 ul of PC and HC in polypropylene microcentrifuge tubes, no UV-C exposure**

After exposure, samples were run on the thermocyler for 45 cycles with a 15 minute RT step. 

## UV-C Exposure Calculations 

### UV-C dose estimate (25 W, 254 nm lamp, 1 ft distance, 45 ° incidence)

| Parameter | Value | 
|-----------|-------|
| Lamp electrical rating | **25 W** |
| Typical germicidal UV-C output | **≈ 8 W** |
| Lamp length (T5 tube) | **0.56 m** |
| Distance to sample | **0.305 m** |
| Incidence angle | **45 °** |

---

#### 1. Power per unit length  

$$
P_L \;=\; \frac{P_{\text{UVC}}}{L}
       \;=\; \frac{8\ \text{W}}{0.556\ \text{m}}
       \;=\; 14.4\ \text{W}\!\cdot\!\text{m}^{-1}
$$

#### 2. Irradiance at 0.305 m (line-source model)  

$$
E_{\text{normal}}
  \;=\; \frac{P_L}{2\pi r}
  \;=\; \frac{14.4}{2\pi \times 0.3048}
  \;\approx\; 7.51\ \text{W}\,\text{m}^{-2}
  \;=\; 0.751\ \text{mW}\,\text{cm}^{-2}
$$

#### 3. Correct for 45 ° incidence  

$$
E_{\text{effective}}
  \;=\; E_{\text{normal}} \cos 45^{\circ}
  \;\approx\; 0.751 \times 0.707
  \;\approx\; 0.53\ \text{mW}\,\text{cm}^{-2}
$$

#### 4. Dose vs. exposure time  

| Time | Dose \(E \times t\) |
|------|--------------------|
| 1 min | 32 mJ cm\(^{-2}\) |
| 10 min| 319 mJ cm\(^{-2}\) |
| 60 min| 1,914 mJ cm\(^{-2}\) |

> **Note:** Back-of-the-envelope estimate—verify actual irradiance with a calibrated UV-C radiometer; lamp output can vary ± 25 %.





### Results

Ct values:


| Samples exposed to UV-C for 1 hour                                                      | FAM  | Quasar 670 | Orange 560 | Red 610 |
|--------------------------------------------------------------|------|-----------|------------|---------|
| **Synthetic RNA – Control**                                  | 32.22 | 29.51 | 26.17 | 23.81 | 
| **Synthetic RNA – UV-exposed**                               | 35.21 | 31.02 | 28.32 | 26.79 |
| **Synthetic RNA – UV-exposed in PP microcentrifuge tube**    | 34.99 | 31.27 | 28.24 | 26.55 |
| **Human RNase P – Control**                                  | N/A  | N/A  | N/A  | 30.53 |
| **Human RNase P – UV-exposed in PP microcentrifuge tube**    | N/A  | N/A  | N/A  | 31.53 |
| **Human RNase P – UV-exposed**                               | N/A  | N/A  | N/A  | 34.95 |


Results are suprising, for one, it's expected that high dose UV-C would certainly render RNA useless for amplification, but we can see that an hour of exposure, ct increased by approximately 3 for both the synthetic and human control. 

Equally suprising, the polypropylene tubes did not offer much protection against the UV-C. In theory, PP should block the majority of UV-C, but the shielding factor may be much less than anticipated. 

The synthetic control is theoretically expected to perform better and maintain a lower ct relative to the control due to the short and high-copy transcript supplied. We can see that it did perform better, but it's unclear if the buffer solution used would help reduce the amount of UV lesions per molecule. 

Interestingly, you can see that the human control RNA, when exposed to direct UV-C without shielding, does not follow a conventional exponential and platoe curve. This could be caused by a decrease in effective intact copy number preventing it from exponentiating cleanly. 

## UV Dose Curve
![UV Ct Curve]({{ "/assets/images/UV-DNA_Curve.png" | relative_url }})



### Conclusion

Direct exposure to high intensity UV-C did not prevent amplification for both the direct UV-exposed RNA, or the RNA stored in PP microcentrifuge tubes. The UV-C did increase Ct by approximately 3-4 cycles in both the synthetic and human RNA control. 




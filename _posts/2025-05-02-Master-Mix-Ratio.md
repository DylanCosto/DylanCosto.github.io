---
title: "Master Mix Ratios                            "
layout: post
usemathjax: true
date: 2025-01-20
tags: []
author: Dylan Costo
description: "How much master mix do you really need in your reactions?."
---

## Background

Master Mix is a carefully balanced pre-prepared solution that contains most of the components needed for PCR, these include 

- **DNA Polymerase : 5U/µL**
- **dTNPs : 200 µM**
- **MgCl : 1.5–2.5 mM**
- **Buffer : 1X**
- **Stabilizers and enhancers**

Most manufactures have their own guidelines of stoichiometric ratios for their respective master mix. But how much can these ratios be manipulated with while maintaining good results? Theoretically, too much MM can inhibit Taq, amplify non-specific products, and increase error rates. Too little MM can stall synthesis via insufficient dNTPs, poor enzyme activity, not enough primer or probe, suboptimal salt conditions, and so on. 

Let's find out what happens when we modify these ratios past manufacture recommendations. 

---

## Experimental Design

I tested four popular master mixes with different MM to sample ratios.
1. **TaqPath ProAmp Master Mix** (Applied Biosystems)
2. **TaqMan Fast Advanced Master Mix** (Applied Biosystems)
3. **Logix Smart ABC MM** (CO-DX)
4. **Enhanced PCR Mix** (Illumina)

Each master mix was added with the following ratios:

1. **5ul-MM : 5ul-Synthetic control**
2. **2.5ul-MM : 2.5ul H20: 5ul-Synthetic control**
3. **1ul-MM : 4ul H20: 5ul-Synthetic control**
4. **0.1ul-MM : 4.9ul H20: 5ul-Synthetic control**

**Note:** 0.1 ul is difficult and innacurate to pipette, results may vary significantly with subsequent repetitions. 
---






### Results

Ct values:

| Master Mix | MM vol (10 µL)* | FAM Ct     | &nbsp;Quasar 670 Ct&nbsp; | &nbsp;Orange 560 Ct&nbsp; | &nbsp;Red 610 Ct&nbsp; |
|------------|-----------------|----------------|--------------------------|--------------------------|------------------------|
| **TaqPath ProAmp** | 5 µL  | 24.09 | &nbsp;N/A&nbsp; | &nbsp;22.61&nbsp; | &nbsp;N/A&nbsp; |
|              | 2.5 µL | 25.85 | &nbsp;N/A&nbsp; | &nbsp;24.13&nbsp; | &nbsp;N/A&nbsp; |
|              | 1 µL   | 37.18 | &nbsp;N/A&nbsp; | &nbsp;31.10&nbsp; | &nbsp;N/A&nbsp; |
|              | 0.1 µL | NO AMP| &nbsp;N/A&nbsp; | &nbsp;NO AMP&nbsp;| &nbsp;N/A&nbsp; |
| **TaqMan Fast Adv.** | 5 µL  | 23.80 | &nbsp;N/A&nbsp; | &nbsp;23.01&nbsp; | &nbsp;N/A&nbsp; |
|              | 2.5 µL | 25.94 | &nbsp;N/A&nbsp; | &nbsp;24.29&nbsp; | &nbsp;N/A&nbsp; |
|              | 1 µL   | 32.62 | &nbsp;N/A&nbsp; | &nbsp;29.83&nbsp; | &nbsp;N/A&nbsp; |
|              | 0.1 µL | NO AMP| &nbsp;N/A&nbsp; | &nbsp;NO AMP&nbsp;| &nbsp;N/A&nbsp; |
| **Logix Smart ABC** | 5 µL  | 28.66 | &nbsp;29.62&nbsp; | &nbsp;21.29&nbsp; | &nbsp;22.65&nbsp; |
|              | 2.5 µL | 32.35 | &nbsp;32.20&nbsp; | &nbsp;24.20&nbsp; | &nbsp;29.43&nbsp; |
|              | 1 µL   | NO AMP| &nbsp;NO AMP&nbsp; | &nbsp;NO AMP&nbsp; | &nbsp;NO AMP&nbsp; |
|              | 0.1 µL | NO AMP| &nbsp;NO AMP&nbsp; | &nbsp;NO AMP&nbsp; | &nbsp;NO AMP&nbsp; |
| **Enhanced PCR Mix**| 5 µL  | NO AMP| &nbsp;N/A&nbsp; | &nbsp;25.89&nbsp; | &nbsp;N/A&nbsp; |
|              | 2.5 µL | 33.00 | &nbsp;N/A&nbsp; | &nbsp;29.82&nbsp; | &nbsp;N/A&nbsp; |
|              | 1 µL   | NO AMP| &nbsp;N/A&nbsp; | &nbsp;N/A&nbsp;   | &nbsp;N/A&nbsp; |
|              | 0.1 µL | NO AMP| &nbsp;N/A&nbsp; | &nbsp;N/A&nbsp;   | &nbsp;N/A&nbsp; |



Results are suprising, for one, it's expected that high dose UV-C would certainly render RNA useless for amplification, but we can see that an hour of exposure, ct increased by approximately 3 for both the synthetic and human control. 

Equally suprising, the polypropylene tubes did not offer much protection against the UV-C. In theory, PP should block the majority of UV-C, but the shielding factor may be much less than anticipated. 

The synthetic control is theoretically expected to perform better and maintain a lower ct relative to the control due to the short and high-copy transcript supplied. We can see that it did perform better, but it's unclear if the buffer solution used would help reduce the amount of UV lesions per molecule. 

Interestingly, you can see that the human control RNA, when exposed to direct UV-C without shielding, does not follow a conventional exponential and platoe curve. This could be caused by a decrease in effective intact copy number preventing it from exponentiating cleanly. 

## UV Dose Curve
![UV Ct Curve]({{ "/assets/images/UV-DNA_Curve.png" | relative_url }})



### Conclusion

Direct exposure to high intensity UV-C did not prevent amplification for both the direct UV-exposed RNA, or the RNA stored in PP microcentrifuge tubes. The UV-C did increase Ct by approximately 3-4 cycles in both the synthetic and human RNA control. 




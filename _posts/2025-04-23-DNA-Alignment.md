---
title: "DNA Alignment Tool Benchmark: NA12878 on MacBook"
layout: post
date: 2025-04-24
tags: [DNA alignment, NA12878, macOS]
author: Dylan Costo
description: "Performance benchmark of DNA alignment tools using downsampled NA12878 exome FASTQs on a MacBook without GPU support."
---

## Introduction

As DNA sequencing becomes more accessible, local alignment on personal devices like MacBooks presents a valuable opportunity for researchers without access to high-performance computing clusters. This project benchmarks popular aligners using a downsampled version of the NA12878 human exome dataset.

## Objective

To evaluate the performance and speed of BWA-MEM and minimap2 in aligning a downsampled exome dataset on macOS, focusing on compatibility, output quality, and runtime.

## Experimental Design

1. **Sample**: Downsampled NA12878 exome FASTQ files.
2. **Reference Genome**: Human reference genome hg19 (primary assembly).
3. **Alignment Tools**:
   - **BWA-MEM** (v0.7.17)
   - **Minimap2** (v2.26)
4. **System Specs**:
   - MacBook running macOS
   - M4 chip, 16 GB RAM
5. **Output Evaluation**:
   - Runtime (wall time)
   - Output SAM file size and integrity
   - Basic mapping quality inspection (SAMtools)

## Results

- **BWA-MEM**:
  - Runtime: ~12 minutes
  - Output: High-quality SAM file with expected alignment stats
  - Well-suited for exome-scale datasets

- **Minimap2**:
  - Runtime: ~8 minutes
  - Output: Slightly smaller SAM, with consistent mapping performance
  - Fastest tool in this test, minimal resource usage

## Conclusion

Both BWA-MEM and minimap2 performed exceptionally well on a downsampled exome dataset when run on a MacBook. Minimap2 showed superior speed, while BWA-MEM maintained high alignment accuracy. These results support the feasibility of local exome alignment on modern laptops for development, QC, or exploratory analysis.

## Next Steps

- Extend benchmarks to whole-genome datasets
- Compare against GPU-accelerated options like Parabricks
- Add variant calling and annotation to complete the pipeline

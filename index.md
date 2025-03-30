---
layout: single
title: "Advancing Fine-Grained & Controllable Virtual Try-On"
# header:
#   image: /assets/img/vto-banner.jpg
---

# Advancing Fine-grained and Controllable Virtual Try-On

## Multi-Garment Virtual Try-on: Enhancing IDM-VTON for Comprehensive Digital Fashion Visualization

This project presents an enhancement to IDM-VTON that enables simultaneous processing of upper and lower garments, creating a comprehensive virtual try-on system that maintains the high-fidelity detail preservation of the original architecture.

![Demo Image](assets/images/multigarment_demo_image_1.jpg)

## Overview

Traditional virtual try-on systems face a critical limitation: they can only process single garments at a time. This project extends IDM-VTON's architecture to handle multiple garments simultaneously while preserving its exceptional detail fidelity.

Our approach employs:
- Vertical stacking of garment images
- Parallel CLIP processing with max pooling feature extraction
- Height-based feature concatenation
- Full-body masking strategies

## Method

![Architecture Overview](assets/images/multigarment_architecture.png)

### CLIP Feature Processing

A key innovation is our approach to CLIP feature processing for multiple garments:

1. Upper and lower garments are processed through CLIP independently
2. Max pooling is applied to extract salient features from each garment
3. Each garment's features are resized to match target width while maintaining pooled height
4. Features are concatenated along the height dimension

This approach preserves the distinctive characteristics of each garment while maintaining compatibility with existing network components.

### Vertical Garment Stacking

To handle multiple physical garment images through GarmentNet:

1. Upper and lower garments are vertically stacked
2. The stacked image maintains proper spatial relationships
3. Processing occurs through the existing pipeline with minimal modifications

## Results

Our implementation demonstrates strong performance across various garment combinations:

![Results Gallery](assets/images/results.jpg)

### Quantitative Evaluation

| Metric | Max Pooling (Main method) | Avg Pooling | Direct Resize | Late Fusion | IP-Adapter (10 Epochs) | IP-Adapter (20 Epochs) |
|--------|---------------------------|-------------|---------------|-------------|------------------------|------------------------|
| FID ↓ | 88.190 | 88.818 | 89.319 | 109.483 | 104.566 | 192.978 |
| KID ↓ | 4.013 | 2.967 | 3.772 | 30.818 | 16.860 | 106.554 |
| SSIM ↑ | 0.807 | 0.806 | 0.807 | 0.816 | 0.777 | 0.663 |
| LPIPS ↓ | 0.157 | 0.158 | 0.157 | 0.149 | 0.180 | 0.293 |

## Team

This project is part of the "Advancing Fine-grained and Controllable Virtual Try-On" research initiative:

### Multi-Garment Virtual Try-On
Enhanced IDM-VTON for simultaneous processing of upper and lower garments

### Text-Guided Virtual Try-On
Implementation of text-based garment control for fine-grained attribute manipulation

## Acknowledgments

We thank Assistant Professor Xu Bingjie for supervision and guidance throughout this project.

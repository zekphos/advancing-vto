---

title: "Advancing Fine-Grained & Controllable Virtual Try-On"
# header:
#   image: /assets/img/vto-banner.jpg
---

## Multi-Garment Virtual Try-on: Enhancing IDM-VTON for Comprehensive Digital Fashion Visualization

## Abstract

This project presents the technical development and implementation of a multi-garment virtual try-on system that extends the IDM-VTON architecture to process upper and lower garment images simultaneously. The project focuses on modifying the diffusion-based approach to accommodate multiple input streams while preserving the fine-grained texture and pattern details that are crucial for realistic garment visualization. Key technical contributions include the development of a parallel processing pipeline that handles multiple garment inputs, implementation of a feature fusion mechanism for combining garment features, and a novel CLIP processing workflow where upper and lower garments are processed independently through CLIP, followed by max pooling on the features for both garments. Each garment's features are then resized to match a target width while maintaining the pooled height, before being concatenated along the height dimension for further processing. Testing across various garment combinations demonstrates that the enhanced architecture successfully generates comprehensive outfit visualizations with particularly strong performance for common garment types such as t-shirts and long pants. This work addresses a fundamental limitation in current virtual try-on technology and demonstrates that diffusion-based approaches can be successfully extended beyond single-garment processing without sacrificing the detail preservation capabilities that make these methods valuable.

## Overview

Traditional virtual try-on systems face a critical limitation: they can only process single garments at a time. This project extends IDM-VTON's architecture to handle multiple garments simultaneously while preserving its exceptional detail fidelity.

This approach employs:
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

This implementation demonstrates strong performance across various garment combinations:

![Results Gallery](assets/images/multigarment_demo_image_1.jpg)
![Results Gallery](assets/images/multigarment_demo_image_2.jpg)
![Results Gallery](assets/images/multigarment_demo_image_3.jpg)
![Results Gallery](assets/images/multigarment_demo_image_4.jpg)
![Results Gallery](assets/images/multigarment_demo_image_5.jpg)
![Results Gallery](assets/images/multigarment_demo_image_6.jpg)

## Acknowledgments

We thank Assistant Professor Xu Bingjie for supervision and guidance throughout this project.


## Text-Guided Garment Transformation: Advanced Virtual Try-On with Natural Language Control

## Abstract

This research introduces a comprehensive text-guided virtual try-on system that improves the EditAnything framework through advanced prompt engineering techniques and ControlNet fine-tuning. Utilizing cutting-edge AI technologies, including the Segment Anything Model (SAM), GroundingDINO for object detection, and Stable Diffusion with ControlNet architecture, the system facilitates seamless text-prompted garment visualization without manual intervention. The combined approach of fine-tuned ControlNet and sophisticated prompt engineering generates high-quality apparel modifications while maintaining image integrity and natural appearance, demonstrating significant improvements in both modification quality and usability. Quantitative evaluation shows improvements of up to 90.5% in KID scores and 7.3% in structural similarity, responding to the escalating need for intuitive, automated garment alterations in e-commerce settings.

## Overview

In the rapidly evolving landscape of fashion e-commerce, the ability to visualize clothing modifications instantly and accurately has become increasingly crucial. This project presents an enhanced version of the EditAnything framework, specifically optimized for automatic clothing modification through text prompts.

The virtual try-on system integrates numerous advanced AI components to provide a comprehensive solution for text-guided clothing alteration. At its core, the system utilizes an enhanced version of ControlNet, fine-tuned specifically for fashion applications through four complete training epochs. This fine-tuning process substantially improves the model's ability to understand and implement clothing-specific modifications while maintaining visual coherence.

Key features include:
- Automatic clothing region detection using Segment Anything Model (SAM)
- Sophisticated prompt engineering to optimize text descriptions
- Cross-attention mechanisms for accurate style transfer
- Region preservation techniques for maintaining image integrity

## Method

![System Architecture](assets/images/text_guided_architectuxt-guided virtual try-on system employs a sophisticated multi-stage architecture designed to transform descriptive text and reference images into photorealistic visualizations of clothing items on human subjects.

### Input Layer Components

The system begins with processing both textual and visual input:

1. **Text Input Processing**: Accepts natural language descriptions of desired clothing modifications
2. **Dynamic Prompt Engineering**: Enhances basic text prompts by adding relevant clothing attributes and specifications
3. **Input Image Processing**: Prepares the source person image for downstream processing

### Core Processing Layer

The detection and segmentation of target garment areas happens through:

1. **GroundingDINO**: Bridges natural language understanding with visual elements by processing both input image and text description
2. **Segment Anything Model (SAM)**: Performs pixel-level segmentation of the target clothing area

### Text-Guided Modification Process

The system translates natural language descriptions into visual changes through:

1. **Diffusion-Based Image Generation**: Employs Stable Diffusion with ControlNet for high-quality image generation
2. **Pattern and Material Intelligence**: Incorporates domain knowledge about clothing to improve output quality
3. **Comprehensive Negative Prompting**: Guides the diffusion model away from common failure modes

### Region Preservation Techniques

To maintain the integrity of non-target regions, the system implements:

1. **Precise Mask Generation**: Creates highly accurate binary masks corresponding to clothing items
2. **Inpainting-Based Modification**: Preserves pixel values outside the masked area
3. **Structural Guidance with ControlNet**: Maintains the structural integrity of clothing items

## Acknowledgments

We thank Assistant Professor Xu Bingjie for supervision and guidance throughout this project.
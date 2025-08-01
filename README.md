# Monet Style Transfer with CycleGAN by Rylan Turner
![image_07000](https://github.com/user-attachments/assets/8f58ba42-669a-4f20-86ff-cbb63ce904aa)
![image_06991](https://github.com/user-attachments/assets/ca29e867-b92a-473c-8d79-6c5023b8e2ce)
![image_06972](https://github.com/user-attachments/assets/d0e6a74b-0848-48d9-a080-6ca9560d8931)

This project implements a CycleGAN model ~~for~~ inspired by the Kaggle "GAN Getting Started" competition, which generates Monet-style paintings from photographs.

## Project Overview

The goal is to build a Generative Adversarial Network (GAN) that can transform regular photographs into paintings that mimic Claude Monet's artistic style. The model uses CycleGAN architecture to learn the mapping between photo and Monet painting domains without requiring paired training data.

## Dataset

- **monet_jpg**: 300 Monet paintings (256x256 RGB)
- **monet_tfrec**: Same images in TFRecord format
- **photo_jpg**: 7,028 photographs (256x256 RGB)
- **photo_tfrec**: Same images in TFRecord format
- **Output**: ~8,000 generated Monet-style images

## Model Architecture

- **CycleGAN**: Two generators and two discriminators
- **Generator**: ResNet-based with skip connections
- **Discriminator**: PatchGAN discriminator
- **Loss Functions**: Adversarial loss + Cycle consistency loss + Identity loss

## Installation

1. Clone this repository
2. Install dependencies:
```bash
pip install -r requirements.txt
```

## Usage

1. Download the Kaggle competition dataset
2. Extract and place the data in the appropriate directories:
   - `monet_jpg/` - Monet paintings
   - `monet_tfrec/`
   - `photo_jpg/` - Photographs
   - `photo_tfrec/`

3. Run the notebook to train the model and generate submission

## Key Features

- Comprehensive EDA and data analysis
- CycleGAN implementation with modern best practices
- Training monitoring and sample generation
- Automatic submission zip file creation
- Detailed documentation and analysis

## Competition Submission

The model generates 8,000 Monet-style images and packages them into `images.zip` for Kaggle submission (this notebook runs 50 epochs to maximize training, too long for Kaggle submission). The evaluation metric is MiFID (Memorization-informed Fréchet Inception Distance).

## Results

<img width="1554" height="788" alt="output_64_1" src="https://github.com/user-attachments/assets/366c2f3e-f4c2-4756-b281-886e4c9fd652" />
The model successfully learns to transfer photographic images to Monet's artistic style while maintaining the original content and structure of the input photographs.

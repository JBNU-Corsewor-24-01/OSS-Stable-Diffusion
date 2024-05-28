# OSS-Stable-Diffusion


# Stable Diffusion Model Setup and Jeonbuk National University Symbol Image Generation

## Introduction
This project demonstrates how to set up the Stable Diffusion model and use it to generate an image of the Jeonbuk National University (JBNU) symbol. Stable Diffusion is a powerful AI model for generating high-quality images from text descriptions.

## Prerequisites
- A system with a compatible GPU (recommended) or CPU.
- Install Anaconda or Miniconda.
- Install Git.

## Installation Guide

### Step 1: Set Up the Environment
1. Download and install [Anaconda](https://www.anaconda.com/products/distribution) or [Miniconda](https://docs.conda.io/en/latest/miniconda.html).
2. Open the Anaconda Prompt (or your preferred terminal).

### Step 2: Create a Conda Environment
```bash
conda create -n stable-diffusion python=3.8
conda activate stable-diffusion
```

### Step 3: Install Dependencies
```bash
# Install PyTorch
conda install pytorch torchvision torchaudio cudatoolkit=11.1 -c pytorch -c nvidia

# Install other dependencies
pip install transformers diffusers
pip install opencv-python
```

### Step 4: Clone the Stable Diffusion Repository
```bash
git clone https://github.com/CompVis/stable-diffusion.git
cd stable-diffusion
```

### Step 5: Download Pre-trained Weights
Download the pre-trained weights for the Stable Diffusion model from the official repository or from Hugging Face and place them in the appropriate directory (`models/ldm/stable-diffusion-v1/`).

### Step 6: Run the Stable Diffusion Model
```bash
# Navigate to the directory
cd scripts

# Run the model to generate an image of the JBNU symbol
python txt2img.py --prompt "Jeonbuk National University symbol" --plms --ckpt ../models/ldm/stable-diffusion-v1/model.ckpt --skip_grid --n_samples 1 --n_iter 1 --W 512 --H 512
```

This command generates an image based on the provided prompt and saves it to the output directory.

## Viewing the Generated Image
The generated image will be saved in the `outputs/txt2img-samples/` directory. You can open it with any image viewer.

## Troubleshooting
- Ensure all dependencies are installed correctly and their paths are properly set.
- If you encounter errors related to CUDA, make sure you have the correct version of CUDA installed and configured.

## Conclusion
By following this guide, you should have a functional setup of the Stable Diffusion model and be able to generate images from text prompts. This setup can be extended to generate a variety of images for different use cases.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

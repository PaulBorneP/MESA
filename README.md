

<h1 align="center">MESA: Text-Driven Terrain Generation Using Latent Diffusion and Global Copernicus Data </h1>
<p align="center"><a href="https://www.linkedin.com/in/paul-bp-cs/" target="_blank">Paul Borne--Pons</a>, <a href="https://mikonvergence.github.io/" target="_blank">Mikolaj Czerkawski</a>,<a href="https://research.adobe.com/person/rosalie-martin/" target="_blank">Rosalie Martin</a>,
<a href="https://research.adobe.com/person/romain-rouffet/" target="_blank">Romain Rouffet</a></p>

<p align="center"><a href="https://sites.google.com/view/morse2025" target="_blank">CVPR 2025 Workshop MORSE</a> </p>

[![HF](https://img.shields.io/badge/%F0%9F%8F%94%EF%B8%8FProject%20Page-679c39)](https://paulbornep.github.io/mesa-terrain/)
[![paper](https://img.shields.io/badge/arXiv-2402.12095-D12424)](https://arxiv.org/abs/2504.07210)
[![HF](https://img.shields.io/badge/%F0%9F%A4%97-Models-yellow)](https://www.huggingface.co/NewtNewt/MESA)
[![HF](https://img.shields.io/badge/%F0%9F%A4%97-Datasets-yellow)](https://www.huggingface.co/Major-TOM) 
[![HF](https://img.shields.io/badge/%F0%9F%A4%97-Spaces_Demo-yellow)](https://huggingface.co/spaces/mikonvergence/MESA)
 <a href="https://colab.research.google.com/drive/1dI8uTzNICpOPTaWmFM9Hhp_n67-Y2m7-?usp=sharing" target="_parent"> <img src="https://colab.research.google.com/assets/colab-badge.svg"  alt="Open In Colab"/></a> 


MESA is a novel generative model based on latent denoising diffusion capable of generating 2.5D representations of terrain based on the text prompt conditioning supplied via natural language. The model produces two co-registered modalities of optical and depth maps.

<p align="center"><img src=assets/mesa-header-nz.png></p>

## Abstract

Terrain modeling has traditionally relied on procedural techniques, which often require extensive domain expertise and handcrafted rules. In this paper, we present MESA - a novel data-centric alternative by training a diffusion model on global remote sensing data. This approach leverages large-scale geospatial information to generate high-quality terrain samples from text descriptions, showcasing a flexible and scalable solution for terrain generation. The model’s capabilities are demonstrated through extensive experiments, highlighting its ability to generate realistic and diverse terrain landscapes. The dataset produced to support this work, the Major TOM Core-DEM extension dataset, is released openly as a comprehensive resource for global terrain data. The results suggest that data-driven models, trained on remote sensing data, can provide a powerful tool for realistic terrain modeling and generation.

## Model Weights

You still manually acquire the weights by cloning the models from Hugging Face:

```bash
mkdir weights
huggingface-cli download NewtNewt/MESA --local-dir weights
```

## Installation

```bash
# using python 3.11.12
pip install -r requirements.txt
```

Note that this environment is only compatible with NVIDIA GPUs. Additionally, we recommend using a GPU with a minimum of 8GB of memory.

## Inference

```python
from MESA.pipeline_terrain import TerrainDiffusionPipeline
import torch

pipe = TerrainDiffusionPipeline.from_pretrained("./weights", torch_dtype=torch.float16)
pipe.to("cuda");

prompt = "A sentinel-2 image of montane forests and mountains in Mexico in August"
image,dem = pipe(prompt, num_inference_steps=50, guidance_scale=7.5)
```

A straightforward code for inference is provided in  <a href="https://colab.research.google.com/drive/1dI8uTzNICpOPTaWmFM9Hhp_n67-Y2m7-?usp=sharing" target="_parent"> <img src="https://colab.research.google.com/assets/colab-badge.svg"  alt="Open In Colab"/></a> 

Alternatively, you can download and use the Gradio demo from the HF page.

## Citation

```latex
@inproceedings{mesa2025,
title={MESA: Text-Driven Terrain Generation Using Latent Diffusion and Global Copernicus Data},
author={Paul Borne--Pons and Mikolaj Czerkawski and Rosalie Martin and Romain Rouffet},
year={2025},
booktitle={MORSE Workshop at CVPR 2025},
eprint={2504.07210},
url={https://arxiv.org/abs/2504.07210},}
```
## Acknowledgements

This implementation builds upon Hugging Face’s [Diffusers](https://github.com/huggingface/diffusers) library. We also acknowledge [Gradio](https://www.gradio.app/) for providing an easy-to-use interface that allowed us to create the inference demos for our models.

This model is the product of a collaboration between [Φ-lab, European Space Agency (ESA)](https://philab.esa.int/) and the [Adobe Research (Paris, France)](https://research.adobe.com/careers/paris/).

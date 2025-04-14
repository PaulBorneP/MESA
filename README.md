

<h1 align="center">MESA: Text-Driven Terrain Generation Using Latent Diffusion and Global Copernicus Data </h1>
<p align="center"><a href="https://www.linkedin.com/in/paul-bp-cs/" target="_blank">Paul Borne--Pons</a>, <a href="https://mikonvergence.github.io/" target="_blank">Mikolaj Czerkawski</a>,<a href="https://research.adobe.com/person/rosalie-martin/" target="_blank">Rosalie Martin</a>,
<a href="https://research.adobe.com/person/romain-rouffet/" target="_blank">Romain Rouffet</a></p>

<p align="center"><a href="https://sites.google.com/view/morse2025" target="_blank">CVPR 2025 Workshop MORSE</a> </p>


[![paper](https://img.shields.io/badge/arXiv-2402.12095-D12424)](https://arxiv.org/abs/2504.07210)
[![HF](https://img.shields.io/badge/%F0%9F%A4%97-Models-yellow)](https://www.huggingface.co/NewtNewt/MESA)
[![HF](https://img.shields.io/badge/%F0%9F%A4%97-Datasets-yellow)](https://www.huggingface.co/Major-TOM) 
[![HF](https://img.shields.io/badge/%F0%9F%A4%97-Spaces_Demo-yellow)]()
 <a href="" target="_parent">
<img src="https://colab.research.google.com/assets/colab-badge.svg" href="https://colab.research.google.com/drive/1dI8uTzNICpOPTaWmFM9Hhp_n67-Y2m7-?usp=sharing" alt="Open In Colab"/></a> 


MESA is a novel generative model based on latent denoising diffusion capable of generating 2.5D representations of terrain based on the text prompt conditioning supplied via natural language. The model produces two co-registered modalities of optical and depth maps.

<p align="center"><img src=assets/mesa-header-nz.png></p>

## Abstract

Terrain modeling has traditionally relied on procedural techniques, which often require extensive domain expertise and handcrafted rules. In this paper, we present MESA - a novel data-centric alternative by training a diffusion model on global remote sensing data. This approach leverages large-scale geospatial information to generate high-quality terrain samples from text descriptions, showcasing a flexible and scalable solution for terrain generation. The model’s capabilities are demonstrated through extensive experiments, highlighting its ability to generate realistic and diverse terrain landscapes. The dataset produced to support this work, the Major TOM Core-DEM extension dataset, is released openly as a comprehensive resource for global terrain data. The results suggest that data-driven models, trained on remote sensing data, can provide a powerful tool for realistic terrain modeling and generation.

## Model Weights


## Installation

## Inference


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

This model is the product of a collaboration between Φ-lab, European Space Agency (ESA) and the Adobe Research (Paris, France).
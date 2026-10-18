<img width="6848" height="1507" alt="pipeline" src="https://github.com/user-attachments/assets/c4aab195-0bc0-4a21-a092-e96d1fd865bd" /><div align="center">

# MRSR-NeRF: Multi-View Reference-Guided Super-Resolution for Neural Radiance Fields

**WACV 2027**

[Junseo Choi](mailto:wnstj010126@gmail.com) · [YoungJun Choi](mailto:chldudwns2002@gmail.com) · [Jaehwan Kim](mailto:jonny0010@gmail.com) · [Seunghwa Jeong](mailto:seunghwajeong@sejong.ac.kr)<sup>†</sup>

Sejong University, Republic of Korea  
<sup>†</sup>Corresponding author

[![WACV 2027](https://img.shields.io/badge/WACV-2027-4b44ce)](https://wacv.thecvf.com/)

| Ours | [DiSR-NeRF](https://github.com/leejielong/DiSR-NeRF) |
|:--:|:--:|
| <video src="https://github.com/user-attachments/assets/469860be-abde-4de8-aaad-594ec2075421" controls muted playsinline loop width="400"></video> | <video src="https://github.com/user-attachments/assets/afc5865a-5315-4841-a796-9528a587da47" controls muted playsinline loop width="400"></video> |

*MRSR-NeRF restores fine details with significantly less flickering across views.*

</div>

## 📢 News
- **[2026.10]** MRSR-NeRF has been accepted to **WACV 2027**! 🎉
- **[Coming soon]** Camera-ready paper and code will be released.

## Overview
**TL;DR**: MRSR-NeRF is a zero-shot, scene-specific super-resolution framework for NeRF. Instead of hallucinating details, it borrows *authentic* high-frequency textures from neighboring views where the same region appears magnified, producing multi-view consistent and structure-preserving high-resolution reconstructions.

<p align="center">
  <img src="https://github.com/user-attachments/assets/441d5d87-be5b-4c12-8b67-40321d1763e2" width="90%">
</p>

Our framework consists of four stages:
1. **NeRF Initialization**: An LR-trained NeRF provides geometric depth guidance.
2. **Reference Patch Sourcing (RPS)**: Magnified reference patches are retrieved from adjacent views via feature matching.
3. **MRSR Training & Inference**: A Multi-view Cross-Attention Block (MCAB) with depth priors and an Adaptive Sampling Network (ASN) transfer textures while correcting sub-pixel misalignments.
4. **NeRF Update**: The NeRF is fine-tuned on the super-resolved images.

No external data or pre-trained SR models are required. Only the multi-view LR images of the target scene are used.

## Quantitative Results
4× SR on LLFF and NeRF-synthetic (all methods use the Instant-NGP backbone).

| Method | LLFF PSNR↑ | LPIPS↓ | SSIM↑ | NIQE↓ | Synthetic PSNR↑ | LPIPS↓ | SSIM↑ | NIQE↓ |
|:--|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|
| Instant-NGP | 23.16 | 0.3964 | 0.7174 | 6.8741 | 26.36 | 0.1174 | 0.8981 | 6.5410 |
| NeRF-SR | 23.16 | 0.3262 | 0.7177 | 6.9874 | 26.34 | 0.1169 | 0.8982 | 6.3542 |
| DiSR-NeRF | 22.73 | 0.3340 | 0.7255 | **5.8330** | 25.88 | 0.1186 | 0.8971 | 6.0364 |
| **Ours** | **23.36** | **0.3244** | **0.7305** | 5.9597 | **27.31** | **0.1102** | **0.9075** | **5.9547** |

## Citation
If you find our work useful, please consider citing:
```bibtex
@inproceedings{choi2027mrsrnerf,
  title     = {MRSR-NeRF: Multi-View Reference-Guided Super-Resolution for Neural Radiance Fields},
  author    = {Choi, Junseo and Choi, YoungJun and Kim, Jaehwan and Jeong, Seunghwa},
  booktitle = {Proceedings of the IEEE/CVF Winter Conference on Applications of Computer Vision (WACV)},
  year      = {2027}
}
```

## Acknowledgements
Our MRSR network builds upon [RZSR](https://github.com/junsang7777/RZSR-Reference-based-Zero-Shot-Super-Resolution-with-Depth-Guided-Self-Exemplars) and uses [LoFTR](https://github.com/zju3dv/LoFTR) for feature matching and [Instant-NGP](https://github.com/NVlabs/instant-ngp) as the NeRF backbone. We also thank the authors of [DiSR-NeRF](https://github.com/leejielong/DiSR-NeRF), which served as a baseline comparison.

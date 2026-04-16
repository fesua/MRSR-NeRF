This repository contains the official demonstration and results of our research on view-consistent scene reconstruction. 

## Overview
We propose a novel approach to enhance view-consistency in 3D scene representation. This demo highlights the performance of our method compared to existing state-of-the-art techniques like DiSR-NeRF and SRGS.

> **Note**: The full implementation and source code will be released after the paper review process is complete.

---

## View-consistency Comparison

We evaluate our method's ability to maintain structural integrity and visual consistency across different viewpoints. Specifically, we qualitatively compare flickering artifacts with DiSR-NeRF (NeRF-based) and assess floaters and reconstruction accuracy against SRGS (3DGS-based).

### Comparison with DiSR-NeRF
| Ours | [DiSR-NeRF](https://github.com/leejielong/DiSR-NeRF) |
|:--:|:--:|
| <video src="https://github.com/user-attachments/assets/469860be-abde-4de8-aaad-594ec2075421" controls muted playsinline loop width="360"></video> | <video src="https://github.com/user-attachments/assets/afc5865a-5315-4841-a796-9528a587da47" controls muted playsinline loop width="360"></video> |

### Comparison with SRGS
| Ours & [SRGS](https://github.com/XiangFeng66/SRGS) |
|:--:|
| <video src="https://github.com/user-attachments/assets/42db4140-d955-4c95-b5db-556dc1479f2a" controls muted playsinline loop width="360"></video> |



## References
We would like to acknowledge the following works which served as baseline comparisons for our evaluation:

* **DiSR-NeRF**: [Diffusion-Guided View-Consistent Super-Resolution NeRF](https://github.com/leejielong/DiSR-NeRF)
* **SRGS**: [Super-Resolution 3D Gaussian Splatting](https://github.com/XiangFeng66/SRGS)

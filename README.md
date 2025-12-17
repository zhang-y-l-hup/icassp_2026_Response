# icassp_2026_Response
This repository provides supplementary experimental results to address the reviewers' comments, including extended baselines, dataset details, and quantitative comparisons under uniform/non-uniform lighting.

------

## 1. Extended Experimental Setup
### 1.1 Datasets
We evaluate our method on two representative datasets covering diverse lighting scenarios:
| Dataset               | Number of Scenes | Lighting Scenarios                  | Resolution | Split Ratio (Train/Test) |
|-----------------------|------------------|-------------------------------------|------------|---------------------------|
| MipNeRF360-varying    | 7                | Varying exposure + normal lighting  | [例如：1920×1080] | 7:1                       |
| LOM                   | 5                | Low-light + normal lighting         | [例如：1280×720]  | 7:1                       |

### 1.2 Extended Baseline Methods
We add **LLGS (ICASSP 2025)** as an extra baseline, covering classic and state-of-the-art methods:
| Method         | Conference (Year) | Core Contribution                  |
|----------------|-------------------|-------------------------------------|
| 3DGS           | ACM Trans. Graph. (2023) | Basic 3D Gaussian Splatting         |
| Aleth-NeRF     | AAAI (2024)       | Illumination adaptive via concealing field |
| GS-W           | ECCV (2024)       | Gaussian feature decoupling for wild scenes |
| Luminance-GS   | CVPR (2025)       | View-adaptive curve adjustment for lighting |
| LLGS           | ICASSP (2025)     | Gaussian illumination via absorptance modulation |

### 1.3 Experimental results



## 2. Quantitative Comparisons (Uniform/Non-Uniform Lighting)
We report the PSNR/SSIM/LPIPS metrics of our method under both uniform and non-uniform lighting conditions (lower LPIPS = better perceptual quality) to better evaluate the contribution of our approach.
### 2.1 Uniform/Non-uniform Quantitative Comparison



### 2.2 Effect Comparison
<img src="https://github.com/zhang-y-l-hup/icassp_2026_Response/raw/main/Color%20Conversion%20Comparison.png" width="800" alt="颜色转换前后对比">

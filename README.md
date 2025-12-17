# icassp_2026_Response
This repository provides supplementary experimental results to address the reviewers' comments, including extended baselines, dataset details, and quantitative comparisons under uniform/non-uniform lighting.

------

## 1. Extended Experimental Setup
### 1.1 Datasets
We evaluate our method on two representative datasets covering diverse lighting scenarios:
| Dataset               | Number of Scenes | Lighting Scenarios                  | Split Ratio (Train/Test)  |
|-----------------------|------------------|-------------------------------------|---------------------------|
| MipNeRF360-varying    | 7                | Varying exposure + normal lighting  | 7:1                       |
| LOM                   | 5                | Low-light + normal lighting         | 7:1                       |

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


**Add the method LLGS (ICASSP) for comparison on the LOM dataset.**
| scene   | metric | 3DGS   | Aleth-NeRF | GS-W   | Luminance-GS |  LLGS  | Ours   |
|---------|--------|--------|------------|--------|--------------|--------|--------|
|         | PSNR ↑ | 18.447 |   9.378    | 26.747 |    20.358    | 15.753 | 22.371 |
|  "bike" | SSIM ↑ | 0.547  |   0.254    | 0.851  |    0.754     | 0.623  | 0.858  |
|         | LPIPS ↓| 0.328  |   0.751    | 0.278  |    0.368     | 0.445  | 0.219  |
|---------|--------|--------|------------|--------|--------------|--------|--------|
|         | PSNR ↑ | 14.472 |   13.288   | 27.012 |    16.486    | 22.877 | 26.119 |
|  "buu"  | SSIM ↑ | 0.634  |   0.633    | 0.895  |    0.741     | 0.878  | 0.916  |
|         | LPIPS ↓| 0.407  |   0.639    | 0.199  |    0.376     | 0.218  | 0.176  |
|---------|--------|--------|------------|--------|--------------|--------|--------|
|         | PSNR ↑ | 16.482 |   12.269   | 19.177 |    16.161    | 16.541 | 19.845 |
| "shrub" | SSIM ↑ | 0.559  |   0.129    | 0.553  |    0.667     | 0.543  | 0.714  |
|         | LPIPS ↓| 0.374  |   0.713    | 0.289  |    0.207     | 0.366  | 0.204  |

| scene   | metric | 3DGS   | Aleth-NeRF | GS-W       | Luminance-GS | LLGS   | Ours       |
|---------|--------|--------|------------|------------|--------------|--------|------------|
|         | PSNR ↑ | 18.447 | 9.378      | **26.747 ✅** | 20.358       | 15.753 | 22.371     |
|  "bike" | SSIM ↑ | 0.547  | 0.254      | 0.851      | 0.754        | 0.623  | **0.858 ✅** |
|         | LPIPS ↓| 0.328  | 0.751      | 0.278      | 0.368        | 0.445  | **0.219 ✅** |
|---------|--------|--------|------------|------------|--------------|--------|------------|
|         | PSNR ↑ | 14.472 | 13.288     | **27.012 ✅** | 16.486       | 22.877 | 26.119     |
|  "buu"  | SSIM ↑ | 0.634  | 0.633      | 0.895      | 0.741        | 0.878  | **0.916 ✅** |
|         | LPIPS ↓| 0.407  | 0.639      | 0.199      | 0.376        | 0.218  | **0.176 ✅** |
|---------|--------|--------|------------|------------|--------------|--------|------------|
|         | PSNR ↑ | 16.482 | 12.269     | 19.177     | 16.161       | 16.541 | **19.845 ✅** |
| "shrub" | SSIM ↑ | 0.559  | 0.129      | 0.553      | 0.667        | 0.543  | **0.714 ✅** |
|         | LPIPS ↓| 0.374  | 0.713      | 0.289      | 0.207        | 0.366  | **0.204 ✅** |

## 2. Quantitative Comparisons (Uniform/Non-Uniform Lighting)
We report the PSNR/SSIM/LPIPS metrics of our method under both uniform and non-uniform lighting conditions (lower LPIPS = better perceptual quality) to better evaluate the contribution of our approach.
### 2.1 Uniform/Non-uniform Quantitative Comparison



### 2.2 Effect Comparison
<img src="https://github.com/zhang-y-l-hup/icassp_2026_Response/raw/main/Color%20Conversion%20Comparison.png" width="800" alt="颜色转换前后对比">

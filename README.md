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
## Quantitative Results (MIPNeRF360-Varying, Partial Scenes)
Table below shows performance metrics (PSNR ↑, SSIM ↑, LPIPS ↓) across different methods on partial scenes:

| Scene       | Metric   | 3DGS    | Aleth-NeRF | WS-GS   | Luminance-GS | Ours    |
|-------------|----------|---------|------------|---------|--------------|---------|
|             | PSNR ↑   | 18.523  | 12.943     | 15.616  | 18.383       | 18.291  |
| **bicycle** | SSIM ↑   | 0.514   | 0.195      | 0.563   | 0.646        | 0.637   |
|             | LPIPS ↓  | 0.396   | 0.796      | 0.371   | 0.330        | 0.274   |
|             | PSNR ↑   | 20.176  | 12.265     | 20.456  | 20.984       | 21.506  |
| **garden**  | SSIM ↑   | 0.787   | 0.689      | 0.782   | 0.791        | 0.827   |
|             | LPIPS ↓  | 0.203   | 0.813      | 0.212   | 0.195        | 0.191   |
|             | PSNR ↑   | 15.098  | 12.454     | 15.892  | 16.850       | 17.341  |
| **counter** | SSIM ↑   | 0.527   | 0.324      | 0.624   | 0.645        | 0.739   |
|             | LPIPS ↓  | 0.368   | 0.780      | 0.37    | 0.302        | 0.224   |
| **bonsai**  | PSNR ↑   | 12.53   | 8.14       | 15.52   | 15.70        | *       |
|             | SSIM ↑   | 0.299   | 0.403      | 0.554   | 0.563        | *       |
|             | LPIPS ↓  | 0.561   | 0.685      | 0.419   | 0.433        | *       |
| **kitchen** | PSNR ↑   | 22.31   | 11.35      | 20.67   | 23.10        | *       |
|             | SSIM ↑   | 0.831   | 0.397      | 0.802   | 0.833        | *       |
|             | LPIPS ↓  | 0.177   | 0.579      | 0.164   | 0.143        | *       |
| **room**    | PSNR ↑   | 14.35   | 7.15       | 17.19   | 16.82        | *       |
|             | SSIM ↑   | 0.549   | 0.315      | 0.558   | 0.643        | *       |
|             | LPIPS ↓  | 0.299   | 0.733      | 0.375   | 0.319        | *       |
| **stump**   | PSNR ↑   | 16.61   | 12.43      | 14.89   | 15.63        | *       |
|             | SSIM ↑   | 0.476   | 0.471      | 0.503   | 0.532        | *       |
|             | LPIPS ↓  | 0.402   | 0.665      | 0.432   | 0.389        | *       |


**Add the method LLGS (ICASSP) for comparison on the LOM dataset.(Note: ✅ indicates the best-performing metric for each evaluation item.)**
| scene   | metric | 3DGS   | Aleth-NeRF | GS-W   | Luminance-GS |  LLGS  | Ours   |
|---------|--------|--------|------------|--------|--------------|--------|--------|
|         | PSNR ↑ | 18.447 |   9.378    | **26.747 ✅** |    20.358    | 15.753 | 22.371 |
|  "bike" | SSIM ↑ | 0.547  |   0.254    | 0.851  |    0.754     | 0.623  |**0.858 ✅**  |
|         | LPIPS ↓| 0.328  |   0.751    | 0.278  |    0.368     | 0.445  | **0.219 ✅**  |
|---------|--------|--------|------------|--------|--------------|--------|--------|
|         | PSNR ↑ | 14.472 |   13.288   | **27.012 ✅** |    16.486    | 22.877 | 26.119 |
|  "buu"  | SSIM ↑ | 0.634  |   0.633    | 0.895  |    0.741     | 0.878  | **0.916 ✅**  |
|         | LPIPS ↓| 0.407  |   0.639    | 0.199  |    0.376     | 0.218  | **0.176 ✅**  |
|---------|--------|--------|------------|--------|--------------|--------|--------|
|         | PSNR ↑ | 16.582 |   12.229   | 19.173 |    16.161    | 16.543 | **19.845 ✅** |
| "shrub" | SSIM ↑ | 0.449  |   0.169    | 0.557  |    0.667     | 0.511  | **0.714 ✅**  |
|         | LPIPS ↓| 0.374  |   0.713    | 0.289  |    0.207     | 0.366  | **0.204 ✅**  |



## 2. Quantitative Comparisons (Uniform/Non-Uniform Lighting)
We report the PSNR/SSIM/LPIPS metrics of our method under both uniform and non-uniform lighting conditions (lower LPIPS = better perceptual quality) to better evaluate the contribution of our approach.
### 2.1 Uniform/Non-uniform Quantitative Comparison



## 3. Comparison of Colors Before and After Conversion
<img src="https://github.com/zhang-y-l-hup/icassp_2026_Response/raw/main/Color%20Conversion%20Comparison.png" width="800" alt="颜色转换前后对比">

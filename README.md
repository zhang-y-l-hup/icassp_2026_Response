# icassp_2026_Response

This repository provides supplementary experimental results to address the reviewers' comments, including extended baselines, dataset details, and quantitative comparisons under uniform/non-uniform lighting.

------

## 1. Extended Experimental ()

### 1.1 Datasets

We evaluate our method on two representative datasets covering diverse lighting scenarios:

| Dataset            | Number of Scenes | Lighting Scenarios                 | Split Ratio (Train/Test) |
| ------------------ | ---------------- | ---------------------------------- | ------------------------ |
| MipNeRF360-varying | 7                | Varying exposure + normal lighting | 7:1                      |
| LOM                | 5                | Low-light + normal lighting        | 7:1                      |

### 1.2 Extended Baseline Methods

We add **LLGS (ICASSP 2025)** as an extra baseline, covering classic and state-of-the-art methods:

| Method       | Conference (Year)        | Core Contribution                                |
| :----------- | :----------------------- | :----------------------------------------------- |
| 3DGS         | ACM Trans. Graph. (2023) | Basic 3D Gaussian Splatting                      |
| Aleth-NeRF   | AAAI (2024)              | Illumination adaptive via concealing field       |
| GS-W         | ECCV (2024)              | Gaussian feature decoupling for wild scenes      |
| Luminance-GS | CVPR (2025)              | View-adaptive curve adjustment for lighting      |
| LLGS         | ICASSP (2025)            | Gaussian illumination via absorptance modulation |

### 1.3 Experimental results

**The following table presents the performance metrics (PSNR↑, SSIM↑, LPIPS↓) of various methods under non-uniform illumination conditions on the NeRF360-Varying dataset.(Note: ✅ indicates the best-performing metric for each evaluation item.)**

|     scene     |   metric   |     3DGS     | Aleth-NeRF |     GS-W     | Luminance-GS |     Ours     |
| :-----------: | :--------: | :----------: | :--------: | :----------: | :----------: | :----------: |
|               |   PSNR ↑   | **18.523 ✅** |   12.943   |    15.616    |    18.383    |    18.237    |
| **"bicycle"** |   SSIM ↑   |    0.514     |   0.195    |    0.563     |    0.646     | **0.691 ✅**  |
|               |  LPIPS ↓   |    0.396     |   0.796    |    0.371     |    0.330     | **0.274 ✅**  |
|  ----------   | ---------- |  ----------  | ---------- |  ----------  |  ----------  |  ----------  |
|               |   PSNR ↑   |    20.187    |   12.685   |    20.482    |    20.984    | **21.526 ✅** |
| **"garden"**  |   SSIM ↑   |    0.736     |   0.229    |    0.756     |    0.791     | **0.807 ✅**  |
|               |  LPIPS ↓   |    0.203     |   0.813    |    0.212     |    0.195     | **0.191 ✅**  |
|  ----------   | ---------- |  ----------  | ---------- |  ----------  |  ----------  |  ----------  |
|               |   PSNR ↑   |    15.098    |   12.454   |    15.892    |    16.850    | **17.341 ✅** |
| **"counter"** |   SSIM ↑   |    0.527     |   0.324    |    0.624     |    0.645     | **0.739 ✅**  |
|               |  LPIPS ↓   |    0.368     |   0.780    |    0.337     |    0.302     | **0.224 ✅**  |
|  ----------   | ---------- |  ----------  | ---------- |  ----------  |  ----------  |  ----------  |
|               |   PSNR ↑   |    12.533    |   8.141    |    15.526    |    15.708    | **17.973 ✅** |
| **"bonsai"**  |   SSIM ↑   |    0.299     |   0.403    |    0.554     |    0.563     | **0.684 ✅**  |
|               |  LPIPS ↓   |    0.561     |   0.685    |    0.419     |    0.433     | **0.273 ✅**  |
|  ----------   | ---------- |  ----------  | ---------- |  ----------  |  ----------  |  ----------  |
|               |   PSNR ↑   |    22.310    |   11.357   |    20.672    | **23.100 ✅** |    16.858    |
| **"kitchen"** |   SSIM ↑   |    0.831     |   0.397    |    0.802     |    0.833     | **0.848 ✅**  |
|               |  LPIPS ↓   |    0.177     |   0.579    |    0.164     | **0.143 ✅**  |    0.148     |
|  ----------   | ---------- |  ----------  | ---------- |  ----------  |  ----------  |  ----------  |
|               |   PSNR ↑   |    14.354    |   7.151    | **17.198 ✅** |    16.825    |    17.150    |
|  **"room"**   |   SSIM ↑   |    0.549     |   0.315    |    0.558     |    0.643     | **0.762 ✅**  |
|               |  LPIPS ↓   |    0.299     |   0.733    |    0.375     |    0.319     | **0.245 ✅**  |
|  ----------   | ---------- |  ----------  | ---------- |  ----------  |  ----------  |  ----------  |
|               |   PSNR ↑   |    16.619    |   12.434   |    14.891    |    15.639    | **19.458 ✅** |
|  **"stump"**  |   SSIM ↑   |    0.476     |   0.471    |    0.503     |    0.532     | **0.664 ✅**  |
|               |  LPIPS ↓   |    0.402     |   0.665    |    0.432     |    0.389     | **0.304 ✅**  |

**Add the method LLGS (ICASSP) for comparison on the LOM dataset. Training with a mixed dataset of normal-light and low-light images(Note: ✅ indicates the best-performing metric for each evaluation item.)**

|   scene    |   metric   |    3DGS    | Aleth-NeRF |     GS-W     | Luminance-GS |    LLGS    |     Ours     |
| :--------: | :--------: | :--------: | :--------: | :----------: | :----------: | :--------: | :----------: |
|            |   PSNR ↑   |   18.447   |   9.378    | **26.747 ✅** |    20.358    |   15.753   |    22.371    |
|   "bike"   |   SSIM ↑   |   0.547    |   0.254    |    0.851     |    0.754     |   0.623    | **0.858 ✅**  |
|            |  LPIPS ↓   |   0.328    |   0.751    |    0.278     |    0.368     |   0.445    | **0.219 ✅**  |
| ---------- | ---------- | ---------- | ---------- |  ----------  |  ----------  | ---------- |  ----------  |
|            |   PSNR ↑   |   14.472   |   13.288   | **27.012 ✅** |    16.486    |   22.877   |    26.119    |
|   "buu"    |   SSIM ↑   |   0.634    |   0.633    |    0.895     |    0.741     |   0.878    | **0.916 ✅**  |
|            |  LPIPS ↓   |   0.407    |   0.639    |    0.199     |    0.376     |   0.218    | **0.176 ✅**  |
| ---------- | ---------- | ---------- | ---------- |  ----------  |  ----------  | ---------- |  ----------  |
|            |   PSNR ↑   |   16.582   |   12.229   |    19.173    |    16.161    |   16.543   | **19.845 ✅** |
|  "shrub"   |   SSIM ↑   |   0.449    |   0.169    |    0.557     |    0.667     |   0.511    | **0.714 ✅**  |
|            |  LPIPS ↓   |   0.374    |   0.713    |    0.289     |    0.207     |   0.366    | **0.204 ✅**  |


## 2. Experimental results under normal illumination conditions

### 2.1 Quantitative Comparisons (normal Lighting)

We report the SSIM/PSNR/LPIPS metrics of our method under both uniform lighting conditions (lower LPIPS = better perceptual quality) to better evaluate the contribution of our approach. 

#### The following table shows the average results of the MipNeRF360-varying dataset under normal illumination conditions.(Note: ✅ indicates the best-performing metric for each evaluation item.)

|            |    SSIM    |    PSNR     |   LPIPS    |
| :--------: | :--------: | :---------: | :--------: |
|    3DGS    |   0.870    |   28.691    |   0.182    |
| ---------- | ---------- | ----------  | ---------- |
|  Pixel-GS  |   0.886    |   29.490    |   0.152    |
| ---------- | ---------- | ----------  | ---------- |
|    Ours    | **0.895✅** | **29.601✅** | **0.108✅** |

####  The quantitative comparison results of <font color="blue">SSIM/PSNR/LPIPS</font> across all scenarios under normal illumination conditions are presented in the following table.(Note: <span style="color:red;">Red font</span> indicates the optimal metric value.)

|            |                           bicycle                            |                            bonsai                            |                           counter                            |                            garden                            |
| :--------: | :----------------------------------------------------------: | :----------------------------------------------------------: | :----------------------------------------------------------: | :----------------------------------------------------------: |
|    3DGS    |                      0.771/25.246/0.205                      |                      0.938/31.980/0.205                      |                      0.905/28.700/0.204                      |                      0.868/27.410/0.103                      |
| ---------- |                          ----------                          |                          ----------                          |                          ----------                          |                          ----------                          |
|  Pixel-GS  |      0.793/25.739/<span style="color:red;">0.173</span>      |      0.951/<span style="color:red;">32.697</span>/0.162      |                      0.921/29.299/0.162                      |      0.878/27.834/<span style="color:red;">0.094</span>      |
| ---------- |                          ----------                          |                          ----------                          |                          ----------                          |                          ----------                          |
|    Ours    | <span style="color:red;">0.808</span>/<span style="color:red;">26.365</span>/0.204 | <span style="color:red;">0.955</span>/32.183/<span style="color:red;">0.057</span> | <span style="color:red;">0.920</span>/<span style="color:red;">29.373</span>/<span style="color:red;">0.080</span> | <span style="color:red;">0.893</span>/<span style="color:red;">28.549</span>/0.096 |

|            |                           kitchen                            |                             room                             |                            stump                             |
| :--------: | :----------------------------------------------------------: | :----------------------------------------------------------: | :----------------------------------------------------------: |
|    3DGS    |                      0.922/30.317/0.129                      |                      0.914/30.632/0.220                      |                      0.775/26.550/0.210                      |
| ---------- |                          ----------                          |                          ----------                          |                          ----------                          |
|  Pixel-GS  |                      0.936/31.956/0.106                      |                      0.930/31.794/0.183                      | <span style="color:red;">0.796</span>/<span style="color:red;">27.111</span>/<span style="color:red;">0.181</span> |
| ---------- |                          ----------                          |                          ----------                          |                          ----------                          |
|    Ours    | <span style="color:red;">0.954</span>/<span style="color:red;">32.107</span>/<span style="color:red;">0.041</span> | <span style="color:red;">0.950</span>/<span style="color:red;">32.115</span>/<span style="color:red;">0.064</span> |                      0.787/26.518/0.211                      |

<font color="green">**Although our method is specifically proposed for non-uniform illumination scenarios, experimental results demonstrate that it still achieves state-of-the-art (SOTA) performance even under normal illumination conditions.**</font>





## 3. Comparison of Colors Before and After Conversion

<img src="https://github.com/zhang-y-l-hup/icassp_2026_Response/raw/3e6779475717787f9fbb050af572eab847e4b24e/images/Color%20Conversion%20Comparison.png" width="800" alt="颜色转换前后对比">

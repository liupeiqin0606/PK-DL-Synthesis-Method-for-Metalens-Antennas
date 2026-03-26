# Prior-Knowledge-Guided Deep-Learning (PK-DL) Synthesis for Metalens Antennas

[![Paper: IEEE TAP](https://img.shields.io/badge/IEEE_TAP-2022-blue)](https://doi.org/10.1109/TAP.2021.3138517)
[![Algorithm: CDCGAN](https://img.shields.io/badge/Algorithm-CDCGAN-orange)](https://www.tensorflow.org/)
[![Application: 5G/6G/Satellite](https://img.shields.io/badge/Application-Satellite_Comm-green)](https://ieeexplore.ieee.org/xpl/RecentIssue.jsp?punumber=8)

[cite_start]Official implementation of the paper: **"Prior-Knowledge-Guided Deep-Learning-Enabled Synthesis for Broadband and Large Phase Shift Range Metacells in Metalens Antenna"**. [cite: 969]

## 📖 Overview
[cite_start]This project introduces a **Prior-Knowledge-Guided (PK)** synthesis method for enhancing the transmission bandwidth and phase shift range of metacells used in metalens antennas. [cite: 971] [cite_start]The framework utilizes **Conditional Deep Convolutional Generative Adversarial Networks (CDCGAN)** to generate pixelated metacell patterns. [cite: 972, 1030]

### Key Scientific Contributions
* [cite_start]**Breaking Technical Limits**: The synthesized triple-layer metacell achieves a 1 dB phase shift range of **330°**, breaking the previous technical limit of 308°. [cite: 975, 1280]
* [cite_start]**Bandwidth Enhancement**: A Ku-band metalens antenna designed with these cells demonstrates a **52.2% increase** in 1 dB gain bandwidth and a **42.6% increase** in 3 dB gain bandwidth compared to conventional Jerusalem cross (JC) designs. [cite: 977, 1513, 1653]
* [cite_start]**Physics-Guided Efficiency**: By integrating fundamental EM theorems and antenna design experience at the early stage, the method strategically guides and speeds up the synthesis process. [cite: 973, 1034, 1038]

---

## 🛠️ Methodology & Architecture

[cite_start]The synthesis engine consists of a **Generator** (deconvolutional neural network) and a **Discriminator** (convolutional neural network). [cite: 1039, 1040, 1041]

### 1. Prior-Knowledge Integration
* [cite_start]**Geometric Symmetry**: To ensure dual-polarization properties, the metacell geometry is maintained with mirror symmetry in horizontal, vertical, and diagonal directions. [cite: 1138, 1152, 1166] 
* [cite_start]**Data Reduction**: By focusing on the upper-left quarter of the geometry, the input matrix dimension is reduced from $30 \times 30$ pixels to $15 \times 15$ pixels, saving 75% of computational load. [cite: 1139, 1153, 1154]
* [cite_start]**Basic Units (Scheme C)**: Instead of individual pixels, the method uses $1 \times 5$-pixel blocks ($0.1\lambda_0 \times 0.02\lambda_0$) as basic units to generate physically meaningful patterns more efficiently. [cite: 1182, 1184]



### 2. Implementation Details
* [cite_start]**Dataset**: More than 6,000 metacell models were built using CST Studio, ANSYS HFSS, and a progressive growth method. [cite: 1185, 1186]
* [cite_start]**Optimization**: The model uses the **Adam optimizer** with a learning rate of $2 \times 10^{-4}$. [cite: 1121]
* [cite_start]**Architecture**: The generator has four layers (256, 128, 64, N channels), and the discriminator has five layers (64, 128, 256, 512, N channels). [cite: 1053, 1063]

---

## 📊 Performance Benchmark
[cite_start]Measured results for the fabricated Ku-band metalens antenna prototype: [cite: 1515, 1570, 1603]

| Metric | [cite_start]Jerusalem Cross (JC) [cite: 1513] | [cite_start]This Work (PK-DL) [cite: 1513, 1633] | Improvement |
| :--- | :--- | :--- | :--- |
| **1-dB Gain Bandwidth** | 9.2% | **14.0%** (Sim) / **13.5%** (Meas) | **+52.2%** |
| **3-dB Gain Bandwidth** | 16.9% | **24.1%** (Sim) / **23.9%** (Meas) | **+42.6%** |
| **Aperture Efficiency** | N/A | **31.6%** (at 12 GHz) | N/A |

---

## 📜 Citation
If you find this work helpful for your research, please cite:

```bibtex
@ARTICLE{Liu2022PKDL,
  author={Liu, Peiqin and Chen, Liushifeng and Chen, Zhi Ning},
  journal={IEEE Transactions on Antennas and Propagation}, 
  title={Prior-Knowledge-Guided Deep-Learning-Enabled Synthesis for Broadband and Large Phase Shift Range Metacells in Metalens Antenna}, 
  year={2022},
  volume={70},
  number={7},
  pages={5024-5034},
  doi={10.1109/TAP.2021.3138517}}

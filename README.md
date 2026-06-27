# market-microstructure-alpha-decoder.
Quantifying information loss and parity between continuous VWAP feeds and quantized LOB indicators.
![Model Performance Parity](performance_plot.png)


## 📊 Project Overview: Signal Detection & Alpha Decoding

This project is a cross-disciplinary simulation that analyzes signal processing efficiency. It uses a mathematical framework commonly found in sensor networks and maps it onto quantitative finance data streams to compare **Continuous vs. Quantized (Binary)** information networks.

The core objective is to determine how efficiently an observer can decode a true hidden market signal ("alpha") out of a chaotic, noisy environment using two different data-gathering methods.

### 🔍 The Two Models Compared

1. **Continuous Feed Model (Gaussian Noise)**
   * [cite_start]**Financial Example:** A high-resolution, continuous data stream (e.g., a decimal price feed or VWAP)[cite: 39, 49].
   * [cite_start]**Mechanism:** The system aggregates precise numbers from $n$ feeds and takes an average[cite: 54]. [cite_start]Random noise naturally cancels out via a bell-curve (Gaussian) distribution[cite: 40, 51].
   * **Result:** Highly efficient. [cite_start]It requires fewer data feeds to reach an incredibly low error rate[cite: 112, 121].

2. **Quantized LOB Model (Binomial Majority Voting)**
   * [cite_start]**Financial Example:** A network of cheap, binary indicators (e.g., a simple Limit Order Book flag checking if an order is buy/sell or $\ge 0$)[cite: 62, 65].
   * [cite_start]**Mechanism:** The system throws away exact decimal precision, turning every indicator into a `1` or `0`[cite: 65]. [cite_start]It then decodes the signal using a **majority vote** threshold[cite: 46, 67, 68].
   * **Result:** Less efficient. [cite_start]Because precision is lost during quantization, you need significantly more indicators to match the accuracy of the continuous model[cite: 113, 121].

### 📈 Key Takeaways

* [cite_start]**The Resource Trade-off:** The simulation proves mathematically (via Binomial and Normal distributions) and empirically (via Monte Carlo simulations) that high-fidelity continuous data streams drastically reduce decision error rates compared to aggregated binary data[cite: 40, 47, 60, 70].
* **Infrastructure Implications:** In trading environments, utilizing fewer premium, high-resolution feeds minimizes computational overhead and execution latency compared to processing a massive volume of noisy, quantized indicators.

* [![Project Status: In Progress](https://img.shields.io/badge/repo--status-in--progress-yellow)](https://www.repostatus.org/#in-progress)
## 🛠️ Project Status & Roadmap
The core statistical engine, Monte Carlo simulations, and threshold optimization models are **100% complete and validated**. This repository is currently being updated with structured documentation for recruitment presentation.

- [x] Mathematical framework & analytical error bounds
- [x] Vectorized Monte Carlo verification engines
- [x] Threshold ($\tau$) optimization engine for the Parity Paradox
- [ ] Write detailed Markdown documentation explaining the financial intuition of the results
- [ ] Add formal mathematical write-up for the Binomial/Gaussian decoding proofs

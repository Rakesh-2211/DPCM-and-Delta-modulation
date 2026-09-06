
# DPCM and Delta Modulation Simulation

## Overview
This repository contains a Python simulation demonstrating the principles of **Differential Pulse Code Modulation (DPCM)** and **Delta Modulation (DM)**. The code is designed to be easily run in Google Colab or any standard Python environment.

This project was built to fulfill specific digital communication experiment objectives:
1. Using prediction to reduce sample redundancy.
2. Identifying granular noise and slope-overload distortion in delta modulation.

## Features
* **First-Order DPCM Predictor:** Implements a customizable DPCM loop with explicit separation of prediction, quantization, and reconstruction.
* **PCM vs DPCM Comparison:** Visualizes the difference in quantization and prediction errors to demonstrate redundancy reduction.
* **Delta Modulation (1-bit DPCM):** Simulates a standard delta modulator.
* **Signal Variation Tests:** Tests modulators against both slowly varying (low frequency) and rapidly varying (high frequency) inputs.
* **Distortion Visualization:** 
  * Demonstrates **Granular Noise** (step size too large for a slow signal).
  * Demonstrates **Slope-Overload Distortion** (step size too small for a fast signal).
* **MSE Analysis:** Computes and plots Mean Squared Error (MSE) versus varying step sizes ($\Delta$) to help identify optimal quantization parameters.
* **Mandatory Validation Check:** Includes an automated check ensuring each delta-modulator output step changes by exactly $+\Delta$ or $-\Delta$.

## Prerequisites
To run this simulation, you need Python installed with the following libraries:
* `numpy`
* `matplotlib`

## How to Run
### Google Colab (Recommended)
1. Open [Google Colab](https://colab.research.google.com/).
2. Create a new notebook.
3. Copy the contents of the provided python script.
4. Paste it into a cell and press `Shift + Enter` to run.

### Local Python Environment
1. Clone this repository or download the python script.
2. Ensure you have the required libraries installed: `pip install numpy matplotlib`
3. Run the script: `python dpcm_dm_simulation.py`

## Expected Visualizations
When you run the script, a single figure with four subplots will be generated:
1. **DPCM vs PCM:** Shows the original, predicted, and reconstructed signals.
2. **Error Comparison:** Plots the PCM error vs. DPCM prediction error.
3. **Granular vs. Slope Overload:** Two side-by-side graphs showing the step staircase effect on slow and fast signals.
4. **MSE vs Step Size ($\Delta$):** A graph showing the optimal step size trade-off between slope overload and granular noise.

## Observation and Interpretation
* **Granular Noise:** Occurs when the input signal is relatively flat, but the delta modulator continues to step up and down by $\Delta$, causing jaggedness.
* **Slope Overload:** Occurs when the signal amplitude changes faster than the maximum rate of change of the modulator (determined by step size $\Delta 	imes f_s$). The reconstructed signal fails to track the steep slopes.
README.md
Displaying README.md.

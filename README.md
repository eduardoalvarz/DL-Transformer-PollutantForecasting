# Deep Learning for Atmospheric Pollutant Forecasting: Transformer-Based Approach to Predict Coarse Particulate Matter (PMCO) Concentrations in Mexico City 

## Introduction

This repository hosts the research project "Deep Learning for Atmospheric Pollutant Forecasting: Transformer-Based Approach to Predict Coarse Particulate Matter (PMCO) Concentrations in Mexico City". It focuses on employing Artificial Neural Networks (ANNs) to predict PMCO particle concentrations, a significant atmospheric pollutant due to its impact on public health and the environment.

### Problem Context
PMCO particles, with diameters between 2.5 and 10 micrometers, originate from sources such as industry, transportation, fossil fuel burning, etc. They exhibit complex non-linear behaviors, posing substantial analytical challenges.

### Project Objectives
To address this challenge, the project develops and implements an advanced probabilistic transformer model for temporal prediction of PMCO concentrations. The study analyzes data collected in Mexico City during 2022, evaluating forecasts at intervals of 12, 24, 48, and 72 hours with help to Root Mean Square Error (RMSE).

<img src="https://github.com/Lmauricio14/Time-Series-Forecasting-for-Particles-PMCO-in-CDMX/blob/main/Figures/Map.PNG" width="325">

## Methodology

### 1. Data Acquisition and Preprocessing
  - 1.1 **Data Collection:** PMCO concentration data from 2022, sourced from Mexico City's RAMA, SEDEMA, 2023. 
  - 1.2 **Station Selection:** Focused on stations with minimal missing data and outliers.
  - 1.3 **Outlier Removal:** Applied z-scores method with a ±3 standard deviation threshold.
  - 1.4 **Missing Value Imputation:** Employed MICE (Multiple Imputation by Chained Equations) for handling missing data.

### 2. Model Development and Training
  - 2.1 **Transformer Architecture**: Utilizes the Encoder-Decoder structure, excelling in handling sequential data with its attention mechanism.
    - 2.1.1 **Attention Mechanism**: Focuses selectively on important data parts, crucial for time-dependent PMCO prediction.
      - Attention Formula: `Attention(Q, K, V) = Softmax((QK^T) / sqrt(d_k))V`
      - Self-Attention: `Self-Attention(X) = Softmax((XW^Q(XW^K)^T) / sqrt(d_model))XW^V`
  - 2.2 **Layer Configuration:** Balanced with 4 layers each in encoder and decoder, and a 32-dimensional model structure.
  - 2.3 **Activation Function:** Utilized ReLU for introducing non-linearity.

### 3. Training Process
  - 3.1 **Data Batching:** Formatted data into batches of 256 for each of the 100 epochs. Testing done with batches of 64.
  - 3.2 **Optimizer:** Employed AdamW optimizer for adaptive learning rates and better handling of sparse gradients, with beta values set at 0.9 and 0.95.

### 4. Forecasting and Validation
  - 4.1 **Forecasting Horizon:** Predicted future PMCO values at intervals of 12, 24, 48, and 72 hours.
  - 4.2 **Model Validation:** Used Root Mean Square Error (RMSE) to compare predictions against actual values for accuracy assessment.

### 5. Hyperparameters
  - 5.1 **Training Data Loader:** Batch size of 256 with 100 batches per epoch.
  - 5.2 **Testing Data Loader:** Batch size of 64.
  - 5.3 **Optimizer Settings:** AdamW with a 30-day look-back period.

| Project Flowchart | Transformer Algorithm Flowchart |
|-------------------|---------------------------------|
| <img src="https://github.com/Lmauricio14/Time-Series-Forecasting-for-Particles-PMCO-in-CDMX/blob/main/Figures/flowchart.svg" width="325"> | <img src="https://github.com/Lmauricio14/Time-Series-Forecasting-for-Particles-PMCO-in-CDMX/blob/main/Figures/Transformers-Arquitectura.PNG" width="325"> |


## Tools and Database Used

For this study, the following tools and database were used:

- **Python** and its libraries; Python, Pandas, Matplotlib, Seaborn, gluonts and TensorFlow/PyTorch for data processing and analysis.
- **Forcasting model**: Transformer-based deep learning neural network.
- **Data source**: Automatic Atmospheric Monitoring Network (RAMA) of Mexico City for the year 2022.
- **Selected monitoring stations**: 
  - **BJU (Benito Juárez), Mexico City:** Exhibiting the lowest range of PMCO concentration.
  - **MER (Merced), Mexico City:** Notable for a slightly higher maximum concentration.
  - **UIZ (UAM Iztapalapa), Mexico City:** Shows higher average and standard deviation of PMCO.
  - **TLA (Tlalnepantla), Mexico State:** Stands out with the highest maximum concentration and standard deviation, presenting a challenging dataset with a significant amount of missing values.

<img src=https://github.com/Lmauricio14/Time-Series-Forecasting-for-Particles-PMCO-in-CDMX/blob/main/Figures/raw-data.svg width="600">

| Estaciones | Min (µg/m³) | Max (µg/m³) | Mean (µg/m³) | σ (µg/m³) | Missing Values |
|------------|-------------|-------------|--------------|------------|----------------|
| BJU        | 1.0         | 146.0       | 13.200403    | 8.635373   | 332            |
| MER        | 1.0         | 161.0       | 17.154006    | 10.451417  | 1059           |
| UIZ        | 1.0         | 158.0       | 19.866365    | 12.862693  | 1247           |
| TLA        | 1.0         | 520.0       | 26.823141    | 18.358227  | 1336           |

## Objectives, Hypothesis, and Results of the Research

- **General Objective**: Evaluate the efficacy of Transformers in forecasting PMCO.
- **Hypothesis**: Transformers can capture temporal patterns in PMCO concentrations to make accurate predictions.
- **Results**: Visualization of forecasts generated by the model.

## Results 
Presentation of the model's results, including comparisons and accuracy analysis using Root Mean Square Error (RMSE).

Full panorama (Go to file "Forcasting" for more info):

<img src=https://github.com/Lmauricio14/Time-Series-Forecasting-for-Particles-PMCO-in-CDMX/blob/main/Forecasting/BJU.PNG width="700">
<img src=https://github.com/Lmauricio14/Time-Series-Forecasting-for-Particles-PMCO-in-CDMX/blob/main/Forecasting/MER.PNG width="700">
<img src=https://github.com/Lmauricio14/Time-Series-Forecasting-for-Particles-PMCO-in-CDMX/blob/main/Forecasting/UIZ.PNG width="700">
<img src=https://github.com/Lmauricio14/Time-Series-Forecasting-for-Particles-PMCO-in-CDMX/blob/main/Forecasting/TLA.PNG width="700">

## Confidentiality and Collaboration
Due to the confidential nature of certain aspects of this project, only the *data preprocessing code* will be shared publicly. For potential collaborations, please contact me directly at lmauricio14@alumnos.uaq.mx.

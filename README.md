# Machine Learning for Temporal Forecasting: Transformer-Based Approach to Predict Coarse Particulate Matter (PMCO) Concentrations in Mexico City

### Introduction

Time series forecasting is crucial in various fields, including science, technology, business, and economics. A significant public health and environmental concern is the concentration of suspended particles, or Particulate Matter (PM), especially in densely populated urban areas like Mexico City. Coarse Particulate Matter (PMCO), with micrometric sizes between 2.5 μm and 10 μm in diameter, is of special concern due to its ability to penetrate the lungs and bloodstream.

For this study, we use data provided by the Automatic Atmospheric Monitoring Network (RAMA), managed by the Ministry of the Environment of Mexico City (SEDEMA). RAMA is responsible for monitoring and recording air quality in this large metropolis. The study specifically focuses on PMCO particles.

![](https://github.com/Lmauricio14/Time-Series-Forecasting-for-Particles-PMCO-in-CDMX/blob/main/Estaciones/MAP.PNG)

### Tools and Database Used

For this study, the following tools and database were used:

- **Python** and its libraries (Pandas, Matplotlib, Seaborn, TensorFlow/PyTorch) for data processing and analysis.
- **Transformers** for predictive modeling.
- **RAMA Database (2022)**: Air quality data from Mexico City provided by the Automatic Atmospheric Monitoring Network.

### Data

We selected the RAMA database for the year 2022, avoiding the atypical years of the pandemic. Monitoring stations with complete and reliable records were chosen to ensure data quality.

![](https://github.com/Lmauricio14/Time-Series-Forecasting-for-Particles-PMCO-in-CDMX/blob/main/Estaciones/p001.svg)
![](https://github.com/Lmauricio14/Time-Series-Forecasting-for-Particles-PMCO-in-CDMX/blob/main/Estaciones/raw%20statistics.PNG)

### Probabilistic Forecasting and Time Series Transformer

We address the probabilistic forecasting of PMCO using Transformers, which allow for capturing long-term dependencies and modeling the uncertainty associated with predictions.

![](https://github.com/Lmauricio14/Time-Series-Forecasting-for-Particles-PMCO-in-CDMX/blob/main/Protocolo/Transformers-Arquitectura.PNG)

### Objectives, Hypothesis, and Results of the Research

- **General Objective**: Evaluate the efficacy of Transformers in forecasting PMCO.
- **Hypothesis**: Transformers can capture temporal patterns in PMCO concentrations to make accurate predictions.
- **Results**: Visualization of forecasts generated by the model.

![](https://github.com/Lmauricio14/Time-Series-Forecasting-for-Particles-PMCO-in-CDMX/blob/main/Forecasting/results_BJU.PNG)
![](https://github.com/Lmauricio14/Time-Series-Forecasting-for-Particles-PMCO-in-CDMX/blob/main/Forecasting/results_MER.PNG)
![](https://github.com/Lmauricio14/Time-Series-Forecasting-for-Particles-PMCO-in-CDMX/blob/main/Forecasting/results_UIZ.PNG)
![](https://github.com/Lmauricio14/Time-Series-Forecasting-for-Particles-PMCO-in-CDMX/blob/main/Forecasting/results_TLA.PNG)

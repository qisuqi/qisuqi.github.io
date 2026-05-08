---
title: "FocusLearn: Fully-Interpretable, High-Performance Modular Neural Networks for Time Series"
collection: publications
permalink: /publications/ijcnn
excerpt: ""
date: 2024-07-01
venue: 'IJCNN'
paperurl: 'https://ieeexplore.ieee.org/abstract/document/10651481'
citation: 'Su, Q.; Kloukinas, C.; Garcez, A (2024) &quot;FocusLearn: Fully-Interpretable, High-Performance Modular Neural Networks for Time Series.&quot; 2024 International Joint Conference on Neural Networks (IJCNN), Yokohama, Japan, 2024, pp. 1-8, doi: 10.1109/IJCNN60899.2024.10651481'
---

## Abstract

Multivariate time series have many applications, from healthcare and meteorology to life science. Although deep learning
models have shown excellent predictive performance for time series, they have been criticised for being "black-boxes" or non-interpretable. This paper proposes a novel modular neural network model for multivariate time series prediction that is interpretable by construction. A recurrent neural network learns the temporal dependencies in the data while an
attention-based feature selection component selects the most relevant features and suppresses redundant features used in the learning of the temporal dependencies. A modular deep network is trained from the selected features independently to show the users how features influence outcomes, making the model interpretable. Experimental results show that this approach can outperform state-of-the-art interpretable Neural Additive Models (NAM) and variations thereof in both regression and classification of time series tasks, achieving a predictive performance that is comparable to the top non-interpretable methods for time series, LSTM and XGBoost.

## GitHub Repo
Python code for FocusLearn is available [here.](https://github.com/qisuqi/FocusLearn)

## Bibtex

```bibtex
@INPROCEEDINGS{10651481,
  author={Su, Qiqi and Kloukinas, Christos and d’Avila Garcez, Artur},
  booktitle={2024 International Joint Conference on Neural Networks (IJCNN)}, 
  title={FocusLearn: Fully-Interpretable, High-Performance Modular Neural Networks for Time Series}, 
  year={2024},
  volume={},
  number={},
  pages={1-8},
  keywords={Representation learning;Additives;Recurrent neural networks;Time series analysis;Finance;Medical services;Artificial neural networks;Explainable Artificial Intelligence;Deep Networks;Time Series;Neural Additive Models;Modular Networks;Weighted Attention Feature Learning},
  doi={10.1109/IJCNN60899.2024.10651481}}
```
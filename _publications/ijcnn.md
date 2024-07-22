---
title: "FocusLearn: Fully-Interpretable, High-Performance Modular Neural Networks for Time Series"
collection: publications
permalink: /publication/ijcnn
excerpt: ""
date: 2024-07-01
venue: 'IJCNN'
paperurl: 'https://arxiv.org/abs/2311.16834'
citation: 'Su, Q.; Kloukinas, C.; Garcez, A (2024) &quot;FocusLearn: Fully-Interpretable, High-Performance Modular Neural Networks for Time Series.&quot; <i>arxiv.org/abs/2311.16834</i>'
---

This paper is accepted at the IJCNN 2024 in Yokohama, Japan in July 2024. A preview version of the paper is available on [arXiv](https://arxiv.org/abs/2311.16834). 

## Abstract

Multivariate time series have many applications, from healthcare and meteorology to life science. Although deep learning 
models have shown excellent predictive performance for time series, they have been criticised for being "black-boxes" or non-interpretable. This paper proposes a novel modular neural network model for multivariate time series prediction that is interpretable by construction. A recurrent neural network learns the temporal dependencies in the data while an 
attention-based feature selection component selects the most relevant features and suppresses redundant features used in the learning of the temporal dependencies. A modular deep network is trained from the selected features independently to show the users how features influence outcomes, making the model interpretable. Experimental results show that this approach can outperform state-of-the-art interpretable Neural Additive Models (NAM) and variations thereof in both regression and classification of time series tasks, achieving a predictive performance that is comparable to the top non-interpretable methods for time series, LSTM and XGBoost.

## GitHub Repo
Python code for FocusLearn is available [here.] (https://github.com/qisuqi/FocusLearn)

## Bibtex

```bibtex
@misc{su2024modular,
      title={FocusLearn: Fully-Interpretable, High-Performance Modular Neural Networks for Time Series}, 
      author={Qiqi Su and Christos Kloukinas and Artur d'Avila Garcez},
      year={2024},
      eprint={2311.16834},
      archivePrefix={arXiv},
      primaryClass={cs.LG}
}
```

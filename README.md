# momentum_former: A Simple Encoder-Only Momentum Transformer

This repository contains the implementation of a transformer-based model for futures prediction and portfolio optimization using a momentum trading strategy. The architecture is inspired by the transformer model proposed by [Kieran Wood et al. (2021)](https://arxiv.org/abs/2112.08534). Compared to their paper, this architecture simplifies the original model and includes the following essential parts:

+ Use LSTM as positional encoding.
+ Use only encoder part of a transformer.
+ Use robust volatility metrics, returns over different time scales, and MACD (Moving Average Convergence Divergence) indicators as features.
+ Use Multi-Head attention.

The model is trained and evaluated using an expanding window approach. A dataset with 24 futures from 2001 to 2023 is used. The dataset is trained for at least 10 years, validated on the following year, and tested the year after the validation year. The model performance is evaluated using an overall Sharpe ratio across test years.  

## Project Structure

- `datasets/`: Contains the custom dataset class for loading and processing futures time series data.
- `models/`: Contains the transformer model and the custom transformer layer used in the model.
- `losses/`: Contains the custom loss function for optimizing the Sharpe ratio.
- `utils/`: Contains utility functions for weight decay and trading strategy calculations.
- `train.py`: The main script for training and evaluating the model across different years.
- `requirements.txt`: Lists the dependencies required to run the project.
- `README.md`: This file, providing an overview of the project.

## Getting Started

### Installation

1. Clone the repository:
   ```sh
   git clone https://github.com/yourusername/simple-encoder-momentum-transformer.git
   cd simple-encoder-momentum-transformer
   ```

2. Install the dependencies:
   ```sh
   pip install -r requirements.txt
   ```

## References

+ Wood, K., Giegerich, S., Roberts, S., & Zohren, S. (2021). Trading with the momentum transformer: An intelligent and interpretable architecture. arXiv preprint arXiv:2112.08534.

+ Lim, B., & Zohren, S. (2021). Time-series forecasting with deep learning: a survey. Philosophical Transactions of the Royal Society A, 379(2194), 20200209.
  
+ Fischer, T., & Krauss, C. (2018). Deep learning with long short-term memory networks for financial market predictions. European journal of operational research, 270(2), 654-669.
  
+ Liang, Z., Chen, H., Zhu, J., Jiang, K., & Li, Y. (2018). Adversarial deep reinforcement learning in portfolio management. arXiv preprint arXiv:1808.09940.

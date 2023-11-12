# ADS_Phase5-CreditCard_Fraud_Detection

## Introduction

The Credit Card Fraud Detection project is designed to detect fraudulent credit card transactions using machine learning techniques. Credit card fraud is a significant concern for financial institutions and consumers. This project aims to provide a solution to identify potentially fraudulent transactions, helping to mitigate financial losses and protect consumers.

## Dataset

The dataset used for this project is stored in the file `creditcard.csv`. This dataset contains credit card transaction data with features that have undergone PCA dimensionality reduction to protect user identities and sensitive features. Each row in the dataset represents a credit card transaction, and the target variable is `Class`, where:
- `Class = 1` indicates a fraudulent transaction.
- `Class = 0` indicates a valid transaction.

## Data Exploration

Before diving into the fraud detection process, it's essential to understand the dataset's structure and characteristics. The following steps are performed for data exploration:

- The dataset is loaded using the Pandas library to create a DataFrame.
- The column names are printed using `print(data.columns)`.
- The shape of the dataset is displayed using `print(data.shape)` to provide an overview of the data size.
- Basic statistical information about the dataset is shown with `print(data.describe())`.
- Histograms of each parameter are plotted using Matplotlib to visualize the distribution of data.

## Outlier Detection

Detecting outliers (potentially fraudulent transactions) is a crucial step in this project. Two different outlier detection algorithms are employed:

1. **Isolation Forest:**
   - The Isolation Forest algorithm is used with the following parameters:
     - `max_samples`: The maximum number of samples used to build the isolation tree.
     - `contamination`: The expected proportion of outliers in the dataset.
     - `random_state`: A random seed for reproducibility.
   - This algorithm is efficient in identifying anomalies in high-dimensional data.

2. **Local Outlier Factor (LOF):**
   - The Local Outlier Factor algorithm is used with the following parameter:
     - `n_neighbors`: The number of neighbors considered for each data point.
     - `contamination`: The expected proportion of outliers in the dataset.
   - LOF is a density-based outlier detection method that identifies anomalies based on the local density deviation of data points.

The results of both algorithms are evaluated to identify potential fraudulent transactions. The `outlier_fraction` is calculated as the ratio of fraudulent cases to valid transactions.

## Getting Started

To run this project on your local machine, follow these steps:

### Prerequisites

Ensure you have the following prerequisites installed:

- Python 3.x
- Required Python libraries: numpy, pandas, matplotlib, seaborn, scipy, scikit-learn

### Installation

1. Clone the repository to your local machine:

   ```bash
   $ git clone https://github.com/yourusername/credit-card-fraud-detection.git
   $ cd credit-card-fraud-detection

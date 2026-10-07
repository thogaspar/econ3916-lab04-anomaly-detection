# econ3916-lab04-anomaly-detection
ECON 3916 Lab 04 - Automated Anomaly Detection
# Robust Statistics - Automated Anomaly Detection

## Objective

I compared how different summary statistics and outlier detection methods behave on California Housing prices, and tested which ones hold up when part of the data is corrupted.

## Methodology

- Loaded the California Housing data (20,640 observations).
- Computed summary statistics that are sensitive to outliers (mean, standard deviation) and ones that are not (median, trimmed mean, IQR, MAD).
- Wrote the Tukey Fences rule by hand to flag price outliers.
- Ran Isolation Forest to flag anomalies using several features at once.
- Compared the observations flagged by Tukey Fences with those flagged by Isolation Forest.
- Corrupted 5% of the data and recomputed all the statistics to see how far each one moved.

## Key Findings

- Tukey Fences and Isolation Forest flagged different observations. Tukey Fences looks only at price, while Isolation Forest looks at all the features together, so each one catches cases the other misses.
- After I corrupted 5% of the data, the mean shifted by 67.1%, while the median shifted by only 3.6%.
- The median, trimmed mean, IQR, and MAD stayed close to their original values under corruption. The mean and standard deviation did not.

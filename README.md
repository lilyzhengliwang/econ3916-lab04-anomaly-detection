# econ3916-lab04-anomaly-detection
Project Title: Robust Statistics — Automated Anomaly Detection

Objective: I compared how different summary statistics and two outlier-detection methods react to extreme values in housing price data.

Methodology:

Calculated mean, median, trimmed mean, standard deviation, IQR, and MAD on California Housing data (20,640 observations)
Built Tukey Fences by hand to flag prices falling outside 1.5 times the IQR
Ran an Isolation Forest to flag unusual rows using all the housing features at once, not just price
Compared which rows each method flagged and checked where they overlapped
Replaced 5% of the price values with extreme numbers and recalculated every statistic to see which ones held steady

Key Findings:

Tukey Fences flagged 1,071 of 20,640 rows (5.2%), and the Isolation Forest flagged 1,032 rows (5.0%), but the two methods only agreed on 165 of those rows — most flagged rows were different between methods
After contaminating 5% of the price values, the mean shifted by 67.13%, while the median shifted by only 3.56%
Standard deviation moved even more than the mean (478.38%), while IQR and MAD barely changed (10.32% and 9.21%), showing a clear split between measures that get pulled by extreme values and ones that don't

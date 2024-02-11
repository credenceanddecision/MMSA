# Measure marketing performance at the sub-channel level (individual channel partners, platforms, etc)

This tool deploys Shapley Value Regression to analyze marketing performance at the level of individual channel partners, complementing traditional channel-level Marketing Mix Modeling (MMM). Shapley Value Regression allows us to understand the specific impact of each marketing partner within a channel. 

## Usage

To begin analysis:

1. Prepare your dataset in an Excel file, ensuring it follows the format of the example provided (`channel_partner_v1.xlsx`).
2. Open the provided Jupyter notebook.
3. Modify the `path` and `sheet_name` parameters in the `read_data` function to match your dataset.
4. Execute the notebook cells in sequence to carry out the analysis.

## Methodology

This tool employs Shapley Value Regression to assess the impact of each channel partner on marketing outcomes. By considering all possible combinations of channel partners, it calculates the marginal contribution of each partner, thereby quantifying their impact on overall marketing effectiveness.

The input data is a time-series data that is stored as an Excel file with column headers. The first column is the date (in weeks), the last column is the dependent variable while the rest are independent variables. Only basic packages are used to produce the Shapley Value Regression and the co-efficient following the steps illustrated in the above section. Please note this is not to be confused with packages like SHAP that aim to explain the variable importance in machine learning models. 

## Interpretation

The analysis outputs include R-squared (R²) values and coefficients derived from linear regression models, quantifying the influence of various marketing partners on sales. R² values indicate the proportion of variance in sales attributed to the partners, while coefficients adjust these contributions based on Shapley value calculations, offering a nuanced view of each partner's relative importance and contribution.



Shapley Value Regression offers a promising avenue to unravel partner-level performance within marketing channels. Its ability to dissect contributions without succumbing to multicollinearity presents a valuable tool for marketers.

The code is based on:

Tang, S., Musunuru, S., Zong, B. and Thornton, B., 2024. Quantifying Marketing Performance at Channel-Partner Level by Using Marketing Mix Modeling (MMM) and Shapley Value Regression. arXiv preprint arXiv:2401.05653.

## Example inputs
<img src="images/img3.png" alt="" width="650">

## Example outputs

<img src="images/img2.png" alt="" width="650">


|    | Independent Variables                                   | R Squared | Coefficients                           |
|----|--------------------------------------------------------|-----------|----------------------------------------|
| 1  | ('partner_a',)                                          | 0.36      | [0.60]                                 |
| 2  | ('partner_b',)                                          | 0.06      | [-0.24]                                |
| 3  | ('partner_c',)                                          | 0.02      | [0.13]                                 |
| 4  | ('partner_d',)                                          | 0.12      | [0.35]                                 |
| 5  | ('partner_e',)                                          | 0.17      | [0.41]                                 |
| 6  | ('partner_a', 'partner_b')                              | 0.40      | [0.58, -0.19]                          |
| 7  | ('partner_a', 'partner_c')                              | 0.56      | [0.82, 0.49]                           |
| 8  | ('partner_a', 'partner_d')                              | 0.81      | [0.92, 0.74]                           |
| 9  | ('partner_a', 'partner_e')                              | 0.36      | [0.60, -0.01]                          |
| 10 | ('partner_b', 'partner_c')                              | 0.07      | [-0.23, 0.11]                          |
| 11 | ('partner_b', 'partner_d')                              | 0.14      | [-0.14, 0.31]                          |
| 12 | ('partner_b', 'partner_e')                              | 0.28      | [-0.33, 0.47]                          |
| 13 | ('partner_c', 'partner_d')                              | 0.16      | [-0.27, 0.55]                          |
| 14 | ('partner_c', 'partner_e')                              | 0.29      | [0.39, 0.58]                           |
| 15 | ('partner_d', 'partner_e')                              | 0.53      | [0.67, 0.71]                           |
| 16 | ('partner_a', 'partner_b', 'partner_c')                 | 0.57      | [0.80, -0.13, 0.47]                    |
| 17 | ('partner_a', 'partner_b', 'partner_d')                 | 0.82      | [0.95, 0.12, 0.80]                     |
| 18 | ('partner_a', 'partner_b', 'partner_e')                 | 0.40      | [0.51, -0.21, 0.10]                    |
| 19 | ('partner_a', 'partner_c', 'partner_d')                 | 0.81      | [0.91, -0.01, 0.75]                    |
| 20 | ('partner_a', 'partner_c', 'partner_e')                 | 0.56      | [0.74, 0.52, 0.13]                     |
| 21 | ('partner_a', 'partner_d', 'partner_e')                 | 0.84      | [0.78, 0.79, 0.22]                     |
| 22 | ('partner_b', 'partner_c', 'partner_d')                 | 0.17      | [-0.09, -0.23, 0.49]                   |
| 23 | ('partner_b', 'partner_c', 'partner_e')                 | 0.40      | [-0.33, 0.39, 0.64]                    |
| 24 | ('partner_b', 'partner_d', 'partner_e')                 | 0.56      | [-0.16, 0.62, 0.72]                    |
| 25 | ('partner_c', 'partner_d', 'partner_e')                 | 0.54      | [-0.09, 0.74, 0.70]                    |
| 26 | ('partner_a', 'partner_b', 'partner_c', 'partner_d')    | 0.83      | [0.95, 0.13, -0.05, 0.83]              |
| 27 | ('partner_a', 'partner_b', 'partner_c', 'partner_e')    | 0.59      | [0.66, -0.18, 0.50, 0.21]              |

and so on




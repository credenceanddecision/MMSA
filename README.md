# Sub-Channel Marketing Performance Analysis Tool

This tool applies Shapley Value Regression to dissect marketing performance at the granular level of individual channel partners, enhancing the broader insights gained from traditional Marketing Mix Modeling (MMM). It's designed to pinpoint the distinct influence each partner has within a channel.

## How to Use

Follow these steps to conduct your analysis:

1. Format your data according to the structure in the provided Excel template (`channel_partner_v1.xlsx`).
2. Launch the Jupyter notebook included in this repository.
3. Update the `path` and `sheet_name` in the `read_data` function to correspond to your Excel file.
4. Run the notebook cells consecutively to perform the analysis.

## Understanding the Methodology

Shapley Value Regression is at the core of this tool, measuring each channel partner's marginal contribution to marketing success. It examines all permutations of partner combinations to quantify their individual impacts.

Input data should be time-series, organized in an Excel spreadsheet with the date (by week) as the first column, followed by independent variables, and concluding with the dependent variable (sales) in the last column. We utilize fundamental Python packages for the regression and subsequent coefficient calculation. It's important to distinguish this approach from other libraries like SHAP, which are typically used for variable importance in machine learning models.

## Interpreting Results

The output comprises R-squared (R²) values and Shapley Value adjusted coefficients from linear regression analyses. These metrics measure the extent of sales variability explained by the marketing partners' efforts and their weighted contribution, respectively. Such insights afford a deeper understanding of each partner's impact on sales. Shapley Value Regression is a useful approach for elucidating performance at the partner level within marketing channels, handling multicollinearity to provide clear-cut contribution metrics.

## Understanding Shapley Value Regression

Shapley Value Regression is a technique that addresses the challenge of assessing the importance of attributes in a linear regression model. Typically, attribute significance is inferred from the model's coefficients. However, when a model includes a multitude of independent variables, it's often unrealistic to assume that all these variables are mutually independent. More often than not, some variables are collinear, meaning they are highly correlated with one another.

In a simplified scenario, one might opt to eliminate collinear attributes before performing the regression analysis. Yet, in complex real-world business cases, every selected attribute carries weight and significance, making it impractical to discard collinear variables arbitrarily. This is where the need arises to accurately measure the importance of each attribute, despite the presence of collinearity.

Shapley Value Regression, also known by several other names such as Shapley regression, Shapley Value analysis, Kruskal analysis, dominance analysis, and incremental R-squared analysis, provides a solution. It's particularly useful in situations where independent variables in a linear regression are moderately to highly correlated. Beyond its application in linear regression, this method is also valuable for calculating the contribution of each predictor in statistical analyses, offering a robust approach to attribute importance quantification.


## Credits

This code is inspired by the following research:

Tang, S., Musunuru, S., Zong, B. and Thornton, B., 2024. Quantifying Marketing Performance at Channel-Partner Level by Using Marketing Mix Modeling (MMM) and Shapley Value Regression. arXiv preprint arXiv:2401.05653.

## Sample Data Input
<img src="images/img3.png" alt="" width="650">

## Sample Analysis Output
<img src="images/img2.png" alt="" width="650">

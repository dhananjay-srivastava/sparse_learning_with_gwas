Based on the content of the PowerPoint slides, here is a `README.md` that summarizes the presentation:

---

# Sparse Learning on GWAS

## Authors
- Dhananjay
- Poorva
- Subhranil
- Mansi

## Table of Contents
1. [Dataset Description](#dataset-description)
2. [Approach 1: Generalized Linear Models (GLM)](#approach-1-generalized-linear-models-glm)
3. [Approach 2: LASSO Regression](#approach-2-lasso-regression)
4. [Approach 3: RIDGE Regression](#approach-3-ridge-regression)
5. [Approach 4: Elastic Net Regression](#approach-4-elastic-net-regression)
6. [Approach 5: L0-Regularized Regression](#approach-5-l0-regularized-regression)
7. [Conclusion](#conclusion)
8. [References](#references)

## Dataset Description

- **Simulated Dataset**: 100 observations with varying number of SNPs (500, 1000, and 2000).
- **Predictor Variable**: Calculated by applying a weight matrix with 10 non-zero values and passing through a logistic function with a cutoff value of 0.5.
- **Active SNPs**: These 10 values are considered the "active" SNPs in the dataset.

## Approach 1: Generalized Linear Models (GLM)

- **Description**: Any distribution of the form can be considered a member of the exponential family. GLM models can be solved by Newton's method.
- **Implementation in R**: Base R package.
- **Results**: 
  - Overall accuracy: 0.54 (for p=500, 1000, 2000)
  - Most coefficient p-values were either 1 or NA.
  
## Approach 2: LASSO Regression

- **Description**: Regression model using L1 Regularization, resulting in sparse models with few coefficients.
- **Results**: 
  - Accuracy and number of non-zero coefficients:
    - p=500: 0.70, 5
    - p=1000: 0.68, 8
    - p=2000: 0.70, 4

## Approach 3: RIDGE Regression

- **Description**: Regression model using L2 Regularization, which reduces unimportant coefficients but not necessarily to zero.
- **Results**: 
  - Accuracy:
    - p=500: 0.60
    - p=1000: 0.52
    - p=2000: 0.64

## Approach 4: Elastic Net Regression

- **Description**: Combines penalties from both Lasso and Ridge to regularize regression models.
- **Results**: 
  - Accuracy:
    - p=500: 0.70
    - p=1000: 0.68
    - p=2000: 0.72

## Approach 5: L0-Regularized Regression

- **Description**: Uses L0 penalty for the number of non-zero coefficients, with L1 or L2 regularization added.
- **Results**: 
  - Accuracy:
    - p=500: 0.96
    - p=1000: 0.96
    - p=2000: 0.96

## Coefficient Comparison

- **L0Learn vs. LASSO**: 
  - L0Learn with L0L1 penalty (p=500): Accuracy 0.96, Support Size 10
  - L0Learn with L0L2 penalty (p=500): Accuracy 0.88, Support Size 10

## Conclusion

L0Learn demonstrates high accuracy and effectively identifies a subset of active SNPs, especially in sparse data scenarios. It outperforms Lasso in selecting the correct coefficients.

## References

- [Generalized Linear Models in R](https://www.rdocumentation.org/packages/stats/versions/3.6.2/topics/glm)
- [L0Learn Package](https://cran.r-project.org/web/packages/L0Learn/index.html)
- [GLMNET Package](https://cran.r-project.org/web/packages/glmnet/index.html)
- [Research Paper on Sparse Learning](https://jmlr.csail.mit.edu/papers/volume22/19-1049/19-1049.pdf)
- [Introduction to Logistic Regression and Lasso Regularization](https://eight2late.wordpress.com/2017/07/11/a-gentle-introduction-to-logistic-regression-and-lasso-regularisation-using-r/)

---

This `README.md` provides a detailed summary of the PowerPoint presentation on Sparse Learning on GWAS.

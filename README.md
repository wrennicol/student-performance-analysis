# Student Performance Data Analysis

Builds a regression model in R to predict student exam scores and find which factors matter most.

**Tools:** R, ggplot2, tidyverse

## Data
6,607 students, 19 predictors (study habits, family background, school factors) and an exam score. Data file: `StudentPerformanceFactors.csv`

## What I did
1. **Full model:** linear regression with all 19 predictors (R² = 0.7275)
2. **Forward selection (AIC):** dropped 3 predictors (sleep hours, gender, school type), leaving 16
3. **Interaction:** added Learning Disabilities × Physical Activity, which improved the fit
4. **ANOVA vs. ANCOVA:** compared one-variable models using access to resources (ANOVA) and access to resources plus attendance (ANCOVA). ANCOVA fit better.
5. **Final comparison:** the forward selection model with the interaction beat the ANCOVA model on AIC, BIC, R², and RMSE

## Final model
R² = 0.7277, adjusted R² = 0.7265, residual standard error = 2.03 points.

- Each extra hour studied is associated with about +0.29 exam points, and each extra percentage point of attendance with about +0.20
- Low access to resources or low parental involvement is associated with about 2 fewer points compared to high
- Family and home factors (parental involvement, income, parental education) appeared throughout the model
- Sleep hours, gender, and school type were not selected

## Limitations
- The improvement over the full model is very small (R² 0.7275 to 0.7277); the main benefit is a simpler model
- These are associations, not proof that any factor causes higher scores
- A few students have very large prediction errors (the largest is about 30 points)

## Files
- `finalproject.R`: full analysis code
- `StudentPerformanceFactors.csv`: data

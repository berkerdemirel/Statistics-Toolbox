# A Toolbox for ANOVA and Linear Regression
## ANOVA Functions

- **ANOVA1_partition_TSS**: Given a dataset of X_ij for j = 1,...,J and i = 1,...,I, it returns SS_total SS_w and SS_b.
- **ANOVA1_test_equality**: Given an alpha and a dataset of X_ij for j = 1,...,J and i = 1,...,I, it returns outcome of the hypothesis "Group means are equal" with p-value and critical values.
- **ANOVA1_is_contrast**: Given a vector c of dimension I, it returns if given vector is a contrast.
- **ANOVA1_is_orthogonal**: Given group sizes and two vector (c1 and c2) of dimension I, it returns if c1 and c2 are orthogonal. It also returns a warning when they are not contrasts.
- **Bonferroni_correction**: Given FWER alpha and number of tests (m), it returns the significance level that each test needs to satisfy for Bonferroni correction.
- **Sidak_correction**: Given FWER alpha and number of tests (m), it returns the significance level that each test needs to satisfy for Sidak correction.
- **ANOVA1_CI_linear_combs**: Given a dataset of X_ij for j = 1,...,J and i = 1,...,I, significance level alpha, a matrix C of dimensions mxI (contains m contrasts each representing a test) and a method parameter (can be Scheffe, Tukey, Bonferroni, Sidak, or Best), it returns simultaneous confidence intervals for those linear combinations.
- **ANOVA1_test_linear_combs**: Given a dataset of X_ij for j = 1,...,J and i = 1,...,I, significance level alpha, a matrix C of dimensions mxI (contains m contrasts each representing a test), a method parameter (can be Scheffe, Tukey, Bonferroni, Sidak, or Best) and a vector d of dimension mx1 (each d_i claims the outcome of the corresponding linear combination), it returns test outcomes in such a way that FWER is kept at alpha 
- **ANOVA2_partition_TSS**: Given a dataset of X_ijk for k = 1,...,K, j = 1,...,J and i = 1,...,I, it returns SS_total, SS_a, SS_b, SS_ab and SS_e
- **ANOVA2_MLE**: Given a dataset of X_ijk for k = 1,...,K, j = 1,...,J and i = 1,...,I, it returns maximum likelihood estimates of mean, a_i, b_j, and delta_ij
- **ANOVA2_test_equality**: Given a dataset of X_ijk for k = 1,...,K, j = 1,...,J and i = 1,...,I and significance level alpha, it returns the test statistics of -depending on choice- a_i's are equal or b_j's are equal or delta_ij's are equal in a tabular format.

## Linear Regression Functions

- **Mult_LR_Least_squares**: Function takes X (design matrix) and y (response vector), and returns maximum likelihood estimates of Beta, sigma^2 and also unbiased estimate of sigma^2
- **Mult_LR_partition_TSS**: Given a matrix X of dimensions nx(k+1) and y of dimensions nx1, it returns total sum of squares, regression sum of squares and residual sum of squares.
- **Mult_norm_LR_simul_CI**: Given X (design matrix) and y (response vector) and significance level alpha, it returns the simultaneous confidence intervals for each Beta_i that simultaneously hold with probability alpha.
- **Mult_norm_LR_CR**: Given X (design matrix) and y (response vector), matrix C of dimensions rx(k+1) with rank r, and significance level alpha, it returns the parameters of the ellipsoid of the 100(1-alpha)% confidence region for C*Beta according to the normal multiple linear regression model.
- **Mult_norm_LR_is_in_CR**: Given X (design matrix) and y (response vector), matrix C of dimensions rx(k+1) with rank r, vector c0 of dimensions rx1, and significance level alpha it returns whether c0 is inside the confidence region for C*Beta.
- **Mult_norm_LR_test_general**: Given X (design matrix) and y (response vector), matrix C of dimensions rx(k+1) with rank r, vector c0 of dimensions rx1, and significance level alpha it returns whether the hypothesis H0:C*Beta = c0 holds at a significance level alpha.
- **Mult_norm_LR_test_comp**: Given X (design matrix) and y (response vector), j1,j2,...,jr with each j_i is inside {0,...,k} and a significance level alpha, it returns the outcome of hypothesis H0: Beta_j1=0, Beta_j2=0,..., Beta_jr=0 at alpha.
- **Mult_norm_LR_test_linear_reg**: Given X (design matrix) and y (response vector), and significance level alpha, it returns whether there is linear regression at all. (in other words, it returns if at least one of the Beta_i's is significant)
- **Mult_norm_LR_pred_CI**: Given X (design matrix) and y (response vector), matrix D of dimensions mx(k+1), a significance level alpha, and a method (which can be Bonferroni, Scheffe or Best), and return simultaneous confidence bounds for d_i*Beta for all i=1,2,...,m that hold simultaneously with probability 1-alpha.
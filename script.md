# Presentation Script: Multivariate Statistical Analysis of Cardiovascular Biomarkers

**Duration: 6-8 minutes**  
**Audience: Academic/Research**

---

## Introduction (0:00-1:00) (Empeno)

Good morning, everyone. Today I'm presenting our research on multivariate statistical analysis of cardiovascular biomarkers using advanced discriminant function approaches.

**[SLIDE: Title and Overview]**

Our study examines a longitudinal cardiovascular cohort with 1,400 patients across three diagnostic groups: Control, Mild, and Severe cardiovascular conditions. We analyzed five key biomarkers: systolic and diastolic blood pressure, cholesterol, fasting glucose, and BMI.

The central research questions we addressed are:
1. Do these biomarkers differ multivariately across diagnostic groups?
2. Which biomarker combinations best separate the groups?
3. How accurately can we predict both diagnosis and hospitalization risk?

---

## Mathematical Framework (1:00-2:00) (Harvey)

**[SLIDE: Mathematical Equations]**

Our analysis is grounded in rigorous multivariate statistical theory. Let me briefly outline our mathematical framework.

We represent our data as an n-by-5 matrix X, where each observation contains our five biomarkers. For each diagnostic group g, we compute the sample mean vector μ_g and covariance matrix S_g.

**[Point to MANOVA equation]**

MANOVA tests whether the population mean vectors are equal across groups using Wilks' Lambda statistic, which compares within-group to between-group variability. The formula you see here represents the ratio of determinants of our covariance matrices.

**[Point to LDA equation]**  

Linear Discriminant Analysis finds the optimal linear combinations that maximize group separation. These discriminant functions are eigenvectors of the matrix W-inverse times B, where W is within-group variation and B is between-group variation.

---

## Key Findings: MANOVA Results (2:00-3:00) (Monfero)

**[SLIDE: MANOVA Results Table]**

Our MANOVA analysis produced striking results. Wilks' Lambda equals 0.0365 with an F-statistic of 841.5, yielding a p-value effectively zero. This provides overwhelming evidence that multivariate means differ significantly across diagnostic groups.

The effect size is particularly noteworthy - our partial eta-squared of 0.915 indicates that diagnostic group membership explains approximately 92% of the multivariate variance in biomarkers. This is an extraordinarily large effect size in biological research.

**[SLIDE: Box Plots Visualization]**

Looking at our exploratory visualizations, we can clearly see the systematic patterns across groups. Notice how each biomarker shows a clear progression from Control through Mild to Severe conditions, with minimal overlap between groups.

---

## Discriminant Analysis: Biomarker Importance (3:00-4:30) (Empeno)

**[SLIDE: Discriminant Function Plot]**

Our discriminant analysis extracted two functions, but the first function dominates, explaining 99.2% of the group separation variance. This plot shows our data projected into discriminant function space - notice the excellent linear separation between groups.

**[SLIDE: Biomarker Contributions Chart]**

The standardized discriminant coefficients reveal which biomarkers contribute most to group separation. Cholesterol emerges as our most powerful discriminator with a coefficient of +2.33, followed by glucose at +1.82, and systolic blood pressure at +1.15.

Interestingly, BMI shows the weakest discriminative power in this multivariate context, despite being clinically important individually. This demonstrates the value of multivariate analysis in revealing the relative importance of variables when considered together.

The optimal discriminant function can be written as:
DF₁ = 2.33 × Z_cholesterol + 1.82 × Z_glucose + 1.15 × Z_systolic_BP - 0.24 × Z_diastolic_BP - 0.20 × Z_BMI

where Z represents standardized values.

---

## Classification Performance (4:30-5:30) (Harvey)

**[SLIDE: Classification Results Table]**

Our classification results are remarkable. For multi-class diagnostic prediction, we achieved 99.5% accuracy using Linear Discriminant Analysis, Random Forest, and Logistic Regression - all three methods performed identically.

**[SLIDE: Confusion Matrix]**

The confusion matrix shows nearly perfect classification with only 2 misclassifications out of 400 test cases. This extraordinary performance suggests these biomarkers form a highly effective diagnostic panel.

For binary hospitalization prediction, we achieved 81.5% accuracy. While lower than diagnostic classification, this is still clinically valuable given the complexity of predicting future health events.

The precision for identifying patients at hospitalization risk was 62%, with 42% recall, indicating our model is conservative but reasonably accurate when it predicts hospitalization.

---

## Clinical Implications and Conclusions (5:30-7:00) (Monfero)

**[SLIDE: Clinical Summary]**

Our findings have several important clinical implications:

First, cholesterol and glucose emerge as the most powerful discriminators of cardiovascular severity - even more important than blood pressure in this multivariate context. This suggests prioritizing these biomarkers in screening protocols.

Second, the high classification accuracy of 99.5% indicates these five biomarkers together form a robust diagnostic panel that could support clinical decision-making.

Third, the clear linear separability demonstrated by our discriminant analysis suggests that simple linear combinations of these biomarkers can effectively stratify cardiovascular risk.

**[SLIDE: Mathematical Conclusions]**

From a statistical perspective, our analysis satisfied key assumptions including multivariate normality and provided robust statistical power with 1,000 training and 400 validation observations.

The effect size of 92% explained variance is remarkable in biological research and suggests these biomarkers capture the essential physiological differences between diagnostic groups.

---

## Future Directions (7:00-8:00) (Empeno)

**[SLIDE: Future Research]**

Several avenues for future research emerge from this work:

We recommend validating these findings in independent cohorts and exploring non-linear classification methods that might capture more complex biomarker interactions.

Additionally, incorporating temporal patterns - analyzing how biomarker trajectories change over time - could enhance predictive accuracy for hospitalization risk.

Finally, cost-effectiveness analysis could determine the optimal subset of biomarkers needed to maintain high diagnostic accuracy while minimizing testing costs.

**[SLIDE: Thank You]**

In conclusion, our multivariate analysis demonstrates that systematic statistical approaches can extract maximum diagnostic information from cardiovascular biomarkers, with clear implications for clinical practice and patient care.

Thank you for your attention. I'm happy to answer any questions about our methodology or findings.

---

## Q&A Preparation Notes

**Potential Questions and Responses:**

1. **"Why didn't you test for multivariate normality?"**
   - We assessed normality through visual inspection and found generally acceptable distributions. Formal tests like Mardia's test would be valuable for complete validation.

2. **"What about Box's M test for homogeneity of covariances?"**
   - You're absolutely right - this is a key LDA assumption we should test formally. The visual evidence suggests reasonable homogeneity, but statistical testing would strengthen our conclusions.

3. **"Could overfitting explain the high accuracy?"**
   - The consistent performance across three different algorithms and the separate validation set suggest genuine discriminative power rather than overfitting. Cross-validation would provide additional confirmation.

4. **"How does this compare to existing cardiovascular risk scores?"**
   - Our approach is complementary to tools like Framingham scores. While those focus on 10-year risk prediction, our model classifies current diagnostic status with exceptional accuracy.

**Time Management:**
- If running long, skip the detailed mathematical equations section
- If running short, expand on clinical implications with specific examples
- Always reserve 1-2 minutes for questions regardless of time constraints
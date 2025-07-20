## Bias Detection

- Detecting bias in data and models is very important to make sure machine learning systems are fair and do not discriminate.
- Many algorithms, tools, and fairness checks (called fairness metrics) have been created to help with this.
- Common ways to detect bias include:
  1. Pre-processing the data
  2. Using special algorithms
  3. Using tools
  4. Checking fairness metrics

---

### Data Pre-processing

- Before training a model, it’s important to check the data for any unfair patterns.
- This can include removing or hiding sensitive information like gender or race, so the model does not learn unfair connections.
- **Pre-train metrics:** These check if the training data is fair *before* building the model. They help find hidden biases in the dataset.
  1. **Statistical Parity Difference:** Compares how often positive results (like being approved for a loan) happen for privileged vs. unprivileged groups.
  2. **Disparate Impact Ratio:** Looks at the ratio of positive outcomes between different groups.
  3. **Smooth Empirical Differential:** Checks the difference in chances of positive results for different groups.

- **Post-train metrics:** These check if the trained model’s predictions are fair. They show if any bias appeared during training.
  1. **Four Fifths Rule:** Compares success rates between groups to see if one group is unfairly favored.
  2. **Cohen's D:** Measures how big the bias is in the model’s predictions.

---

### Bias Detection Algorithms

Different algorithms can check if there is bias in data or models. Here are some common ones with simple examples:

**a. Statistical Parity**

- Checks if different groups get similar results, no matter their protected traits.
- **Example:** Imagine a hiring AI system. If 70% of men get selected but only 30% of women do, statistical parity would detect this gap and show it as a bias.

**b. Equalized Odds**

- Checks if the model makes similar types of mistakes for different groups.
- Looks at false positives (wrongly predicting something is positive) and false negatives (wrongly predicting something is negative).
- **Example:** A loan approval model might approve unqualified applicants. If it wrongly approves 20% of people in one group but only 5% in another, that shows bias. Equalized odds checks if these mistake rates are similar for everyone.

- To do this, it uses:
  1. **True Positive Rate (TPR):** How often the model correctly predicts positive cases.
  2. **False Positive Rate (FPR):** How often the model wrongly predicts positive cases.
  3. **True Negative Rate (TNR):** How often the model correctly predicts negative cases.
  4. **False Negative Rate (FNR):** How often the model wrongly predicts negative cases.

- The goal is for these rates to be similar for all groups.

**c. Conditional Demographic Disparity**

- Checks if the model gives similar results to different groups when they have the same inputs.
- **Example:** Suppose two people with the same credit score, income, and job apply for a loan — but one gets approved and the other doesn’t just because they belong to different groups. This shows conditional demographic disparity.

---

### Bias Detection Tools

There are many tools available to help find and fix bias in data and machine learning models.

1. **Google’s What-If Tool**
   - This is an interactive tool that helps you see how a machine learning model behaves.
   - You can test how fair your model is by checking how it treats different groups.
   - It lets you:
     - Try “what-if” scenarios to see how changing inputs affects predictions.
     - Check fairness metrics.
     - Look at results for different demographic groups.

2. **AI Fairness 360**
   - This is a free, open-source toolkit created by IBM.
   - It has many algorithms and fairness checks to find and fix bias in data and models.
   - It includes:
     - Fairness metrics like disparate impact, equal opportunity, and Theil index.
     - Methods to fix bias, like re-weighting the data or adjusting the model.

---

### Fairness Metrics

Fairness metrics help measure and check if a machine learning model is treating different groups fairly.

1. **Disparate Impact:**  
   - This measures the difference in the chances of getting a positive result (like being approved for a job or loan) between different groups.  
   - If the value is below 1, it may mean one group is being treated unfairly.  
   - *Example:* If 80% of one group gets approved but only 50% of another group does, this shows possible bias.

2. **Equalized Odds:**  
   - This checks if the model makes similar mistakes for different groups.  
   - It looks at false positives (wrong positive predictions) and false negatives (wrong negative predictions).  
   - If the mistake rates are very different between groups, that means there could be bias.

3. **Average Odds Difference:**  
   - This measures the average gap in false positive and false negative rates between groups.  
   - A higher value means there may be unfair differences in how the model predicts for each group.

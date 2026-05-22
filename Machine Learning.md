# **Linear Regression:**

* **# Step 1: Import necessary libraries**
* **import numpy as np**
* **import pandas as pd**
* **from sklearn.linear\_model import LinearRegression**
* **from sklearn.model\_selection import train\_test\_split**
* **from sklearn.metrics import mean\_squared\_error, r2\_score**
* 
* **# Step 2: Example dataset (replace with your own data)**
* **# Features (X) and Target (y)**
* **X = np.array(\[\[1], \[2], \[3], \[4], \[5]])   # Independent variable**
* **y = np.array(\[1, 2, 3, 4, 5])             # Dependent variable**
* 
* **# Step 3: Split dataset into training and testing sets**
* **X\_train, X\_test, y\_train, y\_test = train\_test\_split(X, y, test\_size=0.2, random\_state=42)**
* 
* **# Step 4: Create and train the Linear Regression model**
* **model = LinearRegression()**
* **model.fit(X\_train, y\_train)**
* 
* **# Step 5: Make predictions**
* **y\_pred = model.predict(X\_test)**
* 
* **# Step 6: Evaluate the model**
* **print("Coefficients:", model.coef\_)**
* **print("Intercept:", model.intercept\_)**
* **print("Mean Squared Error:", mean\_squared\_error(y\_test, y\_pred)) # squared=False: gives rmse : but depricated. Use root\_mean\_squared\_error().**
* **print("R^2 Score:", r2\_score(y\_test, y\_pred))**





\# R²: measures the goodness of fit of a regression model. It tells you how much better your model predicts the data compared to simply using the mean of the target variable.

\- Range:

\- 0 ≤ R² ≤ 1 (for most cases).

\- R² = 1 → Perfect fit (model explains all variance).

\- R² = 0 → Model explains none of the variance (no better than predicting the mean).

\- Negative R² → Model performs worse than a horizontal line at the mean.

\- Interpretation:

\- High R² (close to 1): Strong relationship between predictors and target.

\- Low R² (close to 0): Weak relationship; predictors don’t explain much variance.

\- Important caveat: A high R² doesn’t always mean the model is good — it could be overfitting. Similarly, a low R² isn’t always bad, especially in fields where data is inherently noisy (like social sciences).



# **Logistic Regression:**

* **# Step 1: Import necessary libraries**
* **import numpy as np**
* **import pandas as pd**
* **from sklearn.linear\_model import LogisticRegression**
* **from sklearn.model\_selection import train\_test\_split**
* **from sklearn.metrics import accuracy\_score, confusion\_matrix, classification\_report**
* 
* **# Step 2: Example dataset (replace with your own data)**
* **# Features (X) and Target (y)**
* **X = np.array(\[\[2, 3], \[1, 5], \[2, 8], \[5, 7], \[6, 9], \[7, 10]])  # Independent variables**
* **y = np.array(\[0, 0, 0, 1, 1, 1])                                # Binary target (0 or 1)**
* 
* **# Step 3: Split dataset into training and testing sets**
* **X\_train, X\_test, y\_train, y\_test = train\_test\_split(X, y, test\_size=0.3, random\_state=42)**
* 
* **# Step 4: Create and train the Logistic Regression model**
* **model = LogisticRegression()**
* **model.fit(X\_train, y\_train)**
* 
* **# Step 5: Make predictions**
* **y\_pred = model.predict(X\_test)**
* **y\_prob = model.predict\_proba(X\_test)**
* 
* **# Step 6: Evaluate the model**
* **print("Predictions:", y\_pred)**
* **print("Accuracy:", accuracy\_score(y\_test, y\_pred))**
* **print("Confusion Matrix:\\n", confusion\_matrix(y\_test, y\_pred))**
* **print("Classification Report:\\n", classification\_report(y\_test, y\_pred))**





**📊 Accuracy**



Definition: The proportion of correctly predicted instances out of the total predictions.

Formula:  Accuracy = (Number of correct predictions)/(Total predictions)

 

Interpretation: Easy to understand, but can be misleading if the dataset is imbalanced (e.g., 95% of samples are class 0, predicting all as 0 gives 95% accuracy but is useless).



🟦 **Confusion Matrix**



Definition: A table that shows counts of correct and incorrect predictions broken down by each class.

Structure (for binary classification):



|                | Predicted Positive | Predicted Negative |

|----------------|--------------------|--------------------|

| Actual Positive| True Positive (TP) | False Negative (FN)|

| Actual Negative| False Positive (FP)| True Negative (TN) |



Interpretation:

  TP: Correctly predicted positives.

  TN: Correctly predicted negatives.

  FP: Incorrectly predicted positives (false alarms).

  FN: Missed positives (false dismissals).



📑 **Classification Report**

This summarizes \*\*Precision, Recall, and F1-score\*\* for each class:



***Precision:***

Definition: Out of all predicted positives, how many are actually positive.

Formula:  Precision = (TP)/(TP + FP)

 

Interpretation: High precision means fewer false alarms.





***Recall (Sensitivity / True Positive Rate):***

Definition: Out of all actual positives, how many did the model correctly identify.

Formula: Recall = (TP)/(TP + FN)

 

Interpretation: High recall means fewer missed cases.



***F1-score:***

Definition: Harmonic mean of Precision and Recall. Balances the two.

Formula:

 

  F1 = 2 . (Precision . Recall)/(Precision + Recall)

 

Interpretation: Useful when you want a balance between precision and recall, especially with imbalanced datasets.





**Metric              Definition                                Formula**

**-------------------------------------------------------------------------------**

**Accuracy            Proportion of correct predictions         (TP + TN) / (TP+TN+FP+FN)**

**Confusion Matrix    Table of TP, TN, FP, FN                   N/A**

**Precision           Correct positives out of predicted pos.   TP / (TP + FP)**

**Recall              Correct positives out of actual pos.      TP / (TP + FN)**

**F1-score            Balance of precision \& recall             2 \* (Prec\*Rec) / (Prec+Rec)**



**⚖️ Quick Example**

Imagine a spam filter:

\- Accuracy: Overall % of emails correctly classified.

\- Confusion Matrix: Shows how many spams were caught (TP), how many spams were missed (FN), how many normal emails were wrongly flagged (FP), and how many were correctly passed (TN).

\- Precision: Of all emails flagged as spam, how many were truly spam.

\- Recall: Of all actual spam emails, how many were caught.

\- F1-score: A single number balancing precision and recall.





## 📊 **Linear vs Logistic Regression: Training Loss \& Evaluation Metrics**

 

**Linear Regression:** Loss/error metrics directly measure prediction quality. - Evaluated by distance-based errors.



**Logistic Regression:** Loss (cross-entropy) is used during training, but evaluation focuses on classification metrics because the end goal is correct class assignment, not minimizing numeric distance.





**Aspect               Linear Regression                                Logistic Regression**

**-----------------------------------------------------------------------------------------------**

**Goal                 Predict continuous values (e.g., price).         Predict categorical outcomes (e.g., spam/not spam).**

**Training Loss        Minimizes Mean Squared Error (MSE).              Minimizes Log Loss (Cross-Entropy).**

**Error Function       Squared difference between predicted \& actual.   Negative log-likelihood of probabilities vs labels.**

**Evaluation Metrics   RMSE, MSE, MAE, R² score.                        Accuracy, Precision, Recall, F1-score, ROC-AUC.**

**Interpretation       Focus on distance from actual values.            Focus on correct class assignment.**

**Common Pitfall       Sensitive to outliers.                           Accuracy misleading with imbalanced datasets.**









# **Decision Tree:**



A Decision Tree is a supervised machine learning algorithm that uses a tree‑like structure of rules to make predictions or classifications. It splits data into subsets based on feature values, creating branches until reaching final outcomes at leaf nodes



Structure of a Decision Tree:

\- Root Node → Represents the entire dataset and the first feature split.

\- Branches → Paths showing decisions based on feature values.

\- Internal Nodes → Points where the dataset is split further according to conditions.

\- Leaf Nodes → Endpoints that represent the final prediction (class label or numeric value).



How It Works:

\- Select the best feature to split data at each node.

\- Criteria: Gini impurity, Entropy (Information Gain), or MSE (for regression).

\- Recursive splitting → The dataset is divided into smaller subsets until nodes are pure or stopping conditions are met.

\- Prediction → For classification, the majority class at a leaf is chosen. For regression, the average value at a leaf is returned.



Types of Decision Trees

\- Classification Trees → Used when the target variable is categorical (e.g., spam vs not spam).

\- Regression Trees → Used when the target variable is continuous (e.g., predicting house prices).



Gini impurity measures how mixed classes are in a node.

\- Pure node = all samples belong to one class → Gini = 0.

\- Impure node = samples are mixed across classes → Gini > 0.

Decision trees aim to split data so nodes become as pure as possible.



👉 In short: \*\*“Making a node pure” means splitting the data until each node contains samples of only one class (or nearly so), which reduces Gini impurity to zero.\*\*





#### **DecisionTreeClassifier: For classification**

* **# Step 1: Import necessary libraries**
* **import numpy as np**
* **import pandas as pd**
* **from sklearn.tree import DecisionTreeClassifier**
* **from sklearn.model\_selection import train\_test\_split**
* **from sklearn.metrics import accuracy\_score, confusion\_matrix, classification\_report**
* 
* **# Step 2: Example dataset (replace with your own data)**
* **# Features (X) and Target (y)**
* **X = np.array(\[\[2, 3], \[1, 5], \[2, 8], \[5, 7], \[6, 9], \[7, 10]])  # Independent variables**
* **y = np.array(\[0, 0, 0, 1, 1, 1])                                # Binary target (0 or 1)**
* 
* **# Step 3: Split dataset into training and testing sets**
* **X\_train, X\_test, y\_train, y\_test = train\_test\_split(X, y, test\_size=0.3, random\_state=42)**
* 
* **# Step 4: Create and train the Decision Tree model**
* **model = DecisionTreeClassifier(criterion="gini", max\_depth=3, random\_state=42)   # max\_depth: controls tree depth (prevents overfitting)**
* **model.fit(X\_train, y\_train)**
* 
* **# Step 5: Make predictions**
* **y\_pred = model.predict(X\_test)**
* 
* **# Step 6: Evaluate the model**
* **print("Predictions:", y\_pred)**
* **print("Accuracy:", accuracy\_score(y\_test, y\_pred))**
* **print("Confusion Matrix:\\n", confusion\_matrix(y\_test, y\_pred))**
* **print("Classification Report:\\n", classification\_report(y\_test, y\_pred))**





###### **Gini:**  Gini is a measure of impurity. The Decision Tree keeps splitting until nodes are as pure (low Gini) as possible.

Interpretation:

\- Gini = 0 → Pure node (all samples belong to one class).

\- Higher Gini → More mixed classes (more impurity).

\- The Decision Tree algorithm splits data to minimize Gini impurity, i.e., to make nodes as pure as possible.



\- criterion="gini" → Uses Gini impurity to decide splits.

\- criterion="entropy" → Uses Information Gain (based on Shannon entropy).



Both aim to reduce impurity, but Gini is computationally faster and often the default in Scikit-learn.







Aspect              Gini Impurity                               Entropy (Information Gain)

---

Definition          Probability of misclassification.           Measure of uncertainty (Shannon theory).

Formula             Gini = 1 - Σ p\_i^2                          Entropy = - Σ p\_i \* log2(p\_i)

Range               0 (pure) to ~0.5 (binary).                  0 (pure) to 1 (binary).

Interpretation      Lower Gini = purer node.                    Lower Entropy = purer node.

Computation Speed   Faster (no logs).                           Slower (uses logs).

Default in sklearn  Yes (criterion="gini").                     No (criterion="entropy").

Use Cases           Preferred for speed/simplicity.             Preferred for interpretability.





#### **DecisionTreeRegressor: For continuous value prediction**

* **# Step 1: Import necessary libraries**
* **import numpy as np**
* **import pandas as pd**
* **from sklearn.tree import DecisionTreeRegressor**
* **from sklearn.model\_selection import train\_test\_split**
* **from sklearn.metrics import mean\_squared\_error, mean\_absolute\_error, r2\_score**
* 
* **# Step 2: Example dataset (replace with your own data)**
* **# Features (X) and Target (y)**
* **X = np.array(\[\[1], \[2], \[3], \[4], \[5], \[6], \[7], \[8]])   # Independent variable**
* **y = np.array(\[1.2, 1.9, 3.1, 3.9, 5.2, 6.1, 7.1, 8.2])   # Continuous target**
* 
* **# Step 3: Split dataset into training and testing sets**
* **X\_train, X\_test, y\_train, y\_test = train\_test\_split(X, y, test\_size=0.3, random\_state=42)**
* 
* **# Step 4: Create and train the Decision Tree Regressor**
* **model = DecisionTreeRegressor(max\_depth=3, random\_state=42)**
* **model.fit(X\_train, y\_train)**
* 
* **# Step 5: Make predictions**
* **y\_pred = model.predict(X\_test)**
* 
* **# Step 6: Evaluate the model with regression metrics**
* **mse = mean\_squared\_error(y\_test, y\_pred)**
* **rmse = mean\_squared\_error(y\_test, y\_pred, squared=False)  # RMSE directly**
* **mae = mean\_absolute\_error(y\_test, y\_pred)**
* **r2 = r2\_score(y\_test, y\_pred)**
* 
* **print("Mean Squared Error (MSE):", mse)**
* **print("Root Mean Squared Error (RMSE):", rmse)**
* **print("Mean Absolute Error (MAE):", mae)**
* **print("R² Score:", r2)**





#### **Metrics Comparison:**

Decision Tree Classifier Metrics:

\- Accuracy: Overall correctness.

\- Confusion Matrix: TP, TN, FP, FN breakdown.

\- Precision: TP / (TP + FP).

\- Recall: TP / (TP + FN).

\- F1-score: Balance of precision \& recall.

\- ROC-AUC: Class separation ability.



Decision Tree Regressor Metrics:

\- MSE: Average squared error.

\- RMSE: Square root of MSE.

\- MAE: Average absolute error.

\- R² Score: Variance explained by the model.





#### **Plot Tree:**

* **# Step 1: Import libraries**
* **import numpy as np**
* **import matplotlib.pyplot as plt**
* **from sklearn.tree import DecisionTreeClassifier, plot\_tree**
* **from sklearn.model\_selection import train\_test\_split**
* 
* **# Step 2: Example dataset (replace with your own data)**
* **X = np.array(\[\[2, 3], \[1, 5], \[2, 8], \[5, 7], \[6, 9], \[7, 10]])  # Features**
* **y = np.array(\[0, 0, 0, 1, 1, 1])                                # Target classes**
* 
* **# Step 3: Train-test split**
* **X\_train, X\_test, y\_train, y\_test = train\_test\_split(X, y, test\_size=0.3, random\_state=42)**
* 
* **# Step 4: Train Decision Tree**
* **model = DecisionTreeClassifier(criterion="gini", max\_depth=3, random\_state=42)**
* **model.fit(X\_train, y\_train)**
* 
* **# Step 5: Plot the tree**
* **plt.figure(figsize=(10,6))**
* **plot\_tree(**
*  	model,
*  	feature\_names=\["Feature1", "Feature2"],	 # Replace with your actual feature names\*\*
*  	class\_names=\["Class0", "Class1"],        # Replace with your actual class labels\*\*
*  	filled=True,                             # Color nodes by class\*\*
*  	rounded=True,                            # Rounded corners for readability\*\*
*  	fontsize=10,                             # Font size for text\*\*
*  	proportion=True,                         # Show proportions instead of raw counts\*\*
*  	impurity=True,                           # Show Gini/Entropy values\*\*
* **)**
* **plt.show()**





# **Random Forest:**



Definition: Random Forest is an \*\***ensemble learning algorithm**\*\* that builds multiple decision trees and combines their outputs to improve accuracy and reduce overfitting.

It’s called a “forest” because it consists of many decision trees working together.



**How It Works:**

1\. Bootstrap Sampling (Bagging):

   - The algorithm creates multiple subsets of the training data by sampling with replacement.

   - Each subset is used to train a separate decision tree.



2\. Random Feature Selection:

   - At each split in a tree, only a random subset of features is considered.

   - This ensures diversity among trees and prevents them from all making the same splits.



3\. Aggregation of Predictions:

   - Classification: Each tree votes for a class, and the majority vote is the final prediction.

   - Regression: Each tree outputs a numeric value, and the average of all trees is the final prediction.





Random Forest is an ensemble algorithm that builds many decision trees.

\- Uses bootstrap sampling (bagging) and random feature selection.

\- Classification: majority vote of trees.

\- Regression: average of tree outputs.

Advantages: reduces overfitting, robust, handles classification \& regression.

Limitations: less interpretable, slower, more computationally expensive.



👉 In short: \*\*Random Forest = many diverse decision trees working together → stronger, more reliable predictions.\*\*





### **🌳 Random Forest Classifier (Classification):**

* **# Step 1: Import libraries**
* **import numpy as np**
* **from sklearn.ensemble import RandomForestClassifier**
* **from sklearn.model\_selection import train\_test\_split**
* **from sklearn.metrics import accuracy\_score, confusion\_matrix, classification\_report**
* 
* **# Step 2: Example dataset (replace with your own data)**
* **X = np.array(\[\[2, 3], \[1, 5], \[2, 8], \[5, 7], \[6, 9], \[7, 10]])  # Features**
* **y = np.array(\[0, 0, 0, 1, 1, 1])                                # Target classes**
* 
* **# Step 3: Train-test split**
* **X\_train, X\_test, y\_train, y\_test = train\_test\_split(X, y, test\_size=0.3, random\_state=42)**
* 
* **# Step 4: Train Random Forest Classifier**
* **clf = RandomForestClassifier(n\_estimators=100, criterion="gini", max\_depth=3, random\_state=42)   # n\_estimators: No. of trees in the forest**
* **clf.fit(X\_train, y\_train)**
* 
* **# Step 5: Predictions**
* **y\_pred = clf.predict(X\_test)**
* 
* **# Step 6: Evaluation Metrics**
* **print("Accuracy:", accuracy\_score(y\_test, y\_pred))**
* **print("Confusion Matrix:\\n", confusion\_matrix(y\_test, y\_pred))**
* **print("Classification Report:\\n", classification\_report(y\_test, y\_pred))**





### **🌳 Random Forest Regressor (Regression):**

* **# Step 1: Import libraries**
* **import numpy as np**
* **from sklearn.ensemble import RandomForestRegressor**
* **from sklearn.model\_selection import train\_test\_split**
* **from sklearn.metrics import mean\_squared\_error, mean\_absolute\_error, r2\_score**
* 
* **# Step 2: Example dataset (replace with your own data)**
* **X = np.array(\[\[1], \[2], \[3], \[4], \[5], \[6], \[7], \[8]])   # Features**
* **y = np.array(\[1.2, 1.9, 3.1, 3.9, 5.2, 6.1, 7.1, 8.2])   # Continuous target**
* 
* **# Step 3: Train-test split**
* **X\_train, X\_test, y\_train, y\_test = train\_test\_split(X, y, test\_size=0.3, random\_state=42)**
* 
* **# Step 4: Train Random Forest Regressor**
* **reg = RandomForestRegressor(n\_estimators=100, max\_depth=3, random\_state=42)**
* **reg.fit(X\_train, y\_train)**
* 
* **# Step 5: Predictions**
* **y\_pred = reg.predict(X\_test)**
* 
* **# Step 6: Evaluation Metrics**
* **mse = mean\_squared\_error(y\_test, y\_pred)**
* **rmse = mean\_squared\_error(y\_test, y\_pred, squared=False)**
* **mae = mean\_absolute\_error(y\_test, y\_pred)**
* **r2 = r2\_score(y\_test, y\_pred)**
* 
* **print("Mean Squared Error (MSE):", mse)**
* **print("Root Mean Squared Error (RMSE):", rmse)**
* **print("Mean Absolute Error (MAE):", mae)**
* **print("R² Score:", r2)**





### **Random Forest Classifier vs Regressor:**



Aspect               Random Forest Classifier                         Random Forest Regressor

---

Goal                 Predict categorical outcomes.                    Predict continuous values.

Training Criterion   Gini impurity or Entropy.                        Mean Squared Error reduction.

Output               Class labels (0/1 or multi-class).               Continuous numeric predictions.

Evaluation Metrics   Accuracy, Confusion Matrix, Precision, Recall,   MSE, RMSE, MAE, R² Score.

                     F1-score, ROC-AUC.

Interpretation       Focus on correct class assignment.               Focus on closeness to actual values.

Common Pitfall       Accuracy misleading with imbalanced data.        Sensitive to outliers, risk of overfitting.

Use Cases            Spam detection, fraud, medical diagnosis.        Price prediction, demand forecasting, risk modeling.





###### **Pitfall Handle**

######  

Classifier: Need Precision/Recall/F1.







Regression: The situation is different because the outputs are continuous, not categorical.

🌳 Regression Pitfalls \& How They’re Handled



**Pitfall 1: Sensitivity to Outliers**

Problem: Metrics like \*\*MSE\*\* and \*\*RMSE\*\* square the errors, so large outliers dominate the evaluation.

Solution: Use \*\*MAE (Mean Absolute Error)\*\*, which treats all errors equally, or \*\*Median Absolute Error\*\*, which is even more robust to outliers.



Pitfall 2: Scale Dependence

Problem: Raw error values (MSE, RMSE, MAE) depend on the scale of the target variable (e.g., predicting house prices vs predicting temperatures).

Solution: Use R² Score (Coefficient of Determination), which is scale-independent and shows how much variance is explained by the model.



Pitfall 3: Overfitting

Problem: A Random Forest Regressor (or any flexible regressor) can fit training data too closely, leading to poor generalization.

Solution: Compare metrics on \*\*training vs test sets\*\*. If training error is very low but test error is high, that’s overfitting. Cross-validation helps too.



Pitfall 4: Different Error Perspectives

Problem: A single metric may not capture the full picture.

Solution:Report multiple metrics together:

  - MSE/RMSE → penalizes large errors more.

  - MAE → average error magnitude.

  - R² → variance explained.





Regression Pitfalls \& Solutions:

\- Outliers dominate MSE/RMSE → handled by MAE or Median Absolute Error.

\- Scale dependence → handled by R² Score (scale-independent).

\- Overfitting risk → handled by comparing train vs test metrics, or cross-validation.

\- Single metric limitation → handled by reporting multiple metrics (MSE, RMSE, MAE, R²).



👉 In short:

\- Classification pitfall (accuracy misleading) → handled by \*\*Precision/Recall/F1.

\- Regression pitfalls (outliers, scale, overfitting) → handled by MAE, R², cross-validation, and reporting multiple metrics together.


# **Feature Engineering**



## **Working with numerical data:**



**How a model ingests data using feature vectors**



* Models ingest data through floating-point arrays called feature vectors, which are derived from dataset features.
* Feature vectors often utilize processed or transformed values instead of raw dataset values to enhance model learning.
* very value in a feature vector must be a floating-point value.
* Feature engineering is the crucial process of converting raw data into suitable representations for the model, encompassing techniques like **normalization** and **binning**.
* Non-numerical data like strings must be converted into numerical values for use in feature vectors, a key aspect of feature engineering.



You must determine the best way to represent raw dataset values as trainable values in the feature vector. This process is called **feature engineering**, and it is a vital part of machine learning.



The most common feature engineering techniques are:

* **Normalization**: Converting numerical values into a standard range.
* **Binning** (also referred to as **bucketing**): Converting numerical values into buckets of ranges.





Feature value(actual): 8.6, 132.9

Feature vector: \[8.6, 132.9] - Not ingested like this.

Feature vector: \[0.13, 0.47] - Here feature values are scaled in a range





**Numerical Data: First Step**

* Before creating feature vectors, it is crucial to analyze numerical data by visualizing it through plots and graphs and calculating basic statistics like mean, median, and standard deviation and quartiles.



* Visualizations, such as scatter plots and histograms, can reveal anomalies and patterns in the data, aiding in identifying potential issues early in the data analysis process.



* Outliers, values significantly distant from others, should be identified and handled appropriately, either by correcting mistakes, retaining legitimate outliers for model training, or applying techniques like clipping.



* Statistical evaluation helps in understanding the distribution and characteristics of data, providing insights into potential feature and label relationships.



* While basic statistics and visualizations provide valuable insights, it's essential to remain vigilant as anomalies can still exist in seemingly well-balanced data.



**Find outliers:**

An outlier is a value distant from most other values in a feature or label. Outliers often cause problems in model training, so finding outliers is important.



* When the **delta(absolute/positive difference) between the 0th and 25th percentiles** differs significantly from the **delta between the 75th and 100th percentiles**, the dataset probably contains outliers.
* When the standard deviation is almost as high as the mean



Note: Don't over-rely on basic statistics. Anomalies can also hide in seemingly well-balanced data.



Outliers can fall into any of the following categories:



* The outlier is due to a mistake. For example, perhaps an experimenter mistakenly entered an extra zero, or perhaps an instrument that gathered data malfunctioned. You'll generally delete examples containing mistake outliers.
* The outlier is a legitimate data point, not a mistake. In this case, will your trained model ultimately need to infer good predictions on these outliers?

 	1. If yes, keep these outliers in your training set. After all, outliers in certain features sometimes mirror outliers in the label, so the outliers 	   could actually help your model make better predictions. Be careful, extreme outliers can still hurt your model.

 	2. If no, delete the outliers or apply more invasive feature engineering techniques, such as clipping (reducing extreme outliers to max or min threshold).







### **Numerical Data: Normalization**

Data normalization is crucial for enhancing machine learning model performance by scaling features to a similar range.



* Helps models converge more quickly during training.
* Helps models infer better predictions. When different features have different ranges, the resulting model might make somewhat less useful predictions.
* Helps avoid the "NaN trap" when feature values are very high.
* Helps the model learn appropriate weights for each feature. Without feature scaling, the model pays too much attention to features with wide ranges and not enough attention to features with narrow ranges.



###### **If you normalize a feature during training, you must also normalize that feature when making predictions.**



Linear scaling, Z-score scaling, and log scaling are common normalization techniques, each suitable for different data distributions.



Clipping helps manage outliers by limiting extreme values within a defined range, improving model robustness.



Selecting the appropriate normalization method depends on the specific dataset and feature characteristics, often requiring experimentation for optimal results.



Applying normalization consistently during both training and prediction stages ensures accurate and reliable model outcomes.





===============================================================

        NORMALIZATION TECHNIQUES COMPARISON (Plain Text)

===============================================================



1\. Linear Scaling (Min-Max Normalization)

   Formula: x' = (x - xmin) / (xmax - xmin)

   When to use:

     - Features have different ranges but need same scale

     - Distance-based models (KNN, Neural Networks)

   Notes:

     - Preserves relationships

     - Sensitive to outliers



---



2\. Z-Score Normalization (Standardization)

   Formula: x' = (x - μ) / σ

   When to use:

     - Data is normally distributed

     - Algorithms assuming Gaussian distribution (Regression, PCA)

   Notes:

     - Centers data at mean 0, variance 1

     - Less sensitive to outliers than min-max



---



3\. Log Transformation

   Formula: x' = log(x + 1)

   When to use:

     - Data is highly skewed or exponential

     - Reduce impact of large values (rainfall, income, population)

   Notes:

     - Only works for positive values

     - Helps normalize skewed distributions



---



4\. Clipping (Winsorization)

   Formula: x' = min(max(x, L), U)   \[L=lower bound, U=upper bound]

   When to use:

     - Extreme outliers distort dataset

     - Robust models where you want to cap extreme values

   Notes:

     - Limits influence of outliers

     - Doesn’t change distribution shape much



===============================================================

Quick Guidelines:

\- Linear Scaling → Best for bounded ranges and distance-based models

\- Z-Score → Best when features follow Gaussian distribution

\- Log → Best for skewed/exponential data (like rainfall amounts)

\- Clipping → Best when outliers dominate

===============================================================







### **Numerical Data: Binning/Bucketing**



* Binning is a feature engineering technique used to group numerical data into categories (bins/buckets) to improve model performance when a linear relationship is weak or data is clustered.
* 
* Binning can be beneficial when features exhibit a "clumpy" distribution rather than a linear one, allowing the model to learn separate weights for each bin.
* 
* While creating multiple bins is possible, it's generally recommended to avoid an excessive number as it can lead to insufficient training examples per bin and increased feature dimensionality.
* 
* Quantile bucketing is a specific binning technique that ensures each bin contains a roughly equal number of examples, which can be particularly useful for datasets with skewed distributions.
* 
* Binning offers an alternative to scaling or clipping and is particularly useful for handling outliers and improving model performance on non-linear data.





### **Numerical Data: Scrubbing**

* Like sorting good apples from bad, ML engineers spend significant time cleaning data by removing or fixing bad examples to improve dataset quality.
* 
* Common data problems include omitted values, duplicate examples, out-of-range values, and incorrect labels, which can negatively impact model performance.
* 
* You can use programs or scripts to identify and handle data issues such as omitted values, duplicates, and out-of-range feature values by removing or correcting them.
* 
* When multiple individuals label data, it's important to check for consistency and identify potential biases to ensure label quality.
* 
* Addressing data quality issues before training a model leads to better model accuracy and overall performance.







### Qualities of Good Numerical Features



* Good feature vectors require features that are clearly named and have obvious meanings to anyone on the project.
* 
* Data should be checked and tested for bad data or outliers like inappropriate values before being used for training.
* 
* Features should be sensible, avoiding "magic values(value having no explanation like in watch\_time\_in\_seconds there is -1)" that create discontinuities; instead, use separate boolean features or new discrete values to indicate missing data.
* 
* Continuous features should not have magic values representing the absence of measurement, but rather use separate Boolean features or discrete values.
* 
* Discrete numerical features with missing values should be assigned a new value within the finite set, enabling the model to learn weights for each value including missing features.





### **Numerical Data: Polynomial Transforms**



* Synthetic features, like polynomial transforms, enable linear models to represent non-linear relationships by introducing new features based on existing ones.
* 
* Polynomial transforms involve raising an existing feature to a power, often informed by domain knowledge, such as physical laws involving squared terms.
* 
* By incorporating synthetic features, linear regression models can effectively separate data points that are not linearly separable using curves instead of straight lines.
* 
* This approach maintains the simplicity of linear regression while expanding its capacity to capture complex patterns within the data.





## **Numerical Data: Conclusion**



* A machine learning model's predictive ability is directly dependent on the quality of data it's trained on.
* 
* Numerical features often benefit from normalization or binning to improve model performance.
* 
* Data validation through verification tests and visualizations(scatter or histogram) is crucial for identifying and addressing potential issues.
* 
* Understanding data distribution through statistics on both the entire dataset and its subsets is essential for identifying hidden problems.
* 
* Maintaining thorough documentation of all data transformations ensures reproducibility and facilitates model understanding.









# **Working with Categorical Data**





**Encoding** means converting categorical or other data to numerical vectors that a model can train on. This conversion is necessary because models can only train on floating-point values; models can't train on strings such as "dog" or "maple".



* Dimension refers to the number of elements in a feature vector, and some categorical features have low dimensionality.
* 
* Machine learning models require numerical input; therefore, categorical data like strings must be converted to numerical representations.



###### **One-hot encoding** transforms categorical values into numerical vectors where each category is represented by a unique element with a value of 1.



For high-dimensional categorical features with numerous categories, one-hot encoding might be inefficient, and **embeddings or hashing** are recommended.



Sparse representation efficiently stores one-hot encoded data by only recording the position of the '1' value to reduce memory usage.



A feature whose values are predominantly zero (or empty) is termed a sparse feature.



E.g.: \[0, 0, 1, 0, 0, 0, 0, 0]



Since the 1 is in position 2 (when starting the count at 0), the sparse representation for the preceding one-hot vector is:2



Notice that the sparse representation consumes far less memory than the eight-element one-hot vector. Importantly, the model must train on the one-hot vector, not the sparse representation.





##### **Outliers in categorical data**

Like numerical data, categorical data also contains outliers. Suppose car\_color contains not only the popular colors, but also some rarely used outlier colors, such as "Mauve" or "Avocado". Rather than giving each of these outlier colors a separate category, you can lump them into a single "catch-all" category called **out-of-vocabulary (OOV)**. In other words, all the outlier colors are binned into a single outlier bucket. The system learns a single weight for that outlier bucket.



###### **Categorical Data: Common Issues**

* Categorical data quality hinges on how categories are defined and labeled, impacting data reliability.
* 
* Human-labeled data, known as "gold labels," is generally preferred for training due to its higher quality, but it's essential to check for human errors and biases.
* 
* Machine-labeled data, or "silver labels," can introduce biases or inaccuracies, necessitating careful quality checks and awareness of potential common-sense violations.
* 
* Any two human beings may label the same example differently. The difference between human raters' decisions is called **inter-rater agreement**.



* High-dimensionality(high no. of elements in feature vector) in categorical data increases training complexity and costs, leading to techniques like embeddings for dimensionality reduction.



##### **Feature Crosses**



* Feature crosses are created by combining/ crossing (taking the Cartesian product of) two or more categorical or bucketed features to capture interactions and nonlinearities within a dataset.
* 
* They enable linear models to handle nonlinearities similar to polynomial transforms, but feature crosses work with categorical data while polynomial transforms are applied to numerical data.
* 
* Feature crosses can be particularly effective when guided by domain expertise, but using neural networks can automate the process of discovering valuable combinations.
* 
* Overuse of feature crosses with sparse features should be avoided, as it can lead to excessive sparsity in the resulting feature set.



For example, consider a leaf dataset with the categorical features:



* edges, containing values smooth, toothed, and lobed
* arrangement, containing values opposite and alternate



Assume the order above is the order of the feature columns in a one-hot representation, so that a leaf with smooth edges and opposite arrangement is represented as {(1, 0, 0), (1, 0)}.



The feature cross, or Cartesian product, of these two features would be:



{Smooth\_Opposite, Smooth\_Alternate, Toothed\_Opposite, Toothed\_Alternate, Lobed\_Opposite, Lobed\_Alternate}



where the value of each term is the product of the base feature values, such that:



Smooth\_Opposite = edges\[0] \* arrangement\[0]

Smooth\_Alternate = edges\[0] \* arrangement\[1]

Toothed\_Opposite = edges\[1] \* arrangement\[0]

Toothed\_Alternate = edges\[1] \* arrangement\[1]

Lobed\_Opposite = edges\[2] \* arrangement\[0]

Lobed\_Alternate = edges\[2] \* arrangement\[1]



For example, if a leaf has a lobed edge and an alternate arrangement, the feature-cross vector will have a value of 1 for Lobed\_Alternate, and a value of 0 for all other terms: {0, 0, 0, 0, 0, 1}.


# **Dataset**

Collection of examples.



Data Types: Numerical, categorical, human language(words, sentence, entire text doc), multimedia(image, audio, video files), outputs from other ml system, embedding vectors.



###### **Characteristics**:

* A machine learning model's performance is heavily reliant on the quality and quantity of the dataset it's trained on, with larger, high-quality datasets generally leading to better results.
* 
* Datasets can contain various data types, including numerical, categorical, text, multimedia, and embedding vectors, each requiring specific handling for optimal model training.
* 
* Maintaining data quality involves addressing issues like label errors, noisy features, and proper filtering to ensure the reliability of the dataset for accurate predictions.
* 
* Incomplete examples with missing feature values should be handled by either deletion or imputation to avoid negatively impacting model training.
* 
* When imputing missing values, use reliable methods like mean/median imputation and consider adding an indicator column to signal imputed values to the model.





###### **Labels:**

* **Direct labels**, which are labels identical to the prediction your model is trying to make. That is, the prediction your model is trying to make is exactly present as a column in your dataset.
* **Proxy labels**, which are labels that are similar—but not identical—to the prediction your model is trying to make.
* Direct labels are generally better than proxy labels. If your dataset provides a possible direct label, you should probably use it. 
* Proxy labels are always a compromise—an imperfect approximation of a direct label. However, some proxy labels are close enough approximations to be useful.
* Sometimes, a direct label exists but can't be easily represented as a floating-point number. In this case, use a proxy label.



Human-generated-data: Some data is human-generated; that is, one or more humans examine some information and provide a value, usually for the label.

Automated-data: Software (possibly, another machine learning model) determines the value.





**Class-balanced Dataset:** The number of positive classes and negative classes is about equal.

**Class-imbalanced Dataset:** One label(i.e. either of the classes) is considerably more common than the other.

* The more common label is called the **majority class**.
* The less common label is called the **minority class**.



###### **The difficulty of training severely class-imbalanced datasets**

Training aims to create a model that successfully distinguishes the positive class from the negative class. To do so, batches need a sufficient number of both positive classes and negative classes. That's not a problem when training on a mildly class-imbalanced dataset since even small batches typically contain sufficient examples of both the positive class and the negative class. However, a severely class-imbalanced dataset might not contain enough minority class examples for proper training.





##### **Training a class-imbalanced dataset**



During training, a model should learn two things:

* What each class looks like; that is, what feature values correspond to what class?
* How common each class is; that is, what is the relative distribution of the classes?



Standard training conflates these two goals. 

In contrast, the following two-step technique called **downsampling and upweighting the majority class** separates these two goals, enabling the model to achieve both goals.



**Step 1: Downsample the majority class**

Downsampling means training on a disproportionately low percentage of majority class examples. That is, you artificially force a class-imbalanced dataset to become somewhat more balanced by omitting many of the majority class examples from training. Downsampling greatly increases the probability that each batch contains enough examples of the minority class to train the model properly and efficiently.



**Step 2: Upweight the downsampled class**

Downsampling introduces a **prediction bias** by showing the model an artificial world where the classes are more balanced than in the real world. To correct this bias, you must "upweight" the majority classes by the factor to which you downsampled. Upweighting means treating the loss on a majority class example more harshly than the loss on a minority class example.



For example, if we downsample the majority class by a factor of 25, so we must upweight the majority class by a factor of 25. That is, when the model mistakenly predicts the majority class, treat the loss as if it were 25 errors (multiply the regular loss by 25).



**How much should you downsample and upweight to rebalance your dataset?** 

To determine the answer, you should experiment with different downsampling and upweighting factors just as you would experiment with other hyperparameters.



###### **Benefits of this technique**

Downsampling and upweighting the majority class brings the following benefits:

* **Better model**: The resultant model "knows" both of the following:

&nbsp;	1. The connection between features and labels

&nbsp;	2. The true distribution of the classes

* **Faster convergence**: During training, the model sees the minority class more often, which helps the model converge faster.





#### **Dividing the original dataset:**

* Machine learning models should be tested against a separate dataset, called the test set, to ensure accurate predictions on unseen data.
* It's recommended to split the dataset into three subsets: **training**, **validation**, and **test** sets, with the validation set used for initial testing during training and the test set used for final evaluation.
* The validation and test sets can "wear out" with repeated use, requiring fresh data to maintain reliable evaluation results.
* A **good** **test** set is statistically **significant**, **representative** of the dataset and **real**-**world** data, and contains no duplicates from the training set.
* It's crucial to address discrepancies between the dataset used for training and testing and the real-world data the model will encounter to achieve satisfactory real-world performance.



**Note: When you transform a feature in your training set, you must make the same transformation in the validation set, test set, and real-world dataset.**



##### **Transforming Data**

* Machine learning models require all data, including features like street names, to be transformed into numerical (floating-point) representations for training.
* Normalization is crucial for optimizing model training by converting existing floating-point features to a specific range.
* When dealing with large datasets, selecting a relevant subset of data for training is essential for model performance.
* Protecting user privacy by excluding **Personally Identifiable Information (PII)** from datasets is a critical consideration.



##### **Generalization**

Generalization is the ability of a model to perform well on new, unseen data that was not part of its training set. Rather than memorizing training examples, a well-generalized model learns the underlying patterns and relationships, enabling it to make accurate predictions in varied real-world scenarios.



A model that generalizes well strikes a balance between underfitting (too simple, missing patterns) and overfitting (too complex, capturing noise). This balance is often guided by concepts like the bias-variance tradeoff and Occam’s Razor, which favors simpler models that still perform adequately.



Example in Supervised Learning If a classifier is trained to recognize cats and dogs from labeled images, good generalization means it can correctly classify new images of cats and dogs it has never seen before, even if lighting, angles, or breeds differ from the training set.



###### **Key Techniques to Improve Generalization**



* Regularization (L1, L2): Penalizes overly complex models to reduce overfitting.
* Dropout: Randomly ignores neurons during training to improve robustness.
* Ensemble Methods: Combine multiple models to reduce variance.
* Noise Injection: Adds noise to inputs during training to improve resilience.
* Cross-Validation: Evaluates model performance on multiple data splits.
* Transfer Learning: Uses pre-trained models to adapt to new tasks efficiently.



In Unsupervised Learning Generalization focuses on learning representations that capture essential structures in unlabeled data, enabling tasks like clustering or dimensionality reduction to work well on new datasets.



In Reinforcement Learning Generalization refers to an agent’s ability to apply learned strategies to new environments or tasks, not just the training scenarios. This is crucial for adaptability in dynamic settings.





#### **Overfitting**

* **Overfitting** means creating a model that matches (memorizes) the training set so closely that the model fails to make correct predictions on new data. An overfit model is analogous to an invention that performs well in the lab but is worthless in the real world.
* An **underfit model** doesn't even make good predictions on the training data. If an overfit model is like a product that performs well in the lab but poorly in the real world, then an underfit model is like a product that doesn't even do well in the lab.
* **Generalization** is the opposite of overfitting. That is, a model that generalizes well makes good predictions on new data. Your goal is to create a model that generalizes well to new data.



###### **Detecting overfitting**



The following curves help you detect overfitting:

* loss curves
* generalization curves



A **loss curv**e plots a model's loss against the number of training iterations. 

A graph that shows two or more loss curves is called a **generalization curve**.



###### **Causes of Overfitting**

* The training set doesn't adequately represent real life data (or the validation set or test set).
* The model is too complex.



###### **Generalization conditions**

A model trains on a training set, but the real test of a model's worth is how well it makes predictions on new examples, particularly on real-world data. While developing a model, your test set serves as a proxy for real-world data. Training a model that generalizes well implies the following dataset conditions:

* Examples must be independently and identically distributed, which is a fancy way of saying that your examples can't influence each other.
* The dataset is stationary, meaning the dataset doesn't change significantly over time.
* The dataset partitions have the same distribution. That is, the examples in the training set are statistically similar to the examples in the validation set, test set, and real-world data.



##### **Feedback loop**

In machine learning, a situation in which a model's predictions influence the training data for the same model or another model. For example, a model that recommends movies will influence the movies that people see, which will then influence subsequent movie recommendation models.





##### **Overfitting: Model Complexity**

* Simpler models often generalize better to new data than complex models, even if they perform slightly worse on training data.
* Occam's Razor favors simpler explanations and models, prioritizing them over more complex ones.
* Regularization techniques help prevent overfitting by penalizing model complexity during training.
* Model training aims to minimize both loss (errors on training data) and complexity for optimal performance on new data.
* Model complexity can be quantified using functions of model weights, like L1 and L2 regularization.



**Complex models typically outperform simple models on the training set. However, simple models typically outperform complex models on the test set (which is more important)**.



###### **Regularization**

Machine learning models must simultaneously meet two conflicting goals:

* Fit data well.
* Fit data as simply as possible.



One approach to keeping a **model simple** is to **penalize complex models**; that is, to **force the model to become simpler during training**. Penalizing complex models is one form of **regularization**.



##### **Loss and complexity**

* So far, this course has suggested that the only goal when training was to minimize loss; that is:	**minimize(loss)**



* As you've seen, models focused solely on minimizing loss tend to overfit. A better training optimization algorithm minimizes some combination of loss and complexity:	**minimize(loss + complexity)**



Unfortunately, loss and complexity are typically inversely related. As complexity increases, loss decreases. As complexity decreases, loss increases. You should find a reasonable middle ground where the model makes good predictions on both the training data and real-world data. That is, your model should find a reasonable compromise between loss and complexity.



###### **What is Complexity:**

* Complexity is a function of the model's weights. This is one way to measure some models' complexity. This metric is called **L1 regularization**.
* Complexity is a function of the square of the model's weights. You can measure some models' complexity this way. This metric is called **L2 regularization**.



##### **Overfitting: L2 Regularization**

* L2 regularization is a technique used to reduce model complexity and prevent overfitting by penalizing large weights.
* A regularization rate (lambda) controls the strength of regularization, with higher values leading to simpler models and lower values increasing the risk of overfitting.
* Early stopping is an alternative regularization method that involves ending training before the model fully converges to prevent overfitting.
* Finding the right balance between learning rate and regularization rate is crucial for optimal model performance, as they influence weights in opposite directions.



#### Formula:



L2 Regularization = w1^2 + w2^2 + .... + wn^2





**L2 regularization encourages weights toward 0, but never pushes weights all the way to zero. The overall complexity will probably drop.**





###### **Regularization rate (lambda)**

As noted, training attempts to minimize some combination of loss and complexity:	**minimize(loss + complexity)**



Model developers tune the overall impact of complexity on model training by multiplying its value by a scalar called the regularization rate. The Greek character lambda typically symbolizes the regularization rate.



That is, model developers aim to do the following:	**minimize(loss + λ complexity)**



**A high regularization rate**:

* Strengthens the influence of regularization, thereby reducing the chances of overfitting.
* Tends to produce a histogram of model weights having the following characteristics:

&nbsp;	1. a normal distribution

&nbsp;	2. a mean weight of 0.



**A low regularization rate**:

* Lowers the influence of regularization, thereby increasing the chances of overfitting.
* Tends to produce a histogram of model weights with a flat distribution.



**Setting the regularization rate to zero removes regularization completely. In this case, training focuses exclusively on minimizing loss, which poses the highest possible overfitting risk.**



###### **Picking the regularization rate**

The ideal regularization rate produces a model that generalizes well to new, previously unseen data. Unfortunately, that ideal value is data-dependent, so you must do some tuning.



##### **Early stopping: an alternative to complexity-based regularization**

* Early stopping is a regularization method that doesn't involve a calculation of complexity. Instead, early stopping simply means ending training before the model fully converges. For example, you end training when the loss curve for the validation set starts to increase (slope becomes positive).



* Although early stopping usually increases training loss, it can decrease test loss.



* Early stopping is a quick, but rarely optimal, form of regularization. The resulting model is very unlikely to be as good as a model trained thoroughly on the ideal regularization rate.



###### **Finding equilibrium between learning rate and regularization rate**

* Learning rate and regularization rate tend to pull weights in opposite directions. A high learning rate often pulls weights away from zero; a high regularization rate pulls weights towards zero.



* If the regularization rate is high with respect to the learning rate, the weak weights tend to produce a model that makes poor predictions. Conversely, if the learning rate is high with respect to the regularization rate, the strong weights tend to produce an overfit model.



* Your goal is to find the equilibrium between learning rate and regularization rate. 


























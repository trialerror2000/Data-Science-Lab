Understanding all 29 experiments
Below is the explanation of every experiment. The aim is to help you understand what the program does, why each library or function is used, and what you should observe when running it.
Part 1: Data handling and statistics
Q1. Import and export datasets using Pandas

This experiment teaches how to save and retrieve datasets in three formats:
- CSV: Stores data in a comma-separated text file.
- Excel: Stores data in spreadsheet format.
- JSON: Stores data as structured records.
to_csv(), to_excel() and to_json() export the DataFrame. Their corresponding read_*() functions import the files.

Q2. Data preprocessing

Raw data often contains errors. This program handles three common problems:
- Missing values: Replaces missing ages using the median.
- Duplicate records: Removes repeated rows using drop_duplicates().
- Inconsistent data: Removes unnecessary spaces, corrects capitalization, and replaces negative salaries with a valid median value.
The objective is to make the dataset suitable for analysis.

Q3. Descriptive statistical analysis

This program calculates six important statistical measures:
Measure	Meaning
Mean	Average of all values
Median	Middle value after sorting
Mode	Most frequently occurring value
Variance	Measure of data spread
Standard deviation	Square root of variance
Covariance	Indicates how two variables vary together

Pandas provides these calculations directly through functions like mean(), median(), var() and cov().

Q4. Covariance and correlation matrices

This experiment analyzes relationships between four variables.

A covariance matrix shows whether variables move together, while a correlation matrix shows the strength and direction of their relationship.

Seaborn's heatmap() visualizes both matrices.

Remember: correlation ranges from -1 to +1. A value near +1 indicates a strong positive relationship, while a value near -1 indicates a strong negative relationship.

Q5. Univariate and multivariate normal distributions

There are two types of distributions demonstrated here:
- Univariate: A normal distribution involving only one variable.
- Multivariate: A normal distribution involving two or more related variables.
np.random.normal() generates the first type, while np.random.multivariate_normal() generates the second.

The histograms and KDE plots help visualize their distributions.
Part 2: Statistical testing and visualization
Q6. Hypothesis testing using SciPy

Hypothesis testing determines whether there is enough statistical evidence to support a claim.

The program generates two independent groups and performs an independent t-test.

Important terms:
- Null hypothesis (H0): Both groups have equal population means.
- Alternative hypothesis (H1): Their population means are different.
- P-value: Measures how compatible the observed result is with the null hypothesis.
The program uses 0.05 as the significance level.

If p-value is below 0.05, reject the null hypothesis. Otherwise, fail to reject it.

Q7. Confidence intervals

A confidence interval estimates a range within which a population parameter may lie.

The program generates 50 observations and calculates a 95% confidence interval for their population mean using the t-distribution.

Important functions:
- np.mean(): Calculates sample mean.
- stats.sem(): Calculates standard error.
- stats.t.interval(): Calculates the confidence interval.
Q8. Dataset manipulation using Pandas

This experiment demonstrates three operations:
1. Transformation: Creates a new Bonus column equal to 10% of employee salary.
2. GroupBy: Calculates average salary for each department.
3. Pivot Table: Summarizes department-wise mean and maximum salary.
This is useful when working with large employee, financial, or business datasets.

Q9. Visualization using Matplotlib and Seaborn

The program generates a sine wave using NumPy and displays it through Seaborn and Matplotlib.

np.linspace() generates evenly spaced values, and np.sin() calculates their sine.

The line plot displays the relationship between X and Y.

Q10. Different types of graphs

This experiment demonstrates six visualization techniques.
Graph	Purpose
Bar chart	Compare categories
Histogram	Show frequency distribution
Pie chart	Show proportions
Box plot	Show spread and outliers
Scatter plot	Show relationships between variables
Heatmap	Visualize matrix values

All six graphs are displayed together using Matplotlib subplots.
Part 3: Regression and model evaluation
Q11. Simple Linear Regression

Linear regression predicts a numerical output using an input variable.

It follows the equation:
\[
y = mx+c
\]

Where:
- \(y\) = predicted output
- \(x\) = input
- \(m\) = coefficient or slope
- \(c\) = intercept
The program trains a Scikit-learn LinearRegression model and plots the predicted regression line.

Q12. Multiple Linear Regression

Unlike simple regression, multiple regression uses multiple independent variables to predict one output.

The example uses three features to predict a target value.

The model is evaluated using:
- MSE: Mean Squared Error. Lower is generally better.
- R² Score: Measures how much target variation is explained by the model. Values closer to 1 are generally better.
Q13. Ridge and Lasso Regression

Both are modified versions of linear regression that use regularization to reduce overfitting.
- Ridge Regression: Uses L2 regularization and reduces the magnitude of coefficients.
- Lasso Regression: Uses L1 regularization and can reduce some coefficients to exactly zero.
The program trains both models and compares their R² scores and coefficients.

Q14. Train-test split and cross-validation

This experiment demonstrates two ways of evaluating a model.
- Train-test split: Divides data into training and testing portions. Here, 70% is used for training and 30% for testing.
- Cross-validation: Divides data into multiple folds. The program uses 5-fold cross-validation, training and evaluating the model repeatedly.
Cross-validation generally gives a more dependable performance estimate than relying on a single split.

Q15. Model evaluation metrics

This experiment evaluates a classification model using six measures.
Metric	Meaning
Confusion Matrix	Displays correct and incorrect classifications
Accuracy	Overall percentage of correct predictions
Precision	Correct predictions among predicted positives
Recall	Actual positives correctly identified
F1-score	Balance between precision and recall
ROC-AUC	Ability to distinguish between two classes

The model used is Logistic Regression.

One important point: ROC-AUC uses predicted probabilities rather than the final predicted class labels.
Part 4: Classification algorithms
Q16. K-Nearest Neighbors (kNN)

kNN classifies a new data point by examining its nearest neighboring data points.

The program uses n_neighbors=5.

For example, if four out of five nearest neighbors belong to the same class, the new observation is generally assigned that class.

Q17. Decision Tree Classification

A Decision Tree makes predictions through a sequence of conditions.

It works like a flowchart:
- Each internal node represents a decision.
- Each branch represents an outcome.
- Each leaf represents a predicted class.
The program uses the Gini criterion to measure impurity and limits the tree depth to three.

Q18. Support Vector Machine (SVM)

SVM is a classification algorithm that tries to find the best boundary separating different classes.

It aims to maximize the margin between the classes.

The program uses a linear kernel to classify the breast cancer dataset.

Q19. Random Forest Classification

Random Forest combines multiple Decision Trees to make a prediction.

Instead of depending on one tree, it combines the predictions of 100 trees in this experiment.

This usually makes the model more stable and less sensitive to individual training samples.

Q20. Naïve Bayes Classification

Naïve Bayes is a probability-based classification algorithm based on Bayes' theorem.

It assumes that features are conditionally independent given the class.

The program uses Gaussian Naïve Bayes, which assumes that numerical features follow normal distributions within each class.

Q21. Logistic Regression

Despite having the word regression in its name, Logistic Regression is mainly used for classification.

It predicts the probability of an observation belonging to a particular class.

For binary classification, the output is generally converted into either class 0 or class 1 using a probability threshold.

The program creates synthetic data with two classes and evaluates the model using accuracy.

Q22. Comparison of classification algorithms

This experiment compares four algorithms using the same breast cancer dataset:
1. Logistic Regression
2. Decision Tree
3. Support Vector Machine
4. K-Nearest Neighbors
All four models use the same training and testing data.

Their accuracy scores are printed so that their performance can be compared fairly.
Part 5: Clustering
Q23. K-Means Clustering

K-Means is an unsupervised learning algorithm used to divide data into groups called clusters.

The process is:
1. Specify the number of clusters.
2. Initialize cluster centroids.
3. Assign each point to its nearest centroid.
4. Recalculate the centroids.
5. Repeat until the clusters stabilize.
The program creates four clusters and displays their centroids using red X markers.

Q24. Hierarchical Clustering

Hierarchical clustering builds a hierarchy of clusters by repeatedly combining smaller groups.

The program uses Ward linkage, which merges clusters while minimizing the increase in within-cluster variance.

It visualizes the result using a dendrogram.

The dendrogram shows how individual observations and clusters are progressively combined. The height of each merge represents the distance between the merged clusters.

Q25. Comparison of clustering algorithms

This experiment compares:
- K-Means Clustering
- Agglomerative Clustering
Both algorithms are applied to the same two-moons dataset.

Their performance is evaluated using the Silhouette Score.

The score ranges from -1 to +1. A higher score generally indicates better-separated clusters.

The example is particularly useful because the two-moons dataset contains curved clusters, which different algorithms may identify differently.
Part 6: Advanced visualization and real-world applications
Q37. Interactive visualization using Plotly

Unlike ordinary Matplotlib graphs, Plotly creates interactive visualizations.

The program uses the Iris dataset and creates a scatter plot.

It represents:
- Sepal width on the X-axis.
- Sepal length on the Y-axis.
- Species through different colours.
- Petal length through marker size.
You can hover over points, zoom in, and pan around the graph.

Q38. Pair plots and dimensionality reduction

This experiment has two parts.

Part 1: Pair Plot

A pair plot displays relationships between every pair of numerical features in a dataset. It helps identify correlations and patterns.

Part 2: PCA

Principal Component Analysis reduces the number of dimensions while attempting to preserve as much variation in the data as possible.

The Iris dataset originally contains four numerical features. PCA reduces them to two principal components, allowing the data to be visualized on a 2D graph.

Q39. Exploratory Data Analysis (EDA)

EDA means examining and understanding a dataset before applying machine learning.

The program uses the real-world Titanic dataset.

It performs four main operations:
1. Loads the dataset.
2. Displays dataset information using info().
3. Calculates summary statistics using describe().
4. Identifies missing values using isnull().sum().
Finally, it creates a count plot showing passenger survival counts for different ticket classes.

Q40. End-to-end Data Science Application

This is the most comprehensive experiment in the selected list.

It combines multiple stages of a data science project using the Titanic dataset.
Complete workflow
1. Data Loading
   
   Load the Titanic dataset using Seaborn.
2. Data Preprocessing
   
   Remove unnecessary columns, fill missing ages, remove remaining missing rows, and convert categorical data into numerical columns using get_dummies().
3. Data Visualization
   
   Generate a correlation heatmap to inspect relationships between features.
4. Model Development
   
   Train a Random Forest classifier to predict passenger survival.
5. Model Evaluation
   
   Use a confusion matrix and classification report to evaluate predictions.
6. Prediction
   
   Pass one test passenger to the trained model and predict whether that passenger survived.

The final prediction is either:
- 1: Survived
- 0: Did not survive
This experiment demonstrates how separate data science techniques work together to solve a single problem.

Before running the notebook in VS Code
1. Open the downloaded .ipynb file.
2. Select your Python interpreter/kernel.
3. Run the first cell to install the dependencies.
4. Execute the remaining cells in sequence.
Important: Questions 38, 39 and 40 use Seaborn's online sample datasets, so an internet connection may be required to load them.

The notebook is ready for execution. The explanations are also included inside the notebook, so you have both a practical file for your lab work and the detailed explanations here for understanding and viva preparation.

🎯 **Kickstarter Crowdfunding Success Prediction**

📌 **Project Overview**
This project aims to predict the success of crowdfunding campaigns on Kickstarter. A project is considered successful if it raises more money than its goal. The dataset provided contains information on over 100,000 Kickstarter projects, featuring attributes like project details, funding goals, and backer statistics. Using this data, our goal is to predict the likelihood of a project reaching its funding target based on various project characteristics.

The dataset spans projects with deadlines from 2009 to 2014 and provides over 60 features for each project, including both categorical and continuous variables.

**🎯 Goal**
The primary goal is to predict whether a project will be successful. The target variable success is binary:

**YES**: The project raised more money than its goal.
**NO**: The project did not meet its funding goal.

**🗂 Dataset Description**
The dataset is divided into multiple CSV files for training, testing, and exploration:

**Training Data**
ks_training_X.csv: Features for the training instances (projects with deadlines before September 2014).
ks_training_y.csv: Labels (success or failure) for training instances.
**Test Data**
ks_test_X.csv: Features for the test instances (projects with deadlines from September to December 2014).
ks_test_y_FAKE.csv: Fake labels for the test set (all labeled "NO"). This helps with initial testing and debugging.
**Smaller Subset for Exploration**
small_training_X.csv: A smaller subset of the training data (10,000 instances) for faster exploration.
small_training_y.csv: Labels for the smaller subset.

**Features Overview**
The dataset contains over 60 features, such as:

Goal: The financial goal for the project.
Launched At: The date and time when the project was launched.
Category: The category the project belongs to (e.g., technology, design, art).
Creator Information: Information about the project creator (e.g., name and description).
Tags: Various tags related to the project (e.g., "innovative", "crowd-funded").
Description: The project description provided by the creator.
For a detailed description of the features, refer to the Data Dictionary.

**🔧 Methodology**
The R script provided (kickstarter_success_prediction_code.R) follows these key steps:

**1. Data Loading & Preprocessing**
Load data from the CSV files.
Merge feature and label datasets.
Perform data cleaning and transformations (e.g., handle missing values, convert dates).

**2. Feature Engineering**
New features are derived, such as:
goal_by_avg_sentence
reward_desc_attractive_words
reward_count
Sentiment analysis on the project descriptions and rewards.

**3. Model Training**
Various machine learning models are trained:
Decision Trees using rpart
Random Forest
XGBoost
Cross-validation and hyperparameter tuning for optimal performance.

**4. Evaluation**
Accuracy and AUC (Area Under the Curve) are used for model evaluation.
Confusion Matrices to evaluate precision, recall, and F1-score.

**5. Final Prediction**
The final model is used to generate predictions for the test set.
Results are saved in a submission-ready format for further analysis.

**📂 Files**
kickstarter_success_prediction_code.R: The main R script for data loading, feature engineering, model training, and evaluation.
CSV Files: Dataset files required for training and testing (ks_training_X.csv, ks_training_y.csv, ks_test_X.csv, etc.).
[Optional] Additional files for analysis and results.

🧑‍💻** Installation & Requirements**
To run the R script, you need the following R packages. Install them by running this command in R:

install.packages(c("caret", "sentimentr", "tidytext", "text2vec", "stringr", "rvest", "FSelector", "rJava", "DMwR", "smotefamily", "xgboost", "ranger", "vip", "pROC"))

**Required Libraries:**
caret: For general machine learning tasks.
sentimentr: For sentiment analysis.
tidytext: For text processing.
stringr: For string manipulation.
text2vec: For text vectorization.
rvest: For web scraping (if required).
FSelector: For feature selection.
rJava: For interfacing with Java-based packages.
DMwR: For class imbalance handling (SMOTE).
xgboost: For training XGBoost models.
ranger: For random forest models.
vip: For variable importance plots.
pROC: For AUC and ROC curve evaluation.

**🚀 Running the Script**
Install the required R packages using the command above.
Set the correct file paths in the R script to load the dataset.
Run the R script to perform the following tasks:
Feature engineering
Model training
Evaluation
Generating predictions for the test set
The script will output the predictions, which can be used to evaluate the model's performance.

**📄 License**
This project is licensed under the MIT License. See the LICENSE file for more details.

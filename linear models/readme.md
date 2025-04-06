🍷 Wine Quality Prediction Project


Overview

This project focuses on predicting wine quality based on physicochemical tests. Two datasets were analyzed: red wine and white wine, with an emphasis on white wine due to a larger sample size. The project includes full data processing, feature engineering, model training, evaluation, and comparison across multiple regression and classification models.
Agenda

    Primary Data Analysis

        Explored dataset structure, data types, and missing values

        Visualized correlations and boxplots for outlier detection

    Feature Engineering

        Created new features:

            sulfur_ratio: total sulfur dioxide / free sulfur dioxide

            acid_ratio: volatile acidity / fixed acidity

            total_acid: sum of all acidity-related features

    Scaling Features

        Standardized all features using StandardScaler

    Dataset Splitting

        Training and testing: 80/20 split

        Red wine dataset was initially used as validation but later discarded due to domain mismatch

    Model Training (Baseline)

        Trained models with default hyperparameters

        Used Pipeline and cross_val_score for fair evaluation

    Hyperparameter Tuning

        Used GridSearchCV to optimize hyperparameters for SGD-based models

    Model Evaluation

        Used R² score and Mean Absolute Error (MAE) for regression

        Used accuracy for classification

        Stored all model scores in a score_store dictionary for comparison

Models and Results
Model	Metric Used	Score
Linear Regression	R² (Test)	0.3248
Logistic Regression	Accuracy (CV)	0.5429
OLS Regression (StatsModels)	MAE	0.5768
Poisson Regression	R² (CV)	0.2756
SGD Regressor (GridSearch)	R² (CV)	0.2839
SGD Regressor (Default)	R² (Test)	0.3225
SGD Classifier (GridSearch)	Accuracy (CV)	0.4449
SGD Classifier (Default)	Accuracy (Test)	0.4408

➡️ OLS Regression showed the best performance based on mean absolute error.
Key Insights

    Feature engineering significantly improved model understanding and performance

    Red wine and white wine datasets are not interchangeable for model validation due to different distributions

    GridSearchCV did not always improve performance; default SGDClassifier outperformed the tuned one

    Linear models performed reasonably, though results suggest room for more complex models like ensembles or neural networks

Technologies Used

    Python 3

    Google Colab / Jupyter

    Pandas, NumPy, Matplotlib, Seaborn

    Scikit-learn

    Statsmodels

Next Steps

    Try ensemble methods (e.g., Random Forest, XGBoost)

    Explore non-linear feature transformations

    Build a combined red+white classification model with a domain feature

Contact

If you have any questions or want to collaborate, feel free to reach out to me!

Serhii Kolotukhin

🇺🇦

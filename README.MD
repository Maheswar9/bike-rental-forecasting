Bike Rental Demand Forecasting
Project Overview

This project develops an end-to-end machine learning model to forecast the hourly demand for rental bikes. Using the "Bike Sharing Dataset" from UCI, this project demonstrates a complete data science workflow, including data exploration, feature engineering, model training, hyperparameter tuning, and final evaluation.

The goal is to build a reliable regression model that can predict the total number of bike rentals (cnt) based on seasonal and weather-related features. The final model is a fine-tuned Random Forest Regressor.
Project Workflow

    Data Loading & Exploration: The hour.csv dataset was loaded and analyzed to understand its structure, features, and data types.

    Data Cleaning & Feature Engineering:

        Unnecessary or redundant columns (instant, dteday, atemp) were dropped.

        Data leakage was prevented by dropping columns directly related to the target (casual, registered).

    Data Splitting: The data was split into training (70%) and testing (30%) sets. A chronological order was maintained to respect the time-series nature of the data.

    Feature Scaling: Continuous numerical features (temp, hum, windspeed) were standardized using StandardScaler on the training set to ensure all features contribute equally to the model's performance.

    Model Training & Selection: Three different regression models were trained and evaluated using 10-fold cross-validation:

        Decision Tree Regressor

        Linear Regression

        Random Forest Regressor

        The Random Forest Regressor was selected as the best-performing model due to its significantly lower error scores.

    Hyperparameter Tuning: The selected Random Forest model was fine-tuned using GridSearchCV to find the optimal combination of hyperparameters (n_estimators, max_features, max_depth).

    Final Evaluation: The fine-tuned model was evaluated on the unseen test set to get a final, reliable measure of its predictive performance.

Final Results

    Best Model: Random Forest Regressor

    Best Hyperparameters: {'max_depth': 28, 'max_features': 10, 'n_estimators': 150}

    Final RMSE on Test Set: The model's predictions on the test set had a Root Mean Squared Error of approximately 49.3. This means, on average, the model's prediction is off by about 49 bikes.

The final plots show a strong correlation between the model's predictions and the actual rental counts, especially during peak hours like 9 AM and 6 PM.
How to Run This Project

    Clone the repository:

    git clone https://github.com/Maheswar9/bike-rental-forecasting
    cd your-repository-name

    Install the required libraries:

    pip install -r requirements.txt

    Run the Jupyter Notebook or Python script:
    The main code is located in bike_rental_forecasting.ipynb (or .py). Open it and run the cells sequentially to see the entire process.

Technologies Used

    Python

    Pandas

    NumPy

    Scikit-learn

    Seaborn & Matplotlib

    Jupyter Notebook

Acknowledgements

This project uses the Bike Sharing Dataset from the UCI Machine Learning Repository.

Citation:
Fanaee-T, Hadi, and Gama, Joao, "Event labeling combining ensemble detectors and background knowledge", Progress in Artificial Intelligence (2013): pp. 1-15, Springer Berlin Heidelberg, doi:10.1007/s13748-013-0040-3.
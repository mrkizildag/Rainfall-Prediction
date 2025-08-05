# Rain Prediction Using Machine Learning

## Project Overview

This project focuses on predicting rainfall for the Melbourne area using historical weather data collected from 2008 to 2017. The main objective is to develop and compare machine learning models that can forecast whether it will rain the following day based on various meteorological features such as humidity, pressure, temperature, and wind conditions. Accurate rain prediction can support decision-making in agriculture, transportation, and daily planning.

## Dataset Description

The dataset comprises weather observations from multiple locations around Melbourne, including Watsonia and Melbourne Airport. After thorough preprocessing and cleaning, the dataset contains 7,557 records with features capturing weather conditions at different times of the day. The target variable is a binary classification of whether it rained the next day (`RainTomorrow`). The data exhibits class imbalance, with approximately 76% of days labeled as 'No Rain' and 24% as 'Rain,' which presents a challenge for model training and evaluation.

## Methodology

The project workflow includes several key steps: data preprocessing, feature engineering, model training, and evaluation. Initially, data cleaning and transformation prepare the raw data for modeling. Feature engineering enhances predictive power by creating new weather-related variables, such as pressure changes and temperature ranges. The data is split into training and testing subsets to fairly assess model generalization.

Two main classification algorithms are implemented: Random Forest and Logistic Regression. Hyperparameter tuning is performed using grid search with cross-validation to optimize model parameters. Additionally, custom decision thresholds are explored to improve recall, especially important for correctly identifying rainy days. Model performance is evaluated using metrics including accuracy, precision, recall, F1-score, and confusion matrices, giving a comprehensive understanding of strengths and weaknesses.

## Key Findings

Initial models achieve reasonable accuracy (~83-84%) but struggle with recall for the minority 'Rain' class, correctly identifying only about half of rainy days. Feature engineering and threshold adjustments significantly improve recall, boosting it to nearly 78%, though this improvement comes with some loss in overall accuracy and precision. The Logistic Regression model slightly outperforms Random Forest in rain detection, and certain features like afternoon humidity, morning pressure, and sunshine hours are consistently among the most important predictors.

## How to Use

The entire analysis and modeling pipeline is contained within the Jupyter notebook located at `notebooks/rain_prediction.ipynb`. To reproduce the results, simply open the notebook and run all cells sequentially. This notebook includes detailed code for data loading, preprocessing, feature creation, model training, evaluation, and visualization.

For users interested in modularizing or scaling the project, reusable functions can be extracted into separate Python scripts under a `src/` directory. The required Python libraries are listed in `requirements.txt`, and installing them via pip ensures the environment is ready for execution for the `.py` version. In the notebook, there is a cell for installing and importing libraries.

## Future Directions

To further improve the rain prediction model, several enhancements can be explored. 
- Addressing the class imbalance through oversampling techniques such as SMOTE could help the model better detect rainy days. 
- Incorporating time-series features or rolling weather metrics would allow the model to capture temporal trends and patterns more effectively. 
- Experimenting with advanced boosting algorithms like XGBoost or LightGBM may yield better predictive performance due to their ability to handle complex relationships in the data. 
- Additionally, exploring recurrent neural network architectures, such as LSTMs, could provide deeper insights into temporal dependencies inherent in weather data, potentially improving forecasting accuracy.

## Dependencies

The project uses the following Python libraries:

- pandas  
- scikit-learn  
- matplotlib  
- seaborn  

Ensure these are installed in your Python environment to run the notebook without issues.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.



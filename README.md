# Crop-recommender
Crop recommendation using ensemble learning and deploying it as a web application using flask.


## Instructions
**1.** Run app.py. <br>
**2.** Copy and search the address on your browser (localhost:5000/). <br>
**3.** Enter the values required and hit predict to see the prediction made by the model. <br>

## Project details

- **Data**
  - Link : https://www.kaggle.com/atharvaingle/crop-recommendation-dataset
  - Data fields :
    -  *N* - Ratio of Nitrogen in the soil.
    -  *P* - Ratio of Phosphorus in the soil.
    -  *K* - Ratio of Potassium in the soil.
    -  *temperature* - Temperature in Celcius.
    -  *humidity* - relative humidity in %.
    -  *ph* - pH value of the soil.
    -  *rainfall* - Rainfall in mm.
    -  *label* - Target.

- **Data preparation**
  - Missing values :
    -  There were some rows where the ratio of Nitrogen was zero. Those rows were considered as missing values and were dropped as the number of rows with missing values were very less.
  - Potassium and Phosphorus had high correlation so the column containing the ratio of Phosphorus was dropped from the features to avoid multicollinearity.
  - Classes of the target column were encoded using LabelEncoder.
  - Features were scaled using RobustScaler as there are possible outliers in the data. 
  - Train-Test ratio : 80% and 20%.

- **Data modeling**
  - Ensemble learning (Voting Classifier) was used for recommending the crops.
  - Algorithms used for ensemble learning :
    - k-nearest neighbors.
    - Decision Tree.
    - Random Forest Classifier.
    - Gaussian Naive Bayes.
   - Default parameters were used for algorithms. No hyperparameter tuning was done because of the high accuracy achieved by using the default parameters.
   
- **Object files**
   - Pickle was used to save the label encoder and the model for deployment using web application.
  - The saved model was used for prediction on new data.
  - The saved label encoder was used to inverse transform the label predicted by the model.

- **Web application**
  - Flask and HTML were used to create the web application required for deploying the machine learning model.

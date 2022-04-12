# How Price and Availability Impact Airbnb Revenue
Developer:  Aarushi Verma, Cindy Chiu, Dauren Bizhanov, Sydney Donati-Leach

## Project Objectives
This project aims to help potential property investors to estimate their annual revenue. Our model aims to predict the average daily price and occupancy rate bracket for the next year for a listing using Airbnb data. By evaluating feature importance we also aim to help prospective hosts to increase the success of an Airbnb listing. 

## Data
The data can be retrieved from the http://insideairbnb.com/get-the-data website. The city we’re training our model on is Hawaii, USA. Since the data is huge and zipped, the user can clone the github repository and run the download_data.py under the source folder. Running the `download_data.py` on the local machine will retrieve both training and testing data from the website and create a copy on your local machine. The files will be saved under the same folder as the script with 3 separate folders: `Train`, `Test_Broward` and `Test_Create`. Users can open the files on their local machine.

## Conclusion
(To be updated)

## Requirements 
This project is built with Python 3, and the visualizations are created using Jupyter Notebooks. In order to run all the files without error, please follow the following steps:

Step 1: Git clone the repo on your local machine    
```
git clone [to paste link here]
```

Step 2: Install required packages   
``` 
pip install -r requirements.txt
```

Step 3: Download the data by running the `download_data.py` file by navigating to the `/source` folder    
``` 
python3 download_data.py
```

Running this script retrieve both training and testing data from the website and create a copy on your local machine. The files will be saved under the same folder as the script with 3 separate folders: `Train`, `Test_Broward` and `Test_Create`. Users can access the files on their local machine. 

Step 4: Preprocess the train and test data    
```
python3 preprocessing.py
```

Running the `preprocessing.py` will perform feature transformations on both the training set and testing files.

Step 5: Train the models    

For the price prediction model:   
```
python3 train_models_regression.py
```

For the occupancy prediction:   
```
python3 train_models_classification.py
```

Those two files contain multiple models that we have implemented for predictions. The `train_models_regression.py` includes RandomForest Regressor, XGBoost Regressor and LightBGM Regressor. The `train_models_classification.py` includes RandomForest Classifier, XGBoost Classifier and LightBGM Classifier Running these files will also save the model results as JSON files to `\Models` folder. In addition, the evaluation metrics of the validation data, including precision, recall, confusion matrix, RMSE and MAE, are saved in the `\Data` folder
 
Step 6: Test Model performance    
```
python3 predictions_on_test_data.py
```

We leverage the model that performed the best on the validation set and predict it on the testing data (Broward County and Crete). The evaluation metrics of the testing data, including precision, recall, confusion matrix, RMSE and MAE, are saved in the `\Data` folder.  

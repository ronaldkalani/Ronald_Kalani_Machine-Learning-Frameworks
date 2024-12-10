# Ronald_Kalani_Machine-Learning-Frameworks
Model Deployment and Interaction
1. Train and Save the KNN Model
Step 1.1: Import libraries and load the dataset.
Step 1.2: Perform data preprocessing:
Handle missing values.
Encode categorical variables using OneHotEncoder or other relevant techniques.
Step 1.3: Split the data into training and testing sets using train_test_split.
Step 1.4: Create a pipeline with preprocessing steps and the KNeighborsRegressor.
Step 1.5: Train the model using the training dataset.
Step 1.6: Save the trained model to a file using pickle:
with open('knn_sales_model.pkl', 'wb') as model_file:
    pickle.dump(knn_model, model_file)
2. Flask API Development
Step 2.1: Install Flask if not already installed:
pip install flask
Step 2.2: Create a Flask application (app.py) with the following steps:
Import necessary libraries (Flask, request, pickle, etc.).
Load the saved knn_sales_model.pkl using pickle.
Define a /predict endpoint to accept POST requests with JSON payloads.
3. Test the Flask API
Step 3.1: Navigate to the directory containing app.py
cd C:\Users\karon\Flask
Step 3.2: Start the Flask application:
python app.py
Output:
Running on http://127.0.0.1:5000
Step 3.3: Use tools like Postman, curl, or PowerShell to send a POST request to the /predict endpoint. Example using PowerShell:
Invoke-RestMethod -Uri http://127.0.0.1:5000/predict -Method POST -Body (@{'features' = @(3, 70.0, 3.2, 2000.0, 1500.0, 800.0, 3000.0, 500.0, 250.0, 5.0, 1)} | ConvertTo-Json) -ContentType "application/json"
4. Interaction Diagram
Client: Sends a POST request to the Flask API with features in JSON format.
Flask API:
Receives and parses the request.
Passes the parsed features to the KNN model for prediction.
Sends the predicted value back as a JSON response.
Server: Handles API requests and serves the model.
5. Result 
Request
{
  "features": [3, 70.0, 3.2, 2000.0, 1500.0, 800.0, 3000.0, 500.0, 250.0, 5.0, 1]
}
Response
{
  "predicted_sales": 27735.60224423001
}

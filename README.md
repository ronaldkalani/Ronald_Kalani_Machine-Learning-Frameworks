# Ronald_Kalani_Machine-Learning-Frameworks
Sales Prediction API
A Flask-based REST API for predicting sales using a trained KNN regression model. This API accepts input features and returns the predicted sales value.

Table of Contents
Overview
Features
Project Structure
Setup Instructions
Usage
API Endpoints
Example Request and Response
Contributing
License

Overview
This project deploys a K-Nearest Neighbors (KNN) regression model using Flask to predict sales. The API processes input features such as store information, temperature, and economic indicators to generate a prediction for sales.

The trained KNN model is serialized using pickle and served via a Flask application.

Features
RESTful API for predicting sales.
Handles JSON-based requests.
Pre-trained KNN model for regression tasks.
Flask development environment for local testing.

Project Structure
.
├── app.py                   # Flask application code
├── knn_sales_model.pkl      # Pre-trained KNN model file
├── requirements.txt         # Python dependencies
└── README.md                # Project documentation


Setup Instructions
Prerequisites
Python 3.7 or later
Flask framework
Libraries such as NumPy, pandas, scikit-learn, and pickle
Steps
1. Clone the Repository

git clone https://github.com/username/sales-prediction-api.git
cd sales-prediction-api

2. Set Up a Virtual Environment
python -m venv venv
source venv/bin/activate    # On Windows: venv\Scripts\activate

3. Install Dependencies
   pip install -r requirements.txt
   
5. Run the Flask Application

   python app.py
The application will run on http://127.0.0.1:5000.

Usage
1. Start the Flask Server

   python app.py
2. Send a POST Request
Use tools like Postman, curl, or a script to interact with the API.
API Endpoints
POST /predict
Description
Predict sales based on input features.

Request
Content-Type: application/json
Body:
{
  "features": [Store, Temperature, Fuel_Price, MarkDown1, MarkDown2, MarkDown3, MarkDown4, MarkDown5, CPI, Unemployment, IsHoliday]
}

Response
Content-Type: application/json
Body:
{
  "predicted_sales": 27735.60224423001
}


License
This project is licensed under the MIT License. See the LICENSE file for details.

Contact
For issues or inquiries, please contact:

Email: RONALDKALANI@YAHOO.CA

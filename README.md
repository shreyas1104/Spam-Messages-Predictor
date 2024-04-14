# Spam/Ham Predictor

A simple web application for classifying text messages as spam or ham (not spam) using a Multinomial Naive Bayes model. The app is built with Flask, HTML, and CSS.

## Table of Contents

- [Setup](#setup)
- [Usage](#usage)
- [Flask Application](#flask-application)
- [Templates](#templates)

## Setup

1. Clone the repository: `git clone https://github.com/shreyas1104/Spam-Messages-Predictor.git`
2. Install the required dependencies: `pip install -r requirements.txt`

## Usage

1. Train the Multinomial Naive Bayes model and start the flask server: `python app.py`
3. Open your web browser and navigate to `http://localhost:5000`
4. Enter a text message in the provided input field and click "Predict" to classify it as spam or ham.

## Flask Application

The `app.py` file contains the Flask application code for the Spam/Ham Predictor.

### Routes

- `/` (GET): Renders the `home.html` template, which displays the form for entering a text message.
- `/predict` (POST): Handles the form submission from `home.html`. It processes the submitted text message, makes a prediction using the trained Multinomial Naive Bayes model, and renders the `result.html` template with the prediction result.

### Functionality

1. The application loads the dataset (`spam.csv`) and performs necessary data preprocessing steps, such as dropping unnecessary columns and mapping the class labels to numerical values.
2. The `CountVectorizer` from scikit-learn is used to extract features from the text data.
3. The dataset is split into training and testing sets using `train_test_split`.
4. A Multinomial Naive Bayes model is trained on the training data.
5. When a user submits a text message through the form on the `/` route, the application receives the message in the `/predict` route.
6. The submitted message is vectorized using the `CountVectorizer` fitted on the training data.
7. The trained Multinomial Naive Bayes model predicts whether the submitted message is spam or ham (not spam).
8. The prediction result is rendered on the `result.html` template and displayed to the user.

## Templates

The `templates` directory contains the following HTML templates for rendering the web app:

- `home.html`: The main page of the web app, which displays a textarea for the user to enter a text message and a "Predict" button to submit the message for classification.
- `result.html`: The page that displays the prediction result (spam or ham) after the user submits a text message.

Both templates are styled using CSS files located in the `static` directory:

- `static/home-styles.css`: Styles for the `home.html` template.
- `static/result-styles.css`: Styles for the `result.html` template.

# F1 Race Prediction Model

This repository contains a machine learning model that predicts the winner of Formula 1 races for the 2025 season based on historical data, qualifying results, weather conditions, and other relevant factors.

## Features

- Predicts F1 race winners using historical race data and current season qualifying results
- Incorporates weather data from OpenWeatherMap API
- Considers multiple factors including:
  - Previous race performance
  - Sector times
  - Team performance
  - Driver wet weather performance
  - Weather conditions (temperature, rain probability)
  - Track characteristics

## How It Works

The model uses a Gradient Boosting Regressor to predict average lap times for each driver in an upcoming race. Key components:

1. **Data Collection**:
   - Uses FastF1 library to fetch historical F1 race data
   - Fetches weather data from OpenWeatherMap API

2. **Data Processing**:
   - Cleans and preprocesses lap time data
   - Calculates sector times and aggregates by driver
   - Imputes missing values

3. **Feature Engineering**:
   - Qualifying times adjusted for wet conditions
   - Clean air race pace
   - Wet performance factors
   - Team performance scores
   - Average position changes
   - Weather conditions (rain probability, temperature)
   - Previous winner status

4. **Model Training**:
   - Uses GradientBoostingRegressor with 200 estimators
   - Splits data into training/test sets (80/20)
   - Evaluates using Mean Absolute Error (MAE)

5. **Prediction**:
   - Predicts average lap times for each driver
   - Estimates total race time including pit stops
   - Outputs predicted podium finishers

## Requirements

- Python 3.7+
- Required libraries:
  - fastf1
  - pandas
  - numpy
  - scikit-learn
  - matplotlib
  - requests


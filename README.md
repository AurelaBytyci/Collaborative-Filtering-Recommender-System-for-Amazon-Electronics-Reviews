# CollaborativeFilteringRecommenderSystemforAmazonElectronicsReviews

## Overview
This project implements a collaborative filtering-based recommender system for Amazon Electronics reviews. It demonstrates how machine learning techniques can be applied to large-scale user-item interaction datasets for generating personalized recommendations.

## Features
- **Data Cleaning**: Extracts and processes user-item-rating data for matrix construction.
- **Recommender Model**: Uses Singular Value Decomposition (SVD) to predict ratings.
- **Top-N Recommendations**: Generates and saves top-5 item recommendations per user.
- **Visualization**: Includes tools to explore rating distributions and item popularity.

## Folder Structure

CollaborativeFilteringRecommenderSystemforAmazonElectronicsReviews/
│
├── data/
│   ├── raw_data/                  # Contains Electronics_5.json (raw Amazon reviews)
│   ├── preprocessed_data/        # Contains preprocessed_data.csv (cleaned dataset)
│   ├── results/                  # Contains recommendations.json and top_5_recommendations.csv
│
├── notebooks/
│   └── exploratory_data_analysis.ipynb   # Jupyter notebook for data exploration and testing
│
├── src/
│   ├── __init__.py
│   ├── data_cleaner.py           # Cleans and filters the raw JSON into usable CSV
│   ├── recommender.py            # SVD-based recommender model
│   ├── evaluation.py             # Evaluates the model (e.g., RMSE calculation)
│   ├── run.py                    # Main script to run cleaning + training pipeline
│
├── LICENSE                       # MIT License
├── requirements.txt              # Python dependencies
└── README.md                     # Project overview and usage instructions

## Installation
1. **Download the Project Files:**
   - Obtain the project files directly (e.g., via a ZIP file or local transfer).
   - Extract the files to a directory on your computer.

2. **Navigate to the Project Directory:**
   Open a terminal (or command prompt) and go to the project folder:
   ```bash
   cd /path/to/CollaborativeFilteringRecommenderSystemforAmazonElectronicsReviews

3. Create a virtual environment:
   python3 -m venv venv
   source venv/bin/activate  # On macOS/Linux
   # OR
   venv\Scripts\activate     # On Windows


4. Install the required dependencies:
   pip install -r requirements.txt

5. Run the Flask app: Start the Flask application:
    ```bash
    python3.9 main.py
    ```

6. Verify the app is running: Open your browser and go to: http://127.0.0.1:5000

7. (Optional) Data Preprocessing & Model Training:
    Clean and preprocess data:
    ```bash
    python3.9 src/data_cleaner.py
    ```
    Train the recommender model and generate recommendations:
      ```bash
       python3.9 src/recommender.py
      ```
8. Usage
    1. Data Preprocessing:
       Run the preprocess.py script to preprocess the data:
       ```bash
       python3.9 src/preprocess.py
       ```
       - Input: raw_data/Electronics_5.json
       - Output: preprocessed_data/preprocessed_data.csv

    2. Data Cleaning:
       Run the data_cleaner.py script to clean the preprocessed data:
       ```bash
       python3.9 src/data_cleaner.py
       ```
       - Input: preprocessed_data/preprocessed_data.csv
       - Output: cleaned/cleaned_data.csv
       
    3. Train Recommender: 
       After the data preprocessing step, run the recommender.py script to generate personalized recommendations.
      ```bash
       python3.9 src/recommender.py
      ``` 
      - Outputs:
        JSON: data/results/recommendations.json – Contains the full set of recommendations in a structured format.
        CSV: data/results/top_5_recommendations.csv – Contains the top-5 recommendations for each user for easy processing.

   4. Run the Flask App: Start the Flask app to display recommendations:
   ```bash
   python3.9 main.py
    ```

   5. Visualize Data: Open notebooks/exploratory_data_analysis.ipynb in Jupyter Notebook to explore data distributions.
   
   6. Run Full Pipeline: Execute `run.py` to clean, preprocess, and train:
      ```bash
        python3.9 src/run.py
       ``` 
   7. Results:
  Top-5 Recommendations → data/results/top_5_recommendations.csv
  RMSE → 1.83 (based on SVD with filtered user-item interactions)
  
   
   8. Dependencies
    - Python 3.9+
    - NumPy
    - Pandas
    - Flask
    - Matplotlib
    - Seaborn
    - Scikit-surprise

9. License
   This project is licensed under the MIT License. See the LICENSE file for more information.

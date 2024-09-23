# Spotify-Genre-Predicting-Model
## Code-Pudding-Sept-24 Team: TuneTensor

## Description
This project builds a machine learning model that predicts the genre of a song using various metrics provided by Spotify. The goal is to create a predictive model that can  classify the genre of a song based on its features such as danceability, energy, tempo, and other characteristics.  Spotify API is used to retrieve these song metrics for a new track and make predictions on new songs.

## Setup Instructions:

### Spotify API
Setup API at https://developer.spotify.com/

use python code:
```python
client_id = "your-client-id"
client_secret = "your-client-secret"

# Authenticate with Spotify API
sp = spotipy.Spotify(auth_manager=SpotifyClientCredentials(client_id=client_id, client_secret=client_secret))

# Test
result = sp.search(q='breath away', type='track', limit=1)
print(result)
```

Follow these steps if you need to set up the project locally:

**Clone the Repository**

```bash
git clone https://github.com/zoeyespinoza/Spotify-Genre-Predicting-Model---Code-Pudding-Sept-24/.git
cd Spotify-Genre-Predicting-Model---Code-Pudding-Sept-24/
npm install
npm run dev
```

Install requirments.txt to run .ipynb files locally:

```bash
pip install -r requirements.txt
```

## Data Project
### Workflow:
1. Collect Data
    
    Build a dataset from Spotify API calls. Store each new API call locally in 'clean_spotify_set_2'. We read from that file for the data needed to train models.

2. Preprocess Data:

    Clean and preprocess dataset for model training.
3. Train Models:
    
    Train models using the audio metrics as features and genre as target.
    
    Evaluate the model's performance using cross-validation and metrics (accuracy, F1-score, AUC-ROC).
4. Evaluate Model Performance:

    Check for the effectiveness of the model. Analyze predictions.    
5. Make Predictions on New Songs:
    
    Trained a machine learning model to predicts the genre of a new song based on its Spotify audio features.

## Conclusion
Conclusions about model performances, a table of the models' metrics, and graphs are provided.

| Index | Model                              | F1        | AUC_ROC  | Accuracy  |
|-------|------------------------------------|-----------|----------|-----------|
| 0     | Random Forest                      | 0.472206  | 0.885439 | 0.471111  |
| 1     | Support Vector Machine (SVM)      | 0.424195  | NaN      | 0.426667  |
| 2     | Gradient Boosting                  | 0.464789  | 0.867793 | 0.457778  |
| 3     | SVM with PCA                      | 0.464789  | 0.867793 | 0.457778  |
| 4     | Random Forest with class weights    | 0.429641  | NaN      | 0.422222  |
| 5     | CatBoostClassifier                 | 0.574362  | 0.913466 | 0.568889  |
| 6     | Logistic Regression                | 0.424918  | 0.874830 | 0.417778  |
| 7     | KNeighbors Classifier              | 0.437653  | 0.773724 | 0.435556  |


- The CatBoostClassifier works best for the AUC_ROC, accuracy, and f1 metrics. Metrics for all the models tried were collected in the above table for easy comparison. A constant model would be right only 10% of the time. CatBoost had an overall accuracy of .57. Classification reports were generated for each model for ease of comparison across individual genres and models. Support Vector Machines are incompatible with roc_auc scores so a np.nan was left in that spot in the table and graphs.
- The easiest way to improve models' performances would be to add more data to the 'clean_spotify_set2.csv' file. The code has been set up to allow for automatic updating of the dataset to increase the variety of data it has to work with, while checking for duplicates.
- This code originally classified between 20 genres. The genres were shrunk to raise overall accuracy metrics for the models and allow the models to make clearer distinctions. The top ten most accurate genres from that list of 20 were chosen. Classical music consistently was the most identifiable across models. Of the original 20, the genre 'Soul' was least likely to be recognized which seems strangely appropriate of a computer. The API call still requests 20 different genres even though only ten were used for model training to try to keep the dataset as balanced as possible.
- The predict_genre() method was not able to be tested given certain restrictions with the API and relatively tight timeframe for this project.

## Members:

Ayyammal G. - Data Scientist [Github](https://github.com/ayyammal-g) - [Linkedin](https://www.linkedin.com/in/ayyammal-g-25462591/)

Erik M. - Data Scientist [Github](https://github.com/tempest-fugue) - [Linkedin]()

Zoey Espinoza - Data Scientist [Github](https://github.com/zoeyespinoza) - [Linkedin](https://www.linkedin.com/in/zoeyespinoza/)

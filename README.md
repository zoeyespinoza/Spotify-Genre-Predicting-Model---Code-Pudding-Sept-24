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

## Members:

Ayyammal G. - Data Scientist [Github](https://github.com/ayyammal-g) - [Linkedin](https://www.linkedin.com/in/ayyammal-g-25462591/)

Erik M. - Data Scientist [Github](https://github.com/tempest-fugue) - [Linkedin]()

Zoey Espinoza - Data Scientist [Github](https://github.com/zoeyespinoza) - [Linkedin](https://www.linkedin.com/in/zoeyespinoza/)

# Time-Based Music Recommendation Model

A dynamic music recommendation system that suggests curated playlists based on the time of day and the user's listening habits using Spotify's Web API.

**IMPORTANT API NOTICE**
- As of now, Spotify's Web API has disabled access to audio features (e.g., danceability, energy, valence).
- This project relies on those features for clustering and recommendations.
- Running the notebook will likely fail (e.g., 403 errors), return empty audio features, or produce no recommendations.

## Features
- Authenticates with Spotify via OAuth.
- Collects recent tracks and their audio features (currently unavailable due to API changes).
- Clusters tracks by mood-related features (valence, energy, danceability, etc.).
- Generates time-of-day recommendations (morning, afternoon, evening).

## Prerequisites
- Python 3.9+
- A Spotify account
- Spotify Developer App credentials (Client ID, Client Secret)

## 1) Create a Spotify Developer App
- Go to the Spotify Developer Dashboard and accept the terms.
- Click “Create an App” and fill:
  - App Name: Time-Based Music Recommendation Model
  - Description: Time-Based Music Recommendation Model is a dynamic music recommendation system that suggests curated playlists based on the time of day and the user's unique listening habits.
  - Website URL: http://127.0.0.1
  - Redirect URIs:
    - http://127.0.0.1:8888/callback
    - http://127.0.0.1:5000/callback
  - API/SDKs: Check “Web API” and accept terms.
- Save and copy your Client ID. Click “Show Client Secret” to reveal and copy it.

## 2) Configure Environment Variables
Create a .env file in the project root:
```bash
SPOTIFY_CLIENT_ID=your_client_id_here
SPOTIFY_CLIENT_SECRET=your_client_secret_here
SPOTIFY_REDIRECT_URI=http://127.0.0.1:8888/callback
```
Note: The redirect URI must match one configured in your Spotify app.

## 3) Install Dependencies
```bash
pip install spotipy pandas scikit-learn numpy python-dotenv
```

## 4) Run the Notebook
- Open:
  - f:\Music Taste Prediction Model\Time-Based Music Recommendation Model\Music Recommendation Model(Jupyter).ipynb
- Run cells in order to authenticate and fetch data.

## Expected behavior during Spotify API audio-feature outage
- Authentication may succeed.
- Audio feature fetching will fail or return empty results.
- The notebook will print “No audio features found.” or error due to disabled endpoint.
- Recommendations will not be generated.

## Troubleshooting
- Invalid redirect URI: Ensure it exactly matches your Spotify app settings.
- Auth/account issues: Delete any .cache* files and re-run.
- No recent tracks: Play a few songs, then re-run.
- Audio features error/empty:
- This is due to Spotify disabling audio features in the Web API.

## Screenshot (old Spotify Web API)
![App Screenshot](./Screenshot/Screenshot%202025-11-18%20082501.png)
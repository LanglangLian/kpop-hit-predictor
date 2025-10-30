# K-pop Hit Predictor: What Makes a Song Go Viral?

This project explores **which musical features make K-pop songs popular** - combining data science, machine learning, and Spotify's audio analytics.
By analyzing thousands of K-pop tracks released between **2023 and 2025**, this project aims to identify how song characteristics (such as danceability, energy, tempo, and valence) shape popularity.

## Motivation

K-pop isn’t what it used to be — at least, not in sound.
In the early 2010s, you could easily tell a song’s era:
bright synths, catchy hooks, bubblegum energy.
Today, things sound different.
A single track might shift from trap beats to disco basslines to dreamy vocals — all within three minutes.
The boundaries between “styles” are fading, and that raises a question worth asking:
**what kind of sound makes a K-pop song popular now?**


## Research Questions

1. **Prediction:**  
   Can we predict whether a K-pop song will be a *hit* based on its Spotify audio features?

2. **Explanation:**  
   Which musical features (energy, valence, tempo, etc.) contribute most to popularity?

3. **Evolution:**  
   How have K-pop’s musical styles changed from 2023 to 2025?

##  Methodology

### 1. **Data Collection**
- Used the **Spotify Web API** via `spotipy` to scrape:
    - Artists in the `k-pop` genre
    - Albums and tracks from 2023 to 2025
    - Audio features (`danceability`, `energy`, `valence`, `tempo`, etc.)
    - Popularity scores for each track
- Implemented in a custom class `KpopCollector` for reusable data extraction.

### 2. **Feature Engineering**
- Combined Kaggle and Spotify API data into a unified dataset.
- Created a binary target:
  ```python
  is_hit = 1 if popularity >= 90th percentile else 0

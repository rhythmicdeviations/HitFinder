# HitFinder

## Project Description

**HitFinder** is a Python project to determine the impact of various audio-related features in the popularity level of songs in Western popular music.

Data for the project is based on Spotify's API [[1]](https://developer.spotify.com/documentation/web-api), which provides access to the pertinent data for millions of tracks. The API is used directly, in addition to the Python package `spotipy` [[2]](https://spotipy.readthedocs.io/en/2.24.0/#api-reference), which is handy for having already built out some of the custom functions needed to access Spotify data.

## Feature Definitions

14 distinct features were obtained with the objective of predicting the popularity of any given Spotify track, using thousands of tracks of training data. Their definitions are copied from Spotify's API reference for tracks [[3]](https://developer.spotify.com/documentation/web-api/reference/get-track) and reference for audio features of tracks [[4]](https://developer.spotify.com/documentation/web-api/reference/get-audio-features).
1. `explicit`: Whether or not the track has explicit lyrics (true = yes it does; false = no it does not OR unknown).
2. `danceability`: Danceability describes how suitable a track is for dancing based on a combination of musical elements including tempo, rhythm stability, beat strength, and overall regularity. A value of 0.0 is least danceable and 1.0 is most danceable.
3. `energy`: Energy is a measure from 0.0 to 1.0 and represents a perceptual measure of intensity and activity. Typically, energetic tracks feel fast, loud, and noisy. For example, death metal has high energy, while a Bach prelude scores low on the scale. Perceptual features contributing to this attribute include dynamic range, perceived loudness, timbre, onset rate, and general entropy.
4. `key`: The key the track is in. Integers map to pitches using standard Pitch Class notation. E.g. 0 = C, 1 = C♯/D♭, 2 = D, and so on. If no key was detected, the value is -1.
5. `loudness`: The overall loudness of a track in decibels (dB). Loudness values are averaged across the entire track and are useful for comparing relative loudness of tracks. Loudness is the quality of a sound that is the primary psychological correlate of physical strength (amplitude). Values typically range between -60 and 0 db.
6. `mode`: Mode indicates the modality (major or minor) of a track, the type of scale from which its melodic content is derived. Major is represented by 1 and minor is 0.
7. `speechiness`: Speechiness detects the presence of spoken words in a track. The more exclusively speech-like the recording (e.g. talk show, audio book, poetry), the closer to 1.0 the attribute value. Values above 0.66 describe tracks that are probably made entirely of spoken words. Values between 0.33 and 0.66 describe tracks that may contain both music and speech, either in sections or layered, including such cases as rap music. Values below 0.33 most likely represent music and other non-speech-like tracks.
8. `acousticness`: A confidence measure from 0.0 to 1.0 of whether the track is acoustic. 1.0 represents high confidence the track is acoustic.
9. `instrumentalness`: Predicts whether a track contains no vocals. "Ooh" and "aah" sounds are treated as instrumental in this context. Rap or spoken word tracks are clearly "vocal". The closer the instrumentalness value is to 1.0, the greater likelihood the track contains no vocal content. Values above 0.5 are intended to represent instrumental tracks, but confidence is higher as the value approaches 1.0.
10. `liveness`: Detects the presence of an audience in the recording. Higher liveness values represent an increased probability that the track was performed live. A value above 0.8 provides strong likelihood that the track is live.
11. `valence`: A measure from 0.0 to 1.0 describing the musical positiveness conveyed by a track. Tracks with high valence sound more positive (e.g. happy, cheerful, euphoric), while tracks with low valence sound more negative (e.g. sad, depressed, angry).
12. `tempo`: The overall estimated tempo of a track in beats per minute (BPM). In musical terminology, tempo is the speed or pace of a given piece and derives directly from the average beat duration.
13. `duration_ms`: The duration of the track in milliseconds.
14. `time_signature`: An estimated time signature. The time signature (meter) is a notational convention to specify how many beats are in each bar (or measure). The time signature ranges from 3 to 7 indicating time signatures of "3/4", to "7/4".

The definition of the target feature, `popularity`, can also be found on Spotify's API reference for tracks.
1. `popularity`: The popularity of the track. The value will be between 0 and 100, with 100 being the most popular. The popularity of a track is a value between 0 and 100, with 100 being the most popular. The popularity is calculated by algorithm and is based, in the most part, on the total number of plays the track has had and how recent those plays are.
Generally speaking, songs that are being played a lot now will have a higher popularity than songs that were played a lot in the past. Duplicate tracks (e.g. the same track from a single and an album) are rated independently. Artist and album popularity is derived mathematically from track popularity.

## Installation

To run the code, download everything into a working directory satisfactory to you.

You will then need to change a few variables unique to you. In the `.env` file, add your own `CLIENT_ID` and `CLIENT_SECRET` using the Spotify API. You can find the values needed by creating an app in Spotify's web developer dashboard [[5]](https://youtu.be/WAmEZBEeNmg?si=og3Sn_fwvU9MNc6-).

Next, proceed to Usage.

## Usage

Order of project files used is:

1. `1_get_data.ipynb`: Obtain track data used for modeling.

**IMPORTANT**: Install the package `spotipy` using the following command, providing you use pip:
```python
pip install spotipy
```

2. `2_data_prep.ipynb`: Preparation of track data for modeling.
- EDA
- Cleaning
- Feature importance
- Feature list creation

## Contributing

Please open an issue for potential contribution, or check issue history.

## Contact

Author: Enrique Cardenas III
Email: rc3email@gmail.com
LinkedIn: https://www.linkedin.com/in/enriquecardenas24/
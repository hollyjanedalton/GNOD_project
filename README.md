# Spotify Song Recommender

## Background
**GNOD** is a website that provides recommendations for music, art, literature, and products based on filtering algorithms. 

We are data analysts hired to create a **song recommender** of popular songs for **GNOD**, by clustering songs together based on their sound features.

## Process
1. **Prototype 1**(: Create a list of Top Songs and Artists from webscraping websites like Billboard Hot 100. 
      - Create a recommender where the user inputs a song title and check if that song is in the Hot 100 list.
      -If the song is on the list, return a random song and artists from the list. If it's not on the list, let the user know there is no recommendation at this time.
2. **Connect to Spotify API** and import at least 10,000 songs 
3. **Prototype 2**: Cluster the 10,000 songs into 6 groups
      - Build a model using K-means clustering (6 clusters), using the audio features of the 10,000 songs on spotify
          - Scale the audio features of songs 
          - Initialize a K-means model using default parameters
          - Fit the model to song data 
          - Create a column in the dataframe called "cluster" with the songs assigned cluster
      - If the user inputs a song title that's not on the Hot 100 list, find audio features of the song on Spotify, and recommend a song within the same cluster
4. **Assemble project pipeline**
  - Pipeline receives the song input and checks if it's in the Hot 100 list
  - If it's not, send the song to the Spotify API and get its audio features and store them in a variable
  - Scale the audio features using the scaler from Step 3
  - Get the cluster of the song from the Kmeans model created in Step 3
  - From dataframe of 10,000 collected songs, randomly select a song that belongs to the same cluster
  - Final step: print suggested song. This is the final song recommendation

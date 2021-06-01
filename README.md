# Yelp On the Go!
## Collaborative Filtering Application
Authors: Albert Giang, Julian Bonnells, Tiffany Christensen;
Date: 06/03/2021


## Directions to run: 
1. Set up: Download preprocessed and formatted dataset 
     * Download Location (google drive folder):      
        * https://drive.google.com/drive/folders/1zzZMU-4mTBFcn4qJNZ0cP38_0hArSysx?usp=sharing
     * Files to Download:
        * MA_reviews.json
        * MA_users.json
        * MA_restaurants.json
2. Navigate to main Predictive rating and recommender algorithm
     * Collab_Filtering.ipynb file

## Required Installations:
1. The Surprise library
      * Needed to run the predictive rating and recommender algorithms. 
      * The first cell block of the Collab_Filtering.ipynb has the pip command to install the library
      * More information of the library can be found on it's website: http://surpriselib.com/                  


## Repository Navigation:
1) Preprocessing.ipynb
	- This file processes the raw yelp dataset and filters out reviews, users, and businesses for a specific state
        - The full Yelp dataset can be found here: https://www.yelp.com/dataset/download
2) recommender_down_select.ipynb
	- This file opens the preprocessed dataset and runs a gridsearch using different predictive rating algorithms to determine the best hyperparameters for each algorithm
        - A k-folds of 5 cross-validation was ran for each algorithm with their best hyperparameters to determine the algorithm with the lowest RSME
        - That algorithm (SVD++ in this case) was then chosen to be used in the Collab_Filtering.ipynb file
	- Much of the code is commented out with a summary of the gridsearch output given after each code block. 
        - This code takes a long time to run and was only needed to be ran once
	- The full code output is also given at the end of the file
	- The end user can uncomment out all of the code to run their own gridsearch
3) Collab_Filtering.ipynb
	- This file opens the preprocessed dataset and runs SVD++ to get the predictive ratings of our sample user
	- The top 25 ratings of the sample user is outputted as a top 25 recommended restaurants for that user to visit.

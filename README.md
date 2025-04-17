# Project-5
Data Science Project 5

## Problem Statement
We are a team of data scientists consulting film directors who want to increase their chances of winning an Oscar. We will provide insights into whether a movie is likely to win in at least one of the 23 Oscar categories. Using multiple datasets of past Oscar-nominated and winning films, we will build a binary classification model to predict Oscar successes based on features such as genre, runtime, IMDb rating, etc. The model will be evaluated using accuracy, precision, recall, and F1 score.

## Table of contents:
Data Cleaning: Ryan.ipynb
Data Visualizations: Rachels.ipynb
Data Analyzation: Swathi.ipynb
Data Modling/Evaluation: felix.ipynb

## Data Sets
#### Base dataframes:
Oscar_Nominations_Winners.csv(): Contains a list of movies that have been nominated for an oscar
master_oscar.csv (https://dataful.in/search/?q=oscars): Contains a list of movies that have been nominated and won an oscar in its respective categories

#### Cleaned df used 
oscars.csv : Contains a merged and cleaned format of both dataframes

## Data Dictionary
#### Of oscars.csv
film: (object) Name of the film
ceromony: (object) The oscar ceremony 
actor_in_a_leading_role: (float) 1st Oscar category (1 = Won in that category, 0 = did not win)
actor_in_a_supporting_role: (float) 2nd Oscar category (1 = Won in that category, 0 = did not win)
actress_in_a_leading_role:(float) 3rd Oscar category (1 = Won in that category, 0 = did not win)
actress_in_a_supporting_role:(float) 4th Oscar category (1 = Won in that category, 0 = did not win)
animated_feature_film:(float) 5th Oscar category (1 = Won in that category, 0 = did not win)
animated_short_film:(float) 6th Oscar category (1 = Won in that category, 0 = did not win)
best_picture:(float) 7th Oscar category (1 = Won in that category, 0 = did not win)
cinematography:(float) 8th Oscar category (1 = Won in that category, 0 = did not win)
costume_design:(float) 9th Oscar category (1 = Won in that category, 0 = did not win)
directing:(float) 10th Oscar category (1 = Won in that category, 0 = did not win)
documentary_feature_film:(float) 11th Oscar category (1 = Won in that category, 0 = did not win)
documentary_short_film:(float) 12th Oscar category (1 = Won in that category, 0 = did not win)
film_editing:(float) 13th Oscar category (1 = Won in that category, 0 = did not win)
international_feature_film:(float) 14th Oscar category (1 = Won in that category, 0 = did not win)
live_action_short_film:(float) 15th Oscar category (1 = Won in that category, 0 = did not win)
makeup_and_hairstyling:(float) 16th Oscar category (1 = Won in that category, 0 = did not win)
music_original_score:(float) 17th Oscar category (1 = Won in that category, 0 = did not win)
music_original_song:(float) 18th Oscar category (1 = Won in that category, 0 = did not win)
production_design:(float) 19th Oscar category (1 = Won in that category, 0 = did not win)
sound:(float) 20th Oscar category (1 = Won in that category, 0 = did not win)
visual_effects:(float) 21st Oscar category (1 = Won in that category, 0 = did not win)
writing_adapted_screenplay:(float) 22nd Oscar category (1 = Won in that category, 0 = did not win)
writing_original_screenplay:(float) 23rd Oscar category (1 = Won in that category, 0 = did not win)
total_oscars_won:(float) The total number of oscars an individual film has won
won:(int) The target variable, (1 = film had won at least 1 oscar, 0 = film was only nominated, did not win)
title_type: (float) the type of move (Movie, short, documentary, etc)
imdb_rating:(float) rating given to movie by imdb
year:(int) the year the film was released
num_votes:(int) the number of votes given on imdb
directors: (float) the name of the director and/or directors of a film
action:(int) 1st genre category (1 = yes in that genre, 0 = not in that genre)
adventure:(int) 2nd genre category (1 = yes in that genre, 0 = not in that genre)
biography:(int) 3rd genre category (1 = yes in that genre, 0 = not in that genre)
comdey:(int) 4th genre category (1 = yes in that genre, 0 = not in that genre)
crime:(int) 5th genre category (1 = yes in that genre, 0 = not in that genre)
documentary:(int) 6th genre category (1 = yes in that genre, 0 = not in that genre)
drama:(int) 7th genre category (1 = yes in that genre, 0 = not in that genre)
family:(int) 8th genre category (1 = yes in that genre, 0 = not in that genre)
fantasy:(int) 9th genre category (1 = yes in that genre, 0 = not in that genre)
film_noir:(int) 10th genre category (1 = yes in that genre, 0 = not in that genre)
history:(int) 11th genre category (1 = yes in that genre, 0 = not in that genre)
horror:(int) 12th genre category (1 = yes in that genre, 0 = not in that genre)
music:(int) 13th genre category (1 = yes in that genre, 0 = not in that genre)
musical:(int) 14th genre category (1 = yes in that genre, 0 = not in that genre)
mystery:(int) 15th genre category (1 = yes in that genre, 0 = not in that genre)
news:(int) 16th genre category (1 = yes in that genre, 0 = not in that genre)
romance:(int) 17th genre category (1 = yes in that genre, 0 = not in that genre)
sci-fi:(int) 18th genre category (1 = yes in that genre, 0 = not in that genre)
short:(int) 19th genre category (1 = yes in that genre, 0 = not in that genre)
sports:(int) 20th genre category (1 = yes in that genre, 0 = not in that genre)
talk-show:(int) 21st genre category (1 = yes in that genre, 0 = not in that genre)
thriller:(int) 22nd genre category (1 = yes in that genre, 0 = not in that genre)
war:(int) 23rd genre category (1 = yes in that genre, 0 = not in that genre)
western:(int) 24th genre category (1 = yes in that genre, 0 = not in that genre)
num_nominations: (int) the number of nominations that a movie recieved in all award categories 
num_directors: (int) the number of directors that a movie had
nominated_acting:(int) the number of nominations that a movie recieved in that category
nominated_animation:(int) the number of nominations that a movie recieved in that category
nominated_cinematography:(int) the number of nominations that a movie recieved in that category 
nominated_costume_design:(int) the number of nominations that a movie recieved in that category
nominated_directing:(int) the number of nominations that a movie recieved in that category
nominated_documentary:(int) the number of nominations that a movie recieved in that category
nominated_editing:(int) the number of nominations that a movie recieved in that category
nominated_international_feature:(int) the number of nominations that a movie recieved in that category
nominated_makeup_and_hairstyling:(int) the number of nominations that a movie recieved in that category
nominated_music:(int) the number of nominations that a movie recieved in that category
nominated_other:(int) the number of nomnations that a movie recieved in that category
nominated_picture:(int) the number of nominations that a movie recieved in that category
nominated_production_design:(int) the number of nominations that a movie recieved in that category
nominated_short_film:(int) the number of nominations that a movie recieved in that category
nominated_sound:(int) the number of nominations that a movie recieved in that category
nominated_visual_effects:(int) the number of nominations that a movie recieved in that category
nominated_writing:(int) the number of nominations that a movie recieved in that category


# Executive summary/Brief Analysis

There is an imbalance of classes in the model. There are roughly 2000 more rows of data that did not win an Oscar, so as expected our baseline model is poor with a score of 27%.  


## Data Description & Preparation

We used two datasets for this project:

1. **Oscar Awards Dataset** – contains detailed information about Oscar-nominated films, including award categories, nomination outcomes, and the year of the ceremony.
2. **IMDb Metadata Dataset** – provides metadata for films such as IMDb rating, number of votes, runtime, genres, and popularity metrics.

To prepare the data for modeling, we merged the two datasets using the **film title** as the common key. Prior to merging, we ensured consistent formatting by standardizing column names and cleaning up whitespace or special characters in film titles.

Once merged, we:

- Filtered out unnecessary columns and dropped award categories not directly relevant to the modeling task.
- Consolidated the `award_category` column by grouping similar awards under broader categories (e.g., different screenplay awards grouped under "Writing").
- Applied **one-hot encoding** to the award categories to capture each film's nomination distribution.
- Aggregated the dataset at the **film level** using groupby, summarizing nominations and retaining unique values for IMDb metadata fields.
- Removed missing or clearly erroneous data (e.g., films with missing runtime or IMDb ratings).

This final cleaned dataset allowed us to build a robust classification model to predict Oscar-winning films.

##  Software Requirements

The analysis and modeling in this project were conducted using Python and the following core libraries:

- **Pandas** – for data loading, cleaning, merging, and manipulation
- **NumPy** – for numerical operations and array handling
- **Scikit-learn** – for model building, evaluation, and data preprocessing
- **XGBoost** – for advanced gradient boosting classification (optional model)
- **Matplotlib** & **Seaborn** – for data visualization and plotting feature importances

To run this project, ensure you have Python 3.8+ and install the required libraries using:

```bash
pip install pandas numpy scikit-learn xgboost matplotlib seaborn


## Model: Random Forest Classifier
We trained a **Random Forest Classifier** to predict whether a film would win an Oscar based on its features such as IMDb rating, runtime, genre, number of nominations, and more. The model was evaluated on a held-out test set using standard classification metrics.

### Performance Summary

| Metric    | Class 0 (No Win) | Class 1 (Win) |
|-----------|------------------|----------------|
| Precision | 0.85             | 0.64           |
| Recall    | 0.87             | 0.60           |
| F1-Score  | 0.86             | 0.62           |

- **Overall Accuracy**: 80%
- **Macro Avg F1-Score**: 0.74
- **Weighted Avg F1-Score**: 0.80

### Interpretation

- The model performs well in identifying films that did **not** win (Class 0), with high precision and recall.
- Predicting **Oscar-winning** films (Class 1) is more challenging, as seen in the lower precision (0.64) and recall (0.60).
- This imbalance is likely due to fewer Oscar winners in the dataset, causing the model to lean conservative in its predictions.
- Feature importance analysis showed that factors like **IMDb rating**, **number of nominations**, and certain **award categories** contributed most to predictive performance.

## Conclusions & Recommendations 
Our model successfully met our primary goal of accurately predicting whether a film is likely to win at least one Oscar. Starting from a base accuracy score of just 27%, our final model achieved an accuracy of 80%, demonstrating strong predictive capability. Based on the insights gained from the model, we recommend that producers and production companies consider focusing on films within the biography, sport, and music genres, and aim for a runtime between 120 to 150 minutes. Additionally, collaborating with top directors such as Steven Spielberg, William Wyler, and George Cukor may further increase a film's chances of Oscar success. For future improvements, we suggest incorporating additional features such as the presence of leading actors, predicted box office earnings, and more detailed production data to further refine and enhance the model’s performance.
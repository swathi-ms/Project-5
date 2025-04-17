# Project-5
Data Science Project 5

## Problem Statement
We are a team of data scientists consulting film directors who want to increase their chances of winning an Oscar. We will provide insights into whether a movie is likely to win in at least one of the 23 Oscar categories. Using multiple datasets of past Oscar-nominated and winning films, we will build a binary classification model to predict Oscar successes based on features such as genre, runtime, IMDb rating, etc. The model will be evaluated using accuracy, precision, recall, and F1 score.

## Table of contents:
- Data Cleaning: Ryan.ipynb
- Data Visualizations: Rachels.ipynb
- Data Analyzation: Swathi2.ipynb
- Data Modeling/Evaluation: felix.ipynb

## Data Sets
#### Base dataframes:
Swathi.csv(https://www.imdb.com/list/ls088723321/?ref_=exp_t_1&view=compact): Contains a list of all Oscar nominations and Winners in IMDb website.
master_oscar_1.csv(https://dataful.in/search/?q=oscars): Contains a list of movies that have been nominated and won an oscar in its respective categories

#### Cleaned df used 
final.csv: Contains a merged and cleaned format of both dataframes.

## Data Dictionary
#### Of oscars.csv
- **film**: (object) Name of the film  
- **ceremony**: (object) The Oscar ceremony  

**Oscar Categories (1 = Won, 0 = Did not win):**
- **actor_in_a_leading_role**  
- **actor_in_a_supporting_role**  
- **actress_in_a_leading_role**  
- **actress_in_a_supporting_role**  
- **animated_feature_film**  
- **animated_short_film**  
- **best_picture**  
- **cinematography**  
- **costume_design**  
- **directing**  
- **documentary_feature_film**  
- **documentary_short_film**  
- **film_editing**  
- **international_feature_film**  
- **live_action_short_film**  
- **makeup_and_hairstyling**  
- **music_original_score**  
- **music_original_song**  
- **production_design**  
- **sound**  
- **visual_effects**  
- **writing_adapted_screenplay**  
- **writing_original_screenplay**  

- **total_oscars_won**: (float) Total Oscars won by the film  
- **won**: (int) Target variable (1 = won at least one Oscar, 0 = only nominated)  
- **title_type**: (float) Type of movie (Movie, short, documentary, etc)  
- **imdb_rating**: (float) IMDb rating  
- **year**: (int) Year of release  
- **num_votes**: (int) IMDb vote count  
- **directors**: (float) Name(s) of the director(s)  

**Genres (1 = Yes, 0 = No):**
- **action**  
- **adventure**  
- **biography**  
- **comedy** 
- **crime**  
- **documentary**  
- **drama**  
- **family**  
- **fantasy**  
- **film_noir**  
- **history**  
- **horror**  
- **music**  
- **musical**  
- **mystery**  
- **news**  
- **romance**  
- **sci-fi**  
- **short**  
- **sports**  
- **talk-show**  
- **thriller**  
- **war**  
- **western**  

**Nomination Features (Count of nominations per category):**
- **num_nominations**: (int) Total number of nominations  
- **num_directors**: (int) Number of directors  
- **nominated_acting**  
- **nominated_animation**  
- **nominated_cinematography**  
- **nominated_costume_design**  
- **nominated_directing**  
- **nominated_documentary**  
- **nominated_editing**  
- **nominated_international_feature**  
- **nominated_makeup_and_hairstyling**  
- **nominated_music**  
- **nominated_other**  
- **nominated_picture**  
- **nominated_production_design**  
- **nominated_short_film**  
- **nominated_sound**  
- **nominated_visual_effects**  
- **nominated_writing**



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
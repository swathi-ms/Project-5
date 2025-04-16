# Project-5
Data Science Project 5

## Problem Statement
We are a team of data scientists consulting film directors who want to increase their chances of winning an Oscar. We will provide insights into whether a movie is likely to win in at least one of the 23 Oscar categories. Using multiple datasets of past Oscar-nominated and winning films, we will build a binary classification model to predict Oscar successes based on features such as genre, runtime, IMDb rating, etc. The model will be evaluated using accuracy, precision, recall, and F1 score.

## Data Sets
#### Base dataframes:
Oscar_Nominations_Winners.csv (): Contains a list of movies that have been nominated for an oscar
master_oscar.csv (): Contains a list of movies that have been nominated and won an oscar in its respective categories

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


## Brief Summary of Analysis


## Conclusions & Recommendations 
**PROJECT ROTTEN TOMATOES**


Code implementation and complete technicl details can be found at
https://github.com/vikrammuduvadi/Capstone_Rotten_tomatoes/blob/main/rotten_tomatoes.ipynb

**Business Objective**

The basic objective of this project is to predict if a movie can be termed 'ROTTEN' or 'CERTIFIED FRESH' or 'FRESH'.
In other words, the concept can be extended into determine if the movie will be a 'HIT' or a 'DUD' at the Boxoffice.
Now the goal of this project involves understanding what practical parameters will be needed to arrive at this decision. 

**Business Use/Practical use**

1. This model can be used by directors and producers to determine if the movie would be a hit or not, and if it even
   makes sense for them to make the movie
2. This can also be used by streaming companies like Netflix etc to identify if the movie will be viewed well or not.

**Data source**

This rotten tomoatoes data is derived from Kaggle
https://www.kaggle.com/datasets/stefanoleone992/rotten-tomatoes-movies-and-critic-reviews-dataset?select=rotten_tomatoes_movies.csv

**Model Implementation**

The python code with a detailed analysis is found in rotten_tomatoes.ipynb

**Data Understanding**

The Kaggle data had 17,712 entries with 22 columns. What this means is there were 17,712 rows of data and 22 columns.
The target column was tomatometer_status whose values are 'Rotten', 'Certified Fresh', or, 'Fresh'
There were 21 other features to determine the outcome.

**Data  Cleanup**

By visual insection and common sense, a lot of unwanted features were eliminated. Eventually the below features were picked to predict the data

  
 0   content_rating      
 1   runtime            
 2   tomatometer_rating  
 3   audience_status     
 4   audience_rating    
 5   audience_count       

Out of these, content_rating, audience_status, and tomatometer status are considered as categorical features i.e they are not numerical values.
Ordinal Encoding and Onehot encoding was used to convert these non-numeric values.

Other Data clean up steps included
1. Removing all duplicate values
2. Removing all null values
3. Removing values that were not a number

After all the above specified data cleaning methods, we were left with 8077 entries. Basically 50% of the data was not usable.
This clean up is absolutely important to ensure our predictions make sense.

**Data division**

Let us divide the data into Training and Testing data. a 75-25 split was used.
The accuracy on the test data would be instrumental in knowing if the model works and if it can be used 

**Model selection**

To determine the outcome, we used the below methods
1. K NEarest neighbors (KNN)
2. Decision Tree algorithm

  KNN

  With the number of nearest neighbors set to the default value, and the model fit, the accuracy rate was seen at 56%.
  This is a pretty poor number and we need more improvements to use this model

  Decision Tree

  The Decision tree yielded a much improved accuracy of around 86% and the training model had an accuracy rate of 100%.
  So the decsion tree would be a good model to make good predictions.

**Model improvement**

  Based on the CRISP-DM framework, I checked to see if the model could yield better results. On revisiting the 
  input parameters, I found the audience_count to be redundant because it had too many values and there was no 
  co-relation between the output and the input.
  Thus, I re-attempted to run the entire model without the input parameter audience_count.

  KNN 

  With the number of nearest neighbors set to the default value, and the model fit, the accuracy rate was seen improving
  to around 86%, this is a 30% improvement. These numbers are on lines of the Decision tree model.

  Decision Tree

  The Decision tree did not yield much of an improvement and settled in at around 86%. This concluded that Decision tree
  was a more robust model for this kind of an activity. However, good accuracy was also observed on KNN when the input 
  parameters were tweaked.
  
**Achieving optimum accuracy **

  An attempt was made to make the Decision tree the most robust by tweaking the hyper paramters and it was found that
  with the optimal parameters, an accuracy of 90% was achieved.

**Closing Statement**

We have arrived at a good model to yield consistent results to predict the status of a movie. 90% accuracy is reliable 
information.

**Next steps and recommendations**

This kind of a model can be used by
1. Producers/Directors to make an early estimate of if the movie will work or not, and if can find ways to trim the budget
2. Content streaming companies like Netflix, Amazon Prime can use these models to determine if they must decide to even
   stream some movies on their platforms.
   We could go one level up and for movies that are going to be really popular, explore ways to get advertizing revenues

Explore how this model can be further enhanced to handle the above scenarios. Also, further explore how inputs like 
Actors, Directors etc can be used to further solidify this model.



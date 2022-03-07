# Neural Network Charity Analysis

## Overview of the analysis
Alphabet Soup, a non-profit is a philantropic foundation, dedicated to help organizations with goals to protect the environment, improve people's wellbeing, and unify the world. They have raised and donated over $10B over the past 20 years. With the goal to predict which donations are impactful, a CSV file was provided by Alphabet Soup’s business team. It contains data on organizations that have received funding from Alphabet Soup over the years. Within this dataset the included fields about each organization are:

- EIN and NAME—Identification columns
- APPLICATION_TYPE—Alphabet Soup application type
- AFFILIATION—Affiliated sector of industry
- CLASSIFICATION—Government organization classification
- USE_CASE—Use case for funding
- ORGANIZATION—Organization type
- STATUS—Active status
- INCOME_AMT—Income classification
- SPECIAL_CONSIDERATIONS—Special consideration for application
- ASK_AMT—Funding amount requested
- IS_SUCCESSFUL—Was the money used effectively

A deep-learning neural network was setup to predict outcomes.

## Results

- Data Preprocessing
The target variable is IS_SUCCESSFUL. This is provided in the form of a boolean.
EIN and NAME were removed from the dataset, since they are simply identification variables.
The remaining variables were considered to be the features for the model.
- Compiling, Training, and Evaluating the Model
The "optimized" model consists of 4 layers, using the tanh function for hidden layers, and the sigmoid function for the output layer. The number of neurons for the input layer is calculated on the basis of the number of input features within the training data. For the remaining hidden layers, 102, 80, and 80 neurons were used. The model was run for 300 epochs. 

The target model performance (75%) was not reached.

The steps that were taken to improve performance, compared to the previous iteration were as follows:
- Remove outlier entries:
    - 3 entries with an ASK_AMT of $5B
    - 2 entries with the lowest ASK_AMT paired with the highest INCOME_AMT 
- Removed redundant columns: removed SPECIAL_CONSIDERATIONS_N, since SPECIAL_CONSIDERATIONS_Y contains essentially the same data
- Reduced the number of bins to 4, for the CLASSIFICATION column

## Summary

The optimization was not successful. Recommendations for further adjustments to this classification problem include binning the ASK_AMT into a small (6-8) number of bins.
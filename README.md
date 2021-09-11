# Predicting New York Times Comment Engagement
![paperstack](./newspaper_image.jpg)
## Business Problem
The New York Times is reevaluating the comment moderation on its web content, in hopes of stimulating reader engagement, deepening the quality of user feedback, and identifying potentially problematic comments more quickly. They would like to use the existing recommendation tool to develop a machine learning model that will predict which comments will be most popular and which comments will be most likely to generate further engagement. The end goal will be to sort comments according to this prediction (as a third option available to users in addition to presenting comments ranked in response to recommendations or chronologically). Additionally, they would like to identify comments that are most likely to be flagged as abuse to bring these comments to the attention of moderators more quickly.
## Data
The data used for this project represents articles and comments on The New York Times website in April 2017. I downloaded the dataset from Kaggle at this address. The data was originally collected using the New York Times API. The process for this collection is well-documented on the Kaggle page.
My original goal was to use data points from 4 months' worth of articles (potentially up to 1 million) and and unrestricted number of TF-IDF columns. That goal quickly proved unrealistic, as even fitting the TF-IDF model to that number of data points would have demanded over 1 TB of RAM. Ultimately, I ended up using about 2 weeks' worth of data, or around 130,000 data points.
## Results
| model name | precision | recall | accuracy |
---|---|---|---|
| logistic regression | 94/16 | 74/47 | 71% |
| random forest |  91/39 | 100/0 | 90% |


In addition to the size restrictions on the data mentioned previously, I was also limited by the processing power at my disposal. With the data at the current size, I was unable to run additional models due to the amount of RAM they would have required to process a model of that size. Given that I was already severely limiting the quality of the data, I did not want to whittle down the data further in order to run models on an ineffective data set. I had hoped to develop models using: support vector machines, naive Bayes, and XGBoost - none of which were able to work with this dataset with the given RAM. Even attempts to reduce the dimensionality of the data failed, as I was unable to fit a PCA decomposer with the limited processing power.

Attempted Models:
*   Support Vector Machine
*   Decision Tree Classifier
*   Naive Bayes
*   Grid Search (for Random Forest or Decision Tree)
Each of these models used too much RAM or computation time to be effective.
## Recommendations
The results of this project indicate that running a more formal analysis with more computation power (potentially in a distributed system such as PySpark) would lead to promising results around predicting the engagement levels of a comment based on the text itself. 
## For Further Information
Please review the narrative of the analysis in [my jupyter notebook](./capstone-nyt.ipynb) and review [my non-technical presentation](./capstone-NYT Comments Presentation.pdf).

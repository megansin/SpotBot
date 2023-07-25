# SpotBot: Fake Yelp review analyzer

Code files are Jupyter Notebook files and were developed in Amazon Sagemaker. Modification to remove Sagemaker packages is needed if running in another environment. Labeled dataset must also be obtained by contacting professors listed on our website: https://seamussullivan.github.io/CS539-SpotBot-Website/. Data files are not stored in this repository due to privacy concerns.

Spotbot is a project that **attempts** to classify Yelp reviews as either fraudulent or valid. This is done using a two-model process.

1. A review from the Yelp dataset is converted from a JSON object into a dataframe row.
2. The row's "text" column is fed through the tokenizer and encoded for prediction using our trained BERT model.
3. The BERT model is used to classify the text as either valid or fraudulent. This value is stored as the 'BERT_flag' column

## *TO BE COMPLETED IN THE FUTURE*
4. The row now contains a set of categorical attributes (stars, funny, useful,... etc) in addition to the BERT_flag. This updated row is now passed to Autogluon.
5. Autogluon uses a weighted set of models to classify the row as either valid or fraudulent.

## Why didn't this work
Large scale prediction on the first model is slow and incredibly memory intensive. This meant it took too long to obtain all of our test dataset to feed into the second model. With more time we could have waited for the model to predict the text of our training dataset to train the autogluon model.

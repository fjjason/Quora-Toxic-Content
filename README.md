# Quora-Toxic-Content



Very Quick Personal Project. Using Neural Network classify toxic content on Quora


Kaggle Competition Link
https://www.kaggle.com/c/quora-insincere-questions-classification


The dataset
test.csv          questions and labels
train.csv         questions

Questions are the questions users are asking on Quora. 
The Labels are binary labels which basically says if questions are marked as toxic/insincere or not

1: toxic
0: not toxic

This guy did a good job with the data explorations, shows the distribution, examples and different top n-grams. 
https://www.kaggle.com/sudalairajkumar/simple-exploration-notebook-qiqc


Technology:
  * Word Embedding: 
      Gensim Word2Vec Embedding(Kaggle Provided pretrained Word2Vec Model)
  * Text Classification: 
      Keras Neural Networks
      * Adadelta best gradient boosting optimizer in my case
      * All hidden layers performs best with ReLu Activations
      * 3 hidden layers with number nodes all between the input-dim(300) and output dim(2)
      * Output layer: Sigmoid activation with 2 dimension in the last layer for bianry classification
  * Score: 
      Neg-MSE(Negative Means Squared Error)
  * Optimizing hyperparameters: 
      Grid Search
  * Overfitting prevention mechanism: 
      none, since the epoches are low and do not notice overfitting
      Might add more epoches and add early stopping and dropout
  * Feature Selection: 
      None, performed Select K-Best and Chi-Squared feature selection 
      but all features seems to be useful to the model. 
      
Results:

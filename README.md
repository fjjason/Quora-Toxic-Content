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
      
Results: This is the data that were predicted as toxic by my model. The results are very impressive

0    Why do so many women become so rude and arrogant when they get just a little bit of we...           1
17                                                                      Can we eat human poop?           1
21   Why do so many people on this damn site not actually answer the question, but give som...           1
27   Let's say that hypothetically the alt-right nightmare comes true, and Muslims take ove...           1
58   Why do Bengali and Kolkata people dominate Hindi language speaking people from Delhi, ...           1
99   Shouldn’t we blame those who knew how bad Trump was and didn’t go to vote for today’s ...           1
105          Why does the media let Saudi Arabia get away with murder of 50,000 kids in Yemen?           1
211                            Why do Asian people hate white and black people? (READ COMMENT)           1
270              What does Habib Fanny think about black people calling each other the N-Word?           1
273  If only some of the Muslims are bad then why don't the majority of Muslims stop demoli...           1
281                                        Why do the Majority of Malays in Malaysia hate DAP?           1
289                                                  Why do White Americans hate Black people?           1
294  Why is Sharia Law so stupid and why do so many Muslims want it enforced in Canada & Am...           1
327                                                               Why do girls suck guys dick?           1
358  Do all conservatives think liberals are stupid and do all liberals think conservatives...           1
467                                               Why are north Indians always angry and rude?           1
517      Why are many Americans getting the impression that people in Ireland don't like them?           1
541  Instead of blaming the world for Islamophobia do Muslims want to introspect the real r...           1
544  Why do Chinese and Indian (in particular) best and brightest students still flock to A...           1
570                       Why do people think white privilege is real when it's blatantly not? 

# machine-learning-challenge

I decided on 3 different models to try: a random forest model , a KNN model, and a
Neural Network model.

The random forest model performed the best; however, the grid search 
took much longer than that of the KNN model. The final grid search I did showed the
best parameters as 'criterion'='entropy', 'max_features'='log2', 'n_estimators'=500.
This gave an accuracy of .901. That said, my base model has an accuracy of .89 
with 'criterion'='gini', 'max_features'='sqrt', 'n_estimators'=200 so I don't think
that these parameters affected the model much. A lot of the other parameters seemed 
to be more limiting than giving further options so I did not test them much, 
especially since this grid search was already taking nearly 4 minutes to compile. 

The next best preforming was the neural network. This model does not really allow
for GridSeachCV to be used. I tried to change the number of hidden layers but this
did not seem to greatly affect the model. Drastically increasing the epochs did make
a signficant difference though. This makes sense as we are iterating over the data to 
learn from more and more. The highest accuracy I got to was .89 with a loss of .27.

Finally, with the KNN model I realized that the grid search may be over fitting as
with the suggested parameters the train accuracy shot up to 1.00. However, the test
accuracy actually went down from my simple model. I realized then that using the grid
search was not ideal in choosing the k value. I then used the loop from our exercises
and decided to utilizing k=15. There wasn't a lot of parameters in the grid search 
to adjust but I did try to make some changes. The highest accuracary I got was .80.
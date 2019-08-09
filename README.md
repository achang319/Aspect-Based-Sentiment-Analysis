# Aspect-Based-Sentiment-Analysis

## Training data set 
   Two .csv files( one for restaurant review and one for computer review) was provided - data-1_train.csv and data-2_train.csv. 
     The description of each column in each .csv file is as fellows:
     Column A: review sentence id (unique id for a training instance).
     Column B: review sentence
     Column C: aspect term in the sentence
     Column D: aspect term location  [format: start index -- End index]
     Column E: sentiment label
   
   We renamed the files to computer_review.csv and restaurant_review.csv for to adhere to mnemonics.

## Test data set
    Given two .csv test files: one for Data-1 and another for Data-2. Each row is one test instance (just like training data files (Exactly same format!)). But, class labels not provided.

## Implementation
    First we import our training data and test data. Then we define two important functions: the first is for preprocessing the text and aspect term in both training and testing data. The other function is to calculate the weights(tfidf) for the words in order to vectorize the text (after preprocessing). 

    def preprocess :  We remove the punctuation as well as [comma], then remove stop words, finally lemmatize and tokenize the words. 
    def get_weights : Two steps of assigning weights. First assign the aspect term a highest weight of 2. Then assign weights to corresponding adjacent words. The weightagge of words decrease as its location increases from aspect term. Then we see the tfidfs of each word and discard words with more weight but less tfidf. 
    
    After preprocessing and giving weights to our training data, we cross validate using different models. 
    Finally for choosing the training model we use Random Forest for both training sets as it gives better result for each data. 

    In the end we preprocess our test data and vectorize it. Then we use our trained model to predict the class label.

## Working :
    
    Every time you run the notebook, DELETE the previous result txt files, because the results will append to the previous results. Sorry about the inconvinence.

    Simply open both IPython in jupyter notebook and run all the codes.  
    The result will show up in Cheng_Chang_Sreemata_Banerjee_Data-1.txt for computer review, and Cheng_Chang_Sreemata_Banerjee_Data-2.txt for restaurant review.

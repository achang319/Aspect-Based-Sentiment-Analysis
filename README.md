# Aspect-Based-Sentiment-Analysis

## Training data set 
   Two .csv training files(data-1_train.csv for restaurant review and data-2_train.csv for computer review)
     The description of each column in each .csv file is as fellows:
     Column A: review sentence id (unique id for a training instance).
     Column B: review sentence
     Column C: aspect term in the sentence
     Column D: aspect term location  [format: start index -- End index]
     Column E: sentiment label
   
## Test data set
   Two .csv test files: one for Data-1 and another for Data-2. Each row is one test instance (just like training data files (Exactly same format!)). But, class labels not provided.

## Implementation
    First, import our training data and test data. Then define two important functions: the first is for preprocessing the text and aspect term in both training and testing data. The other function is to calculate the weights(tf-idf) for the words in order to vectorize the text (after preprocessing). 

    def preprocess :  Remove the punctuation as well as [comma], then remove stop words, finally lemmatize and tokenize the words. 
    def get_weights : Two steps of assigning weights. First assign the aspect term a highest weight of 2. Then assign weights to corresponding adjacent words. The weight of words decrease as its location increases from aspect term. Then we see the tf-idfs of each word and discard words with more weight but less tf-idf. 
    
    After preprocessing and giving weights to our training data, we cross validate using different models. 
    Finally for choosing the training model we use Random Forest for both training sets as it gives better result for each data. 

    In the end we preprocess our test data and vectorize it. Then we use our trained model to predict the class label.


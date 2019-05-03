# NER_LSTM_TAGGER 

Code -> ner_tagging.ipynb

1. 
Firstly i parsed the data to extract words and it's corresponding NER. After that, i got unique word tokens and unique tags present in the dataset. After, generated dictionary of unique words to numerical representation where tokens is key and number is value. Similarly i did for tags. Once this done, converted the sentences into sequences of fixed length. Similarly converted each sentences tag into corresponding sequences.

2.
maximum lenth of sentence(maxlen) = 49
Embedding dimension = 50
SpatialDropout1D = 0.2 -> Dropout simply drop random features and independent of each other. In SpatialDropout it will drop entire feature along the axis.
LSTM Hidden Units = 100 
Since all these hyperparameters are randomly choosen but it can be tune after trying model with different hyperparameters and comparison between them.

3. 
Increasing the batch size will reduce per epoch time but model learning will be slow. It will take more no. of epochs to reach optimal point. I have used early stopping there may be chance model training will stop before reaching the optimal point.

4.
Validation Data
              precision   recall  f1-score  support

      PER       0.56      0.70      0.62      1793
      LOC       0.43      0.84      0.57      1833
      ORG       0.53      0.69      0.60      1338
     MISC       0.66      0.74      0.70       919

micro avg       0.51      0.75      0.61      5883

macro avg       0.53      0.75      0.61      5883

Test Data:
              precision  recall  f1-score   support

      LOC       0.29      0.70      0.41      1656
     MISC       0.52      0.63      0.57       701
      ORG       0.63      0.60      0.61      1657
      PER       0.49      0.52      0.50      1578

micro avg       0.42      0.61      0.50      5592

macro avg       0.48      0.61      0.52      5592

5.
Apart from LSTM i will like to try train using ELMO Embedding, BERT and Flair as these are state of the art for NLP.

6.
I faced little bit difficulty while parsing the data. After that deciding the initial parameters for model. To generate recall, precision,f1 score and classification i was pretty much confused how go about it.

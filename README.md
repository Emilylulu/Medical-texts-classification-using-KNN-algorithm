# Medical-texts-classification-using-KNN-algorithm
## Dataset
The training dataset consists of 14442 records and the test dataset consists of 14438 records. We provide you with the training class labels and the test labels are held out. The data are provided as text in train.dat and test.dat, which should be processed appropriately.
## Goal
The goal of this competition is to allow you to develop predictive models that can determine, given a particular medical abstract, which one of 5 classes it belongs to. As such, the goal would be to develop the best classification model, with the restriction that you can only use your own implementation of the k-NN classifier.
## Approach
### preprocessing
First read data from dataset. Separate training label and training data from training set. Use stop_words api from nltk.corpus package to find common used words, delete these words to make dictionary small. Use stem api from ipywidgets package to stem all words. Again, this step is also mean to small dictionary to get better performance. Use cmer method to deal with data frequency problem. But after several tests, it shows that cmer=1 will get better precision, so not use cmer after processing above steps. Store the result as 1-D array. So that later will easily build matrix. Build matrix just like activity classification 1.
### KNN algorithm
If target match one in training data, just use its vector to calculate euclidean distance with matrix, if not find, build a new matrix for target with dictionary exists. Then use knn algorithm to calculate neighbors. Similarity approach is Cosine similarity. Use csr_l2normalize to normalize the matrix and target matrix, so that don’t have to calculate length. Add index as key value to similarity so that it will store index. Then sort it to get kth nearest neighbor. 
<img width="314" alt="screen shot 2018-10-17 at 4 30 04 pm" src="https://user-images.githubusercontent.com/27938420/47122041-faeb0b00-d229-11e8-8723-bf80d1e23d4d.png">
### Evalution
<img width="263" alt="screen shot 2018-10-17 at 4 31 09 pm" src="https://user-images.githubusercontent.com/27938420/47122077-1bb36080-d22a-11e8-95f7-9d0981062a7b.png">

# Zack-Skovgaard

Description of Minimum Neighbors kNN

Minimum Neighbors k-Nearest Neighbors (kNN) is a new version of kNN (to the best of my knowledge) that focuses on learning the minimum number of nearest neighbors (exlcuding oneself) that would be needed in order to correctly identify a data point within the training set. Many kNN iterations deal with changing distance metrics, weights and other hyperparameters related to correctly classifying the testing dataset with respect to the training set which serves as a 'memory bank'. In Minimum Neighbors kNN, the minimum nearest neighbors value to correclty classify each training point from only the points available within the training set are learned prior to classifying the testing data points. 

In essence, here is how the code works:
1. Each point in the training dataset is compared to every other point in the training dataset.
2. The minimum number of nearest neighbors (e.g. k = 3) to correctly classify, on a majority basis, the training data point is saved with that training data point. This is done for each training point.
3. Each point in the TESTING dataset finds its first nearest neighbor in the training dataset.
4. The testing data point will then assume the minimum number of nearest neighbors that were previously found for the training data point.
5. kNNClassification will then proceed for the testing data point using the number of k neighbors that it had assumed.

Currently (7/24/2023), this algorithm supports kNN classification and not kNN regression but I will work on the kNN regression version. 
In addition, this algorithm in the code provided in the colab was developed on using only two characteristics ('X', 'Y') but this can be changed to as many characteristics as the future user would like but will need to make sure that the rest of the code matches up (particulary in the zipping).
The target variable is labeled 'Classification'. This can also be changed by the future user but will have to make sure to change it for all uses of it in the code. 
Training dataset and testing dataset are loaded as two separate dataframes in the code. 
If the variables that are being testing by the future user are of different magnitudes, they will need to be scaled as minimum neighbors kNN does not include a scaling function. 

# KNN-blood-transfusion-dataset
Determine wether donors would donate blood in march 2007 using prior data.

## Data Set Information
To demonstrate the RFMTC marketing model (a modified version of RFM), this study adopted the donor database of Blood Transfusion Service Center in Hsin-Chu City in Taiwan. The center passes their blood transfusion service bus to one university in Hsin-Chu City to gather blood donated about every three months. To build a FRMTC model, we selected 748 donors at random from the donor database. These 748 donor data, each one included R (Recency - months since last donation), F (Frequency - total number of donation), M (Monetary - total blood donated in c.c.), T (Time - months since first donation), and a binary variable representing whether he/she donated blood in March 2007 (1 stand for donating blood; 0 stands for not donating blood).

https://archive.ics.uci.edu/ml/datasets/Blood+Transfusion+Service+Center

## Seaborn pairplot of the dataset
![Seaborn pairplot of dataset](https://i.imgur.com/ON1F6a3.png)

## Loops to find optimal values
Using simple loops i was able to find both optimal test size and K values, testing k 1-100 and test size of 0.2, 0.25, 0.33.

## Results
The top three confusion matrices all scored a test set accuracy of 0.79 with k_neighbours 21, 22 and 23.

[TP][FP]

[FN][TN]
* TP = True Positive
* FP = False Positive
* FN = False Negative
* TN = True Negative

![Result matrices](https://i.imgur.com/FXAmKu9.png)

From the confusion matrices we can see that the model is better at predicting wether someone did not donate blood than wether someone did. The accuracy is however rather impressive given the features available!

## Cross-validation (K-fold)
To validate our dataset i used k-fold with 5 splits and k_neighbors 21 which scored:

* [0.5866666666666667, 0.7866666666666666, 0.8933333333333333, 0.7516778523489933, 0.9060402684563759].

Average of k_fold scores: 
* 0.7848769574944071.

As the validation score and test accuracy are almost the same, we can expect to get similar results on new data.

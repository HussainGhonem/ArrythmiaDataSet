# ArrythmiaDataSet
The data set is a database record for several patients that are being tested for arrhythmia. The data  set aim is to distinguish between the presence and the absence of cardiac arrhythmia and to classify  it in one of the 16 groups. The data set aims to determine the type of arrhythmia from the ECG  recordings. This data set contains 279 attributes, 206 are linear; the data set also contains 452  instances.
The data set is a database record for several patients that are being tested for arrhythmia. The data 
set aim is to distinguish between the presence and the absence of cardiac arrhythmia and to classify 
it in one of the 16 groups. The data set aims to determine the type of arrhythmia from the ECG 
recordings. This data set contains 279 attributes, 206 are linear; the data set also contains 452 
instances.
In the beginning, I read the data, the data didn’t have a header so I have added a numeric header. 
Then I have a check for null values and found out that they did name null values as ‘?’ so I did 
replace all the ‘?’ values with null values. I counted the null values in the data set and there were 
407 null values. So, I did a checkup for null values in the column found out that column 13 has 
375 null values out of 451 values so I had to drop it since a column with that percentage of null 
values is a corrupted column. The other columns had an acceptable percentage of null values. I 
then changed the type of all columns in the database to have numeric values. After that, I did 
replace all the null values with a mean value of the correspondent column. I checked for duplicates 
and there was none existed in the database. Then I did use a standard scaler to rescale the data. At 
this point the data was clean so I had to know more about what I am dealing with. So, I did check 
the classification column which was column number 279, I count the values in it I found out that 
I am dealing with 13 different classifications. I did discover the class column more and found out 
that class 1 was the dominant class of 54.3% while the other 12 classes have less than 46%. Then 
I did cluster using the age columns which is the column number that equals 0 and the classes 
columns that carry the classification for the multiple arrhythmia groups. The clustering was done 
using the Gaussian mixture clustering the data into 13 clusters.
In solving the data imbalance, I have used the K-folds method with the nearest neighbor equals 5 
and in each algorithm, I did add a class weight equal to balanced, which will do balance the classes 
weight since I do have an imbalance in the number of classes, for example, I have 13 classes and
class 1 is 54.3% of the total output which will cause a major imbalance in the database. I also 
scaled the data set using Standard Scalar to decrease the effects of the outliers
I have built 4 models using three different algorithms the first one is SVC, the second is SVC with 
the pipeline, the third is logistic regression, and the fourth one is random forest classifier.
In the first model the SVC I did build a graph that will give me the best split percentage, then I did 
split the data to 25% for testing and 75% for training this percentage was the result from the 
previous graph. Then I did build another graph that will give me the best SVC kernel the result of 
this graph was the linear solver which will give me around 75% testing accuracy. Then I did draw
a learning graph a classification report then I ran a bias-variance decomp which gave me Bias 
equals 10.5, MSE equals 14.95, and Variance equals 4.5.
In the second model the SVC with pipeline I took the same split percentage from the previous 
model since they are the same algorithm. I applied the min-max scaler as the transform and the 
SVC as the estimator to the pipeline. The testing accuracy of this model was ~80%. Then I did 
draw a learning graph a classification report then I ran a bias-variance decomp which gave me Bias 
equals 2.7, MSE equals 5, and Variance equals 2.35.
In the third model the logistic regression I did build a graph that will give me the best split 
percentage, then I did split the data to 30% for testing and 70% for training this percentage was 
the result from the previous graph. Then I did build another graph which will give me the best 
solver the result of this graph was the newton-cg solver which will give me around 76% testing 
accuracy. Then I did draw a learning graph a classification report then I ran a bias-variance decomp 
which gave me Bias equals 9.1, MSE equals 13.5, and Variance equals 4.3.
In the fourth model the random forest classifier I did build a graph that will give me the best split 
percentage, then I did split the data to 40% for testing and 60% for training this percentage was 
the result from the previous graph. Then I did build another graph which will give me the best 
depth the result of this graph was the depth of 6 which will give me around 83% testing accuracy. 
Then I did draw a learning graph a classification report then I ran a bias-variance decomp which 
gave me Bias equals 11.3, MSE equals 15.6, and Variance equals 4.3.
Based on these results I would like to say that the best model will be the SVC with Pipeline which 
resulted in the second-highest testing percentage of 80% after the random forest classifier that 
resulted in 83% with a difference of around 3%. The SVC pipeline model also achieved the lowest 
difference between testing and training. It also achieved the lowest bias of 2.7 and the lowest 
variance of 2.35 which means that it also achieved the lowest MSE of 5.05.

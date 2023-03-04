# Deep-Neural-Networks-for-YouTube-Recommendations

This is an implementation of personalized movie recommendation using a neural network model proposed in the paper: Deep Neural Networks for Youtube Recommendations.

### Model

The overall structure of our recommendation network consists of two models, candidate generation and ranking. The candidate generation network generates a hundred movies from a large corpus. And then the ranking network ranks the a hundred movies and recommend maybe the top 10 movies to the user.

![Picture1](https://user-images.githubusercontent.com/62257166/222092298-dab9c635-4e07-4f34-b9e5-4cd87f1cfa8c.png)

### Dataset

We use MovieLens data from kaggle, which contains 10 thousand users with 100 thousand of ratings corresponded to 45 thousand of movies. This data contains about 30 different features that we can explore through it. 
![image](https://user-images.githubusercontent.com/62257166/222091961-51a4b9f4-77e1-4793-b406-04c229cf7bed.png)

## Candidate generation

![2023-03-01_11h04_01](https://user-images.githubusercontent.com/62257166/222094165-46fd5c98-e11e-4b6a-b8f3-56dd3b3693f6.png)

1. input the watching history.
2. predict the top 100 possible future watches, only by the pattern of watching history. it is simply just impossible to predict what a person will watch in the future, so the accuracy in this stage will not be high. In order to recommend better movies, we need to rank them later.

In the paper of youtube recommendation, adding depths to network improves the performance, and indeed it improves the learning speed. it turns out that adding depths does not improve in our network. high accuracy may not be a good sign in this stage, the data is easily overfitted in our case.


## Ranking

![2023-03-01_11h04_38](https://user-images.githubusercontent.com/62257166/222095484-0f6713af-d03c-4de2-9c19-2299d32e3a4f.png)

The ranking model has almost the same structure, although we add a lot more features to feed more user’s information, which makes the ranking network more personalized. We assign the best rated movie as label and predict the ratings in order to rank them.

![2023-03-01_11h06_30](https://user-images.githubusercontent.com/62257166/222106086-9b326fd6-3c6f-4a01-9bb1-66bcf9b242b1.png)


## Results



## Reference

https://static.googleusercontent.com/media/research.google.com/en//pubs/archive/45530.pdf


# Human activity recognition with openpose and Long Short-Term Memory on real time images

6 activities
5 performances
12 subjects

3 * 12 * 5 = 180 videos

60 videos per activity

output of body features are split into sub-sequence called window using sliding window approach

lstm can process single data points as well as sequence of data

one activity is 32 frames (10 for each second?)

training data: batches of 32 frames and activity label with it

input: (1, 32, 36) 
- 1 label
- 32 frames
- 36=2 coordinates for 18 body points

There are 7426 batches used for for 6 activities.


the training of Long Short Term
Memory network gives 91.56% accuracy. The data is split
into 80% as training data and 20% as testing data set.
Model is trained for 200000 iterations and results are
obtained with cross validation. The accuracy on testing
dataset is 87.12%.
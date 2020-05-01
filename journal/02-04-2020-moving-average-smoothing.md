02-04-2020-moving-average-smoothing.md

Today I'm focusing on improving the smoother module I have built to better prepare the data for upcoming neural network training.

So far my smoother module tries to smooth frames data by filling missing values with the previous value. I do this by moving through my frames and when I encounter a missing value then I fill it with a previous value.

Some pros/cons of this solution:

* pro: missing values get replaced by some value which gives the illusion that all "bodyparts are still intact"
* con: if there are multiple missing values in a sequence then they all get replaced by the same value which gives the illusion that the "body part stays at the same space" which probably cannot be the case since we are investigating moving actions (a backflip)

The next solutions to try are what are known as "Centered Moving Average" and "Trailing Moving Average". These methods are used to smooth time series data.

More details here: https://machinelearningmastery.com/moving-average-smoothing-for-time-series-forecasting-python/

I'm going with "Centered Moving Avrerage" since in my dataset the future values are known.

Now I'm reconsidering my previous solution...

Instead of substituting the missing values with previous ones I should instead find the next available value and fill the missing value by taking the average of the previous available and next available value.

Time for coding...



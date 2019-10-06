# MNIST Challenge: 
### To implement a model with less than 10000 parameters on MNIST data and get an accuracy of more than 99% in 10 epochs

The solutions were implemented in Keras with tensorflow backend. 
ADAM is used as an optimizer with initial learning rate 1e-3. Categorical Cross entropy is used as the loss function and accuracy as a metric.
A learning rate scheduler is available which decreases the learning rate by a factor which can be customized if the validation accuracy has not increased compared to its n-3rd run and if learning rate has not been decreased in the last 3 epochs. However, here it’s not being used as the factor is kept to be 1.

## Solution 1: Convolutions Model
Total params: 8,640
Trainable params: 8,580
Non-trainable params: 60

Used bigger kernels of size 7 × 7 and 5 × 5 as information is distributed globally in the image and not locally.
Accuracy on Test Set: 99.2% 
Now that the objective was achieved, tried reducing the parameters to less than 5k parameters.


## Solution 2: Separable Convolution Model
Total params: 4,967
Trainable params: 4,879
Non-trainable params: 88
Used smaller kernels of size 3 × 3 but with many channels.
Accuracy on Test Set: 98.42% 
Now that the objective was achieved, tried further by reducing the number of trainable parameters even further.


## Solution 3: Inception Model
Total params: 3,077
Trainable params: 3,077
Non-trainable params: 0
 
Made use of the inception module in the beginning. Used filters of various sizes – 1 × 1, 3 × 3, 5 × 5. Accuracy on Test Set: 97.36% 


## Observations
With an efficient architecture, smaller and more efficient models can be built with lesser parameters to achieve comparable performance. 
-	In the initial solution, model had 8640 parameters with an accuracy of 99.20%
-	In the second solution, model had 4967 parameters with an accuracy of 98.42%. The number of parameters were reduced by 42.5% with only 0.78% decrease in accuracy compared to the first solution.
-	In the third solution, model had 3077 parameters with an accuracy of 97.36 %. The number of parameters were reduced by 64.38% with only 1.84% decrease in accuracy compared to the first solution.

# Image-Noise-Reducer
Image Noise Reducer in Python using TensorFlow (Auto-Encoders)

This project can be used to remove noise from any image. It has been implemented using TensorFlow in Python.

Firstly, we will import all the libraries that we need for this project.

After we have finished importing all the libraries, the next thing we have to do is import/load the dataset. For this project we will use the Fashion MNIST dataset which contains 60,000 images in the training set and 10,000 images in the test set. We also normalize the images so as to get values between 0 and 1.

Since these are clean images and the images that we have in the real world may be noisy, for training purposes we add noise to the training and testing data and we then visualize the clean and the noisy data to have an understanding between them.

We now build a classifier which will be trained on clean images and it will be trained to output its respective class number. After training we get an accuracy of 91.73%. We then test it on the clean test set and we get an accuracy of 88.74% which is pretty good. We then also check it on the noisy test set to see if only our classifier is good but we get an accuracy of 25.85% which is very low and hence we need some other model.

Hence we now build an encoder model. What the encoder model does is reduce the size of the noisy image and by reducing the size or encoding it only focuses on the main details of the image. We then decode it to it's original size and hence it does not take the noise into account. After building this model, we train it for 100 epochs but we also put a callback such that if the loss doesn't decrease for 5 epochs, then it will stop training.

We then use this model to make the predictions and we can see that most of the noise from the image is removed and most of the features are retained. We also check the accuracy for this model and we see that we are getting a higher accuracy of 83.75% which is a huge improvement from 25%.

We now build a composite model. By composite model I mean we combile our encoder model and our classifier so that when we input a noisy image, it will clean the image using the encoder part and it will then pass this cleaned image into the classifier to get a class prediction. We see that the few images that we ouput are all predicted correctly.

We then save the weights separately and also the whole model which also includes the weights.

The classes are as below:

0 = T-shirt/top
1 = Trouser
2 = Pullover
3 = Dress
4 = Coat
5 = Sandal
6 = Shirt
7 = Sneaker
8 = Bag
9 = Ankle boot

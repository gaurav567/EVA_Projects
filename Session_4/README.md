<h3>Architectural Basics</h3>

1.How Many Layers?
-  Depends on Following Criteria discussed below-:
   Layers should be added such taht Size of Image should be equal to size of object going till last layer.(Convolutional layer)
   Max pooling concept can be used after 2-3 convolutional layer and could not be used before 2-3 layer before prediction layer.
   

2. Max Pooling
-  Max pooling is used to increase the receptive field and helps in building network logically within constraints(computional efficient)

3. 1x1 convolutions.
-  1x1 is used to combine information in transition block and thus helping us to reduce channel going forward exiting transition block to draw up other conclusion

4. 3x3 Convolutional
-  It is used to find out certain pattern and pass it on to another layer , it convolves over 9 block at once of huge image covering each pixel atleast once.

General Architecture.   
   Convolutional Block
   400x400 - 3x3x32 - 398x398
   398x398 - 3x3x64 - 396x396
   396x396 - 3x3x128 - 394x394
   394x394 - 3x3x256 - 392x392
   392x392 - 3x3x512 - 390x390
   
   Transistion Block
   390x390 - (1x1)x32 - 390x390  (combining various info such as arc made up of edges
   390x390 -  Maxpooling(2x2) - 195x195   (assumed detected edges and gradient(or any logical pattern) till this point)
   
   Then again convolution block start to draw furthur textures, patterns and so on.

5.Receptive Field
- Receptive field indicates how much percentage of image our network or layer is able to figure out at certain point.
  Two types of receptive field we consider -:
  Local receptive field - It is considered from previous layer to present layer.
  Global receptive field - It is calculated from where we started till where we are.

6.Softmax
- Softmax is just to scale up our observation to more discreate form so that information could be more specific and clear , but in risky cases it is not that helpful such as medical areas. 

7.Learning rate
- It is the rate by which our network learn to reach certain conclusion(minima point)it should not be very less or more , it should decrease with decreasing step from previous step to reach minima.
   eg Start LR -0.5 -> 0.3 ->0.2 -> 0.12 - > 0.06 -> 0.04 -> and so on to 0.

8.Kernels and how do we decide the number of kernels ?
- Kernels are basically dediced by looking into image size ,it's complexity.
  The more complex(can be expressed in channels) or huge image , the more no of kernels we need to deal to detect various patterns or outcomes.

9.Batch Normalization
- Batch Normalization is used to normalize the images in batches( mainly taking a mean of batch).
  usefulness -:
  To reduce biasness(much difference) throughout images.
  To reduce overfitting.

10.Image Normalization  
-  Image Normalization is done on input features.

11.Position of MaxPooling.
-  As discussed already, Max pooling concept can be used after 2-3 convolutional layer and could not be used before 2-3 layer before prediction layer.

12.Concept of Transistion Layers.
-  Discussed already, To increase receptive field, to reduce channel size before going forward to detect other pattern using another convolutional block.
   edges and gradient -> textures - patterns - part of objects - objects.
   Convolutional Block -> Transistion block -> convolutional block

13.Position of Transistion layer.
-  After and before Convolutional Block like below.
   Convolutional Block -> Transistion block -> convolutional block

14.Number of Epochs and when to increase them?
-  Epochs are generally increase to train model more by providing another random set of batch size again, Mainly used to improve validation accuracy or to reach certain conclusion such as model is overfitting or underfitting.
       Ideal Epoch size is 20-30( but still it depends on complexity of images provided).
	   
15.Dropout
-  Dropout is a technique which help network to get rid of problem of overfitting(good at training but not on testing dataset), It is used to shut down few kernels in forward propogation so that other kernels can able to learn well.
   It's value should be less in code - 0.1 to 0.2 fine enough.
   
16.When do we introduce DropOut, or when do we know we have some overfitting
-   yes we use dropout to get rid of overfitting, overfitting is when our model is performing good at training but not on validation or testing.
    can we observed through running code eg suppose Training acc - 99.8 and val acc is 99.1
    overfitted if we want val acc to 99.4 but training acc cannot be more than 100.

17.The distance of MaxPooling from Prediction
-  It should be 2-3 layers before prediction layer.

18.The distance of Batch Normalization from Prediction
-  It could be before prediction layer but not after it.

19.When do we stop convolutions and go ahead with a larger kernel or some other alternative (which we have not yet covered)
-  when our accuracy is not is not gud at testing as well as validation, we need to check for kernel as well(whether need to be increased or decreased.

20.How do we know our network is not going well, comparatively, very early
-  By checking Training and validation acc at each step , if their is no/decrease in improvement with increase in training accuracy(alternatively if training acc is not consistent with testing accuracy).

21.Batch Size, and effects of batch size.
-  Idealy we need to figure out perfect/threshold batch size for any dataset eg for mnist it is 128, for image net it is 16000 (approx), below it and after it your model may not work as perfect model.
   Increasing batch from initial lead to increase in training accuracy as network is able to differentiate images more accurately(because we provided large no classes one batch).

22.When to add validation checks
-  Add every point to track the performance of our model.

23.LR schedule and concept behind it
-  The concept behind declaring LR schedule is declaring and defining learning rate explicitly

24. Adam vs SGD
-   They both are optimizer used to update weight and bias while back propogation.
    SGD - Scholastic Gradient descent - updates thing incrementally,
    while adam work on batches.

Note -: The order of execution is discussed in my iterations coded as part of assignment 4.
------------------------------------------------x-------------------------------
	   

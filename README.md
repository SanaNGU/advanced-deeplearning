# advanced-deeplearning-course

### Practice 1:

In this task ,two optimizer were used(adaptive moment estimation and Stochastic gradient descent). The SGD was slower than Adam because it depends on the learning rate and the LR was quite small in this  assignment as a result, the model took time to converge while for adam, it leverages the power of adaptive learning rates methods to find individual learning rates for each parameter, as a result the training has faster convergence.


Note :although  the momentum parameter with the SGD helps us to progress faster but is still slower than adam.

 also, two activation function were used (Leaky relu and tanh).

 ### Practice 2:
 - task 1:Transfer Learning from ImageNet
 In practice, very few people train an entire Convolutional Network from scratch (with random initialization), because it is relatively rare to have a dataset of sufficient size. Instead, it is common to pretrain a ConvNet on a very large dataset (e.g. ImageNet, which contains 1.2 million images with 1000 categories), and then use the ConvNet either as an initialization or a fixed feature extractor for the task of interest.
 These two major transfer learning scenarios look as follows:

 - **Finetuning the convnet:** Instead of random initializaion, we initialize the network with a pretrained network, like the one that is trained on imagenet 1000 dataset. Rest of the training looks as usual.
 - **ConvNet as fixed feature extractor:** Here, we will freeze the weights for all of the network except that of the final fully connected layer. This last fully connected layer is replaced with a new one with random weights and only this layer is trained.
 for feature extractor we must freeze the parameter by making requires_grad to false
 for param in model.parameters():
     param.requires_grad = False
  This works because low level information extracted from the input image is universal between tasks, examples of such information is edge detection,
  shape detection and pattern detection. This is what the early layers are optimized to do, as where later layers extract more abstract features relevant for the task.

   - **Feature extrucion is defiantly faster than fine tuning, because we only train the last layers**
- task 2 Transfer Learning from MNIST:

### Practice 4:

In this notebook trained an RNN model(LSTM) to predict the next character given a sequence of characters. Such models are affectionately known as Char-RNNs.

We trained the Char-RNN ,The network will train character by character on on the Tiny Shakespeare dataset. After training , the network will be able to then  new text character by character based on the text from the dataset.

The steps I used to train the network:

- Data tokenization(convert text to int)
- Convert to one-hot vector
- Making training mini-batches
each mini-batxh with size of batch_size * sequence_length
- The training mini_batch should be (X,Y) pairs , wher Y is just the inputs shifted over by one character
- Define model (2 lstm) stacked together
- train and evaluate the model

# advanced-deeplearning-course


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

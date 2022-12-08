# Create a Superhero Name Generator with TensorFlow
 To predict a superhero name using a given letter





The problem statement in this project deals with the prediction of a superhero or supervillain name based on a single character as a seed input.

Firstly, I installed all the dependencies and imported the required libraries. I imported the data and began the analysis of the data.

The data consists of a single feature containing the superhero and the supervillain names.
To begin with the task I created the tokenizer and using the tokenizer I vectorized the texts or the names and manufactured the character to index and index to character dictionaries and the indexes are converted into a list of the tokenized vectors.

The intuition I adopted to deal with this problem statement is that using the given seed input character an another character is predicted as the output and then using the already given input and the output predicted together are used to predict an another character as an output and the similar process is carried out until a certain character or value is predicted that signifies the end of the prediction. All the letters predicted sequentially added to the seed input character gives the required superhero or supervillain name.

To follow this I assigned a tab value, i.e, ‘/t’ as a character at the end of each of the names available in the data that signifies the end of the prediction, i.e, if the character predicted is ‘/t’, the prediction stops.

Then, the tokenized sequences obtained earlier are processed. The sequences of the length greater than 2 are processed to obtain the sub-sequences. These sub-sequences are such that they consist of the sequences of the first two elements, first three elements and so on up to the sequences themselves.
This is done so that the inputs are in the format such that for a given character name, the sequences consist of the first two letters of the name such that the second element of the name is learnt by the model with the first element and then the first three letters such that the third element of the name is learnt by the model with the first two elements and so on.
The final sequences now obtained are pre padded to create the required input.

Then, a pipeline is built to define the training and the validation datasets.
Then, a sequential neural network model is built consisting of an embedding input layer, a convolution layer followed by a max pooling layer followed by a LSTM layer so that the contextual learning is achieved and finally a dense layer is added using the softmax activation function.
Then, I fine tuned the model after compilation using the ‘ADAM’ Optimizer and loss as sparse categorical entropy and the metrics as the Accuracy.
Finally, I evaluated the model.



# RNN-deep-learning

Do you know how Google’s autocompleting feature predicts the rest of the words a user is typing, or how Google Assistant works? This happens with the help of a special kind of neural network called a Recurrent Neural Network. And this is how Google’s autocompleting feature works - A collection of large volumes of most frequently occurring consecutive words is stored in a database, and this data is fed to a recurrent neural network. The network analyzes the data by finding the sequence of words occurring frequently and builds a model to predict the next word in the sentence. 

For example, if you search for “What’s the best food to eat in Las ______,” Google autocompletes to results in Vegas

![Alt Text](https://www.simplilearn.com/ice9/free_resources_article_thumb/RRN_vegas.png)

# What is a Recurrent Neural Network?

A Recurrent Neural Network works on the principle of saving the output of a particular layer and feeding this back to the input in order to predict the output of the layer.

Below is how you can convert a Feed-Forward Neural Network into a Recurrent Neural Network:

![Alt Text](https://www.simplilearn.com/ice9/free_resources_article_thumb/Simple_Recurrent_Neural_Network.png)
                      Fig: Simple Recurrent Neural Network
                      
The nodes in different layers of the neural network are compressed to form a single layer of recurrent neural networks. A, B, and C are the parameters of the network

![Alt Text](https://www.simplilearn.com/ice9/free_resources_article_thumb/Network_framework.gif)

                     Fig: Fully connected Recurrent Neural Network
                     
![Alt Text](https://www.simplilearn.com/ice9/free_resources_article_thumb/Fully_connected_Recurrent_Neural_Network.gif)

Here, “x” is the input layer, “h” is the hidden layer, and “y” is the output layer. A, B, and C are the network parameters used to improve the output of the model. At any given time t, the current input is a combination of input at x(t) and x(t-1). The output at any given time is fetched back to the network to improve on the output.

![Alt Text](https://www.simplilearn.com/ice9/free_resources_article_thumb/Fully_connected_Recurrent_Neural_Network1.png)

                     Fig: Fully connected Recurrent Neural Network
                     
# Feed-Forward Neural Networks

A feed-forward neural network allows information to flow only in the forward direction, from the input nodes, through the hidden layers, and to the output nodes. There are no cycles or loops in the network. 

Below is how a simplified presentation of a feed-forward neural network looks like:
![Alt Text](https://www.simplilearn.com/ice9/free_resources_article_thumb/Feed_forward_Neural_Network.png)
                     Fig: Feed-forward Neural Network
                     
In a feed-forward neural network, the decisions are based on the current input. It doesn’t memorize the past data, and there’s no future scope. Feed-forward neural networks are used in general regression and classification problems.

# HOW RECURRENT NEURAL NETWORKS WORK

To understand RNNs properly, you'll need a working knowledge of "normal“ feed-forward neural networks and sequential data. 

Sequential data is basically just ordered data in which related things follow each other. Examples are financial data or the DNA sequence. The most popular type of sequential data is perhaps time series data, which is just a series of data points that are listed in time order.

# RNN VS. FEED-FORWARD NEURAL NETWORKS

![Alt Text](https://builtin.com/sites/default/files/styles/ckeditor_optimize/public/inline-images/feed-forward-neural-network.png)

RNN’s and feed-forward neural networks get their names from the way they channel information.

In a feed-forward neural network, the information only moves in one direction — from the input layer, through the hidden layers, to the output layer. The information moves straight through the network and never touches a node twice.

Feed-forward neural networks have no memory of the input they receive and are bad at predicting what’s coming next. Because a feed-forward network only considers the current input, it has no notion of order in time. It simply can’t remember anything about what happened in the past except its training.

In a RNN the information cycles through a loop. When it makes a decision, it considers the current input and also what it has learned from the inputs it received previously.

The two images below illustrate the difference in information flow between a RNN and a feed-forward neural network.

![Alt Text](https://builtin.com/sites/default/files/styles/ckeditor_optimize/public/inline-images/rnn-vs-fnn.png)

A usual RNN has a short-term memory. In combination with a LSTM they also have a long-term memory (more on that later).

Another good way to illustrate the concept of a recurrent neural network's memory is to explain it with an example:

Imagine you have a normal feed-forward neural network and give it the word "neuron" as an input and it processes the word character by character. By the time it reaches the character "r," it has already forgotten about "n," "e" and "u," which makes it almost impossible for this type of neural network to predict which character would come next.

A recurrent neural network, however, is able to remember those characters because of its internal memory. It produces output, copies that output and loops it back into the network.

# Simply put: recurrent neural networks add the immediate past to the present.

Therefore, a RNN has two inputs: the present and the recent past. This is important because the sequence of data contains crucial information about what is coming next, which is why a RNN can do things other algorithms can’t.

A feed-forward neural network assigns, like all other deep learning algorithms, a weight matrix to its inputs and then produces the output. Note that RNNs apply weights to the current and also to the previous input. Furthermore, a recurrent neural network will also tweak the weights for both through gradient descent and backpropagation through time (BPTT). 

Also note that while feed-forward neural networks map one input to one output, RNNs can map one to many, many to many (translation) and many to one (classifying a voice).

![Alt Text](https://builtin.com/sites/default/files/styles/ckeditor_optimize/public/inline-images/Feed-Forward-Neural-Networks.png)

# BACKPROPAGATION THROUGH TIME
To understand the concept of backpropagation through time you'll need to understand the concepts of forward and backpropagation first. We could spend an entire article discussing these concepts, so I will attempt to provide as simple a definition as possible. 

In neural networks, you basically do forward-propagation to get the output of your model and check if this output is correct or incorrect, to get the error. Backpropagation is nothing but going backwards through your neural network to find the partial derivatives of the error with respect to the weights, which enables you to subtract this value from the weights.

Those derivatives are then used by gradient descent, an algorithm that can iteratively minimize a given function. Then it adjusts the weights up or down, depending on which decreases the error. That is exactly how a neural network learns during the training process.

So, with backpropagation you basically try to tweak the weights of your model while training.

The image below illustrates the concept of forward propagation and backpropagation in a feed-forward neural network:

![Alt Text](https://builtin.com/sites/default/files/styles/ckeditor_optimize/public/inline-images/propagatiom-rnn.png)

BPTT is basically just a fancy buzz word for doing backpropagation on an unrolled RNN. Unrolling is a visualization and conceptual tool, which helps you understand what’s going on within the network. Most of the time when implementing a recurrent neural network in the common programming frameworks, backpropagation is automatically taken care of, but you need to understand how it works to troubleshoot problems that may arise during the development process.

You can view a RNN as a sequence of neural networks that you train one after another with backpropagation.

The image below illustrates an unrolled RNN. On the left, the RNN is unrolled after the equal sign. Note there is no cycle after the equal sign since the different time steps are visualized and information is passed from one time step to the next. This illustration also shows why a RNN can be seen as a sequence of neural networks.

![Alt Text](https://builtin.com/sites/default/files/styles/ckeditor_optimize/public/inline-images/unrolled-rnn_0.png)

If you do BPTT, the conceptualization of unrolling is required since the error of a given timestep depends on the previous time step.

Within BPTT the error is backpropagated from the last to the first timestep, while unrolling all the timesteps. This allows calculating the error for each timestep, which allows updating the weights. Note that BPTT can be computationally expensive when you have a high number of timesteps.

# TWO ISSUES OF STANDARD RNN’S
There are two major obstacles RNN’s have had to deal with, but to understand them, you first need to know what a gradient is.

A gradient is a partial derivative with respect to its inputs. If you don’t know what that means, just think of it like this: a gradient measures how much the output of a function changes if you change the inputs a little bit.

You can also think of a gradient as the slope of a function. The higher the gradient, the steeper the slope and the faster a model can learn. But if the slope is zero, the model stops learning. A gradient simply measures the change in all weights with regard to the change in error.

# EXPLODING GRADIENTS
Exploding gradients are when the algorithm, without much reason, assigns a stupidly high importance to the weights. Fortunately, this problem can be easily solved by truncating or squashing the gradients.

# VANISHING GRADIENTS
Vanishing gradients occur when the values of a gradient are too small and the model stops learning or takes way too long as a result. This was a major problem in the 1990s and much harder to solve than the exploding gradients. Fortunately, it was solved through the concept of LSTM by Sepp Hochreiter and Juergen Schmidhuber.

 
# LONG SHORT-TERM MEMORY (LSTM)
Long short-term memory networks are an extension for recurrent neural networks, which basically extends the memory. Therefore it is well suited to learn from important experiences that have very long time lags in between.

The units of an LSTM are used as building units for the layers of a RNN, often called an LSTM network.

LSTMs enable RNNs to remember inputs over a long period of time. This is because LSTMs contain information in a memory, much like the memory of a computer. The LSTM can read, write and delete information from its memory.

This memory can be seen as a gated cell, with gated meaning the cell decides whether or not to store or delete information (i.e., if it opens the gates or not), based on the importance it assigns to the information. The assigning of importance happens through weights, which are also learned by the algorithm. This simply means that it learns over time what information is important and what is not.

In an LSTM you have three gates: input, forget and output gate. These gates determine whether or not to let new input in (input gate), delete the information because it isn’t important (forget gate), or let it impact the output at the current timestep (output gate). Below is an illustration of a RNN with its three gates:

![Alt Text](https://builtin.com/sites/default/files/styles/ckeditor_optimize/public/inline-images/rnn-three-gates.png)

The gates in an LSTM are analog in the form of sigmoids, meaning they range from zero to one. The fact that they are analog enables them to do backpropagation.

The problematic issues of vanishing gradients is solved through LSTM because it keeps the gradients steep enough, which keeps the training relatively short and the accuracy high.

# Why Recurrent Neural Networks?
Recurrent neural networks were created because there were a few issues in the feed-forward neural network:

Cannot handle sequential data
Considers only the current input
Cannot memorize previous inputs
The solution to these issues is the Recurrent Neural Network (RNN). An RNN can handle sequential data, accepting the current input data, and previously received inputs. RNNs can memorize previous inputs due to their internal memory.

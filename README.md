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

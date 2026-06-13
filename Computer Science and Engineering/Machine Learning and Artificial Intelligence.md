## Neural Networks
neural networks are an abstraction of the brain. we start with the idea of a perceptron/neuron, which is an abstraction of the building block of the brain - the nerve cell. multiple perceptrons are stacked in layers and are connected to the perceptrons in the adjacent layers. this network is subject to inputs, where in the input signals activate the individual perceptrons. 

more rigorously, each of the connections to a neuron are weighted values of the neurons in the previous layer along with a bias. mathematically, 

$$ n_{i,j} = \sum_{j=0}^{N}a_in_{i-1,j} + b_{i,j}$$
where $n_{i,j}$ is the value of the $j_{th}$ neuron in the $i_{th}$ layer and $b_{i, j}$ is the bias

the neural networks operate in two different phases. 
- the learning phase, where inputs are provided and based on successive perceptron activations, the output is obtained. this output is then compared with an expected output and based on that the weights of the neural network are updated using back propagation
- predict phase, where the inputs are fed and the outputs are read

this is the basic building block of the neural networks. to form more complex networks, we have different architectures/types of these networks for specific tasks. we have convoluted neural networks for vision related tasks, recurrent neural networks for natural language processing, text generation and so on.

off late we have a surge in the use of transformer architecture owing to the popularity of GPTs. 

## Algorithms
types of algorithms
- supervised
- unsupervised
- reinforcement learning


## Supervised learning
paradigm - the algorithms focus on teaching the machine by labelling the test data. on learning, the algorithms are able to readily label the real world. examples
- decision trees
- support vector machines...

## Unsupervised learning
paradigm - the algorithms pick the trends/patterns in the by themselves. examples
- k means clustering
- db scan

## Reinforcement learning
paradigm - the algorithms/agent learn by performing an action and getting feedback from the environment
- Q learning
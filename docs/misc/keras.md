# keras

[Keras](https://keras.io/) is a popular, high level API for implementing ML algorithms. 

Book: Deep Learning with Python by Francois Chollet, the creator of Keras.

It can run on top of TF, CNTK, and Theano.

# chapter 2

## parts of NN

- model/network:
    a directed acyclic graph of layers. it tells network architecture.

- layers:
    layers define the *tensor operations* to be applied on data which will be input to that layer.

- loss: shorthand for *loss function*
   how network will measure success of *task that neural network will do*.
   loss function calculates *model error*.

- optimizer: 
    Tells how gradients are used to calculate the weights during *backpropagation*. Basically it tells how learning proceeds.

- metrics: 
    the metric tells what is being monitored during *training* and *testing* phase.


## chapter 3

### Keras is:
1. a model/layer library, and it does not support tensor operations. For tensor operartions *keras* relies on *back-end-engines* like tensor-flow, cntk, and theano.

2. It can run on CPU and GPUs. 
    - When it runs on CPUs it uses a *Basic Linear Algebra Sub-program called Eigne*, 
    - When running on GPU it uses *NVIDEA's CUDA DNN library*.

## Creating a NN using keras

### step 1 

Define network architecture.

1. Using sequential API
    
    suitable only for *linear stack of layers*
    
psuedocode:

    model = models.Sequential()
    model.add(layers.input())
    model.add(layers.Dense)

2. Using functional API

    suitable for creating arbitrary *directed-acyclic-graph of layers*
    layers are used as *functions*, and *tesnors* as their arguments

psuedocode:

    input_tensor = layer.input()
    x = layers.Dense(input_tensor)
    output_tensor = layer.Dense(input_tensor)
    model = models.Model(input=input_tensor, output=output_tensor)

activation functions:
- relu
- sigmoid


### step 2

Configure the learning process.

    model.compile(loss=loss_function, optimizer=my_optimizer, metrics=['accuracy'])

Some popular loss functions:
- RMSProp

### step 3

Perform the learning.

    model.fit(input_tensor, output_tensor, epochs, batch_size)

## Linear regression

trying to predict a continuous variable.

### Normalizing the training data

generally input data has a number of features, and each of these features has a different range of values. For effectively using this data for ML algorithms it is standard pract to *Normalize the data*:

Data normalization:
- calculate mean of data
- for each sample, subtract its value from mean
- then divide by standard deviation

# ch 4: Fundamentals of Machine Learning

## Four branches of ML

There are four branches of machine learning:

1. Supervised learning

It consists of learning to map input data to known targets/labels.

Further divided into two broad categories: Classification and Regression

Other types of supervised learning:
- sequence generation
- syntax tree prediction
- object detection
- image segmentation

2. Un-supervised learning

It consists of finding interesting transformation of input data without the help of any targets/lables, for the purpose of better understanding the correlation in the data, data visualization, data denoising, data compression etc. It is bread and butter of data analytics.

sub-categories: Dimenstionality reduction, clustering

3. Self-supervised learning
Superviesed learning without human annotated labels. Labels are generated from the input data typically using heuristic.

4. Reinforcement learning
In reinforcement learning, an agent receives information about its environment and learns to choose actions that will maximize some reward


## Evaluating ML models

### Overfitting - central problem in ML

In machine learning practice, the  goal is to create models which *generalize* well, and *overfitting* is a central problem. When a ML model performs well on *training data* but its performance on *test data* begins to *stall or worsen*.

### parameters of a network

- wights for each layer
- biases 

### Hyperparameters of a NN

- number of layers
- size of each layer
- shape of the network
- epochs
- batch size
- learning rate
- loss functions
- optimizer
- metric 

## Training/Testing/Validation dataset

Learning process consists of repeating following for *num_epochs*
- *Training data* is used for training the model
- *Validation data* used to test at each iteration

* data* is used in the end to test performance of model when all iterations using testing and validation data are over.

Plese note that:
- hyperparameters are caliberated so that performance of *Validation data* improves i.e. *error on the testing data is used as feedback* to tune *hyperparameters*. 
- network's hyperparameters are already calibrated to suite Validation data. 
- Or we can say that they are *learned* using feedback from validation data. 

So, we must test the performance of the network on a separate set of data called *testing data*, which is kept separate from training/validation data.

### Splitting data for training

Data should be partitioned into three sets:

- Training set
- Validation set
and:
- Testing set

Strategies for spliltting data into three sets:
1. Simple Hold out validation

i.e. split the data into three sets and use them as mentioned in [Training/Testing/Validation dataset](#Training/Testing/Validation-dataset).

2. K-Fold validation

this strategy should be used when sufficient data is not available.

3. Iterated K-Fold validation with shuffling

This strategy is used when relatively less data is available, i.e. *K-Fold validation* can not be used.

In this strategy we use *K-Fold validation* multiple times, by shuffling data each time. and the overall score is the average of all *Iterations*.

Important guidelines for Data partitioning:

- Always, radomly shuffle your data before dividing into training, validation, and testing data set.
- In situations where we are trying to use future output based on past outputs, we must not randomly shuffle. Infact, test data should be from future time w.t.t. training data.
- data should not have redundancy.

## Data pre-processing

### Data representation for NN

Vectorization
Value Normalization
Handling missing values

### Feature Engineering

## Overfitting and Underfitting

optimization: process of adjusting a model to get best performance on training data.

generatlization: how well the model performs on data it has never seen before.

underfitting: in the begining of training when network has not yet modelled all relevant patterns in the training data, the network is said to underfit the training data.

overfitting: after performing a number of iterations of the learning process, the performance of network on training data is improving but its performance on *test data* stalls, or begins to degrade. This is called *overfitting*.

### Solutions for overfitting:

1. getting more data

- regularization: modulating the quantity of information that network can store, or to add constrains on what information the network can store. This ways network will try to learn most important patterns.

regularization techniques:

2. reducing the size of the network: i.e. reducing the number of layers, and their sizes.
3. adding weight reularization: i.e. *A cost associated with having large weights* is added to the loss function of the network
- L1 regularization
- L2 regularization 
4. adding dropout layer










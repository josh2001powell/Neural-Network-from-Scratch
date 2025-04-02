I am aiming to produce the a Neural Network from scratch without any special functions from pandas/scikit/keras etc.
Comparitive model   -   https://scikit-learn.org/stable/modules/generated/sklearn.neural_network.MLPClassifier.html

Goals:
  
  - Learn the limitations of a NN and the basic process. 
  - Learn accuracy increase from different optimisations.
  - Learn NN timescale and how benefitial excessive training.
  - I am hoping to match my model within a few percentage to comparitive model.
  - Compare to other MLMs for my premier league predicitons project.
  
General NN process:

1) Initialise model with empty weights, biases and node layers.
2) Train the model using training data (run multiple epochs for consistency).
3) Predict using the finalised weighting and biases.
4) Compare predictions to actual results and fine tune with optimisations.


Further Breakdown:

1) Initialise model with empty weights, biases and node layers.

    - Weights and biases control the activations of nodes/neurons at each layer in the network.
    - Weights and biases can be postive or negative.
    - Initial weights/biases should be randomised and reasonably sized, achieve this with normalised distribution.
    - Xavier initialisation is a common and reliabel normalised distribution.  X ~ N(0, sqrt(layer_size) ).
    
    - Input is determined by the number of prediction metrics.
    - Output is determined by the required classification, i.e predicting goals might have nodes for 0,1,2....,6 goals.
    - We also need to choose how many hidden layers and the size of each layer in the network.
    - Common to choose slightly larger hidden layers than input/output, potentially pyramidal for larger networks.
    - For a model with a small amount of metrics <5 then theres probably no benefit to more than 2 hidden layers with around       2x the input neurons in each layer. 
    - In general the more complex you believe the relationships between metrics may be the more the model will likely               benefit from an increased number of layers and/or nodes in each layer. 




2) Train the model using training data (run multiple epochs for consistency).

    - Training the model can be split into 3 main parts:
          1  -  Activate the nodes in succession using the weights and biases  Z2 = W1 * A1 + B2  -->  A2 = relu(Z2)
          2  -  Compare the output layer to the actual result and apply a cost function.
          3  -  Backpropogate through the layers using the initial cost to create a loss for each weight/bias matrix.

    - For classification problems   --->  Use Cross Entropy loss   (with softmax this simplifies to dl_dz = Y_pred - Y_true)
    - For regression problems       ---> Use Mean Squared loss


    - Once we have adjusted all the weights and biases through backpropogation we can use the next input and repeat.
    - Eventually we pass through all the data multiple times to get the final weights and biases.



  3) Predict using the finalised weighting and biases.

    - Now we hold the finalised weights and biases constant and use each testing data input to create an output.
    - The result is classified by the most active node in the output layer.
    



  4) Compare predictions to actual results and fine tune with optimisations.

    - Compare the result to the actual target from each row in training data.
    - Store all the predictions and actual results in a table.
    - Calculate the accuracy and precision from the table.
    - Note the most common prediction made by the model.
    - 







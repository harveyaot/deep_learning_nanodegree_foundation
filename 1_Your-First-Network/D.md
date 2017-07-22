# Project1: Your first neural network

### About 
   * build Neural Network from scratch
   * regression predicton problem
   * better understanding of gradient descent, backpropagation
   
### Review
The review from expert is in the [link](https://review.udacity.com/#!/reviews/359548).
After this kinds of scratch coding, I could more understand about neural network and backpropagation. The one thing I got is to know that decomposition is useful when coding and understanding concepts (e.g., backpropagation). In other words, to make a nice structure/frame of neural network. 

I decompose backpropagation like these ways (below) <br>
(I design several blocks for easily coding backpropagation.)

#### Forward pass vs. Backward pass
The flows of both are the same. But, the shape of input door and output door is different. In detail...

* In forward, each node has two doors (input door, output door)
   - Input Door: 
      - inputs (=outputs)
      - hidden inputs: np.dot(w1, inputs)
      - final inputs: np.dot(w2, hidden outputs) 
   - Output Door: (Wrapping using activation function)
      - outputs (=inputs)
      - hiden outputs: sigmoid(hidden_inputs)
      - final outputs: linear(final_inputs)

* In backward, each node has two doors (input door, output door)
   - Input Door: 
      - output errors: difference between true and prediction
      - hidden errors: np.dot(w2, output gradient errors)
   - Output:
      - output gradient errors: output_errors * output_activation_prime(final_outputs)
      - hidden gradient errors: hidden_errors * hidden_activation_prime(hidden_outputs)
	  
Actually, we use only forward pass for evaluating our model while use both forward and backward pass for udating weights. 

#### Error vs. Gradient Error
The terms are very confusing. Error is the actual error while gradient error is related weight and is defined by us for capsulation. The important thing is that only gradient error is used for doing backpropagation. 

#### Dot Product vs. Hadamard Product
Dot product is for summation of all elements after products while hadamard product is related to element-wise products. Since it is confusing when coding, we need to distinguish them. 

### Result
After building neural network and finding good hyper-parameters, the model could have good numerical prediction for bike regression problem. However, the model seems got a little underfitted (examining the results from test data). The reason is because the amount of data is relatiely small and the specitial days such as holidays, when poeple don't ride bikes so much. So, since that kinds of data has unnormal patterns compared to other data, it is considered as noise. So, the model couldn't find their complex patterns perfectly. But, I believe that when we have fully enough data and large capacity models (e.g., deep neural networks), we can have better results.  







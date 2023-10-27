# Task 1

### a) 
wTo *sample* is to digitize the coordinate values of a function given by the waveform of the continuous voltage output of a sensor. 
In practice, spacial sampling is accomplished by selecting the number of individual mechanical increments at which we activate the sensor to collect data.

### b)
*Quantization* is digitizing the amplitude of a sampled value.

### c)
One can tell that an image is high-contrast by its histogram by identifying that an even distribution across the entire domain of possible values. Meaning that the pixel Iamge uses all available intensity values.

### d)
| Hr(r)     | Pr(r)        | Fr(r) |  T(r)        |
|:---------:|:------------:|:-----:|:------------:|
| Hr(0) = 1 | Pr(0) = 1/15 | 1/15 |  T(0) = 7/15  |
| Hr(1) = 1 | Pr(1) = 1/15 | 2/15  | T(1) = 14/15 |
| Hr(2) = 0 | Pr(2) = 0    | 2/15  | T(2) = 14/15 |
| Hr(3) = 1 | Pr(3) = 1/15 | 3/15  | T(3) = 21/15 |
| Hr(4) = 2 | Pr(4) = 2/15 | 5/15  | T(4) = 35/15 |
| Hr(6) = 4 | Pr(6) = 4/15 | 11/15 | T(6) = 77/15 |
| Hr(5) = 2 | Pr(5) = 2/15 | 7/15  | T(5) = 49/15 |
| Hr(7) = 4 | Pr(7) = 4/15 | 15/15 | T(7) = 7     |


### e)
Applying a log transform will widen (brighten) the low intensities and squeeze (darken) the high intensities. Effectivley lowering the dynamic range of the imgage

### f) 
To handle boundaries we chose reflecting the information across the edge, and on the corners we used the same pixel as on the sides of the corner. \

Padded image

|   |   |   |   |   |   |   |
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| 1 | 1 | 7 | 6 | 3 | 6 | 6 |
| 1 | 1 | 7 | 6 | 3 | 6 | 6 |
| 7 | 7 | 7 | 5 | 6 | 4 | 4 |
| 5 | 5 | 4 | 7 | 7 | 0 | 0 |
| 5 | 5 | 4 | 7 | 7 | 0 | 0 |

Kernel 

|   |   |   |
|:-:|:-:|:-:|
| 1 | 0 | -1 |
| 2 | 0 | -2 |
| 1 | 0 | -1 |



Convolved image

|   |   |   |   |   |
|:-:|:-:|:-:|:-:|:-:|
| -17 | -13 | 12 | 1 | -7 |
| -3 | -3 | 1 | 9 | 8 |
| 4 | -4 | -9 | 22 | 23 |

# Task 2

### a)
![Grey Scaled Duck](assignment%201/image_solutions/duck_greyscale.jpeg)

### b)
![Inverse Grey Scaled Duck](assignment%201/image_solutions/duck_inverse.jpeg)

### c)
![Sobel kernel applied to duck](assignment%201/image_solutions/im_sobel.jpg)

![Smoothing kernel applied to duck](assignment%201/image_solutions/im_smoothed.jpg)


# Task 3

### a) 
The XOR operation cannot be represented by a single-layer, as it's not linearly separable. The input space cannot be separated into two regions representing 1 and 0 using a single linear function, which by design is all that a single layer neural net can do because its only a linear combination of the inputs.

### b)
Hyperparameters are essentially external configuration parameters for the model chosen before training the model. For example the number of layers, and hiden units per layer. 

### c)
The goal of multiclass clasification networks is to take an input and predict which one of the K classes it belongs to. To achieve this the network attempts to model a classification distribution over the k classes. The output value of each of the networks K output nodes will then be the probability that input x belongs to class {1,2,...,K}. For the probability distribution outputted by the neural net to be valid the sum of all outputs from the k nodes must be 1 and all outputs must be in the range [0,1]. We cannot guarantee that the neural network respects these limitations, so we must use a function that maps the entire number line onto [0,1] ensuring that all the outputs of the function sum to 1. This is what softmax does


### d)
Firse we list out the values asked for in the task, and below we've attached an image showing the working out by hand which explains how each of the derivatives were computed 


$\frac{\partial C}{\partial w_1} = -1$,
$\frac{\partial C}{\partial w_2} = 0$,
$\frac{\partial C}{\partial w_3} = 0$,
$\frac{\partial C}{\partial w_4} = 0$,
$\frac{\partial C}{\partial b_1} = 1$,
$\frac{\partial C}{\partial b_2} = 0$,

![Calculation](assignment%201/image_solutions/forwardbackward.jpg)  


### e)
$$\overline{w_1} = w_1 - \alpha \frac{\partial C}{\partial w_1} = -0.9$$
$$\overline{w_2} = w_2 - \alpha \frac{\partial C}{\partial w_2} = 0$$
$$\overline{b_1} = b_1 -\alpha \frac{\partial C}{\partial b_1} = 0.9$$


# Task 4

### a)
As is clear in the plot, the model trained on normalized data outperforms the one trained on non normalized data.

![Normalized Data vs Unormalized Data](assignment%201/image_solutions/task_4a_normalized.png)

### b)
In the Image we see that the highest weights drawing the shape of the numebr, with the lowest weights tracing the edges of the numbers. It seems that the network is learning to recognize the numbers by their shape and edges

![Weights visualized as images](assignment%201/image_solutions/task_4a_weights.png)

### c)
The network achieves worse performance than previusly because with a learning rate of 1.0 the network is unable to converge on a local/global minimum. In the graph its clear from the test loss plot that the model takes wild jumps during gradient descent and is physically not able to converge to the minimum with that big step sizes.

![Model Trained with learning rate 1.0](assignment%201/image_solutions/task_4c.png)

### d)
The network achieves greater performance with a hidden layer because it is able to learn more complex features. The network is able to learn more complex features because it has more parameters to learn from.

![Model trained with hidden layer](assignment%201/image_solutions/task_4d.png)

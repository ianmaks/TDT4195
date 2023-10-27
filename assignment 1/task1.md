# Task 1

### a) 
wTo *sample* is to digitize the coordinate values of a function given by the waveform of the continuous voltage output of a sensor. 
In practice, spacial sampling is accomplished by selecting the number of individual mechanical increments at which we activate the sensor to collect data.

### b)
*Quantization* is digitizing the amplitude of a sampled value.

### c)
One can tell that an image is high-contrast by its histogram by identifying that an even distribution across the entire domain of possible values. Meaning that the pixel Iamge uses all available intensity values.

### d)
TODO ADD CALCULATIONS

### e)
Applying a log transform will widen (brighten) the low intensities and squeeze (darken) the high intensities. Effectivley lowering the dynamic range of the imgage

### f) 
To handle boundaries we chose reflecting the information across the edge, and on the coreners we used the same pixel as on the sides of the corner.
TODO ADD CALCULATIONS

___

# Task 3

### a) 
The XOR operation cannot be represented by a single-layer, as it's not linearly separable. The input space cannot be separated into two regions representing 1 and 0 using a single linear function, which by design is all that a single layer neural net can do because its only a linear combination of the inputs.

### b)
Hyperparameters are essentially external configuration parameters for the model chosen before training the model. For example the number of layers, and hiden units per layer. 

### c)
The softmax function takes a vector and returns a vector of the same size where all inputs are mapped onto the range [0,1] while preserving the inputs' relative scale to one another. 

### d)

#### Header-only C/C++ libraries for making predictions using a saved Keras model
  - https://github.com/Dobiasd/frugally-deep
  - https://github.com/pplonski/keras2cpp

#### Max-pooling vs. Dropout
- dropout:
  - In a dropout layer, a portion of the input data is thrown away/not used
  - Droput is not part of a trained model but only a way to enhance the training process; it is not active during evaluation
  - The goal of dropout is to reduce unnecessary feature dependencies in the network, allowing it to be simpler and improves its generalization abilities (reduces overfitting)
- Max-pooling:
  - Steps in a max-pooling layer: 1) pick a window size, 2) pick a stride for moving the window, 3) walk the window across the input, 4) for each stop, take the maximum value
  - Pooling is part of the trained model and is used during evaluation
  - The goal of max-pooling is to down-sample the input so that the trained model is less sensitive to some translations
  
  
#### Misc. notes
- Balancing dataset: In the train data is very unbalanced, the less frequent features/labels could be considered outliers. To avoid this, the train datasets need to be "balanced".
- Caching: Create a class to hold data already read from files on the slow disk into the fast memory. Use the `psutil.virtual_memory` etc. to measure memory occupied.
- Use `TensorRT` to use the trained model faster.
- Use `flask` to create web api.

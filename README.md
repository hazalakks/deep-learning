# CNN Hyperparameter Tuning – Controlled Experiments

This repository contains controlled experiments conducted to analyze the effects of individual hyperparameters in a Convolutional Neural Network (CNN) model. The experiments were conducted by varying one hyperparameter at a time while keeping all other parameters fixed. Metrics such as validation accuracy, validation loss, training accuracy, and training loss were used to evaluate model performance.

## Hyperparameters Tested and Best Values

| Hyperparameter             | Values Tested                          | Best Value |
|---------------------------|----------------------------------------|------------|
| Convolutional Kernel Size | 3, 5, 7, 9, 11, 13                      | 3          |
| Conv Dropout              | 0, 0.2, 0.3, 0.5, 0.7, 0.9              | 0.2        |
| Activation Function       | ReLU, Tanh, Sigmoid                    | ReLU       |
| Batch Size                | 16, 32, 64, 128, 256, 512               | 512        |
| Optimizer Type            | Adam, SGD, RMSprop                     | Adam       |
| Num Conv Layers           | 1, 2, 3, 4, 5, 6                        | 2          |
| FC Hidden Units           | 64, 128, 256, 512, 1024, 2048           | 64         |
| Pool Kernel Size          | 2, 3, 4, 5, 6, 7                        | 5          |
| Pool Stride               | 1, 2, 3, 4, 5, 6                        | 1          |


## Findings

### Convolutional Kernel Size
- Best kernel size: **3**
- Smaller kernels (like 3) captured local patterns better and retained more spatial information.
- Larger kernels (especially 9–13) led to performance degradation due to loss of spatial resolution and information.

### Convolutional Dropout
- Best dropout: **0.2**
- Dropout helped reduce overfitting.
- 0.2 performed the best, whereas very high values like 0.7 and 0.9 led to underfitting.

### Activation Function
- Best function: **ReLU**
- ReLU performed significantly better than Tanh and Sigmoid.
- ReLU avoided vanishing gradient problems and converged faster.

### Batch Size
- Best batch size: **512**
- Larger batch sizes led to smoother gradient updates and better generalization.
- Smaller batch sizes performed poorly.

### Optimizer Type
- Best optimizer: **Adam**
- Adam showed higher accuracy and faster convergence.
- SGD and RMSprop did not perform as well, especially SGD which had the worst results.

### Number of Convolutional Layers
- Best number: **2**
- Too many layers (e.g., 5, 6) led to overfitting or increased complexity without benefits.
- One layer was insufficient for feature extraction.

### FC Hidden Units
- Best number: **64**
- More units did not improve performance and instead caused overfitting or increased complexity.
- 64 units generalized best to the validation set.

### Pooling Kernel Size
- Best size: **5**
- Helped remove redundant information while preserving important spatial patterns.
- Larger kernels performed poorly.

### Pooling Stride
- Best stride: **1**
- Smaller stride preserved more spatial information and boosted validation performance.
- Larger strides lost too much detail.

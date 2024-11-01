Here's a concise summary of the AlexNet architecture and its components for your GitHub repository:

---

## AlexNet Architecture Summary

AlexNet was the first CNN architecture that utilized GPUs to improve training speed. The model has:
- **Layers**: 5 Convolution layers, 3 Max-Pooling layers, 2 Normalization layers, 2 Fully Connected layers, and a SoftMax output layer.
- **Activation**: Uses ReLU instead of tanh, speeding up training.
- **Parameters**: Over 60 million.
- **Input Size**: 227x227x3 (due to padding), though often listed as 224x224x3.

### Key Features
- **ReLU Activation**: Faster training compared to tanh.
- **Batch Size**: 128.
- **Optimizer**: SGD with momentum.
- **Data Augmentation**: Techniques include mirroring, cropping, jittering, and color normalization.
- **Hardware**: Trained on GTX 580 GPU, split across two GPUs to fit the model.

### Max Pooling
Max pooling reduces spatial dimensions, lowers computation, and provides translation invariance. AlexNet used overlapping 3x3 pooling with a stride of 2, reducing top-1 error by 0.4% and top-5 by 0.3% compared to non-overlapping 2x2 pooling.

### ReLU Non-Linearity
ReLU was critical to faster training in AlexNet, achieving lower training error rates significantly faster than tanh. 

### Data Augmentation Techniques
- **Mirroring**: Images are flipped along the vertical axis to increase dataset size.
- **Random Cropping**: Random 227x227 crops from 256x256 images, enhancing data variety.

### Dropout Regularization
Dropout, with a probability of 0.5, was used to prevent overfitting by deactivating neurons randomly during training, leading to more robust models.

### Implementation Outline
1. **Dataset**: Scrape and preprocess images (e.g., using Beautiful Soup).
2. **Model Definition**: Build the AlexNet model from scratch, or use a Keras implementation.
3. **Training**: Initialize training parameters and train on a subset of ImageNet.
4. **Prediction**: Use the trained model to make predictions on test images.

--- 
-[FOR MORE DETAILS](https://medium.com/@siddheshb008/alexnet-architecture-explained-b6240c528bd5)

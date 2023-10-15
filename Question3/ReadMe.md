# This is the code for Fine Tuned ResNet model for classifying Cats and Dogs

This code is an example of building an image classification model to distinguish between cats and dogs using the ResNet-50 architecture. It makes use of the Keras and TensorFlow libraries to create and train the model.

## Requirements
* Python 3.x
* TensorFlow
* Keras
* NumPy
* Matplotlib
* PIL (Python Imaging Library)
* Dataset
The dataset should be organized into two folders, one for training data and another for validation data. You can specify the paths to these folders in the train_path and valid_path variables.

You can find the link for the Dataset Here

## Model Architecture
The code uses a pre-trained ResNet-50 model as a base model. The pre-trained weights are loaded from the 'imagenet' dataset.
A Global Average Pooling layer is added to reduce spatial dimensions.
A fully connected Dense layer with 1024 units and ReLU activation is added.
The final output layer consists of two units for binary classification (cat or dog) with a softmax activation.
Training
The model is compiled using the Stochastic Gradient Descent (SGD) optimizer with a low learning rate (0.0001) and momentum.
Categorical cross-entropy is used as the loss function for multi-class classification.
The model is trained for 10 epochs using the training and validation data generators.
Save Model
The trained model is saved as 'cat_vs_dog_resnet50.h5'.

## Usage
You can use the saved model for making predictions on new cat or dog images.

```
from tensorflow.keras.models import load_model

# Load the saved model
model = load_model('cat_vs_dog_resnet50.h5')

# Make predictions on a new image
img = load_and_preprocess_image('new_image.jpg')  # You need to implement load_and_preprocess_image
predictions = model.predict(img)

```

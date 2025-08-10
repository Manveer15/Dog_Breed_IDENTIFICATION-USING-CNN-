**Dog Breed Identification**
This Jupyter Notebook implements a deep learning model that can identify the breed of a dog from an uploaded image using transfer learning with MobileNetV2.

** Features:**
Upload an image of a dog and get the predicted breed name.

Uses MobileNetV2, a lightweight and efficient convolutional neural network pretrained on ImageNet.

Fine-tuned on a custom dataset of dog breed images stored in Google Drive.

Supports multiple dog breeds dynamically based on the folder structure of the dataset.

Includes real-time data augmentation to improve model robustness.

** Dataset:**
The model reads image data from Google Drive (/content/drive/MyDrive/data).

Each dog breed should have its own subfolder within the data directory (e.g., data/golden_retriever, data/beagle, etc.).

Automatically loads and classifies based on the folder names.
**
Model Architecture:**
Base Model: MobileNetV2 (with frozen layers)

Custom Layers: GlobalAveragePooling2D → Dense(128, ReLU) → Dropout(0.5) → Dense(softmax output)

Loss Function: Categorical Crossentropy

Optimizer: Adam

** Training:**
Data is split into training and validation sets using ImageDataGenerator with an 80/20 split.

Data augmentation includes rotation, shift, zoom, flip, etc.

Trained for 10 epochs with batch size 32 and image size 224x224.

** Prediction:**
The notebook includes an interface to:

Upload a new image

Preprocess it

Use the trained model to predict the breed

Display the result

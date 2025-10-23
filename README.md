# Brain-Tumor-MRI-Image-Classification
## Overview
In the critical domain of medical imaging, the early and precise classification of brain tumors is vital. This project applies deep learning via Convolutional Neural Networks (CNNs) to analyze T1C-enhanced MRI scans. By developing a model capable of reliable and automated classification, we aim to provide healthcare professionals with a rapid, supportive diagnostic tool to enhance clinical decision-making.
## Dataset
This project utilizes the **Brain Tumor Classification MRI** dataset, which contains a rich collection of MRI images categorized into four classes:
- **Glioma Tumor**
- **Meningioma Tumor**
- **Pituitary Tumor**
- **No Tumor**
The images are organized into training , testing and valid dataset directories, ensuring an efficient workflow for model training and evaluation.
From this data, I constructed an overall dataset with five classes (pituitary, meningioma, glioma, no tumor). When building my models, I prioritized maximizing accuracy - the overall proportion of correct predictions by the model. In refining this model in the future I would likely prioritize recall most highly since a false negative is a potentially fatal error, but given the limited scope of the training data accuracy felt appropriate for now.

My preprocessing included splitting the data into train and test sets, and using image augmentation to increase the size of the training data. I tested a variety of different CNN architectures, eventually settling on a transfer learning approach using the pre-trained weights for the Mobilenet  model. The model achieved roughly a 94% accuracy score on test data.
## Project Structure
The project is neatly organized into the following components:
- **Data Directory**: Contains categorized MRI images.
- **collab Notebook**: The heart of our project, where we perform data preprocessing, model training, and evaluation and streamlit deployment takes place
### 1. Data Preparation
We kick off the project by importing necessary libraries like **NumPy**, **Pandas**, **Keras**, etc . The images are then loaded and resized to a uniform dimension of **640x640 pixels** to maintain consistency across the dataset.
### 2. CNN Model Architecture
The architecture of our CNN model includes:
- Multiple **Convolutional Layers**: These layers automatically extract features from the images.
- **MaxPooling Layers**: These reduce dimensionality while preserving essential features.
- **Dropout Layers**: These layers mitigate overfitting by randomly dropping units during training.
- A fully connected layer at the end for final classification.
### 3. Training the Model 
- Using the **Adam optimizer** and **categorical crossentropy loss**, the model is trained on the dataset with validation to monitor its performance.
## Results
The performance of the model is evaluated through accuracy metrics, with training and validation accuracy and loss visualized through plots.

## ## Conclusions and Next Steps
This project built on existing work in the brain tumor detection space by expanding the number of classes in the dataset. The selected model achieved an overall accuracy of roughly 94%, while achieving a recall of 99% and a precision of 97% for the "no tumor" class. In order to be more broadly applicable, the model would need to be trained on a wider variety of tumor images, as well as images of other potential diagnoses detectable by MRI such as blood clots, aneurysms, dementia, and others.

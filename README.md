## About the Project

This project uses a **Convolutional Neural Network (CNN)** to detect whether a person is wearing a face mask or not.  
The model is trained on labeled images and can classify a new input image into **with mask** or **without mask**.

## Dataset

The dataset is obtained from [Kaggle – Face Mask Dataset](https://www.kaggle.com/datasets/omkargurav/face-mask-dataset).  
It contains two folders: **with_mask** with 3,725 images and **without_mask** with 3,828 images.
Masked - 1 
Without Mask - 0

## Libraries Used
- Python
- TensorFlow / Keras
- NumPy
- OpenCV
- Matplotlib
- PIL

## Preprocessing & Training

All images were resized to **128 × 128 pixels**, converted to **RGB format**, and pixel values were scaled to the range **0–1 by dividing them by 255**. RGB conversion was performed because OpenCV loads images in **BGR format**, while the CNN model was trained using **RGB images**.

The preprocessed images were then used to train the **CNN model** to classify images as **with mask** or **without mask**.

## Training

A **CNN model** was built using two convolutional layers with **32 and 64 filters**, each followed by a MaxPooling layer. The extracted features were flattened and passed through Dense layers with **128 and 64 neurons**, along with Dropout layers to help reduce overfitting.

The model was compiled using the **Adam optimizer** and **Sparse Categorical Crossentropy** loss function, with accuracy used as the evaluation metric. The final output layer contains **2 neurons**, corresponding to the `with_mask` and `without_mask` classes.

## Prediction

For prediction, the input image is first **resized to 128 × 128 pixels**, converted from **BGR to RGB**, and the pixel values are **scaled by dividing them by 255** before being passed to the model.

The model returns probabilities for both classes. For example, `[[0.09658545, 0.7560797]]` represents the predicted probability for **class 0 (without mask)** and **class 1 (with mask)**. We use `argmax()` to select the class with the highest probability. Therefore, **0 represents without mask** and **1 represents with mask**.

For masked 
<img width="726" height="506" alt="Screenshot 2026-10-05 024345" src="https://github.com/user-attachments/assets/ede8d04c-99dd-4058-8677-b764d4f9951b" />
For W<img width="657" height="553" alt="Screenshot 2026-10-05 024337" src="https://github.com/user-attachments/assets/ba059fa5-6342-406c-9c1e-2a3c03916a0e" />
ithoutmask 






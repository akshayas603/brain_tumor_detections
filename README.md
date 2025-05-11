Tumor Classification using CNN & Gradio

This project is a deep learning-based web application for classifying brain MRI images into four categories:

Glioma
Meningioma
No Tumor
Pituitary Tumor
It uses TensorFlow/Keras for model training and Gradio for a user-friendly web interface.

🚀 Demo
Upload a brain MRI image to the interface, and the model will predict the type of tumor.

Demo Screenshot

📂 Dataset
Make sure you have the dataset structured like this:

/Training/ ├── glioma/ ├── meningioma/ ├── notumor/ └── pituitary/

kotlin

You can place this dataset in your Google Drive and set the path in DATASET_PATH variable accordingly:

DATASET_PATH = '/content/drive/MyDrive/braintumor/Training'
🧠 Model Architecture
The CNN model consists of:

3 Convolutional Blocks

Conv2D → MaxPooling2D → BatchNormalization

Global Average Pooling

Dense (128) + Dropout

Output Layer (Softmax)

🛠 Requirements
Install the required Python packages:


pip install tensorflow opencv-python gradio scikit-learn
If you're running on Google Colab, make sure to mount Google Drive if your dataset is stored there.

🧪 Training
Train the model with:

model.fit(X_train, y_train, batch_size=16, validation_data=(X_test, y_test), epochs=10)
🖼 Gradio Interface
After training, launch the Gradio app with:


interface.launch()
You’ll get a public link to test your model in a browser.

🔮 Prediction
Each uploaded image is:

Resized to 128x128

Normalized

Passed through the trained model

Top 4 class probabilities are shown

📈 Performance
You can view model training accuracy/loss by checking the history object returned by model.fit().

📌 Notes
Ensure your images are MRI brain scans (preferably clean and centered).

Training time may vary depending on the size of the dataset and environment (GPU recommended).

You can save the model using model.save("brain_tumor_model.h5") and load it later for inference.

📃 License
This project is open-source and free to use under the MIT License.

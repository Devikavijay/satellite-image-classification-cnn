# Satellite Image Classification using CNN

## Project Aim

This project builds a Convolutional Neural Network (CNN) to classify satellite images into four land-cover/weather categories: **Cloudy**, **Desert**, **Green Area**, and **Water**. The aim is to demonstrate how deep learning can automatically identify terrain and surface patterns from satellite imagery.

## Dataset Used

The project uses a folder-based satellite image dataset stored in the following structure:

```text
satellite_data/
├── cloudy/
├── desert/
├── green_area/
└── water/
```

The dataset is not uploaded to this repository because of its large size.
Download the dataset from Google Drive:
(Download Dataset)
https://drive.google.com/drive/folders/1XLv9Wm1BFPWq-UiwdClLKrDI1r4NrIBg?usp=sharing

Dataset summary from the notebook:

| Class | Label | Number of Images |
|---|---:|---:|
| Cloudy | 0 | 1500 |
| Desert | 1 | 1131 |
| Green Area | 2 | 1500 |
| Water | 3 | 1500 |

Total images: **5631**

## Tools and Libraries

- Python
- NumPy
- Matplotlib
- Seaborn
- TensorFlow / Keras
- Scikit-learn
- Scikit-image
- Glob

## Project Workflow

1. **Import libraries**  
   Required libraries are imported for image loading, preprocessing, model building, visualization, and evaluation.

2. **Load dataset**  
   Images are loaded from four class folders using `glob`.

3. **Create labels**  
   Each image is assigned a numeric label:
   - `0` = Cloudy
   - `1` = Desert
   - `2` = Green Area
   - `3` = Water

4. **Shuffle dataset**  
   Images and labels are shuffled using `sklearn.utils.shuffle` to avoid class-order bias.

5. **Visualize sample images**  
   A few random images are plotted with their class names.

6. **Preprocess images**  
   Images are resized to **128 × 128 × 3** using `skimage.transform.resize` and converted into NumPy arrays.

7. **Train-test split**  
   The dataset is split into:
   - Training set: **4504 images**
   - Testing set: **1127 images**

8. **Build CNN model**  
   The model uses:
   - Convolution layer with 16 filters
   - Max pooling
   - Convolution layer with 32 filters
   - Max pooling
   - Flatten layer
   - Dense hidden layer with 128 neurons
   - Output layer with 4 neurons using Softmax activation

9. **Compile model**  
   The model is compiled using:
   - Optimizer: `adam`
   - Loss function: `sparse_categorical_crossentropy`
   - Metric: `accuracy`

10. **Train model**  
    The CNN is trained for **25 epochs** with a batch size of **32**.

11. **Evaluate model**  
    The model is evaluated using accuracy, confusion matrix, and classification report.

## Model Performance

From the notebook output:

- Training accuracy: **95.16%**
- Test accuracy: **94%**

Classification report:

| Class | Precision | Recall | F1-score |
|---|---:|---:|---:|
| Cloudy | 1.00 | 1.00 | 1.00 |
| Desert | 1.00 | 1.00 | 1.00 |
| Green Area | 0.87 | 0.93 | 0.90 |
| Water | 0.92 | 0.84 | 0.88 |

## How to Run the Project

1. Clone the repository:

```bash
git clone https://github.com/your-username/satellite-image-classification-cnn.git
cd satellite-image-classification-cnn
```

2. Install dependencies:

```bash
pip install numpy matplotlib seaborn tensorflow scikit-learn scikit-image
```

3. Add the dataset folder:

```text
satellite_data/
├── cloudy/
├── desert/
├── green_area/
└── water/
```

4. Open and run the notebook:

```bash
jupyter notebook "Satellite Image Classification.ipynb"
```

## Expected Output

The notebook produces:

- Sample satellite image visualizations
- Resized image previews
- CNN model summary
- Training progress over 25 epochs
- Predictions on test images
- Confusion matrix heatmap
- Classification report

## Repository Structure

```text
satellite-image-classification-cnn/
├── Satellite Image Classification.ipynb
├── README.md
└── satellite_data/
    ├── cloudy/
    ├── desert/
    ├── green_area/
    └── water/
```


## Conclusion

This project shows how a CNN can classify satellite images into meaningful categories with high accuracy. It can be extended further using data augmentation, transfer learning, hyperparameter tuning, or deployment as a web application.

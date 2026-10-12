# Sign Language Letter Classifier
A small neural network (scikit-learn MLP) that recognizes hand-sign letters from 28x28 grayscale images.

### Dataset
SignMNIST, using a small balanced sample: 130 training images and 130 test images (13 per class, so I believe 10 classes; please double-check this). Each row has a `class` label and 784 pixel values (28x28), which are scaled to 0–1 before training.

Files: `sign_mnist_13bal_train.csv`, `sign_mnist_13bal_test.csv`

### How to Run
1. Clone this repo and install dependencies: `pip install -r requirements.txt`
2. Run the model: `python main.py`
3. Optional helper scripts:
   - `python ClassViewer.py` – shows the first 10 images of a class (edit `class_number`)
   - `python DataDumper.py` – prints the dataset
   - `python DisplayClassHist.py` – histogram of class counts
   - `python ShowPixelGrid.py` – one image with pixel values overlaid

### Results
- Split: 110 training / 20 validation images (stratified); separate 130-image test set
- Network: 784 inputs, 1 hidden layer of 64 neurons, 10 outputs
- Final test accuracy: 69.2%
- Training accuracy: 98.2%
- Most often misidentified classes: 5, 6 and 7
- The large gap between training and test accuracy shows the model overfits the small training set.

### Limitations
- Very small dataset (130 training images), so results vary a lot with the random seed and split.
- The validation set is only 20 images, so per-class numbers are noisy.
- Test accuracy is measured on only 130 images.
- Images are low-resolution (28x28).
- Not tested on new people, lighting or backgrounds.

### Built With
- Python
- scikit-learn (MLPClassifier)
- pandas, NumPy
- Matplotlib

### P.S.
*This project is built as part of Girls Who Code's Basic Neural Nets Course*
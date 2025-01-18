# APS Fault Detection Using Artificial Neural Networks

## Overview

This project implements an Artificial Neural Network (ANN) for detecting APS (Air Pressure System) faults using a dataset containing features and class labels. The project employs TensorFlow and Keras for building the neural network and utilizes hyperparameter tuning for optimization. The following tasks are performed:

1. Data preprocessing (handling null values and scaling features).
2. Building and training an ANN.
3. Hyperparameter tuning using Keras Tuner.
4. Saving the best-trained model.

## Prerequisites

Ensure the following libraries are installed in your Python environment:

- TensorFlow
- scikit-learn
- NumPy
- Pandas
- Matplotlib
- Keras Tuner

You can install these dependencies using:

```bash
pip install tensorflow scikit-learn numpy pandas matplotlib keras-tuner
```

## Dataset

The dataset used is `aps_data.csv`, which contains:

- Multiple features representing sensor readings and other parameters.
- A `class` column indicating fault or no-fault (target variable).

## File Structure

```
.
├── aps_data.csv          # Dataset file
├── main.py               # Python script containing the implementation
├── SAVED_MODELS          # Directory to store trained models
└── README.md             # Project documentation
```

## Steps in the Code

### 1. Importing Libraries

The script imports essential libraries such as TensorFlow, Pandas, NumPy, scikit-learn, and Matplotlib.

### 2. Loading and Preprocessing the Dataset

- Loads the dataset using Pandas.
- Handles missing values by replacing them with the median of the respective feature.
- Encodes the target variable using `LabelEncoder`.
- Splits the dataset into training and test sets.
- Scales the features using `StandardScaler`.

### 3. Building the ANN

- Defines a Sequential model with:
  - Dense layers for feature processing.
  - ReLU activation in hidden layers.
  - Sigmoid activation in the output layer for binary classification.
- Compiles the model with the Adam optimizer and binary cross-entropy loss.
- Trains the model on the training set and validates on a validation split.

### 4. Visualizing Model Performance

- Plots training and validation accuracy.
- Plots training and validation loss.

### 5. Hyperparameter Tuning

- Uses Keras Tuner for hyperparameter optimization.
- Explores different values for layer count, units, and optimizers.

### 6. Saving the Model

- Defines a utility function to save the trained model with a timestamped filename in the `SAVED_MODELS` directory.

## Usage

### Running the Code

1. Place `aps_data.csv` in the same directory as the script.
2. Run the script:
   ```bash
   python main.py
   ```
3. The trained model will be saved in the `SAVED_MODELS` directory.

### Evaluating the Model

- Predictions are generated on the test set.
- A confusion matrix is computed to evaluate performance.

## Results

- The script outputs the training and validation accuracy/loss plots.
- Hyperparameter tuning results are logged.

## Notes

- Ensure the dataset path is correctly specified in the script.
- Modify the batch size, epochs, or other hyperparameters as required.

## References

- TensorFlow Documentation: [https://www.tensorflow.org/](https://www.tensorflow.org/)
- Keras Tuner Documentation: [https://keras.io/keras\_tuner/](https://keras.io/keras_tuner/)








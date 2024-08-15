

## Project Title: Credit Card Fraud Detection Using Autoencoders

### Overview
This project applies an autoencoder neural network to detect fraudulent transactions from credit card data. Autoencoders are unsupervised learning models that learn to compress and then reconstruct the input data. By training exclusively on normal transactions, the model learns a representation of "normality" and can thus flag anomalies when they fail to reconstruct with similar fidelity.

### Objectives
- **Detect anomalies** in credit card transactions using autoencoders.
- **Evaluate** the effectiveness of autoencoders in reconstructing data and using reconstruction error to identify outliers.

### Data Preprocessing
1. **Normalization and Standardization**: Apply transformations to ensure that the data attributes have a mean of zero and a standard deviation of one.
2. **Train/Validate/Test Split**:
   - **Training data**: Only non-fraudulent transactions to simulate unsupervised learning.
   - **Validation data**: A subset of non-fraudulent transactions to tune the model parameters.
   - **Test data**: A mix of fraudulent and non-fraudulent transactions to evaluate model performance.

### Model Architecture
- **Input Layer**: Matches the number of features in the dataset.
- **Encoding Layers**: Sequentially reduced number of neurons to compress the data into a lower-dimensional representation.
- **Bottleneck Layer**: The smallest layer that captures the essence of the data.
- **Decoding Layers**: Sequentially increased number of neurons to reconstruct the data back to the original dimension.
- **Output Layer**: Matches the number of features in the dataset, reconstructs the compressed data.

### Training
- **Loss Function**: Mean Squared Error (MSE) to quantify the difference between the original and reconstructed data.
- **Optimizer**: Adam, for efficient stochastic gradient descent.
- **Epochs and Batch Size**: Tuned based on validation loss to prevent overfitting.

### Threshold Setting for Anomaly Detection
- Calculate the reconstruction error on the validation set.
- Set a threshold above which a transaction is considered fraudulent, based on error distribution.

### Results
- **Reconstruction Error Analysis**: Transactions with higher than threshold reconstruction error are flagged as potential fraud.
- **Model Performance**: Evaluate using metrics such as precision, recall, and F1-score on the test dataset.

### Conclusion
The model demonstrates the viability of using autoencoders for anomaly detection, where the key is to effectively train on "normal" data and use deviations from this norm to detect anomalies.

### Usage
Provide steps on how to run the script, including installing dependencies, running the model, and evaluating results.

### Future Work
Suggestions for improving the model, experimenting with different architectures, or using alternative anomaly detection techniques.


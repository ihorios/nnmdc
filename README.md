# nnmdc - Neural Network Digit Classifier

A from-scratch implementation of a neural network for MNIST handwritten digit classification, built using only NumPy and SciPy. This project demonstrates fundamental neural network concepts including backpropagation, activation functions, and matrix operations without relying on high-level deep learning frameworks.

## Features

- **Custom Neural Network Class**: Fully implemented `neuralNetwork` class with:
  - Configurable architecture (input, hidden, and output nodes)
  - Train and query methods
  - Backquery functionality for output visualization
- **Multiple Activation Functions**:
  - Sigmoid (with `scipy.special.expit`)
  - ReLU (Rectified Linear Unit)
- **Data Augmentation**: Training with rotated images to improve model robustness
- **Weight Initialization Strategies**:
  - Normal distribution scaling
  - He initialization for ReLU networks

## Project Structure

```
nnmdc/
├── fProject.ipynb      # Main Jupyter notebook with implementation
├── README.md           # Project documentation
├── GEMINI.md           # Development context and guidelines
└── .git/               # Git repository
```

## Architecture

The neural network follows a standard 3-layer architecture:

| Layer | Nodes | Description |
|-------|-------|-------------|
| Input | 784   | 28×28 flattened MNIST images |
| Hidden | 200-256 | Configurable hidden layer |
| Output | 10    | Digit classes (0-9) |

## Performance

Tested on MNIST dataset with the following results:

- **Sigmoid activation** (5 epochs, 200 hidden nodes): ~96.72% accuracy
- **ReLU activation** (5 epochs, 256 hidden nodes, He initialization): ~96.37% accuracy

## Requirements

- Python 3.x
- NumPy
- SciPy
- Matplotlib
- Jupyter Notebook or VS Code with Python extension

## Installation

```bash
pip install numpy scipy matplotlib jupyter
```

## Usage

### 1. Prepare the Dataset

Download the MNIST dataset in CSV format:
- `mnist_train.csv` (60,000 training samples)
- `mnist_test.csv` (10,000 test samples)

Place the files in a `Downloads/` directory relative to the notebook, or update the file paths in `fProject.ipynb`.

### 2. Run the Notebook

Open and execute all cells in `fProject.ipynb`:

```bash
jupyter notebook fProject.ipynb
```

Or use VS Code's Jupyter integration.

## Key Components

### Neural Network Class

```python
class neuralNetwork():
    def __init__(self, inputNodes, hiddenNodes, outputNodes, learnRate)
    def train(self, inputs_list, targets_list)
    def query(self, inputs_list)
    def backquery(self, targets_list)  # Generate input from output
```

### Training Process

1. Load MNIST CSV data
2. Scale pixel values to appropriate range (0.01-0.99 for sigmoid, -1 to 1 for ReLU)
3. Apply data augmentation (rotation) for improved generalization
4. Train for specified epochs with backpropagation
5. Evaluate on test set

### Backquery Feature

The `backquery()` method allows reverse inference—generating an input image from a target output. This visualizes what the network has learned for each digit class.

## Configuration Options

| Parameter | Default | Description |
|-----------|---------|-------------|
| `input_nodes` | 784 | Input layer size (28×28 images) |
| `hidden_nodes` | 200-256 | Hidden layer neurons |
| `output_nodes` | 10 | Output classes (digits 0-9) |
| `learning_rate` | 0.001-0.05 | Training learning rate |
| `epochs` | 5 | Number of training iterations |


## Acknowledgments

This project is based on educational implementations of neural networks for understanding the mathematical foundations of deep learning.

# GEMINI.md - Project Context

## Project Overview
The `nnmdc` project is a neural network implementation for classifying MNIST handwritten digits, built from scratch using Python. It demonstrates fundamental concepts of backpropagation, activation functions (Sigmoid/ReLU), and matrix-based neural network architecture.

### Key Technologies
- **Python**: Core programming language.
- **NumPy**: Used for efficient matrix operations and vectorization.
- **SciPy**: Utilized for activation functions (e.g., `scipy.special.expit`) and image rotation for data augmentation.
- **Matplotlib**: Used for visualizing the dataset and network outputs (backquery).

## Building and Running
As this project is primarily contained within a Jupyter Notebook, there is no separate build process.

### Prerequisites
- Python 3.x
- `numpy`
- `scipy`
- `matplotlib`
- `jupyter` or a compatible IDE (VS Code, etc.)

### Running the Project
1.  Open `fProject.ipynb` in a Jupyter Notebook environment.
2.  Ensure that the MNIST dataset files (`mnist_train.csv` and `mnist_test.csv`) are available.
    - **Note**: The current implementation expects these files to be in a `Downloads/` directory relative to the notebook.
3.  Execute all cells to train and test the model.

## Project Structure
- `fProject.ipynb`: Contains the `neuralNetwork` class definition, training loops with data augmentation (rotation), and testing logic.
- `README.md`: Basic project introduction.

## Development Conventions
- **Class-Based Architecture**: The network is encapsulated in a `neuralNetwork` class for modularity.
- **Data Augmentation**: Includes logic to rotate training images to improve model robustness.
- **Backquery**: A unique feature that allows the network to work "backwards"—querying an output label to generate a visualization of what the network "expects" that digit to look like.
- **Manual Implementation**: Avoids high-level deep learning frameworks (like TensorFlow or PyTorch) to focus on the underlying math of neural networks.

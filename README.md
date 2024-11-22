# Classifier Free Guidance - Denoising Diffusion Probabilistic Model

This repository provides an extensible framework for implementing and training generative models, including diffusion models, U-Net architectures, and attention-based mechanisms. The structure is designed to promote scalability, maintainability, and modularity for advanced research and experimentation in deep generative modelling.

**This CFG DDPM implementation supports datasets with resolutions ranging from 32x32 to 256x256 pixels. Ensure that your dataset is added to the repository and update the dataset path in base_options.py before running the scripts.**


## Project Structure

The project is organized into the following directories and files:

### 1. `data/`
Contains scripts related to dataset handling and preprocessing:

- **`datasets.py`**: Defines dataset loaders and acts as a base class for the other datasets.
- **`mnist.py`**: Contains utilities specific to the MNIST dataset.
- **`topographies.py`**: Handles biomaterial topographic datasets.

### 2. `model/`
Implements core architectures and modules for generative models:
- **`ddpm.py`**: Defines the implementation of the Denoising Diffusion Probabilistic Model (DDPM).
- **`unet.py`**: Implements the U-Net architecture used in diffusion models.
- **`attention_block.py`**: Implements attention mechanisms for enhancing feature extraction.
- **`resnet_block.py`**: Contains ResNet blocks for residual learning.
- **`nin_block.py`**: Implements Network-in-Network blocks for feature extraction.
- **`downsampling_block.py`**: Defines the downsampling layers.
- **`upsampling_block.py`**: Defines the upsampling layers.
- **`timestep_embedding.py`**: Encodes temporal information into model embeddings.
- **`networks.py`**: Base class for all the networks created. 
- **`models.py`**: Base class for the models and acts as an entry point for accessing various model instances. 

### 3. `option/`
Handles command-line arguments and configurable options for training and experiments:
- **`base_options.py`**: Defines shared options for general configurations.
- **`train_options.py`**: Extends `base_options.py` with training-specific parameters.

### 4. `utils/`
Provides helper functions and utilities for the project.

### 5. Other Files
- **`train.py`**: Main script for training the models.
- **`call_methods.py`**: Contains method calls dynamically for initiating specific processes or experiments.
- **`.gitignore`**: Specifies files and directories to be ignored by Git.

## How to Use

### 1. **Setup**
- Clone the repository:
  ```bash
  git clone <repository-url>
  cd <repository-folder>

### 2. Install the required dependencies:
```bash
pip install -r requirements.txt

### 3. Configurations
Configure model parameters and dataset options in the option/ directory:

Modify base_options.py for shared settings.
Modify train_options.py for training-specific configurations.

### 4. Training
Run the train.py script to start training:

 ```bash
python train.py

or

parse all the options in bash -> `train.sh` and run `./train.sh`

### 5. Generating New Images


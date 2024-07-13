# DopeVisionNet
Here is the official repo for DopeVisionNet 

This repository contains a training script for predicting molecule properties using a deep learning model. The script uses PyTorch for training and validation, with data preprocessing handled by custom dataloaders.

## Requirements

- Python 3.8+
- PyTorch 1.8+
- torchvision
- numpy
- matplotlib
- tqdm
- pandas

## Setup

1. Clone the repository:

    ```bash
    git clone https://github.com/yourusername/molecule-property-prediction.git
    cd molecule-property-prediction
    ```

2. Install the required packages:

    ```bash
    pip install -r requirements.txt
    ```

## Train Usage

The training script can be executed with various parameters. Below are the available arguments:

- `--num_epochs`: Number of training epochs (default: 100).
- `--learning_rate`: Learning rate for the optimizer (default: 0.01).
- `--batch_size`: Batch size for data loaders (default: 64).
- `--data_folder`: Path to the data folder (required).
- `--csv_file`: Path to the CSV file (required).
- `--root`: Root directory for saving results (default: `saved_model`).
- `--physicals`: List of physical properties to train (required).

### Example Command

```bash
python train.py --num_epochs 50 --learning_rate 0.001 --batch_size 32 --data_folder "/path/to/data" --csv_file "/path/to/csv" --root "/path/to/root" --physicals normalized_homo normalized_lumo
```

## Test Usage

The test script can be executed with various parameters. Below are the available arguments:

- `--data_folder`: Path to the data folder (required).
- `--csv_file`: Path to the CSV file (required).
- `--batch_size`: Batch size for data loaders (default: 350).
- `--root`: Root directory for saved models (required).
- `--physicals`: List of physical properties to evaluate (required).
- `--device`: Device to use for computation (default: `cuda`).

### Example Command

```bash
python test.py --data_folder "/path/to/data" --csv_file "/path/to/csv" --batch_size 350 --root "/path/to/saved/models" --physicals normalized_homo normalized_lumo --device cuda
```
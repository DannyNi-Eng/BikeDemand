# BikeDemand

BikeDemand is a planned PyTorch project to forecast hourly demand using the UCI Seoul Bike Sharing Demand dataset. The proposed comparison covers MLP and GRU models, one-hour and 24-hour forecasts, and 48-hour and 168-hour historical lookbacks. This repository currently contains setup and planning only; no dataset, models, or results are included.

## Setup (Windows, Conda, VS Code)

1. From this directory, create the environment: `conda env create -f environment.yml`.
2. Activate it: `conda activate bikedemand`.
3. Install the CUDA-enabled PyTorch wheel for the tested NVIDIA setup: `python -m pip install "torch==2.14.1+cu130" --index-url https://download.pytorch.org/whl/cu130`. See [PyTorch installation](#pytorch-installation) for other hardware.
4. Register the kernel: `python -m ipykernel install --prefix "$env:CONDA_PREFIX" --name bikedemand --display-name "Python (bikedemand)"`.
5. Open this folder in VS Code with `code .`. Use **Python: Select Interpreter** and choose the `bikedemand` Conda environment. In notebooks, select **Python (bikedemand)** as the kernel. Install the VS Code Python and Jupyter extensions if prompted.
6. Run `python -m pytest` to check the test runner. There are no project tests yet.

## PyTorch installation

The tested machine has an NVIDIA GeForce RTX 4060 Laptop GPU (compute capability 8.9), driver 592.82, and driver-reported CUDA 13.1 support. The CUDA 13.0 PyTorch wheel is appropriate for this setup. The hardware-specific command is separate from `environment.yml` so the Conda file stays usable on other machines. Choose the correct stable wheel for your machine using the [official PyTorch install guide](https://pytorch.org/get-started/locally/) and [versioned wheel commands](https://pytorch.org/get-started/previous-versions/). Only PyTorch itself is needed here; image and audio packages are omitted.

To check the installation, run:

```powershell
python -c "import torch; print(torch.__version__, torch.version.cuda, torch.cuda.is_available())"
```

The dataset has not been downloaded. See [data/README.md](data/README.md) for its intended location and [PROJECT_PLAN.md](PROJECT_PLAN.md) for planned work.


# Standard conda environment for ML development with GTX970 CUDA support

This provides a Conda environment made to support GTX970 CUDA with popular ML libraries.

## Table of contents

> - [Contact info](#contact-info)
> - [Loading the conda environment](#loading-the-conda-environment)
> - [Using the sample notebook](#using-the-sample-notebook)
> - [Exporting the conda environment](#exporting-the-conda-environment)
> - [Manually loading the conda environment](#manually-loading-the-conda-environment)

## Contact info

| Name             | GitHub                                      | Email                                                       |
| :--------------- | :------------------------------------------ | :---------------------------------------------------------- |
| Bontinck Lennert | [Pikawika](https://www.github.com/pikawika) | [info@lennertbontinck.com](mailto:info@lennertbontinck.com) |

## Loading the conda environment

```shell
# Navigate to the folder where this GitHub directory is 
cd .../conda-ml-cuda/
# Configure a new environment from the YML file
conda env create -f ml-env-windows.yml
```

## Using the sample notebook

```shell
# Navigate to the folder where this GitHub directory is 
cd .../conda-ml-cuda/
# Activate the desired export environment
conda activate ml
# Open jupyter notebook
jupyter notebook
```

## Exporting the conda environment

```shell

# Navigate to the folder where this GitHub directory is 
cd .../conda-ml-cuda/
# Activate the desired export environment
conda activate ml
# Export to yml file
conda env export > ml-env-windows.yml --no-builds
```

## Manually loading the conda environment

1. Using Anaconda Navigator add an environment named `ml` with Python version `3.19.3` and R `3.6.1`.

2. Install SciKit-Learn

```shell
# Install/upgrade scikit-learn for traditional ML
# V1.1.2 was used.
pip install -U scikit-learn==1.1.2
```

3. Install Pandas
 
```shell
# Install/upgrade pandas
# V1.4.4 was used.
pip install -U pandas==1.4.4
```

4. Install TensorFlow
 
```shell
# Install/upgrade tensorflow
# V2.10.0 was used.
pip install -U tensorflow==2.10.0
```

5. Check if NVIDIA drivers are installed correctly (i.e. Geforce drivers)
 
```shell
nvidia-smi
```

5. Install CUDA and cuDNN using Conda
 
```shell
# The Cuda version used is V11.2
# The CuDNN version used was V8.1.0
conda install -c conda-forge cudatoolkit=11.2 cudnn=8.1.0
```
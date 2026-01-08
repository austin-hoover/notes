# Conda

## Create new environment
```
conda create --name <name>
```


## Create new environment with specific python version
```
conda create --name <name> python=3.11.5
```


## Create new environment from file
```
conda env create -f environment.yml
```


## Delete environment
```
conda remove --name <env_name> --all
```


## Rename environment
```
conda rename -n <old_name>  <new_name>
```


## Install jupyter kernel in conda environment
```
conda activate <name>
python -m ipykernel install --user --name <name>
```


## Delete jupyter kernel
```
jupyter kernelspec uninstall unwanted-kernel
```


## Automatically add conda environements as jupyter kernels
```
conda install nb_conda_kernels
```


## Remove unused packages/caches
```
conda clean --all
```


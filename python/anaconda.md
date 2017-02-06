# Anaconda

## Install package

```bash
$ conda install package_name
```


## Manage environments

```bash
$ conda create -n env_name list_of_packages

$ conda create -n py3 python=3
$ conda create -n py2 python=2

$ source activate my_env
```

## Update package

```bash
$ conda update package_name
```

## Environment

### Export

```bash
$ conda env export
$ conda env export > environment.yaml
```

### Create

```bash
$ conda env create -f environment.yaml
```

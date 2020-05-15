# conda env

tutorials at:

 [first](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html)

 [second](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#creating-an-environment-with-commands)

## Advantages of using conda

- conda environments isolated changes which pip makes
- pip should not be used in the root environment

## important commands

All below commands are tested on **conda version 4.8.1**, please ensure that environment version is above this.

### version of conda installation

    conda --version

### conda environment creation

create conda evironment with a given name

    conda create --name test_env

create conda environment with given python version
    
    conda create -n test_env python=3.6

creating an environment with given YML file

    conda env create -f environment.yml

### list conda environments

    conda env list

### activating/deactivating a conda evironment

    conda activate test_env

    conda deactivate

### exporting conda env

Exporting environment which is currently active

    conda env export > environment.yml

### remove conda environment

    conda remove --name myenv





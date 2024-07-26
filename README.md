# Server Information


| Server Name | CPU | Ram | GPU | Hard Drive | Services |
| ------------- |:-------------:|:-------------:|:-------------:|:-------------:| -----:|
| m1.bughunter.cloud.edu.au (130.194.72.128) | AMD Ryzen 9 3950X (Base: 3.50GHz, Boost: 4.70GHz / 64MB Cache / AM4 / 32 Cores | 64GB | RTX 3090 24GB | 4 TB | JupyterHub + Rstudio + Remote Desktop + SSH + FTP| 
| m2.bughunter.cloud.edu.au (130.194.73.118) | Intel i7 12 Cores | 64GB | RTX 3090 24GB | 4 TB | JupyterHub + Rstudio + Remote Desktop + SSH + FTP| 
| m4.bughunter.cloud.edu.au (130.194.131.187) | AMD Ryzen 9 5950X | 64GB | RTX 3090 24GB | 4 TB | JupyterHub + Rstudio + Remote Desktop + SSH + FTP| 

# Add User Environment to Jupyterhub

Create a new environment (see the cheatsheet).  Lets call the environment name myenv (you can give it any name you want)

    conda create --name bughunter

Try activating the environment by typing

    conda activate bughunter

To make it appear in Jupyterhub, type in the terminal window the following

    python -m ipykernel install --user --name bughunter --display-name "Python (bughunter)"

Note. run the following if "No module named ipykernel" then rerun the above code to set up your ipykernel under your env 

    conda install ipykernel

You can install any package you want using “conda install PACKAGENAME“, or if a particular version is needed “conda install PACKAGENAME=versionnumber”

    pip install --user nltk gdown

If you want to list all conda environments,

    conda info --envs

If you want to list all available kernels,

    jupyter kernelspec list

If you want to list delete unwanted kernels,

    jupyter kernelspec uninstall unwanted-kernel

If you want to remove the whole environment (e.g., bughunter),

    conda env remove -n bughunter

# Install packages to all users
Since the python virtual environment is at /opt/jupyterhub/, so we need to use the following command.

    sudo /opt/jupyterhub/bin/pip install pydriller pandas scikit-learn matplotlib html5lib beautifulsoup4 seaborn keras tensorflow-gpu torch torchvision nltk numpy scipy statsmodels textblob gensim spacy polygot


# Install R kernel for Jupyterhub

    install.packages('IRkernel')

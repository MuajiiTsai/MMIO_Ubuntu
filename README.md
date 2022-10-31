# MMIO_Ubuntu
A note of Ubuntu(Linux) commands

## For Sudoers
### Add user
```
sudo adduser <username>
```
or
```
sudo adduser <username> sudo
```
When adding new user as sudoer.

## For Other Users
When using any command start with _sudo_, please ask sudoers for help.
### Change password
```
$ passwd
```
## Install Miniconda & create a virtual environment
#### Install Miniconda
```
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
sh Miniconda3-latest-Linux-x86_64.sh
```
#### Create a virtual environment**
```
conda create -n <envname> (python=3.x)
```
#### Activate/Deactivate the environment:
```
conda activate/deactivate <envname>
```
#### Remove the environment:
```
conda remove -n <envname> --all
```
#### Check all environments in your account:
```
conda info -e
```
#### Install a new package:
```
pip install <packagename>
conda install <packagename>
```
or google the guide of installing the package.


#### Install specific edition of a package: (take *numpy* for instance)
```
conda search numpy
conda install numpy=1.11.2
```
## FSL
Add the following code into .profile:
```
FSLDIR=/usr/local/fsl
. ${FSLDIR}/etc/fslconf/fsl.sh
PATH=${FSLDIR}/bin:${PATH}
export FSLDIR PATH
```
then, **close SSH connection and reconnect to the server.**
#### To open FSL:
```
fsl
```

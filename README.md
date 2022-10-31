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
**Install Miniconda**
```
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
sh Miniconda3-latest-Linux-x86_64.sh
```
**Create a virtual environment**
```
conda create -n <envname> (python=3.x)
```
To activate/deactivate the environment:
```
conda activate/deactivate <envname>
```
To remove the environment:
```
conda remove -n <envname> --all
```
## FSL
add the following code into .profile:
```
FSLDIR=/usr/local/fsl
. ${FSLDIR}/etc/fslconf/fsl.sh
PATH=${FSLDIR}/bin:${PATH}
export FSLDIR PATH
```
then, **close SSH connection and reconnect to the server.**

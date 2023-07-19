# MMIO_Ubuntu
## Connect to the Server Using Command Line
Entering the following command in your terminal:
```
ssh <username>@<hostname> -p <port>
```
*Hostname*: ip address of the remote server.  
You can also use SSH service via visualized softwares. (MobaXTerm, FileZilla, etc.)

## For Sudoers
### Add user
#### 1. 
```
sudo adduser <username>
```
or
```
sudo adduser <username> sudo
```
When adding a new user as sudoer.
#### 2. Change the permission (drwx------)
```
sudo chmod 700 /home/<username>
```
#### 3. Check users' disk usage (du)
```
sudo du -sh /home/*
```

## For Other Users
When using any command start with _sudo_, please ask sudoers for help.
### Check Linux Disk Space
```
df
```
### Change password
```
$ passwd
```
### Miniconda
#### Create a virtual environment
```
conda create -n <envname> <python=3.x> (optional, the default is the latest stable edition)
```
#### Activate/Deactivate the environment
```
conda activate/deactivate <envname>
```
#### Remove the environment
```
conda remove -n <envname> --all
```
#### Check all environments in your account
```
conda info -e
```
#### Install a new package
```
pip install <packagename>
conda install <packagename>
```
or google the official guide of installing the package.


#### Install specific edition of a package (take *numpy* for instance)
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
![alt text](https://github.com/MuajiiTsai/MMIO_Ubuntu/blob/main/img/fsl.png)
# SSH Settings
## Server
To check whether SSH is available on the remote server, run:
```
ssh localhost
```
If the output responds with "Connection refused", move on to **installing SSH on the server**.
#### 1. Run the following command to install the SSH server
```
sudo apt-get install openssh-server ii
```
#### 2. Run “ssh localhost” to check if the installation is completed. Enter yes or y to continue.
#### 3. To check the status of the service, enter:
```
sudo service ssh status
```
#### 4. The output should respond that the service is active. You will need to enable it when the service is down by running the command:
```
systemctl start sshd
```
## Client
To check whether you have the SSH client on your system, run the command:
```
ssh
```
If the output responds with "Command not found", move on to installing OpenSSH Client.
#### Run the following command to install the SSH client:
```
sudo apt install openssh-client
```

## Cuda
https://docs.nvidia.com/cuda/cuda-installation-guide-linux/index.html#removing-cuda-toolkit-and-driver  

#### Cuda uninstall
To remove CUDA Toolkit:  
```
sudo apt-get --purge remove "cuda*" "*cublas*" "*cufft*" "*cufile*" "*curand*" \
 "*cusolver*" "*cusparse*" "*gds-tools*" "*npp*" "*nvjpeg*" "nsight*" "*nvvm*"
```
To remove NVIDIA Drivers:  
```
sudo apt-get --purge remove "*nvidia*" "libxnvctrl*"
```
To clean up the uninstall:  
```
sudo apt-get autoremove
```


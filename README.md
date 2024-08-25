# _How to create a genuine macOS installer without access to a Mac?_

<div align="center">
    <img src="./assets/macOS-recovery.png" width="150">
</div>

### _Well, this is relatively easy, thanks to the good work of the [Acidanthera team](https://github.com/acidanthera/OpenCorePkg) with macrecovery_


> [!NOTE]
> _Avoid images distributed on the internet_
> _This process will not use a full macOS image, but rather a recovery image. It will download everything from Apple's servers that will be used to install macOS on your PC/Notebook._ 

#### _Requirements:_
- _USB flash drive or external SSD with at least 2GB of available space_
- _Obviously, internet access_
- _Download the [recovery]() folder_
- _**Windows** or **Linux**_
- _[Python 3](https://www.python.org/downloads/) installed on the machine_

##

#### _On Windiwns_

- _when installing on **Windows** check `Add Python to PATH`_


<div align="center">
    <img src="./assets/path-python.png" width="600">
</div>


- _Checking the installation:_
    - _On **Windows**, open a prompt or terminal and run the command below_

```
python --version
```
- _If it returns something like `python 3.x.x`, the installation was successful and we can go to step 1_
----

#### _On Linux_

- _On **Linux**, Ubuntu for example, usually comes with Python installed, so check first if you have it installed._  

- _Checking the installation:_
    - _On **Linux** open a terminal and run the command below_

```
python --version
```
#### _Or_

```
python3 --version
```
- _If it returns something like `python 3.x.x`, the python is already installed, we can go to step 1_

- _Otherwise, for **Debian** and derivatives, in the terminal run the command below_

```
sudo apt update && sudo apt upgrade
```

- _Enter the user password to update the packages and update the system, once the process is complete, run the command below_

```
sudo apt install python3
```
- _Enter the user password for installation, after completion close the terminal and open it again. Finally verify the installation by running the command below again_

```
python --version
```
#### _Or_

```
python3 --version
```

- _If it returns something like `python 3.x.x`, the python is already installed, we can go to step 1_

## _Step 1_

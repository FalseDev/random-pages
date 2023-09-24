# Install Dependencies
Visit [this link](https://microsoft.com/en-us/download/confirmation.aspx?id=48145) to download the dependency for matplotlib.
After downloading it, open the file and agree to the licence to install it.

In case installation fails, click `download manually` and select the x86 version and try installing again.

# Install matplotlib
## Check python version
Open powershell and run this command to check your version of python
```ps
py -V
```

## Python 3.7
Use the following powershell command
```ps
py -m pip install matplotlib==3.3.1
```

## Python 3.10 or 3.11
Use the following powershell command
```ps
py -m pip install matplotlib
```

## Other versions
Other versions are untested, but should likely work with the method for python 3.10
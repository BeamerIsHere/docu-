#Python 3 Installation - Steps

- Step 1 : Go to the desired installation location. 
	```cd /usr/src```
- Step 2: Download latest python tar file from official archive.
	```wget https://www.python.org/ftp/python/3.7.2/Python-3.7.2.tgz```
- Step 3: Extract the downloaded file. 
	```tar xzf Python-3.7.2.tgz```
- Step 4: Go to extracted python directory.
	```cd Python-3.7.2.tgz```
- Step 5: Compile python source code.
	```./configure --enable-optimizations```
- Step 6: Install python.
	```make altinstall```
- Step 7: Remove the downloaded tar file.
	```rm /usr/src/Python-3.7.2.tgz```
- Step 8:  Create system link as python3.
	```ln -s /usr/src/Python-3.7.2/python  /usr/bin/python3```
- Step 9: Try loading python3.
	```python3```
## Python Package installation.
	
	 ```python3 -m pip install <package>```
## Possible error while installation is pip module error while installing from source.

		Solution is to install dependency package ```yum install libffi-devel```

Link :-  https://bugs.python.org/issue31652 

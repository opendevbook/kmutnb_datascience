# **Section 1**  Setup Environment 
## Install Native Python
**Step 1. Downloading the pthon installer**  
1. Go to official  [https://www.python.org/downloads/](https://www.python.org/downloads/)  
2. Download the latest or previous versions of Python for Windows 64bit (3.13,3.12), including installers

![python download](../assets/images/python1.png)  

1. After the installer is downloaded, double-click the `.exe` file `python-3.13.1-amd64.exe, python-3.12.8-amd64.exe`  
1. Select the install launcher for all user, eanbles all users for the computer to access to the python   
1. Select the python.exe to PATH checkbox, which enables users to launch python from command line
![python download](../assets/images/python2.png)

!!! type "Python Directory"
    **Before you start, learning about python directory**:  
    locate the Python installation directory on your system. The following directories are examples of the default directory paths:

    **C:\Program Files\Python313**: if you selected (User admin priviledges)  Install for all users during installation, then the directory will be system wide
    **C:\Users\"username"\AppData\Local\Programs\Python\Python313**: if you didn’t select Install for all users during installation, then the directory will be in the Windows user path

  
## Discuss: Python Environment:
![python download](../assets/images/PythonEnv.png)

## Start Install process
1. Installing
![python download](../assets/images/python3.png)
Successfull install
![python download](../assets/images/python4.png)

## Setup python environment 
![python download](../assets/images/python13.png)


![python download](../assets/images/python14.png)

## Verify python  
we can verify python installation by command line. Start to use command line from windows. open windows cmd or powershell. run command belows
```
python --version
where python
```
![python download](../assets/images/python5.png)

## Install package with command pyhon -m pip 
```
python -m pip install tersorflow
```
from output below there is ERROR: say Could not find a version that satisfies the requirement tensorflow version 
![python download](../assets/images/python6.png)

let goto [https://pypi.org/project/tensorflow/](https://pypi.org/project/tensorflow/)
![python download](../assets/images/python7.png)

**Interesting we can install numpy package:**  
The error occurs because TensorFlow currently does not support Python 3.13. TensorFlow's development cycles typically lag behind the latest Python versions, and support is usually added after thorough testing.

![python download](../assets/images/python8.png)


## Next Step: we reinstall python 3.12
we want to install tensorflow again. We will install tersorflow to python 3.12. Let download python 3.12:
![python download](../assets/images/python9.png)

continue process installation:
![python download](../assets/images/python10.png)


![python download](../assets/images/python11.png)

Success install:
![python download](../assets/images/python12.png)

Let Change python environment to python312:
![python download](../assets/images/python15.png)

Verify new python version and install tensorflow again:
![python download](../assets/images/python16.png)

we will see the result: Successfully install package:
![python download](../assets/images/python17.png)

## Create python project
create normal folder and change folder to python project with environment

1. create folder with `mkdir` command and move to folder with `cd ` command  
2. create python virtal enviroment with command `python -m venv myvenv` in project directory
![python download](../assets/images/python18.png)
3. activate pthon envionment with `.\myenv\Scripts\activate.bat`
![python download](../assets/images/python19.png)
we will see the indicator `(myenv)` whick show the corrent environment we reside.

Discuss: install package in environment
![python download](../assets/images/python_engine1.png)
isolation:
![python download](../assets/images/python_engine2.png)

## Key Python Package for DataScience
key packages in Python for Data Science and Machine. 
1. Pandas
2. Numpy
3. Scikit Learn
4. Matplotlib
5. Seaborn

We have a foundation in Python, so it's essential to explore various Python packages such as numpy, pandas, and matplotlib, as well as Python modules like math, random, and datetime. In the Python ecosystem, both modules and packages serve as tools to organize and structure code based on different purposes.

![](../assets/images/Python-packages.webp)

### Difference Between Packages and Modules in Python

| **Aspect**        | **Module**                                        | **Package**                                      |
|--------------------|--------------------------------------------------|-------------------------------------------------|
| **Definition**     | A single Python file containing code (functions, classes, etc.). | A collection of modules organized in a directory with an `__init__.py` file. |
| **Structure**      | A `.py` single file.                             | A directory containing an `__init__.py` file and one or more modules. |
| **Purpose**        | To group related code together.                  | To organize multiple modules into a hierarchical structure. |
| **Example**        | `math`, `random`, `datetime`                     | `numpy`, `pandas`, `matplotlib`                |
| **Use Case**       | Lightweight organization for smaller functionality. | Manage larger projects with complex dependencies and modularity. |
| **How to import**  | import module_name                               |  import package_name.module_name |

### Key Concepts and Purposes

#### Modules:
- Provide a way to reuse code in a single file.
- Focus on a specific functionality (e.g., math operations, random number generation).
- **Example**: Importing a single module:
```python
  import math
  print(math.sqrt(16))  # Output: 4.0
```
### Packages:
- Group related modules together to create a larger, well-organized library.
- Enable a hierarchical structure for large-scale applications.
- **Example**: Importing a module from a package:
```python
  import numpy.linalg
  print(numpy.linalg.norm([3, 4]))  # Output: 5.0
```
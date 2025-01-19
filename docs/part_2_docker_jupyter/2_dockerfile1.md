# **Section 2** Dockerfile for Data Science Environment with Jupyter Lab

``` title="Dockerfile"
# Use Python 3.12 as the base image
FROM python:3.12-slim

# Set the working directory in the container
WORKDIR /app

# Install system dependencies for data science packages
RUN apt-get update && apt-get install -y \
    build-essential \
    libcurl4-openssl-dev \
    libssl-dev \
    libffi-dev \
    && apt-get clean

# Install Jupyter Lab and common data science packages
RUN pip install --no-cache-dir \
    jupyterlab \
    numpy \
    pandas \
    matplotlib \
    scikit-learn \
    seaborn \
    scipy \
    plotly \
    && pip install --upgrade pip

# Expose Jupyter Lab's default port
EXPOSE 8888

# Set the default command to launch Jupyter Lab
CMD ["jupyter", "lab", "--ip='*'", "--port=8888", "--no-browser", "--allow-root"]

```

This Dockerfile creates a containerized environment for data science workflows, including the installation of Jupyter Lab and common data science packages.

### **1. Use Python 3.12 as the base image**
The base image is set to Python 3.12 with a slim variant to reduce image size.

```
FROM python:3.12-slim
```

Click link to see specification of <a href="https://hub.docker.com/layers/library/python/3.12-slim/images/sha256-ac212230555ffb7ec17c214fb4cf036ced11b30b5b460994376b0725c7f6c151" target="_blank">python3.12-slim page</a>


### **2. Set the working directory in the container**
This instruction sets the working directory to /app inside the container. All subsequent commands will be run from this directory.
```
WORKDIR /app
```

### **3. Install system dependencies for data science packages**
This step installs system dependencies required for compiling and installing various Python packages used in data science.
```
RUN apt-get update && apt-get install -y \
    build-essential \
    libcurl4-openssl-dev \
    libssl-dev \
    libffi-dev \
    && apt-get clean

```

### **4. Install Jupyter Lab and common data science packages**
The following Python packages are installed:  

1. Jupyter Lab: The web-based interactive development environment for notebooks.
2. Data Science Libraries: Including numpy, pandas, matplotlib, scikit-learn, seaborn, scipy, and plotly.  
This installation is done using pip to ensure that packages are installed without caching.
```
RUN pip install --no-cache-dir \
    jupyterlab \
    numpy \
    pandas \
    matplotlib \
    scikit-learn \
    seaborn \
    scipy \
    plotly \
    && pip install --upgrade pip
```

### **5. Expose Jupyter Lab's default port**
Expose port 8888, the default port that Jupyter Lab listens on, making it accessible from outside the container.
```
EXPOSE 8888
```

### **6. Set the default command to launch Jupyter Lab**
The default command launches Jupyter Lab with the following params options:

* --ip='*': Allows connections from any IP address.
* --port=8888: Specifies the port to run Jupyter Lab on.
* --no-browser: Prevents the automatic opening of a browser.
* --allow-root: Allows running Jupyter Lab as the root user inside the container.

### **7. Complete CMD command**
```
CMD ["jupyter", "lab", "--ip='*'", "--port=8888", "--no-browser", "--allow-root"]
```

### Format of CMD

Format of CMD:

```
CMD command param1 param2
```
This is executed in the shell (/bin/sh -c).

- Exec form (recommended):

```
CMD ["executable", "param1", "param2"]
```
This does not invoke a shell, which prevents issues like signal handling and allows the executable to run directly.


### **Summary of Workflow:**
1. Base Image: Python 3.12-slim for a lightweight container.
2. System Dependencies: Essential packages for compiling and installing Python packages.
3. Python Packages: Installs Jupyter Lab and essential libraries for data science.
4. Expose Port: Makes Jupyter Lab accessible at port 8888.
5. Start Jupyter Lab: The container automatically starts Jupyter Lab with the appropriate configurations when run.
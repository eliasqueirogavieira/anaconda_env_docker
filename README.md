
# Docker Image for Python Environment with Anaconda

This repository contains the necessary files to create a Docker image for a Python environment with Anaconda. The environment includes a variety of popular packages for data science, machine learning, and other applications.


## File
- **Dockerfile (Linux and Windows version)** - the instructions for building the Docker image.
- **environment.yml** - the list of packages to be installed in the Python environment.
## Building the image
The image can be built using the **'docker build'** command. Before building the image, navigate to the directory containing the **Dockerfile** and **environment.yml** files.

### Linux
To build the Linux version of the image, run the following command:
```bash
    docker build -t <image_name> .
```
Replace _<image_name>_ with a descriptive name for the image.

### Windows
To build the Windows version of the image, run the following command:
```bash
docker build -t <image_name> -f Dockerfile.windows .
```
Replace _<image_name>_ with a descriptive name for the image.
If you encounter the following error:
```bash
Error response from daemon: open \\.\pipe\docker_engine_windows: The system cannot find the file specified.
```
Open pwsh with Administrator permissions and execute the code below and restart your machine:
```bash
Enable-WindowsOptionalFeature -Online -FeatureName $(“Microsoft-Hyper-V”, “Containers”) -All
```
## Running the image

The image can be run as a container using the **'docker run'** command. The following command will start a new container based on the image:
```bash
docker run -it <image_name> /bin/bash
```
Replace _<image_name>_ with the name of the image you built in the previous step.

### Using the Container
Once the container is running, you can start using the Python environment with Anaconda. The environment includes a variety of popular packages for data science, machine learning, and other applications.

To activate the environment, run the following command:
```bash
conda activate envml
```
Replace _envml_ with the name of the environment defined in the _environment.yml_ file.

You can then start using the packages in the environment, for example, by starting a Jupyter notebook:
```bash
jupyter notebook
```
This will start a Jupyter notebook server in the container, which you can access from your host machine's web browser.

To exit the container, simply type **'exit'** or **'CTRL + D'**.

## 🔗 Links

[![linkedin](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/elias-queiroga/)



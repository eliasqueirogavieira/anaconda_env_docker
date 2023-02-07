# Use an official Python runtime as the base image
FROM python:3.9

# Set the working directory
WORKDIR /app

# Copy the environment file
COPY environment.yml .

# Install Anaconda
RUN wget https://repo.anaconda.com/archive/Anaconda3-2022.10-Linux-x86_64.sh && \
    bash Anaconda3-2022.10-Linux-x86_64.sh -b -p /opt/conda && \
    rm Anaconda3-2022.10-Linux-x86_64.sh

# Set up the environment
RUN /opt/conda/bin/conda env create -f environment.yml

# Set the default command
CMD [ "/bin/bash" ]
# Use an official Python runtime as the base image
FROM python:3.10.9-windowsservercore-1809

# Set the working directory
WORKDIR /app

# Copy the environment file
COPY environment.yml .

# Install Anaconda
RUN powershell -Command \
    Invoke-WebRequest https://repo.anaconda.com/archive/Anaconda3-2022.10-Windows-x86_64.exe -OutFile Anaconda3-2022.10-Windows-x86_64.exe 

RUN powershell -Command \
    Start-Process Anaconda3-2022.10-Windows-x86_64.exe -ArgumentList '/InstallationType=JustMe','/AddToPath=0','/RegisterPython=0','/S','/D=C:\anaconda' -NoNewWindow -Wait

RUN powershell -Command \
    Remove-Item Anaconda3-2022.10-Windows-x86_64.exe -Force

# Set up the environment
RUN C:\anaconda\Scripts\conda.exe env create -f environment.yml

# Set the default command
CMD [ "cmd.exe" ]

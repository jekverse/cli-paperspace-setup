Setup Environment for Paperspace Gradient Notebook Command Line Interface

Description:
This setup.sh script is designed to get your Python environment ready for Paperspace Gradient Notebook. It’ll update your system, install Python 3.7 and its dependencies, create a virtual environment, and set up pip and the Gradient SDK. This script is super powerful. Normally, you’d have to configure your notebooks directly through the Paperspace website, but with this setup, you can do it all right from the terminal!

Steps:

1. Create a file named setup.sh in your desired directory.
Use this command in the terminal to create the file:

nano setup.sh


2. Paste the following code into the setup.sh file.
Here’s the code you need to add:

#!/bin/bash

# Update and upgrade packages
sudo apt update
sudo apt upgrade -y

# Install required packages
sudo apt install -y build-essential libssl-dev libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev libncursesw5-dev xz-utils tk-dev libffi-dev liblzma-dev python3-openssl git
sudo apt install software-properties-common

# Add deadsnakes PPA and install Python 3.7
sudo add-apt-repository ppa:deadsnakes/ppa
sudo apt update
sudo apt install python3.7
sudo apt install python3-pip

# Create a virtual environment with Python 3.7
python3.7 -m venv --without-pip venv
source venv/bin/activate

# Download and install pip for Python 3.7
wget https://bootstrap.pypa.io/pip/3.7/get-pip.py
sudo apt-get install python3.7-distutils
python get-pip.py

# Verify pip installation and install Gradient
pip --version
sudo pip install -U gradient

After opening the file in the editor, paste the whole code above, save it by pressing CTRL + O, hit Enter to confirm, and exit with CTRL + X.


3. Save the file and give it executable permissions.
Before running it, make sure to give executable permissions with:

chmod +x setup.sh


4. Run the setup.sh file to execute all the commands.
Use this command to run the script:

./setup.sh



What It Does:

This setup.sh script will do a bunch of things:

Update and upgrade your system packages.

Install essential dependencies like build-essential, libssl-dev, libbz2-dev, and more for your Python environment.

Add the deadsnakes PPA to get Python 3.7.

Install Python 3.7 and pip, then create a virtual environment for better package management.

Finally, it installs the Gradient SDK using pip to run your Paperspace notebooks through the API token.


Once you run this script, your environment will be all set up and ready to go for Paperspace Gradient Notebook!


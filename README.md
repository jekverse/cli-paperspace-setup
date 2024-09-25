###Setup Environment for Paperspace Gradient Notebook

Overview

This setup script, setup.sh, is designed to help you quickly prepare a Python environment for running Paperspace Gradient Notebooks. Normally, you’d have to configure everything directly through the Paperspace web interface, but with this setup, you can get your notebooks up and running just by using terminal commands. How cool is that?

Steps to Follow

1. Create a file named setup.sh in your desired directory. Open your terminal and run:

nano setup.sh


2. Paste the following code into the setup.sh file. Here’s the code you need:

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

Once you’ve got the editor open, paste the code above, save it by pressing CTRL + O, hit Enter, and exit with CTRL + X.


3. Save and give execute permissions to setup.sh. Before running the script, make it executable with this command:

chmod +x setup.sh


4. Run setup.sh to execute all the commands. Fire it up with:

./setup.sh



What Happens Next

When you run this script, it will:

Update and upgrade your system packages.

Install essential dependencies like build-essential, libssl-dev, libbz2-dev, and more to get your Python environment up and running.

Add the deadsnakes PPA to provide access to older Python versions like 3.7.

Install Python 3.7 and pip, then create a virtual environment for better package management.

Install the Gradient SDK via pip so you can easily run your Paperspace notebooks with just your API token.


After you run this setup, you’ll be all set to dive into using Gradient Notebooks on Paperspace!


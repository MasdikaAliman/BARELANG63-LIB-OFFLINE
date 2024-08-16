# Offline Build Instructions

This README provides steps to compile and build your program offline using Nuitka and Python.

## Prerequisites

Ensure you have the following Python packages installed:

- **msgpack**
- **Nuitka**

You can install Nuitka using pip:

```bash
python -m pip install nuitka

Setup Offline Environment

    Add Offline Environment Variable:

    Edit the ~/.bashrc file to include the offline environment variable:

    bash

sudo gedit ~/.bashrc

Add the following line:

bash

export OFFLINE_ENV=/opt/offline

Save the file and apply the changes:

bash

source ~/.bashrc

Create a Compiler Using Nuitka:

Navigate to the maen_boss/builder directory and compile your script using Nuitka:

bash

cd maen_boss/builder
python -m nuitka robot_builder.py -o robot_build

Move the compiled file to /usr/local/bin:

bash

    sudo mv robot_build /usr/local/bin/

Build Package

To build your package, use the robot_build command. You can build multiple packages by specifying the package name and sub-processes:

bash

robot_build package_name sub_process

Example:

bash

robot_build heartbeat/ 5

Troubleshooting
Error: "Wah parah ga ada OFFLINE_ENV"

If you encounter an error indicating that OFFLINE_ENV is missing, run the following command to ensure the correct permissions for the /opt directory:

bash

sudo chown yourusername:yourgroup /opt

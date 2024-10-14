# Implementation Journal: Creating a .sh Script to Install Git on Ubuntu


## Objective:
The goal of this journal is to document the process of creating a shell script (.sh file) that automates the installation of Git on an Ubuntu system. This script will streamline the installation process, ensuring that all necessary steps and dependencies are covered without requiring manual intervention.

## Step-by-Step Procedure:
 ### 1. Understanding the Environment
- Operating System: Ubuntu (20.04 and above)
- Tool: Bash shell script
- Purpose: To automate the installation of Git
Before writing the script, it's essential to understand the dependencies and steps involved in installing Git on Ubuntu manually. These steps will include updating the package index, installing Git, and verifying the installation.

### 2. Prerequisites
Ensure the system has:
- Basic knowledge of editor (nano ,vim)
- Basic knowledge of shell scripting (bash)
- Root or sudo access for installing software
### 3. Writing the Script
The shell script should perform the following actions:

- Update the system package lists
- Install Git
- Verify the installation
- Handle any potential errors
### 4. Set Up the Script File
To begin, you'll need to create a new .sh script file. You can use any text editor available in Linux such as nano, vim, or gedit. Here, we will use nano to create the file.

Command:
```
nano install_git.sh
```
This will open the nano text editor to create and edit the install_git.sh script.

### 5. Add Shebang Line
The first line of any shell script should specify the interpreter that will be used to run the script. This is done using the shebang (#!) followed by the path to the interpreter. For a Bash script, the shebang is:

Shebang Line:
```
#!/bin/bash
```
This line ensures that the script will be executed using the Bash shell.

### 6. Write the Script Logic
Now, you can begin adding the commands that the script will execute. In this case, we want to:

- Update the package lists using apt update.
- Install Git using apt install git.
- Here’s how the script logic will look:

Script Example:

```
#!/bin/bash

# Update package list
echo "Updating package lists..."
sudo apt update

# Install Git
echo "Installing Git..."
sudo apt install git -y

# Confirm installation
echo "Git installation completed!"
git --version
```
Explanation:
- sudo apt update: Updates the list of available packages from the repositories.
- sudo apt install git -y: Installs Git. The -y flag automatically confirms the installation.
- git --version: Checks the installed Git version to verify the installation.
### 7. Save the File
After writing the script, save the file:

Press CTRL + X to exit nano.
Press Y to confirm saving the changes.
Press Enter to confirm the file name.
### 8. Make the Script Executable
After creating the script, it needs to be made executable so it can be run from the terminal. This is done using the chmod command with the +x option.

Command:
```
chmod +x install_git.sh
```
Explanation:
chmod: Stands for "change mode" and is used to modify file permissions.
+x: Adds executable permission to the file.
install_git.sh: The name of the script file.
### 9. Execute the Script
Now that the script is executable, you can run it from the terminal using the following command:

Command:
```
./install_git.sh
```
Explanation:
- ./: Specifies the current directory.
- install_git.sh: The name of the script file you want to execute.
The script will now run and install Git, displaying the steps and outputs in the terminal.
### 10. Verify Script Functionality
After the script runs, check if Git was successfully installed by running the following command:

Command:
```
git --version
```
This should return the installed version of Git if the script executed successfully.

## Conclusion:
By following the above steps, we successfully created a shell script that automates the installation of Git on Ubuntu. This process simplifies the installation, especially for repetitive tasks or when setting up multiple machines. The use of error handling and verification ensures that the script performs as expected without manual oversight.

# MapDrives.bat
Overview
MapDrives.bat is a batch script designed to map multiple network drives to specified locations. The script includes error handling to ensure that if a drive letter is already in use, it will not attempt to map that drive again. The script accepts a username as a command-line argument and appends that username to one of the network paths.

Usage
To run the script, open a command prompt and navigate to the directory where MapDrives.bat is located. Then, execute the script with the username as an argument:
MapDrives.bat username
Replace username with the actual username you want to append to the drive path for X:.

Network Paths and Drive Letters
The script maps the following network paths to their corresponding drive letters:

Z: to \\server\share1
Y: to \\server\share2
X: to \\server\share3\username
Error Handling
The script includes error handling to check if a drive letter is already in use. If a drive letter is in use, the script will skip mapping that drive and output a message indicating that the drive letter is already in use.

Explanation of script:
Username Check:

Ensures a username is provided as an argument.
Drive Definitions:

Defines the network paths and corresponding drive letters using environment variables.
Iterate Through Drives:

Iterates through the specified drive letters (Z, Y, X).
Uses call to handle the nested loop logic by calling a separate label (:checkDrive).
Check Drive Letter Usage and Map Drive:

The :checkDrive label checks if the drive letter is already in use and attempts to map the drive if it is not.
Uses goto :eof to end the subroutine cleanly.

Notes
Ensure that you have the necessary permissions to map network drives.
This script should be run in a command prompt window with appropriate privileges.
Modify the network paths in the script as needed to fit your network environment.

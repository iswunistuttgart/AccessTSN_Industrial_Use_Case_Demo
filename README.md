# AccessTSN Industrial Use Case Demo
This is a demonstration to give an example on how to use Linux with the current support for Time Sensitive Networking (TSN) as an industrial endpoint. For this purpose the components of this demonstration form a converged network use case in an industrial setting. 

The Use Case Demonstration is aim and tested with the AccessTSN Endpoint Image but should also work independently from the image.

This work is a result of the AccessTSN-Project. More information on the project as well as contact information are on the project's webpage: https://accesstsn.com

## Structure of the Industrial Use Case Demo Git-projects

The AccessTSN Industrial Use Case Demo consists of multiple Git-projects, each holding the code to one component of the demonstration. This is the main project. It includes the documentation of the overall industrial use case as well as instructions to set up the complete converged network. To make the setup easier, various scripts to compile, install and run the applications as well as configuration files for system functions are provided. When executed the scripts will clone the required git-projects of the other components.

## Structure of this project: (Work in progress)
* The description and explanation of the Use Case is found in the *doc/usecase* subdirectory.
* Documentation on how to setup the demonstration is found in the *doc/install* subdirectory. This also includes the hardware and software requirements.
* The *scripts* subdirectory contains the necessary scripts to install and configure the demo components. It also includes common scripts to configure Linux TSN functions.
* Sample configuration files which are relevant for all of the use case components are placed in the *config* subdirectory. 

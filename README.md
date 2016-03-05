# pugixml
This repository is a cmake wrapper, that can be used in ROS for the library pugixml: [http://pugixml.org/](http://pugixml.org/).
Current version of library pugixml: 1.7


# Table of contents
+ [Disclaimer](#disclaimer)
+ [Repository information](#repository-information)
  - [Packages](#packages)
  - [Libraries and executables generated by this repository](#libraries-and-executables-generated-by-this-repository)
  - [Branches](#branches)
+ [Repository requirements and dependencies](#repository-requirements-and-dependencies)
	- [System Requirements and Compatibility](#system-requirements-and-compatibility)
	- [Dependencies](#dependencies)
		* [Additional System Dependencies](#additional-system-dependencies)
		* [ROS Dependencies](#ros-dependencies)
		* [Extra ROS Dependencies](#ros-dependencies)
+ [Installation Instructions](#installation-instructions)
	- [Pre-requirements](#pre-requirements)
	- [Installation steps](#installation-steps)
+ [Documentation](#documentation)
+ [License](#license)
+ [Contributors](#contributors)
	- [Authors / Maintainers / Past contributors](#authors-/-maintainers-/-past-contributors)
	- [Contact information](#contact-information)
	- [New contributors](#new-contributors)
+ [Acknowledgments](#acknowledgments)



# Disclaimer
You are using this software at your own risk. The authors decline any responsibility for personal injuries and/or property damage.


# Repository information

## Packages
This repository is formed by one single ROS packages: 

+ pugixml: cmake wrapper, that can be used in ROS, for the library pugixml: [http://pugixml.org/](http://pugixml.org/)

Note that the use of ROS is optional.


## Libraries and executables generated by this repository
This repository generates:

+ Libraries: libpugixml.a
+ Executables: none


## Repository Branches
This repository has the following branches:

+ Master: Catkin version of the package.



# Repository requirements and dependencies

## System Requirements and Compatibility

This package is running under:

+ Ubuntu: 14.04 and above
+ ROS (optional): Indigo and above with Catkin

This package has been tested under:

+ Ubuntu: 14.04
+ ROS (optional): Indigo and Jade with Catkin



## Dependencies

### Additional System Dependencies

This metapackage requires:

+ Nothing special, just a C++ compiler and cmake.


### ROS Dependencies

This metapackage depends on the following ROS packages:

+ Nothing special, optional.



# Installation Instructions


## Pre-requirements
Install all the system and ROS dependencies (for example, using rosdep install, or apt-get, or directly from source).


## Installation steps

Installation on ROS environment:

1. Create your ROS catkin workspace as usual.
2. Inside your workspace, download the pugixml repository:
    git clone https://github.com/joselusl/pugixml ./
3. Compile your ROS catkin workspace as usual.


Installation outside ROS environment:

1. Create your workspace as usual.
2. Inside your workspace, download the pugixml repository:
    git clone https://github.com/joselusl/pugixml ./
3. Compile your workspace as usual using cmake.





# Documentation

For more information related to the pugixml library, please refer to: [http://pugixml.org/](http://pugixml.org/).


This repository is the continuation of the work done by Jose Luis Sanchez-Lopez to use the pugixml library in ROS, initied in January 2013. The first version was splitted in the following repositories (already outdated and deprecated) and its dependencies:

+ https://bitbucket.org/joselusl/lib_pugixml


Unfortunately this repository has no more extra documentation. 

If this repository gets the interest of the community, we will continue adding information depending on the questions made by its users.



# License
All additional distributed software are subject to the 3-clause BSD license. See the LICENSE file. 

Please, refer to [http://pugixml.org/](http://pugixml.org/) to check the license of the pugixml library (MIT License).




# Contributors

## Authors / Maintainers / Past contributors
List of people that have contributed:

+ Jose Luis Sanchez-Lopez (jl.sanchez@upm.es): Main Author, Maintainaince, Debugging, Testing and Documentation.


## Contact information
Questions, suggestions, requests, ... whatever. Feel free to contact me (Jose Luis Sanchez-Lopez - jl.sanchez@upm.es).


## New contributors
You are very welcome to contribute to this repository by opening a pull request via Github.
	

# Acknowledgments
Special thanks to:

+ Computer Vision Group (CVG): [www.vision4uav.eu](www.vision4uav.eu)
+ Centre for Automation and Robotics (CAR): [http://www.car.upm-csic.es/](http://www.car.upm-csic.es/)
+ Consejo Superior de Investigaciones Cientificas (CSIC): [http://www.csic.es](http://www.csic.es)
+ Universidad Politecnica de Madrid (UPM): [http://www.upm.es](http://www.upm.es)


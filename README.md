BEGINNER TUTORIAL
==================

*The aim of this respository is to provide a simple example (talker/listener) about how to 
create and deploy a ROS package in an embedded system using the meta-ros project.*


The code illustrates how to create a simple talker/listener ros package written in **python**.
The package will be cross-compiled using bitbake and deployed in an embedded system
that uses the meta-ros project (https://github.com/bmwcarit/meta-ros).

CROSS COMPILATION
=================

Recipes are available at https://github.com/vmayoral/beagle-ros/tree/master/recipes.



USAGE
=====

The easiest way to use the code is to get the code `git clone https://github.com/vmayoral/beginner_tutorials.git` and the install the through `opkg install beginner_tutorials/ipkg/beginner_tutorials*.ipkg`. (This has been compiled for the **beaglebone** in the Angstrom distribution)

An alternative method is to cross-compile the code by yourself following these instructions:

* Set up an Angstrom distribution in your embedded platform. Some basic instructions about how to do to accomplish this are given at the `README.md`
of https://github.com/vmayoral/beagle-ros.

* `git clone` the beagle-ros project (https://github.com/vmayoral/beagle-ros.git) in some place such as `/tmp`

* add `recipes/*` to the `meta-ros/recipes-ros/`: `cp -r /path/to/beagle-ros/recipes/* /path/to/meta-ros/recipes-ros/`. This step adds the recipe required to cross-compile this code inside of the meta-ros code structure.

* `bitbake beginner_tutorials` to create an ipkg of the ROS package.

* copy `/path/to/the/package/beginner_tutorials*.ipkg` to your embedded platform and install it using `opkg install beginner_tutorials*.ipkg`

* run the package using `rosrun beginner_tutorials talker.py` or `rosrun beginner_tutorials listerner.py`

HOW TO REPLICATE
===================

* Set up an Angstrom distribution in your embedded platform. Some basic instructions about how to do to accomplish this are given at the `README.md`
of https://github.com/vmayoral/beagle-ros.

* Create a ROS package the usual way (`catkin_create_pkg`).

* Edit the CMakeLists so that it'll deploy files according to your needs (check http://ros.org/wiki/catkin/CMakeLists.txt).

* Upload the code of the package to a github repository.

* Create a bitbake recipe such as the one provided for this example available at https://github.com/vmayoral/beagle-ros/blob/master/recipes/beginner-tutorials/beginner-tutorials_git.bb

* Put the recipe in the meta-ros file structure (check USAGE instructions for an example)

* cross-compile and install the package as explained in the USAGE section 


NEXT STEPS
=======
Try the [ros-tutorials](https://github.com/vmayoral/beagle-ros/tree/master/recipes) recipes.

LICENSE
=======

The MIT License (MIT)

Copyright (c) 2013 Víctor Mayoral Vilches.

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

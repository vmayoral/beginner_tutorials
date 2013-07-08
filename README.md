BEGINNER_TUTORIAL
==================

*The aim of this respository is to provide a simple example (talker/listener) about how to 
create and deploy a ROS package in an embedded system using the meta-ros project.*


The code illustrates how to create a simple talker/listener ros package written in **python**.
The package will be cross-compiled using bitbake and deployed in an embedded system
that uses the meta-ros project (https://github.com/bmwcarit/meta-ros).

USAGE
=====

* Set up an Angstrom distribution in your embedded platform. Some basic instructions about how to do to accomplish this are given at the `README.md`
of https://github.com/vmayoral/beagle-ros.

* `git clone` the beagle-ros project (https://github.com/vmayoral/beagle-ros.git) at the `sources/` directory of your Angstrom installation.

* Add the beagle-ros package to the Angstrom packages (COMPLETE)

* `bitbake beginner_tutorials` to create an ipkg of the ROS package.

* copy `beginner_tutorials*.ipkg` to your embedded platform and install it using `opkg install beginner_tutorials*.ipkg`

HOW TO REPLICATE
===================

* Set up an Angstrom distribution in your embedded platform. Some basic instructions about how to do to accomplish this are given at the `README.md`
of https://github.com/vmayoral/beagle-ros.

* Create a ROS package the usual way (`catkin_create_pkg`).

* Upload the code of the package to a github repository

* Create a bitbake recipe such as the one provided for this example available at https://github.com/vmayoral/beagle-ros/blob/master/recipes/beginner-tutorials_git.bb

* COMPLETE
LICENSE
=======

The MIT License (MIT)

Copyright (c) 2013 Víctor Mayoral Vilches.

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

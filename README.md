# roscpp_initializer

Catkin package with python bindings for roscpp to ensure that `ros::init()` and `ros::shutdown()` are called appropiately. Code adapted from moveit's [ROScppInitializer Class](http://docs.ros.org/indigo/api/moveit_ros_planning_interface/html/classmoveit_1_1py__bindings__tools_1_1ROScppInitializer.html). For use case, see ROS tutorial on how to use a [C++ Class with ROS Messages in Python](http://wiki.ros.org/ROS/Tutorials/Using%20a%20C%2B%2B%20class%20in%20Python#Class_with_NodeHandle).

# Dependencies
Install the appropiate version of ROS and the following dependencies:

```shell
$ sudo apt-get install libboost-all-dev python-catkin-tools
```

# Usage
Clone the package into a catkin workspace and build the workspace:

```shell
$ mkdir catkin_ws
$ cd catkin_ws && mkdir src $$ cd src
$ catkin_init_workspace
$ git clone https://github.com/vinitha910/roscpp_initializer.git
< CLONE OTHER NECESSARY REPOSITORIES >
$ cd ~/catkin_ws
$ catkin build
```

Include the following lines in your python script before instanciating the python-wrapped C++ class that requires `ros::NodeHandle`:

```cpp
from roscpp_initializer import roscpp_initializer
roscpp_initializer.roscpp_init("NODE_NAME", [])
```

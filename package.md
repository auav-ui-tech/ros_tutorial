# Creating ROS Package
In the [previous tutorial](https://github.com/auav-ui-tech/ros_tutorial/blob/master/workspace.md "Creating ROS Workspace"), we already created ROS Workspace, specially initialized directory so you can run your ROS program inside it. You can't put your source code at random inside ROS Workspace. In fact, you have to create ROS Package first.

You can think of ROS Workspace as, as the name implies, workspace and you can think of ROS Package as your project, as project in "Create New Project" when you use Visual Studio.

The syntax is `catkin_create_pkg package_name dependency1 dependecy2 ... dependencyN` where `package_name` is the name of your package and `dependecy1`, ... , `dependencyN` is your package dependency. This dependency is in fact another ROS Package. ROS has some built-in basic packages when you install it e.g. `roscpp`, `rospy`, `std_msgs`, etc.

Lets create `krti18` package with dependency on `roscpp` and `std_msgs`.
Run this on your terminal
```
cd ~/auav_ui/src
catkin_create_pkg krti18 roscpp std_msgs
```

Now you already created `krti18` package inside `auav_ui` workspace. You should see the hierarchy of your package is as follows
```
krti18
├── CMakeLists.txt
├── include
│   └── krti18
├── package.xml
└── src
```

What makes up ROS Package is the `CMakeLists.txt` and `package.xml` files. You should notice that this `krti18` directory lies inside `~/auav_ui/src/` and there are 2 `CMakeLists.txt`, the one belongs to workspace i.e. `~/auav_ui/src/CMakeLists.txt` and the one belongs to package i.e. `~/auav_ui/src/krti18/CMakeLists.txt`.

Later on, when we want to build our package, we will deal with `CMakeLists.txt` that belongs to package and the `package.xml` file.

For in-depth explanations about creating ROS Package, you can see it [here](http://wiki.ros.org/ROS/Tutorials/CreatingPackage "Creating ROS Package").

In the next tutorial, we will start building simple application of ROS consists of 3 nodes (1 Publisher, 1 Subscriber, and 1 Publisher and Subscriber).

Notes
--
* `roscpp` is ROS Client Library (you can think of it ROS Package, the most fundamental one) for C++. You need to include `roscpp` as your dependency if you're using C++.
* `rospy` is ROS Client Library for Python. In fact, you can use ROS with [other programming languages](http://wiki.ros.org/Client%20Libraries "ROS Client Libraries"), but C++ and Python is the most stable ones.
* `std_msgs` is ROS Package containing Class to handle some fundamentals data type. When your nodes communicate each other in ROS, it doesn't use data types like `bool`, `int`, `float`, `char`, or `std::stirng`, instead it uses Class (Object) like `Int8`, `Int16`, `Float32`, `Bool`, etc to communicate. Those basic Class is included when you include `std_msgs` as your dependencies. (It will be clearer in the next tutorial).
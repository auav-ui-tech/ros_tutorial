# Robot Operating System (ROS)

This tutorial assumes that you already have installed ROS on your local machine. To test your installation, run `roscore` in your terminal.

According to its [official website](www.ros.org/about-ros "About ROS"), ROS is an open-source, meta-operating system for your robot. The Robot Operating System (ROS) is a flexible framework for writing robot software. It is a collection of tools, libraries, and conventions that aim to simplify the task of creating complex and robust robot behavior across a wide variety of robotic platforms.

In my opinion, explanation of ROS on their website is pretty abstract. So, the aim of this tutorial is to guide you to create simple ROS application first. After following this tutorial, hopefully, you get a grasp of what is ROS and then you can go back to their [introcuction website](http://wiki.ros.org/ROS/Introduction "ROS Introduction") and [tutorial website](http://wiki.ros.org/ROS/Tutorials "ROS Tutorial") to advance your understanding.

### Table of Contents

##### ROS Introduction
* [Creating ROS Workspace](https://github.com/auav-ui-tech/ros_tutorial/blob/master/workspace.md "Creating ROS Workspace")
* Creating ROS Package
* Creating ROS Node as Publisher and Subscriber
* Creating ROS Node as Server and Client (ROS Service)

##### ROS Application
* Creating Flight-Mode Changer Node for MultiCopter
* Creating Node to Move MultiCopter
* Creating Class to Handle Multiple Node to Control MultiCopter

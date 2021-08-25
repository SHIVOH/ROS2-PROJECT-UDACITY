# ROS2-PROJECT-UDACITY

This is my project for the final assessment of the C++ Udacity nano Degree. 

In here, i have implemented the main concepts of the ROS such as ROS publishers, subscribers, messages , topics, services, clients and Actions. In reference to the [ROS-2 Official Tutorial](https://docs.ros.org/en/galactic/Tutorials.html)


## Setup

1. Install ROS 2 Galactic on your system via the [official documentation](https://docs.ros.org/en/galactic/Installation.html)
2. Source the ROS 2 environment by entering this command  `source /opt/ros/galactic/setup.bash`
3. Create the workspace <br/>

   `mkdir -p ~/dev_ws/src` <br/>
   `cd ~/dev_ws/src`
4. Clone my packages in the src folder <br/>

   Publishers,subscribers, server, and client package  <br/> -` git clone https://github.com/SHIVOH/ROS2-PROJECT-UDACITY.git` <br/>
   ROS action server and client package   <br/> -`git clone https://github.com/SHIVOH/ROS2-ACTIONS.git`                                             <br/>
   dependency packages <br/>- `git clone https://github.com/SHIVOH/tutorial_interfaces.git`      <br/>
                       - `git clone https://github.com/ros/ros_tutorials.git -b galactic-devel`  <br/>
                       - `git clone https://github.com/SHIVOH/action_tutorials_interfaces.git`   <br/>
5. Reach the root of your workspace
    `cd dev_ws`
6. Build the packages 
    `colcon build`
7. Source the overlay by ` . install/setup.bash `
## Running the ROS nodes
### Publisher node
After calling the 

### Subscriber node

### Server and clients

### Actions in ROS



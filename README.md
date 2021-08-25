# ROS2-PROJECT-UDACITY

This is my project for the final assessment of the C++ Udacity nano Degree. 

In here, i have implemented the main concepts of the ROS 2 such as ROS 2 publishers, subscribers, messages , topics, services, clients and Actions. In reference to the [ROS-2 Official Tutorial](https://docs.ros.org/en/galactic/Tutorials.html)


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
## Running the ROS 2 nodes

### Publisher and Subscriber nodes for ROS 2 message transfer
Publisher node publishes the ROS messages to the ROS topic and then the Subscriber node collects the ROS messages from that topic.
#### Publisher node
Publisher node will publish a message to the ROS topic named "topic".  <br/>

To run the Publisher ros node <br/>
`cd ~/dev_ws`   <br/>
`source /opt/ros/galactic/setup.bash`
`. install/setup.bash ` <br/>
`ros2 run udacity_final_project utalker ` <br/>

#### Subscriber node
Subscriber node will subscribe to the ROS topic named "topic" and get the messages published in the same. <br/>

To run the subscriber ros node <br/>
Open a new terminal, then <br/>
`cd ~/dev_ws`   <br/>
`source /opt/ros/galactic/setup.bash`
`. install/setup.bash ` <br/>
`ros2 run udacity_final_project ulistener ` <br/>



### Server and clients nodes for a ROS 2 service
Services are another method of data transmission in the ROS 2. In here, the client node request a service to the server client and the server process the request and sent the data to the client node.

#### To run the server node 
Open a new terminal, then <br/>
`cd ~/dev_ws`   <br/>
`source /opt/ros/galactic/setup.bash`
`. install/setup.bash ` <br/>
 `ros2 run udacity_final_project userver`
#### To run the client node
Open a new terminal, then <br/>
`cd ~/dev_ws`   <br/>
`source /opt/ros/galactic/setup.bash` <br/>
`. install/setup.bash ` <br/>
 `ros2 run udacity_final_project uclient X Y` <br/>
 In here, the X and Y represent any number that you wish to multiply. <br/>
 eg `ros2 run udacity_final_project uclient 43 89` <br/>
 
 ![Example of execution](https://github.com/SHIVOH/ROS2-PROJECT-UDACITY/blob/main/ROS%20Message.png)

### Actions in ROS 2
Actions are yet another method of communication in ROS 2. In here, an action client request the action server for a goal completion. The Action server 
do the task and return the result to the client. Moreover, it also provide feedback regarding how the task is progressing.






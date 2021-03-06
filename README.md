# ROS2-PROJECT-UDACITY

This is my project for the final assessment of the C++ Udacity nano Degree. 

In here, i have implemented the main concepts of the ROS 2 in C++, such as ROS 2 publishers, subscribers, messages , topics, services, clients and Actions. In reference to the [ROS-2 Official Tutorial](https://docs.ros.org/en/galactic/Tutorials.html)


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

## ROS 2 File structure
```
dev_ws
│   
│      
│
└───src
│   │   
│   │   
│   │
│   └───udacity_final_project
│       │   CMakeLists.txt
│       │   include
│       │   package.xml
│       │   README.md
│       │   src
│       │     └─── multiply_three_ints_client.cpp
│       │          multiply_three_ints_server.cpp
│       │          multiply_two_ints_client.cpp
│       │          multiply_two_ints_server.cpp
│       │          num_publisher_member_function.cpp
│       │          num_subscriber_member_function.cpp
│       │          publisher_member_function.cpp
│       │          subscriber_member_function.cpp
│       │ 
│       action_tutorials_cpp
│       action_tutorials_interfaces
│       ros_tutorials
│       tutorial_interfaces
│        ...
│   
└───build
│    
───install
│  
└───log  
```



## Running the ROS 2 nodes

### Publisher and Subscriber nodes for ROS 2 message transfer
Publisher node publishes the ROS messages to the ROS topic and then the Subscriber node collects the ROS messages from that topic.
#### Publisher node
Publisher node will publish a message to the ROS topic named "topic".  <br/>

To run the Publisher ros node <br/>
`cd ~/dev_ws`   <br/>
`source /opt/ros/galactic/setup.bash`<br/>
`. install/setup.bash ` <br/>
`ros2 run udacity_final_project utalker ` <br/>

#### Subscriber node
Subscriber node will subscribe to the ROS topic named "topic" and get the messages published in the same. <br/>

To run the subscriber ros node <br/>
Open a new terminal, then <br/>
`cd ~/dev_ws`   <br/>
`source /opt/ros/galactic/setup.bash`<br/>
`. install/setup.bash ` <br/>
`ros2 run udacity_final_project ulistener ` <br/>

 ![Example of execution](https://github.com/SHIVOH/ROS2-PROJECT-UDACITY/blob/main/Topic.png)

### Server and clients nodes for a ROS 2 service
Services are another method of data transmission in the ROS 2. In here, the client node request a service to the server client and the server process the request and sent the data to the client node.

#### To run the server node 
Open a new terminal, then <br/>
`cd ~/dev_ws`   <br/>
`source /opt/ros/galactic/setup.bash` <br/>
`. install/setup.bash ` <br/>
##### to compute multiplication of two numbers we give as input.
 `ros2 run udacity_final_project userver`
##### to compute multiplication of three numbers we give as input.
 `ros2 run udacity_final_project numserver`
#### To run the client node
Open a new terminal, then <br/>
`cd ~/dev_ws`   <br/>
`source /opt/ros/galactic/setup.bash` <br/>
`. install/setup.bash ` <br/>
##### to compute multiplication of two numbers we give as input.
 `ros2 run udacity_final_project uclient X Y` <br/>
 In here, the X and Y represent any number that you wish to multiply. <br/>
 eg `ros2 run udacity_final_project uclient 5 6` <br/>
 ##### to compute multiplication of three numbers we give as input.
 `ros2 run udacity_final_project uclient X Y Z` <br/>
 In here, the X and Y represent any number that you wish to multiply. <br/>
 eg `ros2 run udacity_final_project uclient 5 6 9` <br/>
 
 ![Example of execution](https://github.com/SHIVOH/ROS2-PROJECT-UDACITY/blob/main/ROS%20Message.png)
 ![Example of execution](https://github.com/SHIVOH/ROS2-PROJECT-UDACITY/blob/main/numserv.png)
 

### Actions in ROS 2
Actions are yet another method of communication in ROS 2. In here, an action client request the action server for a goal completion. The Action server 
do the task and return the result to the client. Moreover, it also provide feedback regarding how the task is progressing.

#### To run the Action server node 
Open a new terminal, then <br/>
`cd ~/dev_ws`   <br/>
`source /opt/ros/galactic/setup.bash` <br/>
`. install/setup.bash ` <br/>
`ros2 run action_tutorials_cpp fibonacci_action_server` <br/>


#### To run the Action client node
Open a new terminal, then <br/>
`cd ~/dev_ws`   <br/>
`source /opt/ros/galactic/setup.bash` <br/>
`. install/setup.bash ` <br/>
`ros2 run action_tutorials_cpp fibonacci_action_client` <br/>






In this specific example, you are creating an action in which the client sends the goal to the server to print out the specific [here it is 15] number of fibonacci numbers as the output.Each calculation is send as a feedback to the client too.

To change the number, go to the folder `dev_ws/src/action_tutorials_cpp/src` <br/>
then, edit the 47th line of the `fibonacci_action_client.cpp` file <br/>
 `goal_msg.order = 15;`<br/>
Set the goal_msg.order to the required number of fibonacci terms required.

![Example of execution](https://github.com/SHIVOH/ROS2-PROJECT-UDACITY/blob/main/fibonacci.png)


[Reference](https://docs.ros.org/en/galactic/Tutorials.html)

##### For the grading of the project
| Criteria     | Meets Specifications |
| :---        |    :----:   |
| A README with instructions is included with the project     | Completed      | 
| The README indicates which project is chosen.   | Completed       | 
| The README includes information about each rubric point addressed.   | Completed       | 
| The submission must compile and run.   | Tested        | 
| The project demonstrates an understanding of C++ functions and control structures.   | Yes. eg: multiply_two_ints_server.cpp  line 6 to 13     | 
| The project accepts user input and processes the input.   | yes, eg: ros2 run udacity_final_project uclient 5 6  (takes input 5 and 6)      | 
| Classes use appropriate access specifiers for class members.   | yes, eg: num_publisher_member_function.cpp ,line 11 and 20       | 
| Classes follow an appropriate inheritance hierarchy.   | Yes, eg: dev_ws/src/action_tutorials_cpp/src/fibonacci_action_client.cpp,  line 15      | 
| The project uses smart pointers instead of raw pointers.   | yes, eg: dev_ws/src/action_tutorials_cpp/src/fibonacci_action_server.cpp line 35 (shared_ptr)    | 
| The project uses multithreading.  | Yes, dev_ws/src/action_tutorials_cpp/src/fibonacci_action_server.cpp line 57-58      | 

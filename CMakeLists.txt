cmake_minimum_required(VERSION 3.8)
project(udacity_final_project)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

# find dependencies
find_package(ament_cmake REQUIRED)
# uncomment the following section in order to fill in
# further dependencies manually.
# find_package(<dependency> REQUIRED)
find_package(rclcpp REQUIRED)
find_package(std_msgs REQUIRED)
#for the service and client method
find_package(example_interfaces REQUIRED)

#custom messages and services
find_package(tutorial_interfaces REQUIRED)



# add executables so that you can run node using ros2 run

add_executable(utalker src/publisher_member_function.cpp)
ament_target_dependencies(utalker rclcpp std_msgs)

add_executable(ulistener src/subscriber_member_function.cpp)
ament_target_dependencies(ulistener rclcpp std_msgs)

add_executable(uclient src/multiply_two_ints_client.cpp)
ament_target_dependencies(uclient
rclcpp example_interfaces)

add_executable(userver src/multiply_two_ints_server.cpp)
ament_target_dependencies(userver
rclcpp example_interfaces)

# executables for custom messages

add_executable(numtalker src/num_publisher_member_function.cpp)
ament_target_dependencies(numtalker rclcpp tutorial_interfaces)   

add_executable(numlistener src/num_subscriber_member_function.cpp)
ament_target_dependencies(numlistener rclcpp tutorial_interfaces)

# executables for custom services

add_executable(numserver src/multiply_three_ints_server.cpp)
ament_target_dependencies(numserver
  rclcpp tutorial_interfaces)                     

add_executable(numclient src/multiply_three_ints_client.cpp)
ament_target_dependencies(numclient
  rclcpp tutorial_interfaces)   


# Install(TARGETS) for ros2 run to find the executables.

install(TARGETS
  utalker
  ulistener
  userver
  uclient
  numtalker
  numlistener
  numserver
  numclient
  DESTINATION lib/${PROJECT_NAME})

if(BUILD_TESTING)
  find_package(ament_lint_auto REQUIRED)
  # the following line skips the linter which checks for copyrights
  # uncomment the line when a copyright and license is not present in all source files
  #set(ament_cmake_copyright_FOUND TRUE)
  # the following line skips cpplint (only works in a git repo)
  # uncomment the line when this package is not in a git repo
  #set(ament_cmake_cpplint_FOUND TRUE)
  ament_lint_auto_find_test_dependencies()
endif()

ament_package()

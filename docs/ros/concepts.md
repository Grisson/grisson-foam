---
type: knowledge
title: ROS Concepts
tags: #ros #node #topic #service #action #param
keywords: ROS concepts node topic service action param
---

# ROS Concepts

## Basic Concepts

* node
  Each node should be responsible for a single, module purpose 
* topic
  move data between nodes in pub/sub style
* service
  communication between nodes in request/response style
* action
  combination of service and topic
* param


## CLI

* `list`: figure out what is running
  * `ros2 node list`
  * `ros2 topic list -t`
  * `ros2 service list -t`
  * `ros2 action list -t`
  * `ros2 param list`


* `info`: show details
  * `ros2 node info <node_name>`
  * `ros2 topic info <topic_name>`
  * `ros2 service info <service_name>`
  * `ros2 action info <action_name>`
  
* `interface`: figure out the communication details
  * `ros2 interface show <topic_msg_type>`
  * `ros2 interface show <svc_msg_type>`
  * `ros2 interface show <action_type>`
  
* `topic pub`: trigger topic
  * `ros2 topic pub --once/--rate xxx <topic_name> <topic_msg_type> "pay_load"`
  
* `service call`: trigger service
  * `ros2 service call <service_name> <svc_msg_type> "pay_load"`
  
* `action  send_goal`: trigger action
  * `ros2 action send_goal <action_name> <action_msg_type> "pay_load"`
  
* `topic echo`
  * `ros2 topic echo <topic_name>`
  
* `topic hz`
  * `ros2 topic hz <topic_name>`
  
* `param describe`
* `param get`
* `param set`
* `param dump`
* `param load`


## Custom Package

rosdep install -i --from-path src --rosdistro humble -y

sudo rosdep init
rosdep update

colcon build --packages-up-to 
            --symlink-install
            --event-handlers console_direct+


. install/local_setup.sh
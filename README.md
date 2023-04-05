# ros2_ws

This project creates ROS2 publisher and subscriber nodes.

The publisher_node file creates a publisher node that publishes random numbers.

The subscriber_node file creates a subscriber that recieves the random numbers from the publisher.

To run the nodes:
In a terminal window, type
  source install/setup.bash
  ros2 run package subscriber_node
  
In another terminal window, type
  source install/setup.bash
  ros2 run package publisher_node
  
Now the subsrcriber will report the random numbers from the publisher.

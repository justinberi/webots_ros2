# Launch Node and Simulation

The following procedure should be used to compile the package and launch the simulation and node.

```
export WEBOTS_HOME=~/Downloads/webots
source /opt/ros/dashing/setup.bash
colcon build --symlink-install
source install/setup.bash
source install/local_setup.bash
ros2 launch webots_ros2 launcher.launch.py  # ros2 run webots_ros2 example_controller
```

## Test Action Server

The action server can be tested directly using the ROS2 action CLI interface:

```
ros2 action send_goal /follow_joint_trajectory control_msgs/action/FollowJointTrajectory "{
  trajectory: {
    joint_names: [shoulder_pan_jointTODO, shoulder_lift_jointTODO, elbow_jointTODO, wrist_1_jointTODO, wrist_2_jointTODO, wrist_3_jointTODO],
    points: [ { positions: [0.2, 0.2, 0.2, 0.2, 0.2, 0.2], velocities: [0.1, 0.1, 0.1, 0.1, 0.1, 0.1], accelerations: [0.1, 0.1, 0.1, 0.1, 0.1, 0.1] } ]
  }
}"
```

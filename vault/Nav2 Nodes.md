[[ROS2]] [[Nav2]] [[Nav2 Topics]]

List of components derived from
ros2 node info /component

# Nodes
## Navigation
### /bt_navigator
  Subscribers:
    /bond: bond/msg/Status
    /clock: rosgraph_msgs/msg/Clock
    /goal_pose: geometry_msgs/msg/PoseStamped
    /odom: nav_msgs/msg/Odometry
    /parameter_events: rcl_interfaces/msg/ParameterEvent
    /tf: tf2_msgs/msg/TFMessage
    /tf_static: tf2_msgs/msg/TFMessage
  Publishers:
    /bond: bond/msg/Status
    /bt_navigator/transition_event: lifecycle_msgs/msg/TransitionEvent
    /parameter_events: rcl_interfaces/msg/ParameterEvent
    /rosout: rcl_interfaces/msg/Log
  Service Servers:
    /bt_navigator/change_state: lifecycle_msgs/srv/ChangeState
    /bt_navigator/describe_parameters: rcl_interfaces/srv/DescribeParameters
    /bt_navigator/get_available_states: lifecycle_msgs/srv/GetAvailableStates
    /bt_navigator/get_available_transitions: lifecycle_msgs/srv/GetAvailableTransitions
    /bt_navigator/get_parameter_types: rcl_interfaces/srv/GetParameterTypes
    /bt_navigator/get_parameters: rcl_interfaces/srv/GetParameters
    /bt_navigator/get_state: lifecycle_msgs/srv/GetState
    /bt_navigator/get_transition_graph: lifecycle_msgs/srv/GetAvailableTransitions
    /bt_navigator/list_parameters: rcl_interfaces/srv/ListParameters
    /bt_navigator/set_parameters: rcl_interfaces/srv/SetParameters
    /bt_navigator/set_parameters_atomically: rcl_interfaces/srv/SetParametersAtomically
  Service Clients:

  Action Servers:
    /navigate_through_poses: nav2_msgs/action/NavigateThroughPoses
    /navigate_to_pose: nav2_msgs/action/NavigateToPose
  Action Clients:
    /navigate_to_pose: nav2_msgs/action/NavigateToPose

Other nodes:
/bt_navigatornavigate_through_poses_rclcpp_node
/bt_navigatornavigate_to_pose_rclcpp_node

### /controller_server
  Subscribers:
    /bond: bond/msg/Status
    /clock: rosgraph_msgs/msg/Clock
    /odom: nav_msgs/msg/Odometry
    /parameter_events: rcl_interfaces/msg/ParameterEvent
    /speed_limit: nav2_msgs/msg/SpeedLimit
  Publishers:
    /bond: bond/msg/Status
    /cmd_vel: geometry_msgs/msg/Twist
    /controller_server/transition_event: lifecycle_msgs/msg/TransitionEvent
    /cost_cloud: sensor_msgs/msg/PointCloud2
    /evaluation: dwb_msgs/msg/LocalPlanEvaluation
    /local_plan: nav_msgs/msg/Path
    /marker: visualization_msgs/msg/MarkerArray
    /parameter_events: rcl_interfaces/msg/ParameterEvent
    /received_global_plan: nav_msgs/msg/Path
    /rosout: rcl_interfaces/msg/Log
    /transformed_global_plan: nav_msgs/msg/Path
  Service Servers:
    /controller_server/change_state: lifecycle_msgs/srv/ChangeState
    /controller_server/describe_parameters: rcl_interfaces/srv/DescribeParameters
    /controller_server/get_available_states: lifecycle_msgs/srv/GetAvailableStates
    /controller_server/get_available_transitions: lifecycle_msgs/srv/GetAvailableTransitions
    /controller_server/get_parameter_types: rcl_interfaces/srv/GetParameterTypes
    /controller_server/get_parameters: rcl_interfaces/srv/GetParameters
    /controller_server/get_state: lifecycle_msgs/srv/GetState
    /controller_server/get_transition_graph: lifecycle_msgs/srv/GetAvailableTransitions
    /controller_server/list_parameters: rcl_interfaces/srv/ListParameters
    /controller_server/set_parameters: rcl_interfaces/srv/SetParameters
    /controller_server/set_parameters_atomically: rcl_interfaces/srv/SetParametersAtomically
  Service Clients:
    /controller_server/describe_parameters: rcl_interfaces/srv/DescribeParameters
    /controller_server/get_parameter_types: rcl_interfaces/srv/GetParameterTypes
    /controller_server/get_parameters: rcl_interfaces/srv/GetParameters
    /controller_server/list_parameters: rcl_interfaces/srv/ListParameters
    /controller_server/set_parameters: rcl_interfaces/srv/SetParameters
    /controller_server/set_parameters_atomically: rcl_interfaces/srv/SetParametersAtomically
  Action Servers:

  Action Clients:

Other nodes:
/controller_server_rclcpp_node

### /planner_server
  Subscribers:
    /bond: bond/msg/Status
    /clock: rosgraph_msgs/msg/Clock
    /parameter_events: rcl_interfaces/msg/ParameterEvent
  Publishers:
    /bond: bond/msg/Status
    /parameter_events: rcl_interfaces/msg/ParameterEvent
    /plan: nav_msgs/msg/Path
    /planner_server/transition_event: lifecycle_msgs/msg/TransitionEvent
    /rosout: rcl_interfaces/msg/Log
  Service Servers:
    /planner_server/change_state: lifecycle_msgs/srv/ChangeState
    /planner_server/describe_parameters: rcl_interfaces/srv/DescribeParameters
    /planner_server/get_available_states: lifecycle_msgs/srv/GetAvailableStates
    /planner_server/get_available_transitions: lifecycle_msgs/srv/GetAvailableTransitions
    /planner_server/get_parameter_types: rcl_interfaces/srv/GetParameterTypes
    /planner_server/get_parameters: rcl_interfaces/srv/GetParameters
    /planner_server/get_state: lifecycle_msgs/srv/GetState
    /planner_server/get_transition_graph: lifecycle_msgs/srv/GetAvailableTransitions
    /planner_server/list_parameters: rcl_interfaces/srv/ListParameters
    /planner_server/set_parameters: rcl_interfaces/srv/SetParameters
    /planner_server/set_parameters_atomically: rcl_interfaces/srv/SetParametersAtomically
  Service Clients:
    /planner_server/describe_parameters: rcl_interfaces/srv/DescribeParameters
    /planner_server/get_parameter_types: rcl_interfaces/srv/GetParameterTypes
    /planner_server/get_parameters: rcl_interfaces/srv/GetParameters
    /planner_server/list_parameters: rcl_interfaces/srv/ListParameters
    /planner_server/set_parameters: rcl_interfaces/srv/SetParameters
    /planner_server/set_parameters_atomically: rcl_interfaces/srv/SetParametersAtomically
  Action Servers:

  Action Clients:

Other nodes:
/planner_server_rclcpp_node

### /recoveries_server
  Subscribers:
    /bond: bond/msg/Status
    /clock: rosgraph_msgs/msg/Clock
    /local_costmap/costmap_raw: nav2_msgs/msg/Costmap
    /local_costmap/published_footprint: geometry_msgs/msg/PolygonStamped
    /parameter_events: rcl_interfaces/msg/ParameterEvent
  Publishers:
    /bond: bond/msg/Status
    /cmd_vel: geometry_msgs/msg/Twist
    /parameter_events: rcl_interfaces/msg/ParameterEvent
    /recoveries_server/transition_event: lifecycle_msgs/msg/TransitionEvent
    /rosout: rcl_interfaces/msg/Log
  Service Servers:
    /recoveries_server/change_state: lifecycle_msgs/srv/ChangeState
    /recoveries_server/describe_parameters: rcl_interfaces/srv/DescribeParameters
    /recoveries_server/get_available_states: lifecycle_msgs/srv/GetAvailableStates
    /recoveries_server/get_available_transitions: lifecycle_msgs/srv/GetAvailableTransitions
    /recoveries_server/get_parameter_types: rcl_interfaces/srv/GetParameterTypes
    /recoveries_server/get_parameters: rcl_interfaces/srv/GetParameters
    /recoveries_server/get_state: lifecycle_msgs/srv/GetState
    /recoveries_server/get_transition_graph: lifecycle_msgs/srv/GetAvailableTransitions
    /recoveries_server/list_parameters: rcl_interfaces/srv/ListParameters
    /recoveries_server/set_parameters: rcl_interfaces/srv/SetParameters
    /recoveries_server/set_parameters_atomically: rcl_interfaces/srv/SetParametersAtomically
  Service Clients:

  Action Servers:
    /backup: nav2_msgs/action/BackUp
    /spin: nav2_msgs/action/Spin
    /wait: nav2_msgs/action/Wait
  Action Clients:

Other nodes:
/recoveries_server_rclcpp_node

### /waypoint_follower
  Subscribers:
    /bond: bond/msg/Status
    /parameter_events: rcl_interfaces/msg/ParameterEvent
  Publishers:
    /bond: bond/msg/Status
    /parameter_events: rcl_interfaces/msg/ParameterEvent
    /rosout: rcl_interfaces/msg/Log
    /waypoint_follower/transition_event: lifecycle_msgs/msg/TransitionEvent
  Service Servers:
    /waypoint_follower/change_state: lifecycle_msgs/srv/ChangeState
    /waypoint_follower/describe_parameters: rcl_interfaces/srv/DescribeParameters
    /waypoint_follower/get_available_states: lifecycle_msgs/srv/GetAvailableStates
    /waypoint_follower/get_available_transitions: lifecycle_msgs/srv/GetAvailableTransitions
    /waypoint_follower/get_parameter_types: rcl_interfaces/srv/GetParameterTypes
    /waypoint_follower/get_parameters: rcl_interfaces/srv/GetParameters
    /waypoint_follower/get_state: lifecycle_msgs/srv/GetState
    /waypoint_follower/get_transition_graph: lifecycle_msgs/srv/GetAvailableTransitions
    /waypoint_follower/list_parameters: rcl_interfaces/srv/ListParameters
    /waypoint_follower/set_parameters: rcl_interfaces/srv/SetParameters
    /waypoint_follower/set_parameters_atomically: rcl_interfaces/srv/SetParametersAtomically
  Service Clients:

  Action Servers:
    /follow_waypoints: nav2_msgs/action/FollowWaypoints
  Action Clients:
    /navigate_to_pose: nav2_msgs/action/NavigateToPose



## SLAM
[[SLAM Toolbox]]
### /slam_toolbox
  Subscribers:
    /clock: rosgraph_msgs/msg/Clock
    /map: nav_msgs/msg/OccupancyGrid
    /parameter_events: rcl_interfaces/msg/ParameterEvent
    /scan: sensor_msgs/msg/LaserScan
    /slam_toolbox/feedback: visualization_msgs/msg/InteractiveMarkerFeedback
  Publishers:
    /map: nav_msgs/msg/OccupancyGrid
    /map_metadata: nav_msgs/msg/MapMetaData
    /parameter_events: rcl_interfaces/msg/ParameterEvent
    /rosout: rcl_interfaces/msg/Log
    /slam_toolbox/graph_visualization: visualization_msgs/msg/MarkerArray
    /slam_toolbox/scan_visualization: sensor_msgs/msg/LaserScan
    /slam_toolbox/update: visualization_msgs/msg/InteractiveMarkerUpdate
    /tf: tf2_msgs/msg/TFMessage
  Service Servers:
    /slam_toolbox/clear_changes: slam_toolbox/srv/Clear
    /slam_toolbox/clear_queue: slam_toolbox/srv/ClearQueue
    /slam_toolbox/describe_parameters: rcl_interfaces/srv/DescribeParameters
    /slam_toolbox/deserialize_map: slam_toolbox/srv/DeserializePoseGraph
    /slam_toolbox/dynamic_map: nav_msgs/srv/GetMap
    /slam_toolbox/get_interactive_markers: visualization_msgs/srv/GetInteractiveMarkers
    /slam_toolbox/get_parameter_types: rcl_interfaces/srv/GetParameterTypes
    /slam_toolbox/get_parameters: rcl_interfaces/srv/GetParameters
    /slam_toolbox/list_parameters: rcl_interfaces/srv/ListParameters
    /slam_toolbox/manual_loop_closure: slam_toolbox/srv/LoopClosure
    /slam_toolbox/pause_new_measurements: slam_toolbox/srv/Pause
    /slam_toolbox/save_map: slam_toolbox/srv/SaveMap
    /slam_toolbox/serialize_map: slam_toolbox/srv/SerializePoseGraph
    /slam_toolbox/set_parameters: rcl_interfaces/srv/SetParameters
    /slam_toolbox/set_parameters_atomically: rcl_interfaces/srv/SetParametersAtomically
    /slam_toolbox/toggle_interactive_mode: slam_toolbox/srv/ToggleInteractive
  Service Clients:

  Action Servers:

  Action Clients:

### /map_saver
  Subscribers:
    /bond: bond/msg/Status
    /clock: rosgraph_msgs/msg/Clock
    /parameter_events: rcl_interfaces/msg/ParameterEvent
  Publishers:
    /bond: bond/msg/Status
    /map_saver/transition_event: lifecycle_msgs/msg/TransitionEvent
    /parameter_events: rcl_interfaces/msg/ParameterEvent
    /rosout: rcl_interfaces/msg/Log
  Service Servers:
    /map_saver/change_state: lifecycle_msgs/srv/ChangeState
    /map_saver/describe_parameters: rcl_interfaces/srv/DescribeParameters
    /map_saver/get_available_states: lifecycle_msgs/srv/GetAvailableStates
    /map_saver/get_available_transitions: lifecycle_msgs/srv/GetAvailableTransitions
    /map_saver/get_parameter_types: rcl_interfaces/srv/GetParameterTypes
    /map_saver/get_parameters: rcl_interfaces/srv/GetParameters
    /map_saver/get_state: lifecycle_msgs/srv/GetState
    /map_saver/get_transition_graph: lifecycle_msgs/srv/GetAvailableTransitions
    /map_saver/list_parameters: rcl_interfaces/srv/ListParameters
    /map_saver/save_map: nav2_msgs/srv/SaveMap
    /map_saver/set_parameters: rcl_interfaces/srv/SetParameters
    /map_saver/set_parameters_atomically: rcl_interfaces/srv/SetParametersAtomically
  Service Clients:

  Action Servers:

  Action Clients:

## AMCL
### /amcl_pose
  Subscribers:
    /bond: bond/msg/Status
    /clock: rosgraph_msgs/msg/Clock
    /initialpose: geometry_msgs/msg/PoseWithCovarianceStamped
    /map: nav_msgs/msg/OccupancyGrid
    /parameter_events: rcl_interfaces/msg/ParameterEvent
  Publishers:
    /amcl/transition_event: lifecycle_msgs/msg/TransitionEvent
    /amcl_pose: geometry_msgs/msg/PoseWithCovarianceStamped
    /bond: bond/msg/Status
    /parameter_events: rcl_interfaces/msg/ParameterEvent
    /particle_cloud: nav2_msgs/msg/ParticleCloud
    /rosout: rcl_interfaces/msg/Log
  Service Servers:
    /amcl/change_state: lifecycle_msgs/srv/ChangeState
    /amcl/describe_parameters: rcl_interfaces/srv/DescribeParameters
    /amcl/get_available_states: lifecycle_msgs/srv/GetAvailableStates
    /amcl/get_available_transitions: lifecycle_msgs/srv/GetAvailableTransitions
    /amcl/get_parameter_types: rcl_interfaces/srv/GetParameterTypes
    /amcl/get_parameters: rcl_interfaces/srv/GetParameters
    /amcl/get_state: lifecycle_msgs/srv/GetState
    /amcl/get_transition_graph: lifecycle_msgs/srv/GetAvailableTransitions
    /amcl/list_parameters: rcl_interfaces/srv/ListParameters
    /amcl/set_parameters: rcl_interfaces/srv/SetParameters
    /amcl/set_parameters_atomically: rcl_interfaces/srv/SetParametersAtomically
    /reinitialize_global_localization: std_srvs/srv/Empty
    /request_nomotion_update: std_srvs/srv/Empty
  Service Clients:

  Action Servers:

  Action Clients:


## Costmaps
### /global_costmap/global_costmap
  Subscribers:
    /clock: rosgraph_msgs/msg/Clock
    /global_costmap/footprint: geometry_msgs/msg/Polygon
    /map: nav_msgs/msg/OccupancyGrid
    /parameter_events: rcl_interfaces/msg/ParameterEvent
  Publishers:
    /global_costmap/costmap: nav_msgs/msg/OccupancyGrid
    /global_costmap/costmap_raw: nav2_msgs/msg/Costmap
    /global_costmap/costmap_updates: map_msgs/msg/OccupancyGridUpdate
    /global_costmap/global_costmap/transition_event: lifecycle_msgs/msg/TransitionEvent
    /global_costmap/published_footprint: geometry_msgs/msg/PolygonStamped
    /parameter_events: rcl_interfaces/msg/ParameterEvent
    /rosout: rcl_interfaces/msg/Log
  Service Servers:
    /global_costmap/clear_around_global_costmap: nav2_msgs/srv/ClearCostmapAroundRobot
    /global_costmap/clear_entirely_global_costmap: nav2_msgs/srv/ClearEntireCostmap
    /global_costmap/clear_except_global_costmap: nav2_msgs/srv/ClearCostmapExceptRegion
    /global_costmap/get_costmap: nav2_msgs/srv/GetCostmap
    /global_costmap/global_costmap/change_state: lifecycle_msgs/srv/ChangeState
    /global_costmap/global_costmap/describe_parameters: rcl_interfaces/srv/DescribeParameters
    /global_costmap/global_costmap/get_available_states: lifecycle_msgs/srv/GetAvailableStates
    /global_costmap/global_costmap/get_available_transitions: lifecycle_msgs/srv/GetAvailableTransitions
    /global_costmap/global_costmap/get_parameter_types: rcl_interfaces/srv/GetParameterTypes
    /global_costmap/global_costmap/get_parameters: rcl_interfaces/srv/GetParameters
    /global_costmap/global_costmap/get_state: lifecycle_msgs/srv/GetState
    /global_costmap/global_costmap/get_transition_graph: lifecycle_msgs/srv/GetAvailableTransitions
    /global_costmap/global_costmap/list_parameters: rcl_interfaces/srv/ListParameters
    /global_costmap/global_costmap/set_parameters: rcl_interfaces/srv/SetParameters
    /global_costmap/global_costmap/set_parameters_atomically: rcl_interfaces/srv/SetParametersAtomically
  Service Clients:

  Action Servers:

  Action Clients:

Other nodes:
/global_costmap/global_costmap_rclcpp_node
/global_costmap_client

### /local_costmap/local_costmap
  Subscribers:
    /clock: rosgraph_msgs/msg/Clock
    /local_costmap/footprint: geometry_msgs/msg/Polygon
    /parameter_events: rcl_interfaces/msg/ParameterEvent
  Publishers:
    /local_costmap/clearing_endpoints: sensor_msgs/msg/PointCloud2
    /local_costmap/costmap: nav_msgs/msg/OccupancyGrid
    /local_costmap/costmap_raw: nav2_msgs/msg/Costmap
    /local_costmap/costmap_updates: map_msgs/msg/OccupancyGridUpdate
    /local_costmap/local_costmap/transition_event: lifecycle_msgs/msg/TransitionEvent
    /local_costmap/published_footprint: geometry_msgs/msg/PolygonStamped
    /local_costmap/voxel_grid: nav2_msgs/msg/VoxelGrid
    /parameter_events: rcl_interfaces/msg/ParameterEvent
    /rosout: rcl_interfaces/msg/Log
  Service Servers:
    /local_costmap/clear_around_local_costmap: nav2_msgs/srv/ClearCostmapAroundRobot
    /local_costmap/clear_entirely_local_costmap: nav2_msgs/srv/ClearEntireCostmap
    /local_costmap/clear_except_local_costmap: nav2_msgs/srv/ClearCostmapExceptRegion
    /local_costmap/get_costmap: nav2_msgs/srv/GetCostmap
    /local_costmap/local_costmap/change_state: lifecycle_msgs/srv/ChangeState
    /local_costmap/local_costmap/describe_parameters: rcl_interfaces/srv/DescribeParameters
    /local_costmap/local_costmap/get_available_states: lifecycle_msgs/srv/GetAvailableStates
    /local_costmap/local_costmap/get_available_transitions: lifecycle_msgs/srv/GetAvailableTransitions
    /local_costmap/local_costmap/get_parameter_types: rcl_interfaces/srv/GetParameterTypes
    /local_costmap/local_costmap/get_parameters: rcl_interfaces/srv/GetParameters
    /local_costmap/local_costmap/get_state: lifecycle_msgs/srv/GetState
    /local_costmap/local_costmap/get_transition_graph: lifecycle_msgs/srv/GetAvailableTransitions
    /local_costmap/local_costmap/list_parameters: rcl_interfaces/srv/ListParameters
    /local_costmap/local_costmap/set_parameters: rcl_interfaces/srv/SetParameters
    /local_costmap/local_costmap/set_parameters_atomically: rcl_interfaces/srv/SetParametersAtomically
  Service Clients:

  Action Servers:

  Action Clients:

Other nodes:
/local_costmap/local_costmap_rclcpp_node
/local_costmap_client



## State
### /robot_state_publisher
  Subscribers:
    /clock: rosgraph_msgs/msg/Clock
    /joint_states: sensor_msgs/msg/JointState
    /parameter_events: rcl_interfaces/msg/ParameterEvent
  Publishers:
    /parameter_events: rcl_interfaces/msg/ParameterEvent
    /robot_description: std_msgs/msg/String
    /rosout: rcl_interfaces/msg/Log
    /tf: tf2_msgs/msg/TFMessage
    /tf_static: tf2_msgs/msg/TFMessage
  Service Servers:
    /robot_state_publisher/describe_parameters: rcl_interfaces/srv/DescribeParameters
    /robot_state_publisher/get_parameter_types: rcl_interfaces/srv/GetParameterTypes
    /robot_state_publisher/get_parameters: rcl_interfaces/srv/GetParameters
    /robot_state_publisher/list_parameters: rcl_interfaces/srv/ListParameters
    /robot_state_publisher/set_parameters: rcl_interfaces/srv/SetParameters
    /robot_state_publisher/set_parameters_atomically: rcl_interfaces/srv/SetParametersAtomically
  Service Clients:

  Action Servers:

  Action Clients:


### /transform_listener
/transform_listener_impl_558955707180
/transform_listener_impl_55ff532b9a10
/transform_listener_impl_5653e472abd0
/transform_listener_impl_7f378c0141b0
/transform_listener_impl_7fd454001d60





## Sensors
### /turtlebot3
/turtlebot3_diff_drive
/turtlebot3_imu
/turtlebot3_joint_state
/turtlebot3_laserscan

### /intel_realsense_r200_depth_driver
  Subscribers:
    /clock: rosgraph_msgs/msg/Clock
    /parameter_events: rcl_interfaces/msg/ParameterEvent
  Publishers:
    /intel_realsense_r200_depth/camera_info: sensor_msgs/msg/CameraInfo
    /intel_realsense_r200_depth/depth/camera_info: sensor_msgs/msg/CameraInfo
    /intel_realsense_r200_depth/depth/image_raw: sensor_msgs/msg/Image
    /intel_realsense_r200_depth/image_raw: sensor_msgs/msg/Image
    /intel_realsense_r200_depth/points: sensor_msgs/msg/PointCloud2
    /parameter_events: rcl_interfaces/msg/ParameterEvent
    /rosout: rcl_interfaces/msg/Log
  Service Servers:
    /intel_realsense_r200_depth_driver/describe_parameters: rcl_interfaces/srv/DescribeParameters
    /intel_realsense_r200_depth_driver/get_parameter_types: rcl_interfaces/srv/GetParameterTypes
    /intel_realsense_r200_depth_driver/get_parameters: rcl_interfaces/srv/GetParameters
    /intel_realsense_r200_depth_driver/list_parameters: rcl_interfaces/srv/ListParameters
    /intel_realsense_r200_depth_driver/set_parameters: rcl_interfaces/srv/SetParameters
    /intel_realsense_r200_depth_driver/set_parameters_atomically: rcl_interfaces/srv/SetParametersAtomically
    /set_camera_info: sensor_msgs/srv/SetCameraInfo
  Service Clients:

  Action Servers:

  Action Clients:
  


## Utils
### /gazebo
  Subscribers:
    /clock: rosgraph_msgs/msg/Clock
    /parameter_events: rcl_interfaces/msg/ParameterEvent
  Publishers:
    /clock: rosgraph_msgs/msg/Clock
    /parameter_events: rcl_interfaces/msg/ParameterEvent
    /performance_metrics: gazebo_msgs/msg/PerformanceMetrics
    /rosout: rcl_interfaces/msg/Log
  Service Servers:
    /delete_entity: gazebo_msgs/srv/DeleteEntity
    /gazebo/describe_parameters: rcl_interfaces/srv/DescribeParameters
    /gazebo/get_parameter_types: rcl_interfaces/srv/GetParameterTypes
    /gazebo/get_parameters: rcl_interfaces/srv/GetParameters
    /gazebo/list_parameters: rcl_interfaces/srv/ListParameters
    /gazebo/set_parameters: rcl_interfaces/srv/SetParameters
    /gazebo/set_parameters_atomically: rcl_interfaces/srv/SetParametersAtomically
    /get_model_list: gazebo_msgs/srv/GetModelList
    /pause_physics: std_srvs/srv/Empty
    /reset_simulation: std_srvs/srv/Empty
    /reset_world: std_srvs/srv/Empty
    /spawn_entity: gazebo_msgs/srv/SpawnEntity
    /unpause_physics: std_srvs/srv/Empty
  Service Clients:

  Action Servers:

  Action Clients:

### /rviz
  Subscribers:
    /downsampled_costmap: nav_msgs/msg/OccupancyGrid
    /downsampled_costmap_updates: map_msgs/msg/OccupancyGridUpdate
    /global_costmap/costmap: nav_msgs/msg/OccupancyGrid
    /global_costmap/costmap_updates: map_msgs/msg/OccupancyGridUpdate
    /global_costmap/voxel_marked_cloud: sensor_msgs/msg/PointCloud2
    /local_costmap/costmap: nav_msgs/msg/OccupancyGrid
    /local_costmap/costmap_updates: map_msgs/msg/OccupancyGridUpdate
    /local_costmap/published_footprint: geometry_msgs/msg/PolygonStamped
    /local_costmap/voxel_marked_cloud: sensor_msgs/msg/PointCloud2
    /local_plan: nav_msgs/msg/Path
    /map: nav_msgs/msg/OccupancyGrid
    /map_updates: map_msgs/msg/OccupancyGridUpdate
    /mobile_base/sensors/bumper_pointcloud: sensor_msgs/msg/PointCloud2
    /parameter_events: rcl_interfaces/msg/ParameterEvent
    /particle_cloud: nav2_msgs/msg/ParticleCloud
    /plan: nav_msgs/msg/Path
    /scan: sensor_msgs/msg/LaserScan
    /waypoints: visualization_msgs/msg/MarkerArray
  Publishers:
    /clicked_point: geometry_msgs/msg/PointStamped
    /initialpose: geometry_msgs/msg/PoseWithCovarianceStamped
    /parameter_events: rcl_interfaces/msg/ParameterEvent
    /rosout: rcl_interfaces/msg/Log
  Service Servers:
    /rviz/describe_parameters: rcl_interfaces/srv/DescribeParameters
    /rviz/get_parameter_types: rcl_interfaces/srv/GetParameterTypes
    /rviz/get_parameters: rcl_interfaces/srv/GetParameters
    /rviz/list_parameters: rcl_interfaces/srv/ListParameters
    /rviz/set_parameters: rcl_interfaces/srv/SetParameters
    /rviz/set_parameters_atomically: rcl_interfaces/srv/SetParametersAtomically
  Service Clients:

  Action Servers:

  Action Clients:
    /navigate_through_poses: nav2_msgs/action/NavigateThroughPoses
    /navigate_to_pose: nav2_msgs/action/NavigateToPose

### /lifecycle_manager_slam
/lifecycle_manager_localization_service_client
/lifecycle_manager_navigation
/lifecycle_manager_navigation_service_client


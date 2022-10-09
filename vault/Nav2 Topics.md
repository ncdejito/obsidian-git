[[ROS2]] [[Nav2]] [[Nav2 Nodes]]

Show message format for each topic
```
ros2 topic info /topic
ros2 interface show geometry_msgs/msg/Twist
```

# Topics

## Main
### /map
nav_msgs/msg/OccupancyGrid
```
# This represents a 2-D grid map
std_msgs/Header header
        builtin_interfaces/Time stamp
                int32 sec
                uint32 nanosec
        string frame_id

# MetaData for the map
MapMetaData info
        builtin_interfaces/Time map_load_time
                int32 sec
                uint32 nanosec
        float32 resolution
        uint32 width
        uint32 height
        geometry_msgs/Pose origin
                Point position
                        float64 x
                        float64 y
                        float64 z
                Quaternion orientation
                        float64 x 0
                        float64 y 0
                        float64 z 0
                        float64 w 1

# The map data, in row-major order, starting with (0,0).
# Cell (1, 0) will be listed second, representing the next cell in the x direction.
# Cell (0, 1) will be at the index equal to info.width, followed by (1, 1).
# The values inside are application dependent, but frequently,
# 0 represents unoccupied, 1 represents definitely occupied, and
# -1 represents unknown.
int8[] data
```

### /odom
nav_msgs/msg/Odometry
```
# This represents an estimate of a position and velocity in free space.
# The pose in this message should be specified in the coordinate frame given by header.frame_id
# The twist in this message should be specified in the coordinate frame given by the child_frame_id

# Includes the frame id of the pose parent.
std_msgs/Header header
        builtin_interfaces/Time stamp
                int32 sec
                uint32 nanosec
        string frame_id

# Frame id the pose points to. The twist is in this coordinate frame.
string child_frame_id

# Estimated pose that is typically relative to a fixed world frame.
geometry_msgs/PoseWithCovariance pose
        Pose pose
                Point position
                        float64 x
                        float64 y
                        float64 z
                Quaternion orientation
                        float64 x 0
                        float64 y 0
                        float64 z 0
                        float64 w 1
        float64[36] covariance

# Estimated linear and angular velocity relative to child_frame_id.
geometry_msgs/TwistWithCovariance twist
        Twist twist
                Vector3  linear
                        float64 x
                        float64 y
                        float64 z
                Vector3  angular
                        float64 x
                        float64 y
                        float64 z
        float64[36] covariance
```

### /scan
sensor_msgs/msg/LaserScan
```
# Single scan from a planar laser range-finder
#
# If you have another ranging device with different behavior (e.g. a sonar
# array), please find or create a different message, since applications
# will make fairly laser-specific assumptions about this data

std_msgs/Header header # timestamp in the header is the acquisition time of
        builtin_interfaces/Time stamp
                int32 sec
                uint32 nanosec
        string frame_id
                             # the first ray in the scan.
                             #
                             # in frame frame_id, angles are measured around
                             # the positive Z axis (counterclockwise, if Z is up)
                             # with zero angle being forward along the x axis

float32 angle_min            # start angle of the scan [rad]
float32 angle_max            # end angle of the scan [rad]
float32 angle_increment      # angular distance between measurements [rad]

float32 time_increment       # time between measurements [seconds] - if your scanner
                             # is moving, this will be used in interpolating position
                             # of 3d points
float32 scan_time            # time between scans [seconds]

float32 range_min            # minimum range value [m]
float32 range_max            # maximum range value [m]

float32[] ranges             # range data [m]
                             # (Note: values < range_min or > range_max should be discarded)
float32[] intensities        # intensity data [device-specific units].  If your
                             # device does not provide intensities, please leave
                             # the array empty.
```

## Inputs
### /cmd_vel
geometry_msgs/msg/Twist
```
# This expresses velocity in free space broken into its linear and angular parts.

Vector3  linear
        float64 x
        float64 y
        float64 z
Vector3  angular
        float64 x
        float64 y
        float64 z
```

### /speed_limit
nav2_msgs/msg/SpeedLimit
```
std_msgs/Header header
        builtin_interfaces/Time stamp
                int32 sec
                uint32 nanosec
        string frame_id
# Setting speed limit in percentage if true or in absolute values in false case
bool percentage
# Maximum allowed speed (in percent of maximum robot speed or in m/s depending
# on "percentage" value). When no-limit it is set to 0.0
float64 speed_limit
```

### /initialpose
geometry_msgs/msg/PoseWithCovarianceStamped
```
# This expresses an estimated pose with a reference coordinate frame and timestamp

std_msgs/Header header
        builtin_interfaces/Time stamp
                int32 sec
                uint32 nanosec
        string frame_id
PoseWithCovariance pose
        Pose pose
                Point position
                        float64 x
                        float64 y
                        float64 z
                Quaternion orientation
                        float64 x 0
                        float64 y 0
                        float64 z 0
                        float64 w 1
        float64[36] covariance
```

### /goal_pose
geometry_msgs/msg/PoseStamped
```
# A Pose with reference coordinate frame and timestamp

std_msgs/Header header
        builtin_interfaces/Time stamp
                int32 sec
                uint32 nanosec
        string frame_id
Pose pose
        Point position
                float64 x
                float64 y
                float64 z
        Quaternion orientation
                float64 x 0
                float64 y 0
                float64 z 0
                float64 w 1
```

## Under the Hood

### /plan
nav_msgs/msg/Path
```
root@nexus-0:/# ros2 interface show nav_msgs/msg/Path
# An array of poses that represents a Path for a robot to follow.

# Indicates the frame_id of the path.
std_msgs/Header header
        builtin_interfaces/Time stamp
                int32 sec
                uint32 nanosec
        string frame_id

# Array of poses to follow.
geometry_msgs/PoseStamped[] poses
        std_msgs/Header header
                builtin_interfaces/Time stamp
                        int32 sec
                        uint32 nanosec
                string frame_id
        Pose pose
                Point position
                        float64 x
                        float64 y
                        float64 z
                Quaternion orientation
                        float64 x 0
                        float64 y 0
                        float64 z 0
                        float64 w 1
```

### /amcl_pose
geometry_msgs/msg/PoseWithCovarianceStamped
```
# This expresses an estimated pose with a reference coordinate frame and timestamp

std_msgs/Header header
        builtin_interfaces/Time stamp
                int32 sec
                uint32 nanosec
        string frame_id
PoseWithCovariance pose
        Pose pose
                Point position
                        float64 x
                        float64 y
                        float64 z
                Quaternion orientation
                        float64 x 0
                        float64 y 0
                        float64 z 0
                        float64 w 1
        float64[36] covariance
```

### /local_costmap/costmap
nav_msgs/msg/OccupancyGrid
```
# This represents a 2-D grid map
std_msgs/Header header
        builtin_interfaces/Time stamp
                int32 sec
                uint32 nanosec
        string frame_id

# MetaData for the map
MapMetaData info
        builtin_interfaces/Time map_load_time
                int32 sec
                uint32 nanosec
        float32 resolution
        uint32 width
        uint32 height
        geometry_msgs/Pose origin
                Point position
                        float64 x
                        float64 y
                        float64 z
                Quaternion orientation
                        float64 x 0
                        float64 y 0
                        float64 z 0
                        float64 w 1

# The map data, in row-major order, starting with (0,0).
# Cell (1, 0) will be listed second, representing the next cell in the x direction.
# Cell (0, 1) will be at the index equal to info.width, followed by (1, 1).
# The values inside are application dependent, but frequently,
# 0 represents unoccupied, 1 represents definitely occupied, and
# -1 represents unknown.
int8[] data
```

### /local_costmap/costmap_raw
nav2_msgs/msg/Costmap
```
# This represents a 2-D grid map, in which each cell has an associated cost

std_msgs/Header header
        builtin_interfaces/Time stamp
                int32 sec
                uint32 nanosec
        string frame_id

# MetaData for the map
CostmapMetaData metadata
        builtin_interfaces/Time map_load_time
                int32 sec
                uint32 nanosec
        builtin_interfaces/Time update_time
                int32 sec
                uint32 nanosec
        string layer
        float32 resolution
        uint32 size_x
        uint32 size_y
        geometry_msgs/Pose origin
                Point position
                        float64 x
                        float64 y
                        float64 z
                Quaternion orientation
                        float64 x 0
                        float64 y 0
                        float64 z 0
                        float64 w 1

# The cost data, in row-major order, starting with (0,0).
uint8[] data
```


## Others
/behavior_tree_log
/bt_navigator/transition_event

/bond
/clock


/clicked_point


/controller_server/transition_event


/planner_server/transition_event
/local_plan
/received_global_plan
/transformed_global_plan

/recoveries_server/transition_event

/waypoints
/waypoint_follower/transition_event

/slam_toolbox/feedback
/slam_toolbox/graph_visualization
/slam_toolbox/scan_visualization
/slam_toolbox/update

/cost_cloud
/downsampled_costmap
/downsampled_costmap_updates
/global_costmap/costmap
/global_costmap/costmap_raw
/global_costmap/costmap_updates
/global_costmap/footprint
/global_costmap/global_costmap/transition_event
/global_costmap/published_footprint
/global_costmap/voxel_marked_cloud

/local_costmap/clearing_endpoints


/local_costmap/costmap_updates
/local_costmap/footprint
/local_costmap/local_costmap/transition_event
/local_costmap/published_footprint
/local_costmap/voxel_grid
/local_costmap/voxel_marked_cloud

/imu
/intel_realsense_r200_depth/camera_info
/intel_realsense_r200_depth/depth/camera_info
/intel_realsense_r200_depth/depth/image_raw
/intel_realsense_r200_depth/image_raw
/intel_realsense_r200_depth/points
/mobile_base/sensors/bumper_pointcloud

/joint_states
/tf
/tf_static



/map_metadata
/map_saver/transition_event
/map_updates



/parameter_events
/particle_cloud
/evaluation
/performance_metrics
/robot_description
/rosout
/marker


/amcl/transition_event



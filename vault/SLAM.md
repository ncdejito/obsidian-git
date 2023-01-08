[[Robotics Theory]]

## Theory
[Principles of Robot Autonomy](https://stanfordasl.github.io//aa274a/)
Low cost 3D [conference](https://lc3d.fbk.eu/)
[Robotics Knowledge Base](https://roboticsknowledgebase.com/wiki/sensing/pcl/#3d-slam)

Ces  
Lowcost3d  
Rose2022 robot swe

## Tools
3D Mapping by rsasaki [blog](https://medium.com/@rsasaki0109/3d-mapping-with-graph-slam-using-3d-lidar-in-ros2-12ea7140e548)
[DCPCR](https://www.linkedin.com/posts/cyrill-stachniss-736233173_talk-by-l-wiesmann-dcpcr-deep-compressed-activity-6977007398657921024-FWDE) - Register point clouds with 1% of compute needed (allows more efficient 3d mapping in mobile robots)

ROS1 algos
[ndt-map](http://wiki.ros.org/ndt_map)
[loam-velodyne](http://wiki.ros.org/loam_velodyne)

[VSLAM by Macenski](https://arxiv.org/pdf/2107.07589.pdf)
[AstroSLAM](https://techxplore-com.cdn.ampproject.org/c/s/techxplore.com/news/2022-12-enable-autonomous-spacecraft-deep-space-missions.amp)
[Cheatsheet for VisualSLAM](https://www.linkedin.com/posts/terrywu777_vslam-computervision-imageprocessing-activity-7002272675603619840-j9eL?utm_source=share&utm_medium=member_desktop)
[Acoustic SLAM](https://towardsdatascience.com/acoustic-slam-state-of-the-art-review-3e5f45aeb345)

camera models, multi-view geometry, and structure-from motion
UKF, EKF, Factor Graphs
ROVIO, VINS-MONO, SVO, DSO, or DTAM
visual odometry, bundle adjustment, place recognition / loop detection algorithms

SLAM Toolbox in [[Nav2]]
Modes
- Offline - Mapping is done without realtime data, for instamnce using bag files
- Synchronous - It makes sure if processes all the incoming laser measurements. It can lag over time.
- Asynchronous - It processes incoming laser measurements in real time
- Lifelong - It allows to build a map partially over time. For instance, get a 1st version of a map and update it.

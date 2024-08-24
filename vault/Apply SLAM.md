#job 

Simultaneous [[Localization]] and [[Mapping]]

Concern
Solves chicken and egg problem of map availability vs no movement history

Feb 4, Bayesian Thinking
Feb 11, Working with Matrices
Feb 18, C++ Basics
Feb 25, Performance Programming in C++
Mar 4, Navigating Complex Data Structures
Mar 11, Visualizing Calculus and Controls
Mar 18, Machine Learning and Computer Vision

Jan 17, Bayesian Thinking
Jan 19, ROS Essentials
Jan 21, Localization
Jan 23, Mapping and SLAM
Jan 26, Path Planning and Navigation

[[Occupancy grid]]


## Theory

Low cost 3D [conference](https://lc3d.fbk.eu/)
[Robotics Knowledge Base](https://roboticsknowledgebase.com/wiki/sensing/pcl/#3d-slam)

SLAM roadmap
https://github.com/changh95/visual-slam-roadmap
[Cheatsheet for vslam](https://www.linkedin.com/posts/terrywu777_vslam-computervision-imageprocessing-activity-7002272675603619840-j9eL?utm_source=share&utm_medium=member_desktop)
Visual odometry and slam survey 
[https://github.com/klintan/vo-survey](https://github.com/klintan/vo-survey)
[VSLAM by Macenski](https://arxiv.org/pdf/2107.07589.pdf) 
https://www.linkedin.com/posts/dharun-kumar20_pythonprogramming-robotics-mobilerobots-activity-7151294203119996928-asDK?utm_source=share&utm_medium=member_desktop
Vslam by ieee will be full by 2025
https://www.ieee-ras.org/publications/t-ro/special-issues/visual-slam

Basic SLAM camera concepts
https://www.kudan.io/blog/camera-basics-visual-slam/

[Code for SLAM](https://www.linkedin.com/posts/hyunggi-chang_slam-visualslam-lidarslam-ugcPost-7138388598411730945-ZL9G?utm_source=share&utm_medium=member_android)
ROS1 algos
[ndt-map](http://wiki.ros.org/ndt_map)
[loam-velodyne](http://wiki.ros.org/loam_velodyne)

Ces  
Lowcost3d  
https://lc3d.fbk.eu/
Rose2022 robot swe - 2023 has behaviordriven stuff!

## Tools
3D Mapping by rsasaki [blog](https://medium.com/@rsasaki0109/3d-mapping-with-graph-slam-using-3d-lidar-in-ros2-12ea7140e548)
Realtime semantic mapping
https://jingwenwang95.github.io/SeMLaPS/

[Cheatsheet for VisualSLAM](https://www.linkedin.com/posts/terrywu777_vslam-computervision-imageprocessing-activity-7002272675603619840-j9eL?utm_source=share&utm_medium=member_desktop) 
[Acoustic SLAM](https://towardsdatascience.com/acoustic-slam-state-of-the-art-review-3e5f45aeb345)
[Multi-robot semantic VSLAM](https://www.linkedin.com/posts/open-source-robotics-foundation_resilient-and-distributed-multi-robot-visual-activity-7059397960140283904-twJ0?utm_source=share&utm_medium=member_desktop)
[SLAM with LLMs](https://www.linkedin.com/posts/chenguang-huang-53b287254_can-a-robot-navigate-to-the-sound-theyve-ugcPost-7042145643150110720-KZtR?utm_source=share&utm_medium=member_desktop) "move in between the chair and the couch"
[Roadmap for tesla to become deep learning](https://www.linkedin.com/posts/jeremycohen2626_breakdown-how-tesla-will-transition-from-activity-7108411108306100224-ZP1C?utm_source=share&utm_medium=member_android)
[AstroSLAM](https://techxplore-com.cdn.ampproject.org/c/s/techxplore.com/news/2022-12-enable-autonomous-spacecraft-deep-space-missions.amp)
[Space slam algorithms](https://uk.artechhouse.com/mobile/Navigation-and-Tracking-in-Space-Analysis-and-Algorithms-P2215.aspx)

Lessons from darpa slam
https://www.linkedin.com/posts/kostas-alexis-67713918_present-and-future-of-slam-in-extreme-environments-activity-7120481474268545024-2Fik?utm_source=share&utm_medium=member_android

Monocular realtime navigation
https://arxiv.org/abs/2307.00666


camera models, multi-view geometry, and structure-from motion
UKF, EKF, Factor Graphs
ROVIO, VINS-MONO, SVO, DSO, or DTAM
visual odometry, bundle adjustment, place recognition / loop detection algorithms

SLAM Toolbox in [[Use Nav2]]
Modes
- Offline - Mapping is done without realtime data, for instance using bag files
- Synchronous - It makes sure if processes all the incoming laser measurements. It can lag over time.
- Asynchronous - It processes incoming laser measurements in real time
- Lifelong - It allows to build a map partially over time. For instance, get a 1st version of a map and update it.

Logistics robots: Grid markers for autonomous navigation  
[https://medium.com/black-coffee-robotics/localization-for-warehouse-autonomous-robots-e89a29a5f936](https://medium.com/black-coffee-robotics/localization-for-warehouse-autonomous-robots-e89a29a5f936)

[Different Nature-Inspired Techniques Applied for Motion Planning of Wheeled Robot: A Critical Review](https://www.researchgate.net/profile/Dr-Anish-Pandey-2/publication/326671343_Different_Nature-Inspired_Techniques_Applied_for_Motion_Planning_of_Wheeled_Robot_A_Critical_Review/links/5b5c81460f7e9bc79a6c3963/Different-Nature-Inspired-Techniques-Applied-for-Motion-Planning-of-Wheeled-Robot-A-Critical-Review.pdf)

Tools
[ImMesh](https://github.com/hku-mars/ImMesh) - An Immediate LiDAR Localization and Meshing Framework
Nerf2mesh

Introduction to vslam book  
[https://www.linkedin.com/posts/zenorobotics_this-is-a-very-comprehensive-book-on-visual-activity-7171033894929022976-p_Rh?utm_source=share&utm_medium=member_android](https://www.linkedin.com/posts/zenorobotics_this-is-a-very-comprehensive-book-on-visual-activity-7171033894929022976-p_Rh?utm_source=share&utm_medium=member_android)  


Tools
* [[Use Nav2]]

Small project ideas
https://www.linkedin.com/posts/activity-7183363150484799488-MEzF?utm_source=share&utm_medium=member_android
Fix github issues on ros-planning/navigation2, tag=goodfirstissue
Juan: If you want to implement slam algorithms I advised to use kiss-ICP and lio-sam are "the easiest" and the best way to start 

References
[Intro to Self Driving Cars](https://www.udacity.com/course/intro-to-self-driving-cars--nd113) - 4mo, has C++ basics, performance programming, data structures
[Self Driving Car Engineer](https://www.udacity.com/course/self-driving-car-engineer-nanodegree--nd0013) - 5mo, 3D object detection, sensor fusion, scan matching/registration PCL, planning
##### Links
   [Nerf-slam](https://ar5iv.labs.arxiv.org/html/2210.01276)
   [Nerf](https://ar5iv.labs.arxiv.org/html/2003.08934)  
   [Vslam](https://ar5iv.labs.arxiv.org/html/2107.07589) macenski
   [Orbslamv3](https://ar5iv.org/abs/2007.11898)  
   [Graph based slam](https://journals.sagepub.com/doi/10.1177/0278364906065387)  
   [Grid based fastslam](https://scholar.google.com/scholar?q=grid+based+fastslam)
   [Vslam infographic terms](https://media.licdn.com/dms/image/C4E22AQFmqdqF_rW5yQ/feedshare-shrink_2048_1536/0/1669471900992?e=1677715200&v=beta&t=RM_Y-FW6yqJeYJ4vYq-diDu7f0onJvFpYj_sQbXJnqM)  
   [Dcpcr](https://www.ipb.uni-bonn.de/wp-content/papercite-data/pdf/wiesmann2022ral-iros.pdf)
    

Probabilistic approaches sebastian thrun

##### Papers

[A Comparison of Modern General-Purpose Visual SLAM Approaches](https://ar5iv.org/abs/2107.07589)

[NeRF-SLAM: Real-Time Dense Monocular SLAM with Neural Radiance Fields](https://ar5iv.labs.arxiv.org/html/2210.13641)

Summary

- Real-time depth maps using monocular images
    

Datasets

Methodology

- Neural Radiance Fields?
    

Results

- PSNR (peak signal to noise ratio) - higher is better, means more signal; what’s a signal?
    

Notes

  

##### Updates

0217

Vio leaderboard
[https://www.linkedin.com/posts/davidescaramuzza_slam-vio-ugcPost-7162160631373148160-xuZD?utm_source=share&utm_medium=member_android](https://www.linkedin.com/posts/davidescaramuzza_slam-vio-ugcPost-7162160631373148160-xuZD?utm_source=share&utm_medium=member_android)

Read Ch1 Modern Robotics: Mechanics, Planning, and Control by Kevin M. Lynch

For AMRs: Introduction to Autonomous Mobile Robots (Intelligent Robotics and Autonomous Agents series) by Roland Siegwart

[Principles of Robot Autonomy](https://stanfordasl.github.io//aa274a/)

[Lecture 3 Trajectory Optimization](https://stanfordasl.github.io/aa274a/pdfs/lecture/lecture_3.pdf)

Stuck on Pre-knowledge assessment second order ODER solution https://stanfordasl.github.io/aa274a/pdfs/pre_knowledge_assessment.pdf


Implementations
Implement 3d slam using c++
https://github.com/IntelRealSense/realsense-ros/wiki/SLAM-with-D435i

RTAB-Map

ORB-SLAM3

PythonRobotics - simplified gifs
NeuralRecon

D3VO
barn - https://github.com/Daffan/nav-competition-icra2022

hilti - https://github.com/Hilti-Research/Hilti-SLAM-Challenge-2022


Stereo Depth Raspberry Pi Camera: C++ is faster than Python [https://stereopi.com/blog/opencv-comparing-speed-c-and-python-code-raspberry-pi-stereo-vision](https://stereopi.com/blog/opencv-comparing-speed-c-and-python-code-raspberry-pi-stereo-vision)


monocular depth estimation?

- MiDAS android model - [https://github.com/isl-org/MiDaS/tree/master/mobile/android](https://github.com/isl-org/MiDaS/tree/master/mobile/android)

- Tsukuba Challenge outdoor navigation competition in Japan - [https://github.com/tsukubachallenge/tc-datasets](https://github.com/tsukubachallenge/tc-datasets)
    
- Use semantic segmentation/teacher-student network to learn sidewalk - [https://arxiv.org/pdf/2109.05603.pdf](https://arxiv.org/pdf/2109.05603.pdf)
    
- Monocular is susceptible to scale drift
    
- Use 3d object-based SLAM to solve monocular scale drift - https://ieeexplore.ieee.org/abstract/document/8353862
    
- Distributed monocular SLAM - multiple robots complete the map https://ieeexplore.ieee.org/abstract/document/8688219
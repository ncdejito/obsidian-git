A matrix discretizing the floor into a 2d grid, with each cell having 1 if occupied 0 if not occupied

[Occupancy Grid Node in ROS](https://www.youtube.com/watch?v=suqhnzIyq7w)

Occupancy grid maps
Occupancy grid maps are a useful tool for mobile robots to represent and navigate their environment, but they have limitations and assumptions that may not hold in reality.
00:00 Occupancy grid maps are important for mobile robots as they represent the environment, help with localization and obstacle detection, and can be updated based on sensor data.
Occupancy grid maps are used by mobile robots to represent the environment, similar to architectural floor plans, where white pixels represent free space and black pixels represent occupied areas.
Occupancy grid maps store information about the occupied space and objects in the environment, and this lecture discusses the mathematical model and the process of deriving such maps from sensor data.
Maps are essential for robotics applications, providing information on localization, path planning, and obstacle detection, allowing for effective navigation and avoiding getting stuck.
Learning occupancy grid maps from sensor data is a fundamental task in robot navigation systems to determine which parts of the environment are free and which are occupied, allowing for map updates based on sensor data.
03:39 The video discusses different types of sensors used in mobile robots and the use of occupancy grid maps for planning paths in complex environments, with a focus on feature-based representation and reducing uncertainty in pose estimates.
The speaker discusses different types of sensors used in mobile robots, such as monocular cameras, stereo cameras, laser rangefinders, and rgbd cameras, with a focus on range sensors and provides examples using a sonar range sensor.
The video discusses the different types of map representations, specifically feature-based and volumetric, and how they can be used for localizing a robot and planning a path in the environment.
Occupancy grid maps are a preferred representation for planning paths through free space, and they can be created using laser rangefinders on robots to generate images that show white space as free space and black pixels as occupied space, allowing for the exploration of complex environments such as catacombs.
We can use 3D point cloud data to create occupancy grid maps, which are relevant for autonomous cars and can store both geometric and semantic information about the environment.
We are interested in estimating the map of the environment given sensor data and the known position of the platform, simplifying the simultaneous localization mapping problem.
Today, we will focus on mapping with known poses and specifically on feature-based representation of maps, which involves estimating the location of 3D points in the environment and reducing uncertainty in pose estimates through multiple observations of these features.
12:01 Occupancy grid maps discretize the environment into cells, representing whether each cell is occupied or free, but they may not be suitable for sparse spaces and assumptions about grid size may not hold in reality.
Grid maps are a way to discretize the environment into cells and represent occupancy information for each cell, where each cell can be seen as a tile on the floor.
Every grid cell in an occupancy grid map represents a certain area of the environment and is either occupied or free, with no other states.
Occupancy grid maps provide a non-parametric representation of the environment, storing information about whether each cell is free or occupied, but they can become large in size and may not be suitable for very sparse spaces.
The map shows the structure of an indoor environment, with black pixels representing occupied space and white pixels representing free space, and gray pixels representing unknown space.
The occupancy grid map represents the environment by discretizing it into grid cells, with each cell being either free or occupied, based on the assumption that every part of the physical space is either occupied or free.
The occupancy grid map assumes that the environment is divided into a 4x4 grid structure, with black representing occupied space and white representing free space, but this assumption may not hold in reality due to objects smaller than the grid size or misalignment with walls.
17:30 Occupancy grid maps represent the probability of cells being occupied or free using binary random variables, simplifying the joint belief of individual cells and assuming a static world.
Occupancy grid maps represent the probability of cells being occupied or free using binary random variables, with a value of 1 indicating occupancy, 0 indicating freedom, and 0.5 indicating uncertainty.
The occupancy grid map represents the probability of a cell being occupied or free, with black pixels indicating occupied cells, white pixels indicating free cells, and grayish pixels indicating uncertainty, while also assuming a static world.
The occupancy grid mapping approach assumes that the world is static, with occupied cells remaining occupied and free cells remaining free, and that there is no dependency between neighboring cells, although these assumptions may not hold in reality.
The occupancy grid map represents the probability distribution of the environment by simplifying the joint belief of individual cells using the assumption of independence.
The probability of multiple cells being occupied in an occupancy grid map can be calculated by multiplying the occupancy probability values of each cell, and by exploiting the assumption that a cell is either occupied or free, the probability of a cell being free can be derived from the occupancy probability.
Estimating a map representation from data involves breaking down a joint probability distribution into individual probability distributions and representing them with binary random variables.
29:45 The speaker explains how to estimate the map of the environment using sensor data and position information, simplifying the equations and introducing a new function to compute the probability of a cell being occupied or free in an occupancy grid map.
We want to estimate the map of the environment using sensor data and position information, and we can use a binary base filter to estimate the state of individual cells in the occupancy grid map.
The speaker explains the process of swapping variables and applying Bayes' rule to estimate the likelihood of current observations given the state of a cell, while also simplifying the equations by dropping old positional and pose information.
The probability of a cell being occupied given the current observation and pose can be estimated by considering the probability of an observation given the position information, the probability of the cell being occupied or free given all the old information, and the probability of an observation given the past observation and position information.
The probability of a cell being occupied or free in an environment can be determined by considering the average likelihood of a random cell being occupied or free, taking into account the binary nature of the variable.
The speaker explains how to compute the ratio of the probability of a cell being occupied to the probability of it being free, and simplifies the equation by eliminating terms that are independent from each other.
The speaker explains the components of an occupancy grid map, including the recursive term, the ratio of occupied to free cells, and the prior information, and introduces a new function to simplify the expression.
42:14 The speaker explains how to convert probabilities into odds and vice versa using equations and rules, and suggests using logarithms for efficient occupancy grid map updates, which are used in robotics to build maps of environments by updating the occupancy of cells based on sensor readings.
The odds ratio can be used to convert probabilities into odds and vice versa, with the equation p(x) = odds(x) / (1 + odds(x)).
The speaker explains how to convert odds into probabilities using equations and rules, and suggests using logarithms to simplify the mathematical operations for efficient occupancy grid map updates.
The speaker explains the concept of log odds and how it can be used to update the state of a cell in an occupancy grid map.
The occupancy gridmap algorithm updates a 2D array by iterating over all cells, checking if they are in the sensor's field of view, and adding or subtracting a value based on the occupancy, making it easy to implement, fast, and parallelizable.
Occupancy grid maps are used in robotics to build maps of environments, and the inverse sensor model depends on the type of sensor being used, such as a laser scanner which is typically more accurate and can determine if a cell is occupied or free.
The inverse sensor model updates the occupancy of cells based on sensor readings, with cells in front of the sensor likely to be free, cells where the beam ends likely to be occupied, and cells behind the beam remaining unknown.
53:43 The inverse sensor model for sonar sensors detects reflections, with cells inside the cone more likely to be occupied, and the obstacle representation in occupancy grid maps includes noise, free space, and unknown information, with the thickness of the walls determined by the sensor's noise level, but the representation does not account for dynamic objects.
The inverse sensor model for sonar sensors involves a cone structure that detects reflections, with cells within the cone more likely to be occupied and cells outside the cone more likely to be free.
Objects in front of the robot are considered free space, but the sensor's noise can cause reflections that make it uncertain about the actual location of the object.
The obstacle representation in occupancy grid maps includes areas of noise, free space, and unknown information, with the thickness of the walls determined by the sensor's noise level and the need to accurately detect occupied obstacles.
The speaker demonstrates how sonar range scans can be used to update an occupancy grid map, showing the process of integrating sensor readings and extending the map over time.
Reflections from sonar sensors can cause obstacles to be generated behind real obstacles, but by integrating multiple observations into a map representation, accurate maps can be obtained even with old or inaccurate sensing technology.
Moving objects are often removed in an occupancy grid map, as the robot attributes the changes in occupancy to sensor noise rather than the presence of the objects, but this representation does not account for dynamic objects.
01:00:59 Occupancy grid maps are a technique for creating real-time maps of indoor environments using laser range information, allowing for efficient computation and updates of cells in the map without the need for predefined features or a feature detector.
To implement the estimation of covered cells by a range reading, one can use Brzeznam's line algorithm to determine the grid cells affected by the line and update them accordingly.
An occupancy grid map is created using a laser scanner to record 2D laser range information while a robot explores an indoor environment, allowing for real-time map updates and integration of sensor data.
Occupancy grid mapping is a technique that discretizes the environment into cells, where each cell represents a small part of the space and can be either occupied or free, and the mapping algorithm assumes a static world and independence between cells.
The occupancy grid map is a fast and efficient way to compute and update cells in a map, even with unknown poses, without the need for predefined features or a feature detector.
The speaker explains how occupancy grid maps can be created using range information from a scanner, and how this concept can be extended to 3D using voxel grids, with the caveat of increased memory consumption, and recommends further reading on the topic in the probabilistic robotics book.
You can build a map of the environment by treating each cell individually and estimating the probability of it being occupied or free using sensor models and calibration, which can be done as a homework assignment.
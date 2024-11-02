A matrix discretizing the floor into a 2d grid, with each cell having 1 if occupied 0 if not occupied

[Occupancy Grid Node in ROS](https://www.youtube.com/watch?v=suqhnzIyq7w)
### Overview
- **Purpose**: Represent and navigate environments, aiding localization, obstacle detection, and path planning.
- **Basic Structure**: Environment is discretized into cells marked as either occupied, free, or unknown (black, white, or gray pixels).
- **Use Cases**: Commonly applied in robotics for indoor mapping, autonomous vehicle navigation, and complex environments (e.g., catacombs).
### Creation and Update Process
- **Sensor Integration**: Created using sensor data from laser scanners, sonar, cameras, etc., and updated as robots gather more data.
- **Inverse Sensor Model**: Updates cell occupancy based on readings; cells within the sensor’s range are marked free, while endpoints are marked occupied.
- **Probabilistic Updating**: Uses Bayes' rule to adjust occupancy probabilities, simplifying with log-odds for efficient computation.

### Assumptions and Limitations
- **Static World**: Assumes the environment doesn’t change, though real-world scenarios may include dynamic elements.
- **Cell Independence**: Assumes cells are independent, allowing simplifications in calculations but limiting accuracy in interconnected spaces.
- **Grid Resolution**: Limited by grid size, which may not capture finer details or account for small or misaligned objects.

### Advantages and Limitations of Different Sensors
- **Laser Scanners**: High accuracy for detecting occupancy, preferred for precise applications.
- **Sonar Sensors**: Used with an inverse cone model; effective for basic navigation, though affected by noise and reflections.
- **3D Sensors (e.g., Point Clouds)**: Provide geometric and semantic detail for autonomous systems, though memory-intensive.

### Applications and Practical Implementations
- **Real-Time Mapping**: Laser scanners or other range sensors enable real-time updates, allowing robots to explore unknown spaces.
- **3D Extensions**: Voxel grids extend 2D occupancy grids into 3D but require more memory and processing.
- **Algorithmic Techniques**: Techniques like Bresenham's line algorithm assist in updating affected cells efficiently during robot navigation.

### Practical Challenges
- **Memory and Processing Constraints**: High-resolution maps demand considerable memory and may become impractical for large spaces.
- **Dynamic Environments**: Moving objects are generally treated as noise, leading to inaccuracies in changing surroundings.
- **Map Quality and Sensor Calibration**: Accurate mapping requires well-calibrated sensors and algorithms to handle noise and sensor limitations.
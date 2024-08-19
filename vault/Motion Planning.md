
[Principles of Robot Autonomy](https://stanfordasl.github.io//aa274a/)


Robotics by Cyrill Stachniss
[https://www.youtube.com/playlist?list=PLgnQpQtFTOGSeTU35ojkOdsscnenP2Cqx](https://www.youtube.com/playlist?list=PLgnQpQtFTOGSeTU35ojkOdsscnenP2Cqx)

Basics

3D Coordinates and Representations of Rotations
How to represent points and do transforms
Right hand rule - axes and positive rotation
Notation - timesnewromanlike - homogeneous, cursive - euclidean
Translation
Rotation matrix
Scale change/similarity transform - enlarging or reducing size of objects
Problem: No single operation to describe a transformation in euclidean space, makes calculations complex, operations not commutative
Try alternative representation - homogenous, trick=add 1 more dimension
Similarity transform in 2d - scale change (1dof), rotation(1dof), translation(2dof) = 4dof
Similarity transform in 3d - scale change (1dof), rotation(3dof), translation(3dof) = 7dof
Representations of rotation - advantages and disadvantages
Rotation matrix 
2D - 2x2 mat cos -sin sin cos
Rotations do not change scale
Fix point (rotation center)
Inverse (unrotate) = transpose
3D - 3x3 mat cos -sin sin cos 0s and 1s
3 matrices for each axis xyz
6 constraints
3 degrees of freedom remain
column/row vectors are images of unit vectors
Summary
Overparametrized representation
Commonly used as an exchange format for rotations
Easy composition of rotations
Suboptimal for state estimate problems (9 parameters + constraints)
Euler angles
Rotation consists of 3 rotations
Commonly used for representing robots plans 
Minimal representation - 3 variable for 3 dof
Warning: different conventions!
Often: x-axis point forward
Ground: y to the left
aerospace/marine: y to the right
Rotation matrix to euler angles
Assumptions
Known axes and order
No singularity in euler angles
Rotation to euler formula
Singularity - gimbal lock, when cosbeta = 0, cannot determine parameters
Discontinuity
Rotation angles limited to 0,2pi
Summary
3 rotation around fixed axes
Different conventions
Useful for visualizing rotations
Minimal representation
Singularities
Discontinuities
No direct composition of rotations
Suboptimal for general state estimation problems
Axis-Angle representation
3 rotations can be expressed as 1 rotation
4 parameters (3+1), 3 dof
Axis-Angel vs Normalized Axis-Angle representation
Alternative - encode angle onto length minimal representation with 3 params
Axis-Angle to rotation matrix
Rodrigues formula
Skew-symmetric matrix - identical to its transpose
Rotation matrix to axis-angle
If theta=0, singularity
If theta=pi, something
Summary
Singularity for theta 0
Rotations limited to -pi,pi
Human readable
Minimal representation if normalized
No direct composition of rotations
Quaternions
Popular in state estimation problems
4 dimensional structure, 1 complex number and 3 dimensional complex component
Partially human readable but Manipulations not fully intuitive
Offer outstanding properties, lot of technical systems use this
Properties of quaternions
4 parameter representation
Unique
No singularities
No discontinuities
Quaternions are almost minimal
Addition - 2 quaternions can be added element-wise
Multiplication - more complex, dot products and scalar-vector multiplications
Not commutative
Inverse
Quaternions and rotations
Input rotation axis vector xyz and angle theta
Output = 4d vector that rotates with respect to a point
Quaternions and axis-angle similar
Executing a rotation - p’=qpq-1
Composition - easy to implement with quaternion multiplication
Quaternion and rotation matrix conversions
Best visualization explanation - 3blue1brown video
Interactive tutorial - visualization what quaternion for specific value
Summary
4 param representation
Unique except sign
No singularities, no discontinuities
Easy composition of rotations
Allow for angular interpolation
Often used for state estimation
Attractive way for handling rotations
Partially human readable, often seen as confusing (at first)
Summary
Rotation matrices for transferring data
Euler angle for visualization
Quaternions for State estimation 
Angle-axis representations for human readable
https://www.youtube.com/watch?v=zjMuIxRvygQ&list=PLgnQpQtFTOGQ7eZU0tzmyjSV5w5lt28p8&index=5
Homogenous coordinates
Homogeneous coordinates provide a unified representation for transformations and geometric objects in computer vision, allowing for easy expression of operations and manipulation of objects.
00:00 Homogeneous coordinates are a mathematical tool used in photogrammetry, computer vision, and robotics to represent points or objects infinitely far away in a compact and finite manner, allowing for more elegant descriptions of transformations and state estimation problems involving cameras.
Homogeneous coordinates are a mathematical tool used in photogrammetry, computer vision, and robotics to elegantly perform transformations and represent points or objects that are infinitely far away in a compact and finite manner, which is particularly useful in state estimation problems involving cameras.
The pinhole camera model uses a virtual image plane to project a 3D world onto a 2D image plane, allowing for more compact and elegant descriptions of transformations, but it does not preserve parallel lines or angles between lines.
Straight lines in the real world remain straight lines in the image, but their length and angle may change when projected onto the 2D image plane.
Parallel lines in the real world do not remain parallel in an image, but instead converge towards a vanishing point, which can be elegantly represented using homogeneous coordinates.
Homogeneous coordinates are a useful tool in projective geometry as they simplify the representation of infinitely far points and allow for unified descriptions of transformations using matrices.
Geometric objects can be described using different coordinate systems, such as homogeneous or Euclidean coordinates, with different fonts indicating the dimensionality of the world being discussed.
10:15 Homogeneous coordinates represent points in a higher-dimensional space, allowing for representation of infinitely far points, and can be converted back to Euclidean coordinates by dividing the first two coordinates by the last coordinate.
A homogeneous object is represented by a vector x multiplied by a scalar lambda, where lambda is not equal to zero, and this equation holds for all lambda values except zero.
Homogeneous objects are defined only up to a scale vector, and in the case of a 2D point, it is represented as a vector in an n-plus one-dimensional space with the last dimension set to one.
A point in a two-dimensional projective space can be represented by a three-dimensional homogeneous vector, where the coordinates are multiplied by a scale factor.
Homogeneous coordinates allow for points to be represented in a three-dimensional vector, with the constraint that not all three coordinates can be zero, and to convert back to Euclidean coordinates, the first two coordinates are divided by the last coordinate.
If the last coordinate of a point in homogeneous coordinates is zero, it represents a point that is infinitely far away in the Euclidean world, which can only be expressed as an infinitely large number.
In the projective plane, all points from the Euclidean world are represented, including points infinitely far away, except for the point (0, 0, 0), and to convert from homogeneous coordinates to Euclidean coordinates, divide the first two coordinates by the last coordinate and drop the last coordinate.
18:21 Homogeneous coordinates allow for easy representation of points in a three-dimensional space, enabling transformations through matrix vector multiplication.
In a three-dimensional space, a gray plane represents the euclidean space, while a vector with three values represents the coordinates.
Points in a three-dimensional space can be represented using homogeneous coordinates, where any point on a line towards the origin represents the same point in the Euclidean world, while points on a plane infinitely far away cannot be represented in Euclidean space.
In homogeneous coordinates, a three-dimensional vector is extended to four dimensions by adding a fourth coordinate, and to convert back to Euclidean coordinates, the vector is divided by the fourth coordinate.
Homogeneous coordinates allow for easy representation of the origin and transformations through matrix vector multiplication.
Performing a projective transformation involves multiplying a matrix by a vector, resulting in a new point, and this transformation can be represented by a four by four matrix.
The 3D euclidean world can be represented using a matrix, where translation can be expressed by multiplying a point with the matrix, and rotation can be expressed using the same matrix.
25:52 Homogeneous coordinates provide an elegant way to combine and invert different transformations, such as rotation, translation, similarity, and projective transformations, through matrix multiplications, allowing for chaining of transformations with different effects on parallel lines and angles.
A regular rotation matrix can be used to rotate a point in homogeneous coordinates, resulting in the same rotation as in Euclidean space.
Rigid body transformations involve a rotation and translation, expressed as a rotation matrix and translation vector, and can be used to rotate and shift points.
The similarity transform in computer vision and photogrammetry involves a scale factor that can be applied to objects without changing their angles, while an affine transformation includes additional parameters such as shear and scale, resulting in a matrix with 12 degrees of freedom.
An affine transformation preserves parallel lines but not angles, while a projective transformation adds three parameters and has 15 degrees of freedom, allowing for parallel lines to not remain parallel.
Projective transformations, fine transformations, similarity transformations, and rigid body transformations can all be expressed elegantly through a four by four matrix, allowing for chaining of these transformations through matrix multiplications, with each transformation having different degrees of freedom and effects on parallel lines and angles.
Homogeneous coordinates allow for easy chaining, multiplication, and inversion of transformations, providing an elegant way to combine and invert different transformations in the real world.
34:47 Homogeneous coordinates are used in photogrammetry to describe camera motion, similarity transformations, and represent lines, allowing for easy manipulation and operations such as checking if a point lies on a line or computing intersections.
Homogeneous coordinates are frequently used in photogrammetry for describing camera motion, similarity transformations, and representing lines, allowing for easy manipulation and operations such as checking if a point lies on a line or computing intersections.
Lines can be represented using different forms, such as the normal form, intercept form, or standard form, but they all involve three parameters that can be arranged in a vector.
Rewriting equations in a standardized form allows for the representation of lines in homogeneous coordinates by arranging the coefficients in a vector form.
To determine if a point lies on a line, we can multiply the line equation with the point's coordinates and if the result is zero, the point lies on the line.
A line in homogeneous coordinates can be represented by a three-dimensional vector with non-zero coefficients, allowing for an elegant way to check if a point lies on the line using dot product.
To test if a point lies on a line, compute the dot product of the point and the line and check if it's zero; to find the intersection of two lines, set up a system of two linear equations with two unknowns and solve using matrix multiplication.
42:35 Homogeneous coordinates provide a simple and elegant way to compute the intersection of lines and fit a line through points, using cross products and dot products.
To solve a linear system and find the intersection point of two lines, one can use Kramer's rule to compute the determinants of the matrix and divide them to obtain the x and y coordinates of the intersection point.
The solution to the problem can be obtained by expressing it in homogeneous coordinates as a vector with three components, which corresponds to the cross product of two vectors in 3D.
Homogeneous coordinates provide a simple and elegant way to compute the intersection of two lines and fit a line through two points.
To find the line that connects two points, we can use homogeneous coordinates and solve a linear system using Cramer's rule, resulting in the line parameters being given by d1/d3 and d2/d3.
To check if a point lies on a line, compute the dot product of the point and the line, and to compute the intersection of two lines, take the cross product of the two lines, while a line passing through two points can be computed by taking the cross product of the two points.
Homogeneous coordinates allow us to represent points and lines at infinity by setting the last component to zero, while maintaining the direction of the point or line.
54:48 Homogeneous coordinates are a useful tool for representing points at infinity, allowing for easier mathematical operations and the explicit representation of points at infinity in various applications such as camera sensors.
Homogeneous coordinates are a useful tool for representing points that can be infinitely far away, particularly in the context of cameras, as they allow for expressing direction and determining orientation.
Lines in homogeneous coordinates can be described by fixing the first two coordinates based on their orientation, while the third coordinate is a free parameter, allowing parallel lines to intersect at a single point at infinity.
Two lines with identical first two dimensions but potentially different last two dimensions are parallel, and the cross product of their elements results in the third dimension being the difference between the first two dimensions.
Parallel lines meet at a point at infinity, which can be represented as a horizon line containing all points infinitely far away, and this line can be tested by computing the dot product with points represented as (u, v, 0) to determine if it is the ideal line.
Points and planes in 3D can be represented using homogeneous coordinates, where a point is expressed as a four-dimensional vector and a plane is expressed as an equation with four coefficients, and similar techniques can be used to check if a point lies on a plane or if a point is infinitely far away in 3D.
Homogeneous coordinates provide an alternative representation for geometric objects, allowing for easier mathematical operations and the explicit representation of points at infinity, making them useful for various applications such as camera sensors.
01:07:56 Homogeneous coordinates are a crucial tool in robotics and photogrammetry, allowing for normalization and dropping of dimensions, although they can complicate solving complex linear systems.
Adding or removing the last dimension in homogeneous coordinates allows for normalization and dropping of the last dimension, resulting in homogeneous elements that are only defined up to scale.
Homogeneous coordinates can be disadvantageous in certain situations, particularly when solving complex linear systems, as they increase the number of unknowns, but they are still a common and important tool in the study program.
Homogeneous coordinates are essential in robotics and photogrammetry, and studying them will provide a useful tool for daily transformations.

Least squares
Least squares is a useful tool for solving state estimation problems, particularly in graph-based simultaneous localization and mapping (SLAM), as it minimizes the squared errors in an overdetermined system to compute a solution.
00:00 Least squares is a useful tool for solving state estimation problems, particularly in graph-based simultaneous localization and mapping (SLAM), as it minimizes the squared errors in an overdetermined system to compute a solution.
Least squares is a useful tool for solving state estimation problems, particularly in graph-based simultaneous localization and mapping (SLAM), as it minimizes the squared errors in an overdetermined system to compute a solution.
We use least squares to estimate parameters by minimizing the sum of squared errors in observations, which is a common approach in engineering problems such as SLAM.
The least squares approach has been used for a long time to solve mapping problems, including estimating the future location of the asteroid Ceres, and while there are some unique challenges in robotics, the overall idea remains the same.
Given a set of observation functions that compute expected observations based on known states, the goal is to estimate the state that best explains the actual observations.
We want to find the parameters that best explain our observations by minimizing the squared differences between the predicted and real measurements, using a concrete example of 3D point locations.
The user needs to specify an observation function that describes how 3D points are mapped to pixel coordinates, and then minimize the difference between the actual and computed pixel locations by adjusting the points in the 3D world.
09:55 The goal is to minimize the sum of squared errors by finding the optimal state, but it requires numerical approaches and a good initial guess, with no guarantee of finding the global optimum.
The error function depends on the current configuration of the parameter, and changing the parameter will result in a difference between the observed and predicted values.
The vector estimates the difference between actual and measured values, assuming normally distributed variables with zero mean and no bias, and the uncertainty of the sensor is expressed in an information matrix.
Measurements can be represented as squared errors using the information matrix as a weight, which accounts for the uncertainty of individual measurements and generates an error term for each measurement.
We aim to minimize the sum of squared errors by finding the optimal state X that minimizes the global error function, which is the sum of individual error terms obtained from comparing actual and predicted observations.
Finding the minimum error configuration in a complex problem with a nonlinear function requires numerical approaches and a good initial guess, but there is no guarantee of finding the global optimum.
15:29 We solve the problem iteratively by locally linearizing the error function and computing the minimum of the quadratic function approximation using the Jacobian matrix and Taylor expansion, resulting in a final equation with constant, linear, and quadratic terms.
We solve the problem through an iterative least squares approach by locally linearizing the error function and iteratively computing the minimum of the quadratic function approximation.
Compute the first derivative of the function by adding a variation around the initial guess, resulting in an error term and a sum of absolute value constant offset.
The Jacobian is a matrix that represents the partial derivatives of a function with respect to the dimensions of a parameter, and it is used to compute linear functions in the neighborhood of a linearization point.
The error function is approximated as a linear function, allowing for the computation of the squared error term using a Taylor expansion and the information matrix.
The equation is rearranged to group terms and introduce new variables, resulting in a final equation with a constant term, a linear term, and a quadratic term.
The global error term can be expressed as the sum of individual error terms, with the coefficients for the linear and quadratic terms defined as B and H respectively.
27:09 Least squares is used to minimize systematic errors in odometry calibration by linearizing error terms, computing quadratic error terms, and finding the first derivative to solve a system of linear equations and obtain the solution for the increments.
We linearize error terms, compute quadratic error terms, and minimize the overall function by finding the first derivative, setting it to zero, and solving the resulting system of linear equations.
The first derivative of a quadratic form in an N-dimensional case is given by h plus h transposed times X plus B, where H is a matrix and the constant term is irrelevant, allowing us to compute the derivative and apply it to our problem.
Compute the first derivative, set it to zero, and solve the resulting system of linear equations to obtain the solution for the increments.
Iteratively linearize error functions, compute terms B and H, solve linear system, and update initial guess until convergence to global solution.
The video introduces the concept of least squares and its application in odometry calibration to minimize systematic errors.
To use the least squares problem, we need to find the parameters of the correction function by computing the state vector, which is a nine-dimensional vector representing the elements of the function, and then calculating the error function as the discrepancy between the actual position and the predicted position using the calibration function.
37:15 The Jacobian matrix in least squares has zero elements for variables with no dependencies, and only one iteration is needed for linear functions, while at least three observations are needed to solve the calibration problem using sparse H matrices and matrix decomposition techniques like Cholesky factorization.
The Jacobian matrix in least squares has three rows and nine columns, with zero elements for variables that have no dependencies and no dependency on X.
If the first derivative of a function does not depend on the variable, it means the function is already linear, so only one iteration is needed to compute the solution using the least squares approach.
To find a solution to the calibration problem, at least three observations are needed to fill the nine unknowns in the matrix.
The matrix H is symmetric because it is constructed using the Jacobians, and the structure of the measurements affects the structure of H, with observations only relating a small number of variables, resulting in sparse H matrices.
To efficiently solve a system of linear equations, one can use matrix decomposition techniques such as Cholesky factorization for symmetric and positive-definite matrices.
Replace the matrix A with L L transposed, solve the system L transposed X equals Y, and then solve L transposed X equals Y to easily solve the linear system.
47:53 The least squares method simplifies solving linear systems, involves iterative approaches and probabilistic state estimation, and assumes Gaussian probability distributions.
Computing the Cholesky decomposition simplifies solving a complex linear system into solving two simple linear systems, allowing for easy solution of a system of linear equations using the Gauss Newton method, which is an iterative approach that requires a good initial guess for the parameters of the system.
The initial guess is irrelevant in the computation of the Jacobian, so the algorithm needs to compute the linearizations of the error functions to find the matrix H and vector B, which are the only elements that remain when the first derivative of the quadratic form is set to zero.
Solving the least squares problem involves creating a system of linear equations, solving it using Tedeschi composition, iterating until convergence, and obtaining a new configuration that minimizes the squared error.
The least squares problem is connected to probabilistic state estimation, as maximizing the probability distribution in state estimation leads to the solution generated by the least squares problem under certain assumptions.
We can rewrite the probability distribution of a vector X using Bayes rule and the Markov assumption, and then compute the likelihood of this term.
The speaker explains the concept of least squares by discussing the computation of probabilities and making the assumption that all probability distributions are Gaussian.
54:25 Minimizing squared error maximizes the likelihood of independent Gaussian distributions, allowing for probabilistic state estimation, and the least squares approach is popular in engineering fields like geodesy.
The speaker defines variables to link them to the least squares problem, including the error term, information matrix, and squared error, and demonstrates how to plug them into the expression.
Maximizing the log likelihood of the probability distribution is equivalent to minimizing the error by considering the prior, motion commands, and observations.
Minimizing squared error is equivalent to maximizing the likelihood of independent Gaussian distributions, allowing for the computation of the mean and providing a direct link to probabilistic state estimation.
The video provides an informal introduction to the least squares problem, explaining how to compute or approximate the covariance matrix using matrix H and how to use this as a tool for solving standard least squares problems.
The Gauss Newton approach is used to linearize nonlinear error functions, and by minimizing the error, we can maximize the probability, making the least squares approach popular in various fields of engineering, including geodesy.
59:47 Least squares is a widely covered topic in numeric calculus and optimization, with various notations and resources available, and it can be used for data estimation and solving problems like simultaneous localization and mapping.


Mobile robotics
Bayes filter
The Bayes filter is a versatile framework for state estimation that combines motion and observation data using recursive state estimation, allowing a robot to determine its location by updating its belief about the current state of the system at each time step.
00:00 Recursive state estimation involves updating the belief about the current state of a system based on new observations, using a recursive approach to update the belief at each time step.
Recursive state estimation involves updating the belief about the current state of a system based on new observations, reusing the previous distribution and updating it with new information.
State estimation is the process of estimating the current state of a system based on past observations and control commands, using a recursive approach to update the belief about the system's state at each time step.
A robot in a one-dimensional world can only sense doors and its initial belief about its location is a uniform distribution.
The robot uses sensor information to update its belief about its location in the environment, incorporating observations and adjusting its probability distribution.
04:29 The Bayes Filter helps a robot determine its location by combining motion and observation data, using recursive state estimation and swapping variables in the probability distribution.
The probability distribution of the system's motion smears out and gets wider due to uncertainty, but when the robot receives a new observation, it helps determine its location.
Combining two distributions with overlapping peaks results in the highest peak and a few other peaks, indicating instances where one was right and the other was wrong.
Recursive state estimation involves advancing the belief from one state to the next using current sensor information and motion control commands, and the goal is to derive the equations that allow us to estimate this recursive belief.
Swap the variables zt and xt in the distribution and apply Bayes rule to simplify it, resulting in the first part where zt and xt are swapped and the second part where everything else remains the same except for the verb.
The speaker modifies a part based on the current state of the system and the world.
09:25 The Markov assumption allows us to estimate the likelihood of current state based on past observations and control commands, simplifying the equation by eliminating irrelevant information.
The probability of observing something is independent of past observations and control commands, according to the Markov assumption.
The likelihood of an observation can be estimated by considering the state of the world and applying the Markov assumption.
Modify a specific part of the equation.
We can use the law of total probability to introduce a new variable and create a recursive equation that allows us to move from x t to x t minus one.
By adding a new variable and integrating over all previous states, the speaker explains how to estimate the likelihood of the current state given past observations and motion commands, simplifying the equation by eliminating irrelevant information.
14:11 The speaker explains how the Markov assumption simplifies the expression and updates the probability distribution based on previous observations and control commands, with the recursive Bayes filter forming the basis for various state estimation techniques.
The speaker explains how the Markov assumption simplifies the expression and how the probability distribution is updated based on previous observations and control commands, with an additional motion command.
Assuming the future motion command of going 20 centimeters forward does not help in estimating the current position.
Ignoring the latest motion command is a reasonable assumption in most cases, although there are situations where this independence assumption does not hold.
Ignoring certain information in state estimation can lead to inaccurate results, so it is important to revisit and reassess the assumptions made in the model.
The recursive Bayes filter reduces the estimate of the current belief by incorporating updates based on the current control command and observation, forming the basis for various state estimation techniques such as the Kalman filter, extended Kalman filter, unscented Kalman filter, particle filter, and histogram filter.
19:17 The Bayes filter framework simplifies predictions and corrections using Gaussian distributions, estimating future states with a motion model and correcting mistakes with an observation model.
The Bayes filter framework makes assumptions and can be simplified by using Gaussian distributions, resulting in a prediction step and a correction step to update the belief based on control commands.
The Bayes filter estimates and predicts the system's future state using a motion model in the prediction step, and corrects potential mistakes using an observation model in the correction step.
Specify the motion model and observation model to implement the Bayes filter.
Representing beliefs and advancing in time are influenced by the shape of probability distributions, such as gaussians or sums of gaussians.
22:57 The Bayes filter is a versatile framework for state estimation that can be implemented in different ways depending on system assumptions, allowing for representation of various probability distributions, but with computational and memory costs.
The Bayes filter is a framework for recursive state estimation that can be realized in various ways depending on assumptions made about the system, such as linear or non-linear models and the type of distributions used to describe motion and observations.
The speaker discusses the design decisions and impact on the appearance of the Bayes filter, including the use of gaussian distributions and linear models, as well as the alternative representation of particle filters.
Bayes filters allow for representing arbitrary probability distributions, including multimodal distributions, but come with computational and memory costs, and can handle arbitrary models as long as sampling and point-wise evaluation are possible.
25:41 A robot can determine its current location by using probability distributions, motion models, and observation models based on range measurements with Gaussian noise.
Given the robot's previous location and executed motion command, the speaker explains how to determine the current location using a probability distribution.
The speaker discusses probability distributions and motion models, using the example of a banana shape distribution to describe the motion of a system, and illustrates an observation model using a laser pointer as a measurement device.
The distance measurement from a range sensor is affected by noise, which can be represented by a Gaussian distribution.
The speaker explains how a robot can estimate its position in the world by using a motion model and an observation model based on range measurements with gaussian noise.
29:53 Understand the importance of probabilities in state estimation problems and how the Bayes filter framework incorporates previous beliefs, new observations, and control commands to recursively estimate the state using techniques like the extended Kalman filter or particle filter.
Learn about maps, motion description, and localization in order to reach the end goal of the lecture.
Probabilities are important for state estimation problems, and the base filter framework allows for recursive estimation by incorporating previous beliefs, new observations, and control commands, with different realizations such as the extended Kalman filter or particle filter, and the probabilistic robotics book provides further details on implementing and understanding these techniques.



[[Occupancy grid]]



Robot locomotion
Understanding the different types of robot drives and their movement capabilities is crucial for state estimation and smooth robot movement in various environments.
00:00 Understanding how different mobile robotic systems move in their environment is crucial for state estimation, and the lecture discusses various types of robot drives and their applications, emphasizing the importance of smooth movement and the relationship between linear and angular velocity.
Locomotion is the study of how different mobile robotic systems move in their environment, with a focus on wheeled systems, and it involves understanding how inputs such as motor movement or propellers result in the movement of the robot from one point to another without the need for a map or predetermined plan.
Understanding how a mobile robotic system responds to input commands and moves in its environment is crucial for state estimation, as this locomotion information can be fused with data from other sensors to estimate the system's pose.
The lecture discusses different types of robot drives, including the differential drive, aquaman drive, synchronous drive, and mechanism wheels, and their applications in various environments.
Multiple wheels on a mobile platform can have different velocities and reactions, and understanding their resulting motion is important.
To ensure smooth movement and avoid skidding, the wheels of a robotic system should have their axes intersecting at a common point, allowing them to move smoothly as one object around an instantaneous center of curvature.
The distance moved by a robot is determined by its linear velocity and the time for which the command is given, while the angular orientation is determined by the angular velocity and the time for which it is applied, and the relationship between linear and angular velocity is important for understanding the motion of robots.
10:26 A differential drive robot with two wheels can move independently and go straight by setting the same velocities on both wheels, and can spin on the spot by rotating one wheel clockwise and the other anti-clockwise.
A differential drive robot has two wheels connected to individual motors, allowing for independent movement and the ability to go straight by setting the same velocities on both wheels.
To move back, reverse the velocities, and to move along a curve, the inner wheel travels a shorter distance than the outer wheel.
Differential drive robots can spin on the spot by rotating one wheel clockwise and the other anti-clockwise, allowing for maneuverability in confined spaces.
The variables of interest in understanding the motion of a robot include the left and right velocities, angular velocity, position (x and y coordinates), and orientation (theta) of the robot's center of mass.
The robot's velocity, orientation, and radius to the center of curvature are shown in relation to the wheels.
The relationship between the linear and angular velocities of a robot can be understood by considering the commands set to the two wheels and the distance between the center of the robot and the instantaneous center of curvature.
17:48 The video explains how to calculate the velocities of a robot based on the wheel velocities and the radius of curvature.
The equations are manipulated to find an expression for r by rearranging and removing terms.
The radius of the circle that the platform follows depends on the distance between the wheels and the velocity of the left and right wheels.
Adding the velocities vl and vr gives us the equation vl + vr = 2 omega r.
The transcript explains how to calculate the angular and linear velocities of a robot based on the individual velocities of its wheels and the radius of curvature.
22:53 The coordinates of the instantaneous center of curvature can be computed to predict the movement of a robot, and different kinematic designs affect a robot's ability to turn and maneuver.
The coordinates of the instantaneous center of curvature can be computed using the radius of curvature, allowing for the expression of these coordinates in a global coordinate frame.
We are interested in predicting the movement of a platform based on its current position and the velocities of its wheels, which is known as forward kinematics.
To determine the new position and orientation of a robot, subtract the coordinates of the instantaneous center of rotation from the current position and multiply it by the rotation matrix, then add the result to the initial position, while the new orientation is calculated by adding the angular velocity multiplied by the time difference to the old orientation.
In robot locomotion, velocities follow a trajectory rather than being constant, and while a robot with fixed axles can control the velocities of its front and back wheels separately, there is a flaw in its kinematic design as the axes of the front and back wheels will never meet, making turning difficult.
Skid steer robots cannot roll freely due to the inability of their two accesses to intersect, while aquaman drive cars can go straight by applying the same velocities to all four wheels and turn by aligning the front and back wheel axes.
The aquaman drive restricts certain maneuvers due to the difference in distance between the back and front wheels, so a virtual wheel is used to approximate the center of mass and create a bicycle model for analyzing the robot's motion.
31:22 The steering angles of a robot's front wheels are determined by the relationship between the distance between the axises and the center of rotation, allowing for smooth motion and tracking along curved surfaces without slipping.
The front wheels of a robot need to be steered at different angles in order to follow the desired path, with the inside wheel steering less and the outside wheel steering more.
The steering angle delta is determined by the relationship between the distance between the two axises (d) and the distance from the center of the car to the instantaneous center of rotation (r).
To achieve smooth motion for a robot, different steering angles for the inner and outer wheels are chosen so that they intersect at the same point as the ideal wheel, allowing the robot to track along curved surfaces without slipping.
Ensure that the wheels of a robot pass through the instantaneous center of curvature by using the equations tan(delta) = d/r and tan(delta I) = d/(r - l/2) for the inner wheel and tan(delta o) = d/(r + l/2) for the outer wheel.
The solution to ensuring smooth movement along a desired curve in autonomous cars and horse carriages involves using a mechanical fix of attaching an extra rod and linkages of specific lengths to prevent skidding and breakdowns.
The mechanism in cars and aquaman-type cars involves rotating the front wheels to enforce specific steering angles, while the synchronous drive allows all wheels to move at the same linear velocity and rotate in the same way, resulting in smooth motions and the ability to reach different positions in a confined space.
41:43 The XR. 4000 drive enables smooth and precise robot movement, while different types of locomotion, such as legged systems and tracked vehicles, allow for versatile navigation in various environments.
The XR. 4000 drive allows the robot to move in tighter circles by steering both the front and back wheels, ensuring a smooth motion and inferring the robot's position at the next time instance.
The mechanism wheels consist of motorized wheels with passive rollers on top, allowing for movement through the rotation of the actuated wheels.
Robots with four motors and four degrees of freedom can achieve movement in multiple directions by setting different velocities for each wheel.
The speaker explains different types of robot locomotion, including a mechanism with rotating wheels for sideways movement and tracked vehicles for navigating rough surfaces and stairs.
Humanoid robots use legged systems for locomotion, which allows them to move in a statically stable manner and operate in environments designed for humans without the need for redesigning them for wheeled vehicles.
The robot's dynamic stability allows it to perform complex movements with the help of specific hardware and an understanding of its environment.
48:49 Non-holonomic and holonomic constraints limit a robot's movement, dead reckoning and odometry are methods for estimating movement but have limitations and errors.
Non-holonomic constraints limit a platform's movement in the configuration space, while holonomic constraints restrict the valid configuration space that the platform can assume.
Holonomic constraints refer to parts of the configuration space that cannot be reached, which is important for planning movements in environments with obstacles.
The planning problem becomes easier as the platform can perform any required action in a free space, and dead reckoning is the estimation of motion based on given inputs, although it is not always accurate.
Dead reckoning is a method of estimating movement by integrating commands over time, even though there may be limits in control and surface conditions that affect accuracy.
Odometry, which uses wheel encoders to measure the number of wheel revolutions and calculate movement, is more accurate than dead reckoning for estimating distance traveled.
The robot's movement in a maze environment is affected by systematic errors in the odometer, resulting in a cumulative error over time, despite the use of noisy odometry sensors.
54:56 Different types of wheeled drives were discussed, including differential and ackermann drives, along with the concepts of non-holonomic and holonomic constraints, and the use of odometry and dead reckoning to estimate robot movement.



Motion models
Probabilistic motion models are used to understand and account for the uncertainty in a robot's movement, allowing for more accurate estimation of its position and trajectory.
00:00 Probabilistic motion models help understand the uncertainty in a robot's movement, capturing the drift in its internal estimate and calculating the probability of its location based on starting position and executed command.
Probabilistic motion models help understand the uncertainty in a robot's movement caused by factors such as slipping wheels or delayed response to commands.
Motion models are used to capture the uncertainty in robot movement, which is important for state estimation in a Bayesian framework.
The robot's internal estimate of its movement is drifting due to an imbalance in the weight distribution, resulting in a systematic drift over time, and the question is how to link the actual movement and the estimate of the model in terms of probability.
The motion model calculates the probability of a robot ending up at a specific location, given its starting position and executed command.
04:41 The video explains how the robot's belief state is estimated by using probability distribution of positions, motion model probabilities, and sensor measurements to predict and modify the robot's state in the environment.
The speaker explains how the probability distribution of different positions in the environment is used to estimate the robot's belief state.
Understand how to move from x t minus 1 to x d by multiplying previous positions with the motion model probabilities and summing them up, which is known as the prediction step in the base filter estimate.
The lecture focuses on how the predicted belief is modified by measurements taken by the sensor, with the motion model introducing uncertainty and the measurement model decreasing it to estimate the state of the robot in the environment.
07:54 The lecture discusses two models for wheel robots, the odometry-based model and the velocity-based model, which determine the probability distribution of the robot's position based on commands and sensor data, with the odometry model providing more accurate measurements of movement.
Compute the posterior probability of ending up at xt given certain conditions, such as being at xt-1 and applying a certain command ut, which applies to various types of robots.
The lecture focuses on two commonly used models for wheel robots, the odometry-based model and the velocity-based model, which determine the probability distribution of ending up at different places in the environment based on commands given to the robot and sensor data from the motor shaft.
Odometry is treated as a control command to measure the movement of a platform, while the velocity-based model predicts the robot's position based on given velocities.
The odometry model uses wheel encoders with alternating white and black lines on a disc attached to a motor shaft to determine the motor's rotation.
The odometry model provides more accurate measurements of robot movement compared to the dead reckoning model because it captures rotations after the command is executed, while the uncertainty in motion for wheel robots arises from factors such as differences in wheel diameter and surface conditions.
13:10 The movement of a robot can be affected by various factors, leading to inaccuracies in estimating distance traveled; the lecture discusses the odometry model, which simplifies analysis by abstracting the robot's movement into rotations and translations.
The movement of a robot can be affected by obstacles, uneven wheel diameters, uneven load distribution, and the type of surface it is moving on, leading to inaccuracies in estimating its distance traveled.
The lecture discusses the odometry model, which abstracts away from the exact drive and simplifies the analysis of deriving equations by expressing the positions at time t-1 and time t.
Motion between two points can be explained as a delta rotation, followed by a delta translation, and then another delta rotation, which is an abstraction over the actual movement of a robot.
The odometry model assumes that the robot's pose is defined by its 2D position and yaw angle, and the control commands consist of two rotations and a translation.
17:27 Modeling uncertainty in motion models involves understanding how noise affects parameters, with Gaussian noise being assumed around a starting point, and epsilon and alpha coefficients representing the error in the robot's movements.
Modeling uncertainty involves understanding how noise affects different parameters, with one assumption being a Gaussian distribution around a starting point.
We model gaussian noise on different commands in motion models, which may not necessarily be gaussian, to better explain the actual noise observed in real-world scenarios.
The noise in the robot's movements is modeled by epsilon, which depends on the rotation and translation parameters, with alpha coefficients representing the error in rotation and translation.
21:06 The video explains how motion models use probability distributions to calculate the likelihood of ending up at different positions based on control or odometry commands, with examples of normal and triangular distributions.
The random variable can be assumed to be normally distributed, but it can also be defined as any other meaningful distribution, such as the triangular distribution, which ensures that uncertainty is within bounds and avoids the possibility of extreme values.
Compute the probability distribution of ending up at different positions by making a control or odometry command and calculating the probability at a particular point.
The speaker explains how query points and standard deviation are used to determine the probability distribution in motion models, using examples of a normal distribution and a triangular distribution.
The algorithm computes a probability distribution between two hypotheses based on odometry measurements.
The probability of moving from position x to position x prime is computed by multiplying the probabilities of the rotation, translation, and rotation movements, assuming they are independent, and repeating this process for all positions in the environment.
The probability distribution visualization shows that the robot is more likely to end up in the darker areas, which are shaped like a banana due to greater error in rotation components than in translation.
27:47 By using a grid-based algorithm, the speaker shows how values are computed for each grid position in a 3D case, emphasizing the importance of representing the motion model through a sample-based representation and the ability to sample from different distributions.
By following a specific path and using a grid-based algorithm, the speaker demonstrates how different values are computed for each grid position in a 3D case.
Representing the motion model through a sample-based representation is preferred over a histogram representation, and the ability to sample from different distributions, such as a normal distribution, is important.
By taking a large number of samples, we can approximate a normal or triangular distribution, which can be seen as a simulation or model.
30:48 The motion model computes the robot's motion and adds noise, resulting in a new probability distribution of its position, while different noise parameters and models are discussed to capture uncertainty in the robot's trajectory.
For each robot position, the motion model computes the motion and adds noise based on the defined distributions, resulting in a new probability distribution of where the robot will end up.
The speaker explains how different noise parameters affect the probability distribution of a robot's motion, using examples of angle and translation errors, and discusses two approaches to capturing uncertainty in the robot's trajectory.
The velocity-based model describes how a robot moves using linear and angular velocity, but it lacks the ability to track the robot's orientation along the arc it travels.
An extra error term, gamma, is added to the final orientation of the system to model the error in the third orientation parameter.
There are two types of models for describing the motion of wheel robots: an odometry model that uses encoders to determine movement and a velocity-based model that relies on commands, with the latter being less accurate but still useful in cases where encoders are not available.
The lecture discusses two methods for determining the probability of ending up at a specific point in space, and explains that these calculations are based on fixed time intervals and can be approximated as continuous integration if done frequently enough.



Observation models
Observation models are crucial for accurate localization and state estimation in robotics, and they can be created using various methods such as Gaussian noise and decaying functions to account for measurement uncertainty and unexpected obstacles.
00:00 The lecture discusses observation models in state estimation algorithms, specifically focusing on how they are used to update the predicted belief into the corrected belief.
The lecture discusses observation models in state estimation algorithms, specifically focusing on the prediction and correction steps of the recursive base filter and how the observation model is used to update the predicted belief into the corrected belief.
The observation model determines the probability of obtaining a specific observation based on the current state.
02:27 Range sensors provide distance information to obstacles, and by treating individual measurements as independent, an observation model can be created to estimate obstacle distance and evaluate range readings for localization.
Range sensors provide distance information to the closest obstacle, such as a 2D laser range scanner or a 3D lighter, and can be used to estimate obstacle distance using time of flight or ultrasonic wave measurements.
Range sensors provide a series of proximity measurements in different directions, and the question is about the probability of range readings given the scanner's reference frame.
Individual measurements are treated as independent given the sensor location and knowledge of the environment, allowing for the creation of an observation model for localization.
The beams in the scan are conditionally independent given the state, allowing for the evaluation of individual range readings in relation to the map and state information for localization.
Compute the likelihood of obtaining a range reading from a laser scanner given the knowledge of one's location and the environment, by breaking it down to a single beam and combining the measurements through a product.
07:22 The video discusses observation models for sensor readings, including the raycast model and a combination of four different models, highlighting the use of Gaussian noise and decaying functions to account for measurement uncertainty and unexpected obstacles.
The raycast model estimates the distance from the sensor to the closest obstacle in the environment, incorporating Gaussian noise to account for measurement uncertainty.
The speaker explains the concept of an expected distance in a raycast model for sensor readings, highlighting the limitations of a simple model and the possibility of measuring a distance that is unlikely but still possible due to environmental factors.
An observation model for obstacle detection includes a Gaussian noise component and a decaying function that accounts for invalid or maximum range readings.
The model discussed in the video is a combination of four different models, including sensor noise, dynamic objects, a random component, and a max range component, with the first model being a beam-based proximity model that accounts for sensor uncertainty.
The sensor's measurement probability is described by a Gaussian distribution with a mean representing the expected measurement and a variance representing the uncertainty, while unexpected obstacles are modeled by an exponentially decaying function that generates different range readings.
The model explains the differentiation between being closer or not, with a function that decays and drops to zero, resulting in a dent in the combined function.
14:18 The speaker discusses the importance of estimating the distance to the closest obstructing object in a crowded space, using an analogy of bit strings to understand the probability of object distribution.
Dynamic obstacles in the environment are only relevant if they obstruct the field of view between the scanner and the obstacle according to the map.
The exponentially decaying function is a plausible model for the dynamics of objects in the world, assuming a uniform distribution and that only the closest object matters.
In a crowded space, the speaker explains the importance of estimating the distance to the closest object and not to any object behind it, using an analogy to bit strings to understand the probability of object distribution.
The speaker discusses the number of configurations where the first bit string is one and all other bit strings are irrelevant, and explores how many of these configurations can exist in a given environment.
Different configurations of bit strings consisting of zeros and ones can occur randomly, and there are 16 different bit strings that exist with four digits.
19:49 Observation models can be generated using an exponentially decaying function trained on real-world situations to favor closer returns, while accounting for random measurements and errors.
Certain bit strings occur more frequently than others, indicating that it is more likely to observe an object close to the platform than further away.
Generate a pattern that favors closer returns over further ones by using an exponentially decaying function, which can be trained by observing real-world situations in different environments.
Random measurements can occur due to unmodeled random events, limited sensing range, or other error configurations, and these probabilities can be accounted for by adding small uniform probabilities to avoid invalidating the entire scan.
23:03 The parameters of the resulting mixture density function can be obtained through various methods, such as measuring pure measurement noise and fitting a Gaussian distribution, and can be used to estimate robot localization and interpret range readings.
The resulting mixture density function is determined by the parameters, such as the weights given to the exponentially decaying function and the Gaussian noise, which can be obtained through various methods including measuring the pure measurement noise and fitting a Gaussian distribution.
Use raw sensor data to learn parameters from a time series of range readings taken in a representative environment, where the frequency of certain range readings can be analyzed.
Fit models to data by using a histogram to determine the weight parameters that best match the occurrences of certain events at expected distances of three or four meters.
Random effects can occur in sensor data, but with more representative data, outliers can be minimized and smooth models can be learned; this applies not only to laser range scanners but also to sonar sensors, allowing for accurate observation estimation in a fixed map.
By using an advanced raycast model, it is possible to estimate the likelihood of obtaining a certain observation at a specific position in order to interpret range readings and estimate robot localization.
The beam endpoint model is a simple and fast alternative to the raycast model for range sensors, where only the end point of the scan is considered to determine the presence of obstacles.
29:01 The proximity of obstacles can be determined by measuring distances, creating lookup tables, and using probability models, such as likelihood fields or beam endpoint models, which are commonly used in mobile systems for efficient likelihood evaluations.
The proximity of an obstacle can be determined by measuring the distance between a point and the closest obstacle, allowing for the creation of a lookup table to easily identify obstacles in the environment.
White cells are free, gray cells are obstacles, and distance information can be efficiently computed using the euclidean distance transform on binary images, making it a popular tool for localization systems like particle filters.
Models are used to estimate the probability of measurements based on the environment, and the resulting model is a probability distribution along a ray.
Occupancy grid maps can be efficiently transformed into likelihood fields or beam endpoint models, which estimate the distance to the closest obstacle and are commonly used in mobile systems for efficient likelihood evaluations.
33:15 Observation models are essential for accurate localization and state estimation, and can be represented using gaussian estimates and lookup tables for efficient computation.
Scan landmarks, detect them, and write down their locations in parametric form assuming gaussian noise, then compute the expected observations based on the pose and landmark information.
Estimating position using a simple model based on distance and orientation, and a similar model using range bearing observations of landmarks, allows for accurate localization even with multiple observations.
The speaker explains a simple model for perceiving landmarks or points in the environment using bearing information and Gaussian noise.
The lecture discusses observation models used in state estimation techniques, such as particle filters and Kalman filters, specifically focusing on range sensors and the likelihood of observations given the knowledge of the system's state and the environment.
The lecture discusses the importance of sensor models in state estimation algorithms, particularly for range sensors, and recommends further reading on the topic.
The speaker explains how observation models can be represented using gaussian estimates, particularly in pixel coordinates for calibrated cameras, and suggests using lookup tables for efficient computation.



Kalman filter
The Kalman filter is a powerful tool for state estimation in linear systems, as it updates beliefs based on current observations and control commands using Gaussian distributions, ensuring that all distributions involved in the filtering process remain Gaussian.
00:00 The Kalman filter is a recursive base filter that estimates the state of a system by combining predicted and observed information, assuming Gaussian distributions and linear models, and it is optimal for linear models with Gaussian probability distributions.
The Kalman filter is a recursive base filter that uses a prediction step and a correction step to estimate the state of a system, assuming Gaussian distributions and linear models, and it provides optimal results when these assumptions are met.
Performing a prediction and correction based on observations allows the Kalman filter to estimate the position of a ship by combining the predicted and observed information.
The Kalman filter is a realization of the base filter, which integrates previous beliefs and observations to make predictions and corrections based on the uncertainties of each.
The Kalman filter is an optimal estimator for linear models with Gaussian probability distributions, and it updates a Gaussian belief based on emotions and observations.
The Kalman filter relies on computing marginal and conditional distributions, which are Gaussian distributions, in order to maintain the assumption that all distributions involved in the filter are Gaussian.
The speaker explains the computation of the margin and conditional in the derivation of the Kalman filter, and discusses the use of linear models for motion and observation.
10:57 The Kalman filter uses linear models and Gaussian distributions to predict and combine data, accounting for uncertainty, and ensuring the result remains Gaussian.
The Kalman filter uses linear models to predict and combine Gaussian distributions, ensuring that the result remains Gaussian and accounting for uncertainty through motion models and observation.
The matrix A represents the change in state over time, the matrix B represents how control commands affect the state, and the matrix C maps the state to observations.
A linear motion model with Gaussian noise is used to estimate the probability distribution of the robot's position based on its previous state and control commands in the Kalman filter.
The speaker explains how a linear model and Gaussian distributions are used to predict the future state and observations of a system, taking into account the uncertainty associated with the control commands and observations.
The predicted belief and corrected belief in the Kalman filter are both Gaussian distributions, as they are obtained by multiplying Gaussian distributions with other Gaussian distributions.
The belief in a Kalman filter remains Gaussian throughout the update steps, as long as the initial belief is Gaussian and the recursive expression is used.
25:20 The Kalman Filter and Extended Kalman Filter rely on the assumption of a Gaussian world, allowing for recursive updates and evolution of the state over time, by representing beliefs as Gaussian distributions and using mathematical tools to compute mean and covariance.
The convolution of two Gaussian distributions results in a Gaussian distribution, which means that if the two distributions in this example are Gaussian, the resulting belief will also be Gaussian.
The speaker explains how to combine exponential functions to form a new Gaussian distribution and demonstrates the process of marginalization.
The predicted belief in the Kalman filter is a Gaussian distribution, which is obtained by multiplying two Gaussian distributions together and normalizing the result.
The Kalman Filter and Extended Kalman Filter rely on the assumption that the system remains in a Gaussian world, allowing for recursive updates and evolution of the state over time.
The Kalman filter maintains Gaussian distributions by representing them with mean and covariance matrices, and the algorithm involves deriving the mean and covariance matrix of the current belief based on previous beliefs and Gaussian distributions.
The speaker explains the importance of exploiting the fact that the marginal and conditional distributions of a Gaussian distribution remain Gaussian, and discusses the use of mathematical tools such as matrix inversion and probability theory to compute the mean and covariance of these distributions, leading to a concise algorithm.
33:43 The Kalman Filter algorithm updates the state by predicting and updating the mean and uncertainty using matrix operations and weighted sums, reducing uncertainty through new observations.
Derive the Kalman filter algorithm in five lines by approaching it from the linear algebra or probability theory point of view.
The Kalman filter evolves the state by predicting the mean and covariance matrix at time t based on the previous mean and uncertainty, and then updating them using the control command and observation.
The uncertainty of Gaussian distributions changes when squeezed through a linear function, with a prediction step involving matrix multiplication and addition of noise, followed by a correction step that computes a weighted sum of two Gaussian distributions using the Kalman gain.
Weighted prediction and correction are used in the Kalman Filter to update the belief based on observations and the uncertainty of those observations.
We use the Kalman gain to update our predicted belief and covariance matrix based on the difference between the actual observation and the predicted observation, taking into account the uncertainty and reducing it through new observations.
39:41 The Kalman Filter is a method that combines Gaussian distributions to predict motion and obtain new observations, but it assumes linearity and Gaussianity, which may not hold in realistic systems.
A probability distribution with a smaller variance has a stronger impact on the final belief, as seen in the illustration, where the blue curve, representing the correction step, is closer to the green curve, representing the measurement, due to higher trust in the measurement, resulting in a smaller uncertainty in the final gaussian distribution.
The prediction step increases uncertainty by adding additional sources of uncertainty through motion, while the measurement step reduces uncertainty by providing new information, resulting in a combination of increased and reduced uncertainty in most real-world situations.
The Kalman Filter is a weighted mean of two state estimates based on their uncertainty, leading to a new belief, and can be used to predict the system's motion and obtain new observations.
The Kalman filter combines Gaussian distributions in a recursive fashion, assuming that the prior belief, observation model, and motion model are all Gaussian and linear.
The assumption that everything is Gaussian and that every model is linear is often violated, particularly in regards to linear motion and observation models.
Realistic systems often involve non-linear functions, which violate the assumptions of the Kalman filter, so we need to find ways to deal with these non-linearities by using different functions.
45:49 The Kalman Filter cannot handle non-linear functions, so the Extended Kalman Filter uses linearization and partial derivatives to approximate and account for non-linearities.
A gaussian distribution is transformed through a linear function, mapping each point to a new location on the x-axis.
The speaker explains how using nonlinear functions to transform a Gaussian distribution can lead to a resulting distribution that is not Gaussian, thus challenging the assumption of linearity.
The problem with the Kalman filter is that it cannot handle non-linear functions, so we need to find ways to modify the algorithm to account for this.
To deal with non-linearities, one approach is to locally linearize the function by computing the first derivative at a specific point and treating it as a linear function, known as Taylor expansion.
Evaluate the function at the linearization point by adding the jacobian of the first derivative of the function with respect to the state, and compute the jacobian of the function with respect to the variable, to determine the distance between the variable and the linearization point.
The speaker explains the concept of linearization and the use of partial derivatives in the Kalman Filter and Extended Kalman Filter.
53:01 Linearization in the Kalman filter allows for state estimation by approximating non-linear functions with Gaussian distributions, with the error depending on the similarity of curves and uncertainty, while the performance of the filter is influenced by the uncertainty and similarity of control and observation models.
The speaker explains how linearization is used in the Kalman filter for state estimation, with the Jacobian being a generalization of the gradient or first derivative in multiple dimensions.
The speaker explains how local linearization works by choosing a linearization point and approximating a non-linear function with a linear function.
The speaker explains that by linearizing a non-linear function, a Gaussian distribution can be used to approximate the function, although it may not be perfect.
The approximation error in performing a local linearization depends on the similarity between the red and blue curves and the uncertainty of the input function, with larger errors occurring when the curves deviate strongly and when there is a larger distribution of probability mass away from the linearization point.
The smaller the uncertainty of a Gaussian distribution, the smaller the error in the output, as illustrated by the difference between two Gaussian curves.
The uncertainty and similarity between the control and observation models affect the performance of the Kalman filter.
58:40 The extended Kalman filter algorithm uses linearized models to track the motion of a system, mapping sensor readings into the state space, but it may fail in cases of large uncertainties or when non-linear models cannot be well approximated.
The linearized motion and observation models are used in the extended Kalman filter algorithm, with minimal changes to the original Kalman filter algorithm, allowing for the use of non-linear models.
The speaker discusses the use of linearized models in the Kalman filter and extended Kalman filter algorithms, and explains the impact of perfect sensor observations on the state space.
The inverse of the observation model's Jacobian matrix is used as the common gain to map the sensor reading into the state space, resulting in the observation being directly mapped into the state space and the remaining state being determined by the sensor.
If the sensor provides no information, the Kalman gain will be a matrix filled with zeros, resulting in the current belief being equal to the predicted belief, which makes sense if the sensor is unreliable.
The video demonstrates how the Extended Kalman Filter can accurately track the motion of a system by integrating predictions and observations, allowing for localization.
The extended Kalman filter is a variant of the Kalman filter that handles non-linearities by local linearizations, and while it is a standard tool for state estimation, it may fail in cases of large uncertainties or when non-linear models cannot be well approximated by a linearized function.



Localization
Robot localization is the process of determining a robot's position and orientation in the world using sensor data and knowledge of its movements, often using probabilistic approaches to account for uncertainties.
00:00 Robot localization is the process of determining a robot's position and orientation in the world using sensor data and knowledge of its movements, often using probabilistic approaches to account for uncertainties.
The lecture provides an overview of robot localization techniques, explaining that localization is the process of determining the robot's or vehicle's location in the world.
Knowing the position and orientation of a robot is crucial for effective navigation, and localization aims to answer the question of where the robot is in relation to a given reference frame using sensor information and knowledge of the robot's movements.
Localization in robotics involves estimating the robot's position and orientation in the environment using sensor data, such as cameras or GPS, and can be done with or without a map as a reference frame.
Robot localization is the process of using sensor information and control commands to estimate the position of a robot or vehicle with respect to a map or reference frame, often using probabilistic approaches to account for imperfect observations and motion commands.
The probabilistic approach to robot localization allows for the representation of uncertainties in the platform's motion command execution, estimating the platform's position and heading in the environment through state estimation.
We need to estimate a three-dimensional or six-dimensional vector to determine the current location of the platform, which includes the xy coordinates, heading, and rotational angles.
08:13 Robot localization is the process of estimating a robot's position and heading, taking into account uncertainties, using recursive state estimation techniques and either recursive filtering or global localization methods, with the choice depending on the need to represent uncertainties and handle large uncertainties and multi-modalities, and online localization being more commonly used for navigation decisions.
The speaker explains that in robot localization, the goal is to estimate the probability distribution of the platform's position and heading information, taking into account the uncertainty of the estimate.
We estimate the probability distribution of the robot's current location using recursive state estimation techniques, such as the base filter, based on observations and control commands received.
The current belief in robot localization is based on the previous belief and the current control command and observation, with the motion model describing the likelihood of ending up at a certain state given the previous state and executed motion command, and the observation model describing the likelihood of receiving a certain observation given the current state.
Localization systems can either be based on recursive filtering or global localization, with the former being simpler as it starts from a known position and has less ambiguity about the environment.
The choice of localization techniques depends on the need to represent uncertainties, whether it is for post-tracking or global localization, and the ability to handle large uncertainties and multi-modalities.
Offline localization uses all available sensor data to estimate the system's location at a given point in time, while online localization only uses data up to the current time step to estimate the current location, with online localization being more commonly used for making navigation decisions.
15:55 Robot localization is the process of determining a robot's position using sensor data, such as visual odometry and laser range finders, to estimate movement and direction.
Localization is the process of determining the robot's position using sensor data instead of wheel encoders, by aligning sensor observations with each other.
Visual odometry is a method of estimating the trajectory of a camera based on feature points extracted from consecutive frames, often combined with inertial sensing to relate camera positions.
We can match features between images to determine the camera's movement and direction, but without a stereo camera or imu, we can only determine the camera's location up to scale.
The speaker discusses the use of point-based estimation techniques, such as the five-point algorithm or eight-point algorithm, along with outlier rejection techniques, to create a robust visual odometry system for robot localization using camera information.
Using a lighter odometry technique, such as incremental scan matching with a laser range finder, allows for estimating the movement of a platform without the need for an IMU, providing scale information and a six-degree of freedom transformation.
20:43 Robot localization involves using sensor observations and different techniques such as markov localization, grid localization, and monte carlo localization to estimate and reduce uncertainty in a robot's position, with the use of histograms to represent the belief about the robot's location in the environment.
Odometry provides relative motion estimates based on sensor observations, which can be used to estimate and reduce the uncertainty of a robot's position, supporting localization.
There are four different approaches to localize a mobile robot, including markov localization, grid localization, monte carlo localization, and non-prometric localization.
Kalman filter and least squares approaches, including sliding window, are popular techniques for robot localization, with sliding window being advantageous for fusing different sensing modalities.
Color localization, monte carlo localization, common filter based localization, markov localization, and grid localization are different techniques used to represent the belief about the platform's location in the environment.
The speaker explains how robot localization works by using a histogram to estimate the probability of the robot's position in a given environment.
25:15 Global and Monte Carlo localization are two approaches to robot localization, with the former using a histogram and the latter using random samples as state hypotheses.
This approach easily handles multimodal beliefs by assigning a probability value to each cell, but it has limitations in terms of accuracy.
The accuracy of robot localization is determined by the size of the cells used, with larger cells limiting the precision, and while this approach is not commonly used for 3D localization due to memory constraints, it is still used for 2D localization despite the computational cost of updating all cells.
The speaker explains two approaches to robot localization: global localization using a histogram to estimate the robot's position based on sensor observations and motion, and Monte Carlo localization using random samples as state hypotheses.
28:24 The robot's position in the environment is represented using random samples, with closer samples being more accurate, and different techniques like monte carlo and gaussian-based filter localization are used to estimate the robot's location.
The system uses random samples to represent the belief about the robot's position in the environment, allowing for initialization and amplification of the samples based on observation likelihood.
Samples that are closer together in space are more likely to be accurate representations of the environment.
The robot's movement in the environment is represented by clusters of beliefs, with more samples in a region indicating higher likelihood, making monte carlo localization a popular technique for representing multimodal beliefs in indoor environments without GPS.
Gaussian-based filter localization is commonly used to estimate the location of a robot by updating gaussian distributions using a kalman filter, particularly when localizing landmarks.
Localization techniques can be based on carbon filter or least squares approaches, with the latter being an offline method that uses all sensor information to compute the trajectory and is often used as a reference for comparing online localization systems.
32:55 Factor graphs are a popular visual representation for robot localization, allowing for the estimation of poses and landmark locations using observations and odometry factors, with the sliding window approach being a balance between accuracy and computational resources.
Factor graphs are a popular graphical representation for estimating poses and landmark locations in robot localization, using observations and odometry factors to track the system's evolution over time, with the possibility of incorporating GNSS or GPS information.
Factor graphs are a useful visual representation for solving localization problems in robotics, allowing for the minimization of errors and the transformation into a matrix or information matrix, while sliding window-based approaches consider only the most recent observations.
The speaker discusses a technique called sliding window approach, which is used for robot localization and is a balance between the computationally expensive least squares approach and the less accurate Kalman filter approach.
The size of the sliding window can be adjusted to control computational resources and solve the localization problem using either a Kalman filter or an online least squares approach.
Approximations are made to discard old information in a graph structure used for localization in an autonomous car driving system, where observations of buildings, poles, corners, and road markings are used to build a factor graph.
Localization is a crucial element in autonomous vehicles and mobile robots, as it allows for efficient navigation and completion of various tasks, and there are different variants and techniques for localization, such as grid-based or macro localization.
39:28 Kalman filter, monte carlo localization, and least squares are commonly used techniques in modern localization systems, with the former two being base filter-based approaches and the latter being a sliding window approach.



Particle filter
Particle filters, specifically Monte Carlo localization, offer a flexible and effective approach for estimating the position of a robot in its environment, allowing for accurate tracking and navigation even in dynamic situations.
00:00 Monte Carlo localization is a particle filter approach that estimates the location and orientation of a mobile platform using non-parametric samples to represent the system's location, allowing for flexible and efficient state estimation.
Monte Carlo localization is a particle filter approach that estimates the location and orientation of a mobile platform without restricting itself to parametric probability distributions like Gaussian distributions.
The particle filter replaces the parametric Gaussian distribution with non-parametric samples to represent the system's location, allowing for flexible and efficient state estimation.
An arbitrary function can be approximated using samples, where the density of samples in an area represents the probability of the system being in that area.
Weighted samples can reduce the number of samples needed to represent a function by assigning larger weights to samples in areas of high probability, resulting in a representation that emphasizes the importance of weight over frequency.
Weighted samples are used to represent the probability distribution of a one-dimensional robot's location, and a sufficient number of samples is needed to accurately approximate the function and estimate the belief about the robot's position and orientation in the environment.
The state hypothesis in particle filter represents the belief of the system's location, with each hypothesis having a weight that determines the probability of the system being located there, and the particle filter uses a weighted sum of direct impulses to approximate a smooth probability distribution.
09:45 Particle filters and Monte Carlo localization can generate samples from non-Gaussian functions by representing them with a set of samples and using important sampling principles.
We can use particle filters and Monte Carlo localization to generate samples from a given function, even if it is non-Gaussian, by representing the function with a set of samples and using closed form sampling for a limited number of functions.
To generate random numbers from a Gaussian distribution, one can approximate it by taking 12 random numbers between minus and plus the desired standard deviation, adding them up, and dividing the result by 2.
The important sampling principle allows us to generate samples from a different distribution than the one we want, as long as we compensate for any mistakes made.
You can estimate samples from a target function by generating samples from a proposal function and compensating for the difference in function values, using the important sampling principle.
The blue curve must be larger than zero at all locations where the target is larger than zero, and the red curve must also be larger than zero.
Drawing samples from a function and assigning weights based on the function values allows for approximation of a non-Gaussian distribution in the particle filter for state estimation.
16:17 The particle filter is a versatile filter that can estimate the state of dynamic systems without relying on specific distributions, using a three-step algorithm involving sample generation, motion and observation, and resampling to improve estimation.
The particle filter is a recursive base filter that can estimate the state of dynamic systems without relying on specific distributions, making it suitable for non-Gaussian distributions and non-linear models.
The particle filter algorithm consists of three steps: generating samples, taking motion and observation into account, and using a larger number of samples for better estimation.
The particle filter consists of a prediction step where samples are drawn from a proposal distribution and a correction step where the weight is computed based on the observation model to compensate for the mismatch between the target and proposal distributions.
The weight of the proposal distribution is determined by how we select the motion model, which is a user-defined choice in the context of particle filter and Monte Carlo localization.
The resampling step in particle filter and Monte Carlo localization involves drawing samples from a weighted sample set with replacement, where the probability of drawing a sample is proportional to its weight, resulting in uniformly weighted samples that represent the same distribution as the original weighted samples.
Particles with low weights are eliminated and replaced with samples in areas of high probability in order to better approximate the probability distribution, making the resampling step an important part of the particle filter algorithm.
23:43 Particle filter and Monte Carlo localization is an effective algorithm for state estimation, using a sample set to predict and correct the system's state based on motion and observation, with weighted samples and resampling steps.
The speaker explains the process of using a sample set to predict and correct the state of a system based on motion and observation, repeatedly updating the sample set with weighted samples.
The particle filter algorithm involves drawing and re-weighting samples, followed by a resampling step, in order to represent belief at a given time, with the user defining the proposal distribution and computing the weight to account for discrepancies between the target and proposal distributions.
Particle filter and Monte Carlo localization is a promising and effective algorithm for state estimation, where multiple samples are used to obtain a belief or probability distribution of the platform's position and orientation.
Each particle in the particle filter represents a hypothesis about the state of the system, and the motion model is used to generate new samples by estimating the current position based on the previous position and motion command, while the observation model is used to calculate the likelihood of obtaining an observation given the current position and map of the environment.
The particle filter algorithm for localization involves generating hypotheses, evaluating the likelihood of observations based on the particle's position, and using motion and observation models to update the particle's position.
The waiting step increases the weight of samples at a specific location, resulting in high weights for those samples and low weights for others, and the resampling step replaces weights with frequencies, duplicating samples that were located in a certain area.
36:43 Particle filter uses resampling to condense and replicate particles based on their weight, allowing the system to estimate its position and converge to a unimodal belief, with the resampling step involving drawing samples proportional to their weight using a red wheel sampling method or stochastic universal resampling for faster and more efficient sampling.
Particles in a particle filter are condensed and replicated based on their weight during the resampling step, resulting in a smaller number of samples with high weight and a majority of samples with lower weight.
The majority of samples representing the position of a mobile robot in a symmetric corridor environment converge to identify the robot's location through repeated sampling and resampling.
The system uses motion, observation, and resampling to estimate its position and identify the correct hypothesis, converging to a unimodal belief.
To represent multimodal distributions and move samples into more likely areas of the state space, the resampling step in particle filter involves drawing samples proportional to their weight with replacement, using a red wheel sampling method where the larger buckets on a roulette wheel represent the more likely samples.
Generate new samples by repeatedly drawing particles with replacement, using roulette wheel sampling or low variance resampling, which can be done efficiently with a computational complexity of O(j log j).
The modified roulette wheel method, called stochastic universal resampling, uses multiple arrows with equal spacing to determine the chosen bucket, resulting in faster and more efficient sampling.
46:01 Stochastic universal resampling is preferred over regular resampling in particle filter sampling as it keeps the sample set the same with identical weights and is faster, while Monte Carlo Localization has become the standard approach for indoor mobile robot localization.
Stochastic universal resampling is superior to standard resampling because it eliminates samples in low areas of the state space and duplicates samples with high weights, resulting in suboptimal output when all samples have the same weight.
Resampling in particle filter enhances the process by increasing the probability of drawing certain samples, while stochastic universal resampling is preferred over regular resampling as it reproduces the same sample set without hurting belief and is faster.
To efficiently implement the process of advancing to the next sample, a random number is drawn between 0 and 1, and then compared to the sum of weights in each bucket to determine the starting point.
The speaker explains how to efficiently perform sampling with replacement using a cumulative array and a random number generator.
Use stochastic universal resampling for particle filter sampling as it keeps the sample set the same in case of identical weights and is fast to compute.
The speaker discusses the use of motion and observation models in Monte Carlo Localization, showcasing examples of robots that have implemented this method, such as the Rhino and Albert robots, which have made Monte Carlo Localization the standard approach for indoor mobile robot localization.
54:45 Particle filters and Monte Carlo localization are versatile methods for estimating and tracking the position of a system, but they have limitations in high dimensional state spaces and require a sufficient number of samples to avoid divergence.
The particle filter algorithm is used to estimate the position of a system by integrating observations and motion commands, with the probability mass converging to the correct location and some samples dying out in unlikely regions of the state space.
The Monte Carlo localization technique allows a system to estimate and track its pose over time by performing motion and weight updates, making it a versatile method for robot localization in both indoor and outdoor environments.
Particle filters have limitations when dealing with high dimensional state spaces, as the number of samples needed to represent the probability distribution grows exponentially with the dimensionality, requiring significant computational resources or simplifications to be made.
Particle filters can handle non-Gaussian distributions well, but they may suffer from the particle depletion problem and diverge if the number of samples is too small.
Particle filter is a versatile and robust method that can handle high dimensional spaces, data association ambiguities, incorporate additional knowledge easily, integrate multiple sensing modalities, perform well even with imperfect models, and is relatively easy to implement compared to other filters.
Particle filters are a recursive implementation of a filter that can handle non-parametric distributions and non-linear motion models, making them suitable for real-time estimation and addressing high-dimensional state spaces.
01:02:22 Particle filters and Monte Carlo Localization (MCL) are effective techniques for accurately estimating and tracking the position of a robot over time, especially in indoor environments with multimodal beliefs and limited external sources.
We represent our belief about the position of the robot using a set of samples, drawing from a proposal distribution and adjusting for the difference between the target and proposal distributions.
Implementing a particle filter with appropriate motion and sensor models is crucial for accurate state estimation, and Monte Carlo Localization (MCL) using particle filters has proven to be a robust and efficient technique for mobile robot localization, especially in indoor environments with multimodal beliefs and limited external sources.
Monte Carlo localization estimates and tracks the position of a platform over time by using a particle filter and motion and observation models.



Robot control
Robot control involves different levels of control, such as trajectory, position, and motor control, and can be achieved through various methods including PID control and advanced algorithms, with the goal of achieving desired performance and meeting specific requirements.
00:00 The lecture discusses different levels of robot control, including trajectory, position, and motor control, as well as the use of PID control and advanced algorithms for specific performance requirements, and explains the concept of feedback control using the example of adjusting the temperature of a shower.
The lecture discusses different levels of robot control, including trajectory, position, and motor control, as well as the use of PID control and advanced algorithms for specific performance requirements.
The lecture discusses the representation of the world for a robot, including techniques for creating a map of the environment and modules for localization, as well as the use of actuators and sensors for the robot's interaction with the world.
The lecture discusses three levels of control in robot control: motor control, position control, and trajectory control, and how these levels are linked to achieve tasks in autonomous systems.
A dc motor can be controlled by adjusting the power input using pulse width modulation, where the duty cycle determines the speed of rotation.
In robotics, open loop control is not always accurate due to calibration issues, so feedback control, which involves sensing and adjusting based on observed movement, is a smarter and more effective approach.
The speaker explains the concept of feedback control using the example of adjusting the temperature of a shower, where the desired temperature is 35 degrees, the current temperature is 30 degrees, and the control is a knob that can be moved left or right to add hot or cold water until the desired temperature is reached.
12:37 Proportional control is a simple method for robot control, but adjusting control parameters is necessary to mitigate noise and measurement errors, while also considering system limitations such as saturation, delays, and dead time.
The controller function is designed to use the error signal, which is the difference between the desired and measured values, to produce a control signal for the system, taking into account that not all states may be observable and that the system model may have simplifications and errors.
The simplest controller for robot control is proportional control, where the control input is a constant multiplied by the error signal, and this control law can be applied to regulate the temperature of a shower by adjusting the amount of heat added to the water.
Noise in the system and measurement errors can prevent a robot from reaching its desired state, so adjusting the control parameters can help mitigate these issues.
Lower gains can help reduce noise in a system, but it may take longer to reach the desired state, while higher gains can amplify errors and lead to instability, and flipping the sign of the error can also result in undesired outcomes.
There are limits to robot control due to the physics of the system and the environment, including saturation and delays, which can result in overshooting and being behind the desired position.
Dead time, or delays in a system, can be addressed using the Smith predictor method, which involves using a virtual model to predict system movement and incorporating measurements from the real system with delay estimations to feed back into the controller.
32:05 Underestimating delay in robot control is recommended to avoid oscillation, and proportional control can be applied to achieve precise rotation speed, but it does not work for controlling the motion of a car.
The speaker discusses the issue of overestimating or underestimating delay time in robot control, which can lead to oscillations and the need to avoid them.
Underestimating the delay in robot control is recommended to avoid oscillation, even though it may result in reaching the state later than expected.
The speaker explains the concept of proportional control and how it can be applied to motors to achieve precise rotation speed despite noise and delays.
The goal of position control is to drive a robot to a specific position and stop there, and the first step is to understand the kinematics of the motion.
The speaker explains a simple model for robot control, where the new position is determined by the previous position plus the velocity multiplied by the time interval, and discusses the goal of reaching a specific position and staying there.
Proportional control does not work for controlling the motion of a car because it does not account for the car's velocity, leading to overshooting and oscillatory behavior.
39:17 PD control combines proportional and derivative control to smoothly reach a desired position with zero velocity, while a PID controller combines proportional, derivative, and integral control to achieve desired performance in controlling a motor, and trajectory control in robotics involves perception, motion planning, longitudinal and lateral control, and actuation.
The speaker explains the concept of pd control, which combines proportional and derivative control to smoothly reach a desired position with zero velocity, using two signals: one from the position error and one from the velocity error.
Setting the gains too high in a control system can result in overshooting and inability to stop, while setting them too low can lead to slow reaching of the desired position, and systematic biases such as unequal wheel sizes or weight distribution can cause the robot to consistently turn in one direction.
The integral term in robot control helps to compensate for systematic bias errors by computing the differences between the desired state and the current state and accumulating them over time to generate control and bring the system back to the desired state, but it should be used with caution to avoid wind-up effects.
To prevent excessive control and accumulation of errors, a small window of time is used to compute errors in robot control, and the addition of derivative terms helps bring the robot closer to the desired position.
A PID controller consists of three parts (proportional, derivative, and integral) that can be combined to achieve desired performance in controlling a motor, with the proportional part used for faster goal attainment, the derivative part for minimizing oscillation and overshoot, and the integral part for addressing systematic bias, although determining the correct gains may require trial and error or other methods.
The speaker explains the concept of trajectory control in robotics, where a car or any other system smoothly follows a predetermined path using perception, motion planning, longitudinal control for velocity, lateral control for staying close to the path, and actuation through acceleration and steering.
55:53 The trajectory generation for a robot involves considering curvature and kinematics, controlling steering angle and meeting certain criteria, such as smooth movement and restrictions, using a PID controller and cascaded control.
The trajectory generation for an autonomous car involves sampling uniformly on a given trajectory to obtain a useful trajectory.
To ensure smooth movement and control in a robot, it is important to consider the curvature of the trajectory and the kinematics of the car's steering system, which involves having one point of rotation for all wheels to prevent skidding and allow for accurate estimation of the system's evolution.
We need to control the steering angle and generate controls that meet certain criteria, such as having an instantaneous center of rotation and ensuring smooth movement, while also considering restrictions on our control.
Considerations for controlling a robot include maximum velocity and steering limits, and separate longitudinal and lateral problem solving can be done using a PID controller to achieve desired states.
To ensure smooth lateral control of a vehicle, it is important to use a PID controller along with kinematics and constraints, such as setting the steering angle as the tangent inverse of a specific value, in order to follow a circular arc and intersect the desired path at a certain distance.
The speaker explains the concept of cascaded control, where different controls are performed at different frequencies to ensure smooth and accurate robot movement.
01:06:52 Design goals for robot control include accuracy, safety, robustness, fast response time, and ease of maintenance; advanced control techniques like optimal control and quadratic linear controller treat control as an optimization problem, while robust control techniques are also mentioned; designing a controller involves accounting for errors, adapting to changing parameters, implementing failsafe control, and exploring learning-based techniques.
Design goals for robot control include accuracy, safety, robustness to noise, fast response time, and ease of maintenance and transferability to new systems.
The lecture discusses advanced control techniques such as optimal control and quadratic linear controller, which treat control as an optimization problem, and also mentions robust control techniques.
Designing a controller involves accounting for measurement and system prediction errors, adapting to changing system parameters, implementing failsafe control, and exploring learning-based control techniques.
Optimal control poses the control problem as an optimization problem, with the objective of minimizing error and control movement, and the linear quadratic regulator provides a closed form solution for the best control based on the system's properties and weighted error and control factors.
You can control a robot by adjusting the weights for position and orientation, and for non-linear systems, you can use linearization or model predictive control to find optimal solutions within a small window of time.
Nonlinear control allows for difficult automated movements, while adaptive control is used to estimate and adapt to changes in a system over time.
01:17:57 Learning-based control techniques, such as using examples and feedback, are explored to improve the trajectory and compensate for disturbances in robots, while fail-safe controls ensure minimum performance even in the event of catastrophic failure.
Robust control techniques provide guarantees on performance despite noise, while adaptive control focuses on the system's parameters, and learning-based approaches are also explored.
Learning-based control involves using examples to understand and predict the dynamics of a system, either at the system level or the controller level, as demonstrated with a quadrocopter.
The controller of the robot learns from feedback and previous performance to improve its trajectory and compensate for external disturbances, either through learning with demonstrations or learning from past experiences.
The car successfully parallel parks by combining physics-based systems with simulations and demonstrations, making a difficult maneuver easier to model and achieve.
The robot has fail-safe control where if one of the propellers breaks, it smoothly comes down instead of falling from the sky.
Fail-safe controls ensure minimum performance even in the event of catastrophic failure, and the lecture covered low level control, feedback control, PID controllers, path following, advanced control methods, and using learning from previous experiences to improve performance.
01:25:06 Check out these sources for more information on robot control and different topics covered in the video.



Robot motion planning
The A* algorithm is a powerful tool for robot motion planning, allowing for efficient and optimal path finding in dynamic environments while considering uncertainties in motion execution.
00:00 Robot motion planning involves finding a collision-free path for a robot to reach its target location using the A* algorithm, considering dynamic environments and uncertainties in motion execution, and using a layered architecture with planning, collision avoidance, and control algorithms.
This lecture discusses motion planning for robots, specifically how they make decisions on where to navigate in order to reach a target location, using the A* algorithm to generate an optimal sequence of motion commands or states.
In robot motion planning, the goal is to find a collision-free trajectory that allows the robot to reach its target location as quickly as possible, taking into account dynamic environments and making assumptions about the movements of other objects.
The A* algorithm is a popular and effective search algorithm used in robotics for generating a sequence of states to navigate from a start to a goal location, with extensions and variants available for real-time optimization, re-planning, and accounting for uncertainties in motion execution.
Consider uncertainties in action execution and perception, react quickly to unforeseen obstacles, and use a layered architecture with planning, collision avoidance, and control algorithms to guide the robot's motion.
The standard motion planning problem involves finding the shortest collision-free path from a start configuration to a goal configuration, taking into account the robot's description and the environment.
The algorithm found an optimal solution to the planning problem, and the next topic is the configuration space.
16:52 Robot motion planning involves determining collision-free paths in a configuration space, using either combinatorial discretization or sampling-based techniques, with search algorithms guiding the robot from its current state to its goal state.
A robot's motion planning is done in a configuration space, which takes into account the robot's position, orientation, and joint angles to determine if a certain configuration is collision-free.
The lecture discusses the concept of a discretized configuration space and how it is used in robot motion planning to plan a path from a start location to a goal location while avoiding obstacles in the workspace.
The function A of q maps the robot's configurations to the workspace, determining if there will be a collision with obstacles, and the free space is defined as the configurations where the shape of the robot does not intersect with any obstacles.
The goal is to find a path in the configuration space that connects the initial and goal configurations without colliding with obstacles, which can be achieved by mapping a function from zero to one that only maps into the free space.
The speaker discusses two approaches to robot motion planning: combinatorial discretization for low-dimensional spaces and sampling-based techniques for higher-dimensional spaces, with the latter being more efficient by sampling promising configurations.
Search algorithms are used to find a sequence of configurations that guide a robot from its current state to its goal state, with uninformed search techniques being the simplest form of search algorithms.
27:38 Uninformed search blindly explores the configuration space, while informed search like A* uses heuristics to find optimal solutions; completeness, optimality, time complexity, and space complexity are important criteria for evaluating search algorithms.
Uninformed search techniques blindly search through the configuration space without utilizing additional information, while informed search techniques, such as A*, use heuristics and knowledge about the environment to guide the search.
Heuristics estimate the cost of reaching a goal configuration, and informed search techniques use these estimates to find optimal solutions more quickly, with criteria for evaluating search algorithms including completeness, optimality, time complexity, and space complexity.
Completeness means the algorithm finds a solution if it exists, while optimality refers to finding the best possible solution under a specified cost function, and considerations of time and space complexity are based on the number of states or transitions.
The speaker explains the breadth-first search algorithm, where the configuration space is expanded level by level to find the smallest number of states needed to reach the goal configuration.
Breadth-first search is an optimal and complete algorithm for robot motion planning, while depth-first search is not optimal and may not find the shortest path, especially in infinite spaces.
Uniform cost search is an optimal and complete algorithm that expands nodes based on their accumulated path cost, making it similar to breadth-first search but with different costs for transitions, and it is also related to Dijkstra's algorithm.
43:27 Informed search techniques, like A*, use heuristics to estimate the cost to reach the goal configuration, allowing for quicker and more efficient robot motion planning.
Informed search techniques use additional knowledge encoded in a heuristic function to estimate the cost from an input configuration to the goal configuration, allowing for quicker and more efficient finding of the goal configuration compared to uninformed search techniques.
Informed search techniques, such as greedy search, use heuristics to find the most promising nodes that are likely to lead to the goal location faster, based on cost estimates.
The h function in A* algorithm provides an estimate of the cost to reach the goal, allowing for quicker solutions, but it may not guarantee the optimal solution, so a combination of uniform cost search and greedy search can be used to improve the algorithm.
A* algorithm combines uniform cost search and greedy search by considering the accumulated path cost and a heuristic to determine the most efficient path to the goal.
A* is an optimal and complete algorithm developed in the robotics community, specifically at Stanford Research Institute, and is now the gold standard algorithm in AI for informed search and planning systems.
The algorithm provides a sequence of configurations for the robot to follow from its current location to the goal location, using a heuristic based on the straight line distance as a lower bound for the length of the path.
53:36 The A* algorithm in robot motion planning expands nodes based on cost estimates to find the optimal path, considering both accumulated path cost and a heuristic estimate, while ensuring the heuristic is admissible for an optimal solution.
The system expands nodes based on the combination of actual and predicted costs to find the optimal path from the start to the goal location.
A* algorithm guides the search towards the goal by expanding nodes based on their promising paths, minimizing the cost by considering both the accumulated path cost and a heuristic estimate.
A* uses the f cost, which is the sum of the g cost and the h cost, to find the smallest sum and expand the node with the smallest f cost, but the heuristic h must have certain properties to find the right solution.
The estimated cost must always be smaller than the actual cost in order to have an admissible heuristic and guarantee an optimal solution in A* motion planning.
Overestimating or underestimating the heuristic in robot motion planning can lead to faster but suboptimal solutions, depending on the trade-off between speed and optimality.
A* algorithm uses a priority queue to expand the search tree and find the cheapest path, considering both the optimal cost and computational efficiency.
01:03:10 Implementing the A* algorithm for robot motion planning requires specifying path cost and an admissible heuristic, taking into account the accuracy of robot localization and motion execution, and making the planning process less sensitive to slight variations in order to be more robust.
Start with the initial configuration of the robot, pick the node with the smallest f cost from the open list, expand and add it to the search tree, remove it from the open list and add it to the closed list, check if it is the goal configuration, and continue expanding nodes until the goal is found.
Look at the neighbors of the current node, add any unvisited neighbors to the open list, update the cost if a cheaper path is found, and continue expanding the cheapest node until the goal is reached.
Implementing the A* algorithm for robot motion planning requires specifying path cost and an admissible heuristic, and while it can be applied to robot navigation out of the box, small tweaks may be necessary for better results, especially in 2D grid maps; however, it is important to revisit assumptions, such as the robot knowing its own location, to ensure their validity in real-world robotics.
The accuracy of robot localization and motion execution must be taken into account when planning robot motion, as assumptions about map correctness and sensor precision may not always hold true.
Avoid driving too close to walls as even a small deviation can lead to a collision, so it is important to reassess assumptions and make the planning process less sensitive to slight variations in order to be more robust, such as increasing the safety distance to obstacles.
To avoid the robot being guided too close to obstacles, one approach is to expand the obstacles in the map by a certain distance, but this may not be feasible in narrow passages, so a trick is used to partially expand the obstacles while still maintaining a safety distance.
01:15:17 Convolution can be used to smooth occupancy values in a map, allowing the robot to navigate more precisely and avoid obstacles, while A* planning with optimal heuristic can be reduced to gradient descent for fast motion planning.
We can use convolution to smooth the occupancy values in a map, increasing the cost for the robot to go to occupied spaces and making it cheaper to go to free spaces.
The system will try to avoid certain cells, but if there is no other path, it will go through the center of the door frame to maximize distance from the walls.
Performing planning in a convolved grid map, using a binomial kernel for smoothing, allows the robot to avoid obstacles and navigate more precisely.
Inflating obstacles in the environment and planning in this type of map leads to navigation behaviors that maintain a safety distance from obstacles, resulting in more reliable motion execution.
Compute the true cost for a given configuration using Dijkstra's algorithm to get the optimal heuristic for A* planning, which is more efficient when re-planning to the same goal location.
The cost increases as you move further away, and if the environment remains constant, A* with the optimal heuristic can be reduced to a gradient descent for fast motion planning.
01:23:00 Robot motion planning using A* algorithm allows for smooth trajectory generation, considering velocity constraints and optimizing the heuristic for faster planning in high dimensional state spaces.
Planning in high dimensional state spaces, such as considering velocities and acceleration, can improve trajectory generation but may lead to larger planning problems.
The speaker discusses the need to consider velocity constraints in robot motion planning and the challenge of executing the planning system at high frequencies, suggesting a hierarchical approach to explore a restricted part of the state space.
The speaker explains how they use sensor information to update a grid map, perform planning in a two-dimensional space, and optimize the trajectory in a five-dimensional configuration space.
Pre-computations are done to optimize the heuristic for faster robot motion planning, by building a 5D space around the 2D path and using an optimal heuristic to guide the search.
The video demonstrates how a robot can navigate through an environment, avoiding obstacles and taking into account kinematic constraints, by generating a smooth trajectory using A* motion planning algorithm.
A* is an effective algorithm for path planning in robotics, allowing for optimal or near optimal trajectories to be generated quickly, making it the gold standard in the field.



Markov decision process
Markov Decision Processes (MDPs) are a powerful tool for planning under uncertainty, allowing for optimal decision making by considering the stochastic environment, rewards, and potential future rewards to find the optimal policy that maximizes expected utility over time.
00:00 Markov Decision Processes (MDPs) are necessary for planning under uncertainty, as they account for situations where actions may not be executed as planned, and while computationally costly, they guarantee desired outcomes when standard planning algorithms cannot.
Planning under uncertainty requires the use of Markov Decision Processes (MDPs) to account for situations where actions may not be executed as planned, and while MDPs can be computationally costly, they are necessary when standard planning algorithms cannot guarantee desired outcomes.
Assuming correct knowledge about the world, uncertainty arises when executing actions, resulting in a partially observable Markov decision process (POMDP).
In robot navigation, finding the optimal path is important, but it is crucial to ensure that the underlying cost function leads to the desired behavior and avoids collisions.
The video discusses challenges in dealing with unforeseen objects, predicting object behavior, and uncertainties in motion execution in the context of Markov decision processes for planning under uncertainty.
The planning level of the system takes into account the imperfect execution of commands by generating trajectories that guide the robot away from obstacles to prevent collisions.
An agent or robot navigating an environment with obstacles and a goal state must consider imperfect action execution when determining the best path to reach the goal.
07:10 A planning system is needed to account for imperfections in execution and make better decisions, such as a mobile robot taking a longer detour to avoid obstacles and increase the probability of reaching the goal.
Given that a system is not perfect and may not always execute desired commands, the question is how to create a planning system that takes this imperfection into account and makes better decisions, such as a mobile robot or a satnav device providing improved instructions to account for errors in execution.
This lecture discusses decision making under uncertainty and how to optimize behavior in order to make optimal decisions, using a simple example of an agent in a simulated world.
The system's intended actions are executed with an 80% probability, while there is a 10% probability of turning left or right, and a 10% probability of bumping into a wall, resulting in a deviation from the planned path.
To prevent the robot from falling down the staircase and increase the probability of reaching the goal, a more conservative strategy can be chosen by taking a longer detour around the obstacle, even though it may result in a slightly longer path length.
The transition model in Markov Decision Processes describes the probability distribution of reaching the next state given the current state and action, similar to the probabilistic motion model in localization, but in a discretized world.
Knowing the current state makes the past irrelevant, allowing us to exploit the fact that the transition model only depends on the current state.
14:26 An MDP is a formal definition of a sequential decision problem where the system's behavior is determined by a stochastic environment and a Markovian transition model, with rewards assigned to states to incentivize desirable behavior and discourage undesirable behavior.
Specify good and bad outcomes by assigning positive or negative rewards to states, where reaching the charging station is good and reaching the staircase is bad.
The reward function in Markov Decision Processes assigns values to states, with positive values for desirable states, negative values for undesirable states, and small negative values for all other states.
In a punishing environment, the system needs to be motivated to take action by receiving rewards rather than having a zero reward where it doesn't care about its behavior.
The robot is incentivized to leave an unpleasant space by giving it a small negative reward, which encourages it to move towards a more desirable state.
An MDP or Markov Decision Process is a formal definition of a sequential decision problem where the system's behavior is determined by a stochastic environment and a Markovian transition model.
18:43 The goal of planning under uncertainty is to find the optimal policy that maximizes reward by mapping states to actions in a Markov Decision Process, where the reward function plays a crucial role and changing reward values can have different consequences for the system.
An MDP is defined by a set of states, actions, an initial state, a transition model, and a reward function, and the goal is to derive an optimal policy that maximizes the reward by mapping states to actions.
The optimal policy determines the best behavior in a given situation, leading to desirable outcomes, while a sub-optimal policy can result in non-desirable states, and finding the optimal policy is crucial for planning under uncertainty.
The reward function in a Markov Decision Process determines the behavior of the system, and designing an appropriate reward function is a challenging task.
Changing the reward values in a Markov Decision Process can result in different consequences for the system, including the possibility of receiving a high negative reward where staying in a state is better than dying.
The agent tries to reach the charging station or the staircase as quickly as possible, even taking risks, if the environment is bad and staying in the world doesn't matter much.
Move in the opposite direction of the staircase to avoid falling down, and if you are on the wall, you will be bumped back but in 10% of the cases you will go left or right, reaching another safe state.
26:18 The utility of a state in a Markov Decision Process is determined by the reward and potential future rewards, and the optimal policy is the one that maximizes the expected utility over time.
Living in a perfect world with positive rewards, the system never wants to reach a terminal state or die, but rather just walk around and never reach the goal or death.
The reward function determines behavior in both robots and humans, and changing the reward function can alter behavior.
The utility of a state is determined by the reward and potential future rewards, quantifying the benefit of the state to the overall task, and is dependent on the policy and state.
The speaker explains how to compute the utility of a state by summing up the rewards obtained from executing a policy and starting from a specific state.
The reward of the current state plus the utility of the next state equals the utility of the current state.
The optimal policy in a Markov Decision Process is the one that maximizes the expected utility over time by choosing actions that maximize the expected utility of the current state.
33:12 The Bellman equation allows for optimal decision making in planning under uncertainty by breaking up the utility of a state into its immediate reward and the expectation over the reward of successor states, while discounting future rewards.
The reward of the current state plus the utility of the subsequent state is the expected future utility, which is computed by iterating over all possible future states, calculating the transition probability of ending up in each state, and multiplying it by the utility of that state.
The true policy of a state is obtained by applying the optimal policy, which maximizes the utility of the state based on the potential outcomes of actions and their probabilities.
The Bellman equation, developed by Bellman in 1957, provides the true utility of a state by breaking it up into the reward of that state and the expectation over the reward of the successor states, allowing for optimal decision making in planning under uncertainty.
The utility of a state is the immediate and long-term reward, and we can compute this for all states, but linear algebra cannot be used due to the maximization operator.
An iterative approach is used to optimize a non-linear operator in order to compute the optimal utility for any state, based on the assumption of separability.
Discounting the rewards over time is a common practice in planning under uncertainty, where immediate rewards are considered more important than future rewards, and a discount factor is used to reduce the value of rewards as time passes.
41:22 The speaker explains how to compute the optimal policy for planning under uncertainty in Markov Decision Processes by iteratively updating the utility of states until convergence, using the value iteration algorithm.
The speaker explains how to compute the utility of states in a Markov Decision Process by taking into account the rewards and utilities of neighboring states in an iterative computation.
This approach finds an optimal solution by monitoring the utility and stopping when the change in utility is below a certain threshold, using the value iteration algorithm in dynamic programming to solve Markov Decision Processes.
Value iteration is a method for planning under uncertainty in which the utility of a state is determined by taking the maximum of the rewards obtained from different actions, and repeating this process until the change in utility between iterations is smaller than a certain threshold.
The value iteration algorithm finds the optimal solution for a Markov decision process by repeatedly updating the utility of each state until convergence, allowing for the extraction of the optimal policy.
The speaker explains how to compute the optimal policy for planning under uncertainty by propagating information through the state space and selecting actions that maximize the sum of probabilities and utilities.
Reward and utility are related but different, with reward being a short-term benefit and utility being a long-term measure of how good a state is, taking into account the accumulation of rewards on the way to the final state.
50:02 Markov Decision Processes (MDPs) are a technique for decision making under uncertainty, using fully observable states and utility values to determine the optimal solution, and can be applied through policy iteration and further explored in AI and probabilistic robotics books.
Markov Decision Processes (MDPs) are used for decision making under uncertainty, providing a technique to select actions based on the assumption of fully observable states and the computation of utility values to determine the optimal solution.
Markov decision processes are useful for planning under uncertainty and can be applied using techniques such as policy iteration, taking into account additional uncertainties and finding further insight in books on AI and probabilistic robotics.


Point cloud alignment icp
The Iterative Closest Point (ICP) algorithm is a powerful tool for aligning and reconstructing 3D environments by finding the transformation between two scans and matching corresponding points, but it requires careful consideration of noise, outliers, and data associations to achieve accurate results.
00:00 The ICP algorithm aligns sensor data to accurately map and reconstruct a 3D environment by finding the transformation between two scans and matching corresponding points.
The iterative closest point algorithm is used to align sensor data, such as laser range scans, in order to accurately map and reconstruct a 3D environment.
The goal is to find the transformation between two scans of the same environment so that corresponding points align, allowing for the recovery of relative transformation and solving the alignment problem of 3D data points.
ICP (Iterative Closest Point) is a common technique used for aligning multiple scans in mapping or slam, allowing for the creation of a consistent global point cloud.
ICP algorithm is used to align scans of building structures and mobile robot scans by shifting and rotating them so that they overlap.
The ICP algorithm aligns two sets of point clouds by transferring one into the coordinate system of the other, using correspondence information to match corresponding points between the two sets.
05:15 Two 3D surfaces are aligned by finding a transformation that minimizes the distances between corresponding points using the iterative closest point algorithm.
Find a transformation that minimizes an error function by using a rotation matrix and translation vector, resulting in a six degree of freedom transformation for 3D point cloud alignment.
The goal is to align two surfaces by finding a transformation that minimizes the squared distances between corresponding points, resulting in an overlap between the two surfaces.
Minimizing squared errors in sensor data is achieved through the iterative closest point algorithm, which determines translation and rotation parameters.
Aligning point clouds involves computing the center of mass for each scan and subtracting it from the individual point sets to shift them on top of each other, followed by rotational alignment to minimize errors in the points.
Only points with correspondences are considered, and by subtracting the mean from each data point, the point clouds are shifted to have the same center of mass.
10:10 Solving the point cloud alignment problem using ICP involves computing rotation matrices, performing singular value decomposition, and minimizing errors caused by noise in the observation process.
The speaker explains how solving the orthogonal procrastination problem using a set of math reduced point sets can minimize the original error function in point cloud alignment.
The expression computes the rotation matrix that aligns the points in matrix P, subtracts the matrices, computes the Frobenius norm, and solves the problem using the orthogonal procrastinates inefficient solution with singular value decomposition.
Executing the SVD on matrix W yields three matrices, with matrix U and V being 3x3 rotation matrices that can be multiplied together to obtain the rotation matrix between analysis functions.
To align point sets, compute the cross covariance matrix, perform singular value decomposition to obtain the rotation matrix, update the point set by reducing the mean, performing the rotation, and shifting to the mean center of mass of the other point set.
The red and blue points are aligned through translation and rotation, minimizing errors caused by noise in the observation process, assuming known correspondences.
15:44 The Iterative Closest Point (ICP) algorithm aligns point clouds by iteratively improving the data association and using an SVD-based approach to compute the closest possible alignment.
In real-world situations, the problem of unknown data association can be addressed by guessing the association, performing a correction, and using an iterative process to improve the alignment.
The process involves finding the closest points on the red surface for each point on the blue surface, using this initial guess to improve the data association and compute the SVD solution.
Iterative Closest Point (ICP) algorithm aligns point clouds by repeatedly computing the alignment based on data associations, resulting in a hopefully perfect alignment even without knowing the correct data association.
Iterative Closest Point (ICP) is a method that aligns two point sets by iteratively computing the closest point data association and using the SVD approach to compute the alignment, with the goal of achieving the closest possible alignment if the initial guess of the data station is accurate.
The iterative closest point (ICP) algorithm is used to align point clouds by guessing a data association and iteratively improving the alignment until the error decreases below a certain threshold.
Compute rotation and translation vectors using an SVD-based approach, apply them to align point clouds, and minimize the error function by iteratively updating the solution until the error doesn't decrease or reaches a certain threshold, checking if the data association remains unchanged.
20:57 Two scans of buildings and buttresses are aligned using ICP, which has variance in error computation and requires reducing points, considering outliers, and adjusting initial misalignment.
Two scans of buildings and buttresses are iteratively aligned using a 2D laser range scanner in a top-down view.
ICP (Iterative Closest Point) has a large variance due to different ways of computing the error function, such as measuring distances between corresponding points or between a point and a plane, which is particularly useful for sparsely sampled surfaces.
Reducing the number of points in point cloud alignment can be beneficial due to factors such as different densities, surface importance, and data certainty, while also considering outlier detection techniques.
Data association mistakes can occur in point cloud alignment due to changes in the environment, such as moving objects, leading to errors in the alignment process.
Considerations for point cloud alignment using the ICP algorithm include speed, stability, handling outliers, and adjusting the initial misalignment.
26:18 Using various techniques for subsampling points, such as normal space sampling and feature-based sampling, can improve the alignment of point clouds in ICP algorithms by considering specific areas and features, while also taking into account the uncertainty of points further away from the camera.
The speaker discusses different techniques for subsampling points in point cloud alignment, including using all points, uniform subsampling, random subsampling, and feature-based subsampling.
Using normal space sampling can improve the alignment of point clouds by considering more points along areas of strong curvature.
Using feature information to sample points on features can improve the alignment of 3D scans by focusing on similar features such as walls, polls, or ground surfaces.
Aligning point clouds using the ICP algorithm can be faster and more accurate by considering a smaller subset of points with similar feature values, and weighting correspondences based on the information they provide.
Points that are further away from the camera have higher uncertainty in their positions, so they should be given a lower weight in alignment algorithms, and this can be achieved by considering the sensing principle and using robust estimation techniques.
Different techniques can be used for data association in point cloud alignment, such as finding the closest points or using point cloud measuring or projection-based approaches.
34:28 Point cloud alignment using ICP is improved by considering surface data associations and using point-to-plane approaches, while also considering the rejection of outliers, but finding the right threshold and identifying incorrect data associations can be challenging.
For point cloud alignment, finding the closest point in one skin to each point in another skin can be done efficiently using KD trees, but it requires a large number of iterations and a good initial guess to perform well.
Normal shooting is a method used for point cloud alignment that computes normals based on neighboring points, shoots the normals in the corresponding direction, and provides better convergence results for smooth surfaces with good initial alignment, but is not effective for noisy data points.
Matching points based on additional information like color or surface properties can help reduce the risk of data associations and improve point cloud alignment.
Point cloud alignment using ICP is improved by considering surface data associations and using point-to-plane approaches, which are slower but provide better convergence rates, while also considering the rejection of outliers in real-world data.
One approach to point cloud alignment is to ignore points that are further away than a certain threshold, but finding the right threshold can be challenging; another approach is to compare compatibility between nearby points on the same surface in different scans, which is more computationally intensive but can help identify incorrect data associations.
Ignore the worst 20% of data stations with high initial error, but this approach requires knowledge of overlap and initial data station quality.
41:42 Point cloud alignment using the ICP algorithm is crucial for creating consistent maps, allowing for corrections and estimation of vehicle movement, and can be improved with techniques like robust minimization and outlier handling.
Different techniques, such as Rancic-based and robust optimization approaches, can be used to deal with outliers in point cloud alignment by subsampling points, determining corresponding points, computing rotation and translation matrices, and repeating the process until a desired result is obtained.
The speaker explains how point cloud alignment using the ICP algorithm can be used to incrementally align scans from a moving vehicle, such as a robot, to create a map of the environment.
The ICP algorithm is used to align 3D point clouds and create consistent maps for slam systems, allowing for corrections and estimation of vehicle movement without loop closure or similar information.
Alignment of 2D and 3D point cloud data is crucial for perception, allowing for the registration of multiple scans or observations taken from different views and locations, and the ICP algorithm is the standard method for calculating the transformation between two scans.
The ICP algorithm uses an iterative approach to align point clouds by estimating data association and optimizing rotation and translation parameters until convergence, with various variants and techniques available.
ICP alignment may not always converge to the correct solution due to mistakes in data association, but techniques such as robust minimization and outlier handling can improve alignment accuracy when aligning large numbers of scans.



RANSAC
RANSAC is a powerful algorithm that can remove outliers from data associations, improving the accuracy of state estimation algorithms in various applications.
00:00 RANSAC is an algorithm that removes outliers in data associations, improving the accuracy of state estimation algorithms in various applications.
RANSAC is an algorithm used to identify and eliminate outliers in data associations, making state estimation algorithms more robust.
Extracting features from images and making feature correspondences is necessary for computing relative orientation and solving simultaneous localization and mapping problems in various applications.
RANSAC is a technique used to identify consistent data points and eliminate outliers in image matching and laser range data analysis.
02:43 RANSAC is a powerful algorithm that separates outliers from data points, enabling accurate state estimation even with a high percentage of outliers.
RANSAC is a powerful algorithm that can identify and separate outliers from data points, allowing for accurate state estimation even with a high percentage of outliers.
RANSAC is a simple and efficient algorithm that repeatedly selects a subset of data points, computes a model, evaluates its consistency with the remaining points, and selects the model with the highest agreement.
04:39 RANSAC is a method for finding the best model by repeatedly fitting lines and counting inliers, ultimately determining the best model.
The five-point algorithm requires five data points to compute the relative orientation between two camera images, and the number of data points needed depends on the model being used.
The speaker explains the process of using RANSAC to find the best model by repeatedly computing and scoring data points, storing the model with the highest number of inliers.
To fit a line through a set of 2D points, randomly sample two points and fit a line through them.
The speaker explains the process of using RANSAC to find the best model by iteratively fitting lines and counting the number of inliers, repeating the process until the best model is determined.
08:16 RANSAC is a method that randomly selects data associations to estimate a line or compute a translation, and it can be used to find the most consistent set of associations between images for alignment and stitching.
RANSAC is a method used to estimate a line or compute a translation by selecting random data associations and evaluating their fit with the rest of the data.
The speaker explains how RANSAC is used to find the most consistent set of data associations between image pairs by iteratively selecting data points and counting inliers.
The speaker demonstrates feature-based alignment by extracting key points and computing potential matches between two images for the purpose of stitching them together.
The speaker uses a small subset of data points to hypothesize a transformation and verifies it with other associations, repeating the process until finding the largest number of supporting data sessions to determine the correct transformation for aligning two images.
The speaker explains how the RANSAC algorithm can be used to separate correct and incorrect data associations in image stitching.
13:02 Repeat the process of identifying and removing outliers until all in line outliers are identified, with the number of trials needed depending on the knowledge of outlier distribution and percentage of outliers in the dataset.
Repeat the process of identifying and removing outliers until all in line outliers are identified, but the frequency of repetition depends on the knowledge of the underlying outlier distribution and the number of outliers in the dataset.
The important parameters in RANSAC are the number of sample data points needed to compute the model and the percentage of outliers in the overall data points.
We need to determine the number of trials (T) needed to achieve a desired probability of obtaining the right result in the RANSAC algorithm, and this can be computed by considering the given parameters and the probability specified.
15:47 The success of RANSAC depends on the probability of drawing only inliers, which decreases with the outlier ratio and sample size, ultimately leading to a zero overall success probability.
The probability of failing in one iteration of RANSAC is 1 minus the probability of drawing only inliers, which is calculated as 1 minus the outlier ratio raised to the power of the sample size.
The probability of failing T times is equal to failing once to the power of T, resulting in an overall success probability of zero.
18:09 The number of trials in RANSAC algorithm depends on the outlier ratio and data points, increasing as success probability and data points increase, but it becomes impractical for real-time applications with high outlier ratios.
Compute the outlier ratio by taking the logarithm of both sides of the equation and solving for T.
The number of trials needed to achieve a desired success probability in the RANSAC algorithm depends on the outlier ratio and the number of data points, with the number of trials increasing as the success probability and number of data points increase.
The number of trials needed to estimate parameters using RANSAC increases significantly as the outlier ratio increases, making it impractical for real-time applications with high outlier ratios.
21:41 RANSAC is a useful algorithm for handling outliers and estimating models with a small number of parameters, commonly used in tasks like finding corresponding points in images and computing visual odometry.
In algorithms for estimating models, it is preferable to use those that require a smaller number of data points, especially in situations with a large number of outliers.
RANSAC is an easy-to-implement algorithm that separates data points into inliers and outliers, allowing for robust handling of outliers and effective state estimation in real-world situations with a small number of parameters.
RANSAC is not the preferred algorithm due to its computational complexity and inability to estimate multiple fits, but it is commonly used for finding corresponding points in images, computing visual odometry, finding ground planes, and performing scan matching.
RANSAC is a standard tool for fitting tasks in the presence of outliers, using a trial and error approach to guess a subset of inliers, compute a model, and score it based on consistency with the remaining data points.



SLAM
SLAM is a complex process that involves estimating the position of a robot and building a map of the environment using sensor data and probabilistic state estimation techniques.
00:00 SLAM is the process of simultaneously estimating the position of a robot and building a map of the environment, taking into account noisy sensor observations and correcting errors over time.
The course introduces the concept of simultaneous localization and mapping (SLAM), starting with an explanation of its importance and the use of least squares for state estimation, followed by an exploration of 2D SLAM using laser range scanners, and then expanding to include outliers in data association and state estimation using cameras or laser rangefinders.
SLAM is the process of computing the position of a mobile platform or sensor while simultaneously building a map of the environment.
Localization, mapping, and SLAM are three interconnected problems in estimating pose, building a map, and solving both simultaneously, with the challenge being the dependency between the tasks.
The robot's observations and movements in the environment are noisy, leading to uncertainty, but it can correct its position based on landmarks and a map of the environment.
The robot estimates the positions of landmarks and its own position in order to build a map of the environment, taking into account noise in sensor observations.
The system estimates the location of landmarks as it moves through the environment, creating its own map that may have errors due to noise, but these errors can be corrected over time to build a consistent map.
06:36 SLAM is the process of building a map and localizing oneself within it using sensor data, which is crucial for autonomous navigation and real-time decision making in robotics applications.
Simultaneous Localization and Mapping (SLAM) is the process of using sensor data from a mobile platform to build a map of the environment while simultaneously localizing oneself within that map, with variants including offline SLAM where all sensor data is collected initially to build the best possible map.
In robotics applications like drones and self-driving cars, it is important to process information in real-time and convert new observations into a model to make decisions based on what is seen.
Online SLAM is a problem of estimating a map and a robot's pose using various sensors, such as cameras and laser scanners, and can be seen as an online version of bundle adjustment.
Localization and mapping are essential for autonomous navigation, and solving the SLAM problem in real-time is crucial for building maps and estimating positions simultaneously, making it a key component for most applications in autonomous systems.
10:42 A vacuum cleaner needs to know its location and have a model of the environment to perform systematic cleaning, while robotic platforms use SLAM systems to build maps and estimate their position for autonomous navigation and tasks.
To perform systematic cleaning or lawn mowing, a vacuum cleaner needs to have a model of the environment and know its location.
Robotic platforms, such as UAVs and underwater systems, require the ability to build a map of the environment and estimate their position in order to navigate autonomously and perform tasks.
The mint cleaning system, originally built by evolution robotics and now owned by iRobot, uses the Northstar system to project infrared patterns to the ceiling, allowing the cleaning robot to perceive landmarks and perform systematic cleaning by estimating its location and the environment.
The video demonstrates a SLAM system using a 2D laser rangefinder to estimate the robot's pose and build a consistent map of the environment by optimizing the system's estimation when re-entering previously seen places.
15:09 Estimating the map and trajectory of a platform in SLAM involves using a probabilistic approach to estimate the probability distribution of the platform's position based on observations and control commands, taking into account the uncertainty of motion and observations.
We assume access to robot controls and sensor observations, and we want to estimate the map of the environment and the path of the platform.
Estimating the map and trajectory of the platform in a probabilistic approach, aiming to provide a probability distribution with a mean close to the true position of the platform.
Estimating a probability distribution of X and M based on observations and control commands is crucial in SLAM, and the uncertainty of motion and observations affects the overall map.
18:11 Networks illustrate the dependencies between variables in SLAM, where the position of the robot and landmarks impact observations, and the unknown variables are estimated based on probability distributions; full SLAM estimates the entire trajectory and map, while online SLAM focuses on the current pose, but is challenging due to the tight coupling between mapping and SLAM.
Networks illustrate probability distribution and dependencies between variables, such as control commands, observations, and maps, which can be read as influences or impacts on the platform at different points in time.
The position of the robot and the landmarks impact the observations, and the unknown variables are estimated based on the probability distributions and dependencies between the variables.
Full SLAM involves estimating the entire trajectory and map of the environment, while online SLAM only focuses on estimating the current pose of the platform.
The online SLAM problem involves estimating the current pose by integrating over all previous poses, but it is difficult due to the tight coupling between mapping and SLAM.
22:23 SLAM is a challenging problem due to correlated observations and movements, making data association crucial for accurate state estimation, with graph-based representations being commonly used.
The challenge in SLAM is that the robot's observations and movements are correlated, making it computationally difficult to maintain all the correlations and obtain a correct probabilistic belief.
SLAM is a challenging problem due to the difficulty of distinguishing between known and unknown correspondences in sensor data.
Unknown correspondences in SLAM can make the problem of distinguishing landmarks and making accurate state estimations difficult, as it is dependent on the uncertainty of the platform.
Data association is a crucial aspect of SLAM, as making wrong decisions can lead to incorrect beliefs about the world and ultimately result in divergence of the state estimation system.
Researchers use slam datasets to estimate the trunks of trees and localize in environments, and there are different representations such as 3D scans, dense models, floorplan-like maps, and feature-based representations that can be handled using the slam system, with the Kalman filter being a traditional paradigm used for estimation.
Graph-based representations are the most commonly used approach for solving the simultaneous localization and mapping problem in SLAM, as they allow for the incorporation of multiple sensors and the revision of previous data, while particle filter-based representations are also available for those interested.
29:27 The graphical model representation in SLAM includes variables for the platform's position and decision, with the motion and observation models being key factors that determine probability and uncertainty, including non-Gaussian distributions, and the importance of estimating observations for updates.
The graphical model representation shows the variables describing the platform's position and decision at different times, as well as the control/command guiding its motion.
The motion model and observation model are two key models that have a significant impact on the system, with the motion model determining the probability of being at a certain position at a given time based on previous knowledge and executed commands.
We can use Gaussian distributions to model uncertainty in SLAM, but due to the non-linearity of the system, non-Gaussian models like banana-shaped distributions may be necessary to accurately represent the likelihood of observations given the pose or current state.
Estimating the likelihood of observations given the current state of the world is crucial for performing updates in SLAM, with landmarks being the most commonly used model, but virtual observations also playing an important role.
33:03 By comparing observations of landmarks, SLAM uses virtual observations to determine the relative transformation between poses, allowing for estimation of the platform's location and the world's appearance using probabilistic state estimation techniques.
By comparing observations of landmarks, the speaker explains how virtual observations can be used to determine the relative transformation between poses in SLAM, which is important for graph-based SLAM and solving the simultaneous localization and mapping problem.
The task is to estimate the platform's location and the world's appearance using probabilistic state estimation techniques, such as optimization, with different variants and map representations available.
The lecture focuses on graph-based representations in SLAM, starting with laser range scanners and later discussing the use of cameras, and recommends reading the slam chapter in the handbook on robotics for a more detailed overview of the different variants of the slam problem.
The speaker encourages viewers to review the basic math concepts covered in the course, and expresses hope that they will understand SLAM and be able to build a state-of-the-art slam system using laser and camera data.



Graph based SLAM with pose graph
Graph-based SLAM using pose graphs is a practical and efficient approach for building maps and localizing platforms, as it optimizes robot poses and generates consistent maps by minimizing errors introduced by constraints.
00:00 Graph-based SLAM using pose graphs is a popular technique for building maps and localizing platforms, as it reduces everything to poses and is flexible in terms of observations, making it a standard tool in systems that build maps of environments.
Graph-based SLAM using pose graphs is a popular technique for building maps and localizing platforms, as it reduces everything to poses and is flexible in terms of observations, making it a standard tool in systems that build maps of environments.
The lecture discusses the basics of graph-based SLAM, which is a least squares approach to solving an over-determined system in order to determine the robot's position in the environment.
The goal is to find a configuration of poses in a graph that minimizes errors introduced by observations and control commands, allowing us to estimate the robot's location accurately.
A mobile robot generates poses at distinct points in time as it moves through the environment, with each pose describing its location and orientation.
Constraints between poses in a pose graph are determined by the motion of the platform, such as the revolution of the wheels, which allows the platform to estimate its position.
Post two is approximately a meter away from post one, but there is uncertainty in this information.
05:32 The graph-based SLAM technique uses pose graphs to optimize the robot's poses and generate a consistent map of the environment by minimizing errors introduced by constraints.
The robot generates constraints from odometry and sensor data, including scan matching, to create a structure that allows it to revisit previously seen places and generate constraints between non-successive poses.
The graph structure, called a pose graph, is central to the SLAM problem as it represents the robot's poses at different points in time and is used to compute a solution.
The goal of graph-based SLAM is to optimize the location of poses in a graph by minimizing the error introduced by constraints, which can be conflicting due to observations and odometry information.
The graph-based SLAM approach uses pose graphs to minimize errors introduced by constraints and generate a consistent map of the environment, allowing for accurate trajectory correction and map building.
The front end of a SLAM system involves converting raw sensor data into constraints, while the back end optimizes the graph and corrects the poses using these constraints, with the front end typically using the ICP algorithm to generate relative transformations.
The graph-based SLAM technique uses nodes to represent the robot's poses at different times, with constraints between nodes representing the robot's movement, which can be generated from odometry information, and the goal is to optimize the graph using least squares to minimize errors.
16:56 Graph-based SLAM using Pose Graphs simplifies the representation of transformations using homogeneous coordinates, allowing for elegant and concise notation, and the uncertainty in the optimization process can be determined by comparing the accuracy of scan measurements to odometry information.
An edge can exist between two arbitrary poses, allowing for the generation of a virtual measurement by aligning the observed environment from different locations, providing information about the relative positions of the robot.
Homogeneous coordinates are used to encode transformations in graph-based SLAM, allowing for elegant representation of translation and rotation between nodes.
Homogeneous coordinates simplify the representation of transformations using matrices, allowing for elegant and concise notation, and involve adding an extra dimension to the n-dimensional space being modeled.
Translations and rotations can be expressed elegantly using a four-dimensional matrix, allowing for easy chaining of transformations.
The transformation between nodes in graph-based SLAM is affected by noise, and the information matrix encodes the uncertainty and importance of each constraint in the optimization process.
The uncertainty in graph-based SLAM can be determined by comparing the accuracy of scan measurements done with ICP to odometry information, with laser range scanners typically being more accurate and having smaller covariance matrices, while a long featureless corridor would result in a narrow covariance matrix along the right and left sides but a long and stretched one along the main axis.
28:42 Graph-based SLAM minimizes error between observations and graph configuration by adjusting node positions, using least squares approach and ICP algorithm, transforming measurements into vector form and expressing constraints in pose graph.
Large uncertainties in certain dimensions can propagate through a graph, leading to a large uncertainty along a specific line in the pose graph.
The goal is to minimize the error between the observation and the current graph configuration by shifting the nodes' positions, represented by edges, in order to satisfy all constraints.
The least squares approach is used to minimize the error vector in graph-based SLAM, where only a small number of variables contribute to each individual error term.
The state vector is a concatenation of the poses of the graph, while the error function relates the individual poses and observations using the ICP algorithm.
The speaker explains the process of transforming graph-based SLAM measurements into vector form using forward and backward transformations, and introduces the functions T to V and V to T for converting between vectorized representations and transformation matrices.
The speaker explains how to express constraints in a pose graph and discusses the conditions for an error of 0, which occurs when the observation and graph transformation are the same, resulting in the identity matrix.
37:47 The Jacobian matrix is a key component in graph-based SLAM, allowing for efficient solving of large linear systems using sparse solvers.
Rebuilding Gauss-Newton involves defining and linearizing the error function, which leads to a system of linear equations when the first derivative is set to 0.
We solve a system of linear equations to update our state and iterate the process until convergence, linearizing the error function by computing the Jacobian matrix, which consists of the partial derivatives of the error function with respect to the state vector.
The Jacobian matrix in graph-based SLAM will have mostly zero elements, except for the blocks related to the variables of interest, resulting in a sparse matrix.
The Jacobian matrix plays a crucial role in solving real-world SLAM problems efficiently by allowing for the computation of the elements B and H, resulting in a sparse matrix that can be solved effectively.
The matrix formed by multiplying the Jacobian and information matrices for each constraint in graph-based SLAM will have four non-zero blocks, and when all the elements are summed up, the resulting matrix will be fully dense, representing the connections in the graph.
The matrix used in graph-based SLAM is typically sparse due to the decoupling of different places in the environment, allowing for efficient solving of large linear systems using sparse solvers.
49:58 Graph-based SLAM using Pose Graphs: Build a linear system by computing error vectors and Jacobians for each constraint, solve it iteratively until convergence, and use the resulting configuration to build a map of the environment.
You build a linear system by computing error vectors and Jacobians for each constraint, adding the corresponding small blocks to the matrix and vector, without needing to compute the zero blocks.
Build a linear system, solve it using a sparse matrix solver, update the configuration iteratively until convergence, and use the resulting configuration to build a map of the environment.
In a simple example of graph-based SLAM, two nodes in a one-dimensional world are initialized with a distance constraint of 1 meter between them.
The information matrix is used to compute the error function, which is the difference between the actual and predicted observations, and the Jacobian is computed to derive the error function with respect to the variables.
Compute the B vector using the error vector, information matrix, and Jacobian, then solve the system of linear equations by inverting the H matrix and multiplying it with X to obtain the update.
The matrix cannot be inverted because it has rank deficiency, resulting in a determinant of 0.
56:51 Graph-based SLAM uses pose graphs to optimize the map created by a moving robot, with techniques such as fixing a reference frame and adding constraints to ensure certain variables have fixed values, and there are methods to compute only necessary parts of the uncertainty matrix to reduce computational cost.
The relative constraint between two nodes in graph-based SLAM can be resolved by fixing one node as a reference frame, which can be achieved by enforcing a constraint that the update on the first node should be zero.
In graph-based SLAM, adding a prior or fixing a coordinate is necessary to address the problem of a matrix not being full rank, and this can be done by setting one of the nodes as the reference frame and adding a constraint to keep it fixed.
A robot moves around an environment, building a map as it goes, and the map is continuously optimized to minimize errors introduced by new observations and to align with previously seen places.
We can fix certain variables in the system by adding prior notes, but this is a soft constraint and other constraints may pull the variable away, so we need a way to ensure that a certain variable has a fixed value.
The speaker explains how to optimize a linear system by constraining certain variables and solving the system with the modified matrix.
The uncertainty of the overall estimate in graph-based SLAM can be obtained by inverting the information matrix, but this can be computationally costly, so there are techniques to compute only the necessary parts of the uncertainty matrix, such as the main diagonal blocks or the relative uncertainty between poses.
01:08:34 Graph-based SLAM using pose graphs is a practical and efficient approach for solving large-scale systems, allowing for online computations and optimization, and students will build their own SLAM system to gain hands-on experience and understanding of the core concepts.
The robot computes the relative uncertainty of nodes to determine which ones to inspect for loop closures, based on its current pose and the quality of its map.
Graph-based SLAM using pose graphs is a practical and efficient approach for solving large-scale systems by representing the robot's poses in a sparse matrix, allowing for online computations and optimization.
Some approaches use outlier rejection techniques to handle unknown data cessation, and there are libraries available to perform efficient optimizations, but in the course, students will build their own SLAM system to gain hands-on experience and understanding of the core concepts.



Graph based slam with landmarks
Graph-based SLAM with landmarks uses a graph to represent robot poses and landmarks, minimizing errors and building maps of the environment.
00:00 Graph-based SLAM with landmarks uses a graph to represent robot poses and landmarks, minimizing errors and building maps of the environment.
Graph-based SLAM with landmarks involves using a graph to represent the positions of a mobile robot and landmarks in the environment, with the goal of minimizing errors introduced by spatial constraints.
The post graph is used to represent robot poses and their relative transformations in order to optimize and minimize errors using least squares.
The video discusses how to represent landmarks in a graph-based SLAM system, where landmarks are distinct points in the environment that can be recognized and used to build maps and estimate the robot's pose.
The video discusses using landmarks, such as trees, in graph-based SLAM to build a map of the environment.
04:31 Graph-based SLAM with landmarks involves different types of edges and nodes in the graph, with the goal of minimizing overall error by finding the optimal configuration of robot poses and landmark locations.
The difference in graph-based SLAM with landmarks is that the robot poses have position and heading information, while the features in the environment only have position information, resulting in different types of edges and nodes in the graph.
The graph in SLAM consists of nodes representing robot poses and landmark locations, with edges connecting robot poses to landmarks.
The goal of graph-based SLAM is to find a configuration of robot poses and landmark locations that minimizes the overall error introduced by constraints, which can be odometry measurements or observations of landmarks in the environment.
The graph structure in graph-based SLAM with landmarks is different from the previous version, with robot poses and landmarks as nodes and additional edges representing robot position and landmark constraints.
08:30 The speaker explains how to compute observations and error functions in graph-based SLAM using different types of sensors and landmarks.
The expected observation in graph-based SLAM is generated by subtracting the landmark position from the robot's location and multiplying it with the transpose of the rotation matrix, resulting in a 2D vector that represents the relative XY location and can be used to derive the error function.
The speaker explains how to compute observations using different types of sensors, such as an XY sensor and a bearing sensor, which provide information about the location and direction of landmarks.
Landmarks are 2D points in the environment and observations are relative headings of the landmarks with respect to the robot.
To estimate what the robot should see, we compute the difference in coordinates between the robot's location and the landmark.
The speaker explains how to compute the error function for a landmark observation by subtracting the predicted measurement from the actual measurement.
13:17 The rank of the H matrix in graph-based SLAM with landmarks is determined by the rank of the Jacobian, allowing for two degrees of freedom in the robot's parameters and providing localization information.
The rank of the H matrix in graph-based SLAM with landmarks is determined by the rank of the Jacobian, assuming the information matrix has full rank.
The matrix H has a rank of at most two, allowing for two degrees of freedom in the robot's parameters and providing information for localization.
15:47 The position of the robot relative to a landmark can be determined by the circle of possible positions it can be in, with each position indicating the direction the robot should look towards the landmark.
The position of the robot relative to a landmark can be determined by the circle of possible positions it can be in, with each position indicating the direction the robot should look towards the landmark.
The robot's location can be determined by fixing two out of three parameters, and with bearing only observations, the robot can be located anywhere in a 2D space and will always point directly towards the landmark.
The rank of the observation in graph-based SLAM with landmarks is important because it determines the number of observations needed to obtain a unique solution.
19:15 If the rank of the graph is not greater than the sum of the ranks of the individual constraints, we cannot find a unique solution for the landmark location, and to determine the robot's pose using landmark observations, a minimum of two observations are needed in a 2D plane and three observations are needed in a bearing-only case, but the system may still lack a full rank.
If the rank of H is smaller or equal to the sum of the ranks of the individual constraints, we cannot determine the unique solution for the landmark location.
To determine the robot's pose using landmark observations, a minimum of two observations are needed in a 2D plane, and three observations are needed in a bearing-only case, but the system may still be underdetermined and lack a full rank.
21:19 Adding a damping factor to the linear system in SLAM improves the solvability of the matrix, and adjusting the damping parameter iteratively helps find the optimal solution.
Adding a damping factor to the linear system in SLAM can help improve the rank and condition of the matrix, allowing for a more solvable system.
Combining Gauss-Newton and steepest descent approaches, the speaker explains how solving the equation H + λIΔx = -b in graph-based SLAM involves scaling the residual vector based on importance and mapping it to the parameter space.
You can deal with underdetermined systems by iteratively adjusting your solution using a linear system and monitoring the error vector to determine how to change the damping parameter.
If the error of a new solution is smaller than the previous error, the damping factor is reduced to improve the solution, but if the error increases, the old solution is recovered and the damping factor is increased.
25:42 A graph-based SLAM approach is discussed in the video, which estimates camera locations and feature points in a 3D environment by minimizing reprojection error and incorporating additional information through landmarks.
The solution discussed in the video is a slam approach that estimates camera locations and feature points in a 3D environment based on a collection of images and their corresponding feature points, minimizing the reprojection error to address underdetermined systems.
Having enough observations of the same environment is necessary for connected graphs in graph-based SLAM, and solutions to this problem have existed since the 1950s with the development of photogrammetry approaches.
The lecture discusses incorporating additional information into a graph-based SLAM approach with landmarks, using nodes for robot poses and landmark locations, and optimizing the system using a combination of Gauss-Newton and steepest descent.



Robust least squares for slam
Implementing robust estimation techniques, such as using robust loss functions and adaptive kernel approaches, in graph-based SLAM can effectively handle outliers and improve accuracy in mapping and state estimation.
00:00 A robust least squares approach is introduced to handle outliers in data association for SLAM, addressing the limitations of the Gaussian assumption and aiming to generate accurate maps even in the presence of outliers.
Introducing a robust least squares approach to deal with outliers in data association for the simultaneous localization and mapping problem, by minimizing squared errors and assuming Gaussian distributions.
The Gaussian assumption in standard least squares is problematic for dealing with outliers in data association, as it does not account for the possibility of mixing up landmarks or having multiple modes in the distribution, leading to substantial errors and parameter deviations in practice.
In graph-based SLAM, the robot can make data association mistakes due to cluttered scenes or repetitive structures, such as mixing up trees while driving, and GPS can be problematic due to signal reflections, resulting in uncertainty in determining the robot's location.
The distribution of the robot's location in a simulated world is multi-modal, indicating that using a Gaussian may not accurately represent the belief.
Aligning two scans using ICP generates constraints between distant poses, improving the accuracy of the map.
Outliers in graph-based SLAM can lead to incorrect maps, so the goal is to perform optimization that is not sensitive to outliers and can generate maps similar to those in an outlier-free case.
06:07 The speaker discusses a novel approach in graph-based SLAM that introduces models with multiple modes, allowing for a sum of Gaussians to represent constraints, and explains how a max mixture approach can be used to approximate the optimization problem and identify outliers in the data set.
The speaker discusses a novel approach in graph-based SLAM that introduces models with multiple modes, allowing for a sum of Gaussians to represent constraints.
The speaker explains how a sum of Gaussians cannot be simplified using the log operator, resulting in individual exponents that cannot be combined.
The speaker discusses a method called max mixtures, which replaces the sum operator with a max operator to approximate the optimization problem in graph-based SLAM, resulting in a smaller approximation error when the modes of the Gaussian distribution are further apart.
The speaker explains how to integrate a Max mixture into the existing least squares formulation by evaluating all components of the Gaussian and selecting the one with the highest likelihood for each multimodal constraint.
The max mixture approach in graph-based SLAM is able to identify and eliminate outliers in the data set, with minimal computational overhead and runtime increase, by using a combination of two gaussians to determine the correct mode for observations.
The shapes of the objects are similar except for a slight variation when switching from inside to outside, and additional information can be added.
17:18 The max mixture approach in graph-based SLAM effectively handles outliers and multiple modes, while dynamic covariance scaling improves optimization by downrating outliers and adding weight to constraints.
Use the max mixture approach to handle outliers and other problems in the kinematics of your platform, as it is an easy and flexible way to implement and still allows for optimization.
The max mixture approach in graph-based SLAM is effective in handling outliers and multiple modes in data association, unlike standard Gauss-Newton optimization.
The speaker discusses two approaches for graph-based SLAM: one that supports multiple modes by approximating the sum of gaussians and another that uses dynamic covariance scaling.
The speaker introduces the concept of dynamic covariance scaling in graph-based SLAM, which adds additional weight to constraints and allows for downrating outliers, improving the optimization process.
The speaker explains how a scaling factor can be used to optimize the error function in graph-based SLAM, with a visual illustration showing the effect of the scaling function on the error.
The speaker discusses the concept of adding a weighting term to the error function in order to give less importance to outliers and more importance to data points closer to the actual solution, which is a technique known as robust kernels or M estimation in the optimization community.
26:48 Robust M estimators, such as the Hoover M estimator, are used in graph-based SLAM to minimize the negative log likelihood of error values and account for outliers, with various ways to define robust functions and the relationship between weighted least squares and robust estimation.
Robust M estimators are proposed to be less sensitive to outliers in data, as they account for the probability mass in the tails of the distribution and provide information about the distribution of the outliers.
The speaker explains the concept of using a root function, Rho, to define a probability density function in order to treat constraints differently and minimize the negative log likelihood of error values, allowing for different effects on outliers.
The Hoover M estimator is a popular choice for graph-based SLAM as it uses a quadratic function for small errors and a linear function for larger errors.
The corrupted Gaussian can be embedded into various kernels, such as the quadratic function near zero that turns into a linear function as you move further away, making it easy and intuitive to determine outliers.
There are various ways to define robust functions in graph-based SLAM, such as the l1 norm, which can disregard outliers in the optimization problem.
Weighted least squares and robust estimation are related in graph-based SLAM, where the information matrix acts as a weighting term in the former and the robust estimation introduces a weight that affects the optimization problem.
34:09 Implementing robust estimation in graph-based SLAM can be achieved by setting the weight in a smart way, using existing tools and connecting to dynamic variant scaling and weighted least squares approach, allowing for handling outliers and optimizing the system.
The derivative of the function e of X with respect to X can be combined with the first derivative of the function role, showing that the weight at these squares can be used to solve the problem.
Implementing robust estimation in graph-based SLAM can be achieved by setting the weight in a smart way, which allows for the use of the existing toolbox and connects to the dynamic variant scaling and weighted least squares approach.
Dynamic covariant scaling is a special case of robust estimation, where the weighted least squares approach can be used by changing the jacobians and selecting the appropriate robust kernel function based on knowledge of outliers.
The speaker discusses a tool for dealing with outliers in slam systems, but it is often unclear what type of outliers are present.
Use generalized robust kernels in graph-based SLAM to handle outliers by starting with a kernel with strong tails for extreme outlier rejection, then gradually weakening the kernel as the estimate gets closer to the true value.
Combine and inspect data, remove outliers, optimize with Gaussian or Hoover beakers, and use remaining data for further optimization.
40:24 By adjusting the alpha parameter, different shapes of loss functions can be achieved, reducing the impact of outliers in graph-based SLAM and adapting to different outlier distributions.
There is a more efficient way to implement the varying kernel function by explicitly including the additional alpha parameter.
By adjusting the alpha parameter, different shapes of loss functions can be achieved, resulting in various robust kernels for graph-based SLAM.
By varying the alpha parameter in the weighted least squares approach, the impact of outliers can be reduced, with smaller alpha values resulting in stronger down weighting of the outliers.
Different loss functions perform better for different types of outlier distributions, but by adjusting the alpha parameter, the beta function can adapt to the outlier distribution and best represent it.
The video discusses an adaptive approach for outlier detection in graph-based SLAM and recommends watching Jonathan Barron's original video for a detailed explanation of the approach.
Optimizing the alpha parameter in graph-based SLAM can be challenging due to the issue of negative values, but by jointly optimizing the problem and determining the kernel function, it is possible to adapt to the outlier distribution and overcome this problem.
49:03 The speaker discusses the use of a modified adaptive loss function in graph-based SLAM to limit outliers and compute error and loss functions, highlighting issues with parameter estimation and suggesting an alternative approach using expectation maximization.
The error distribution in graph-based SLAM does not provide a probability distribution, so a trick is used to avoid integrating from minus infinity to infinity.
The speaker discusses the use of a modified adaptive loss function in graph-based SLAM to limit the maximum outlier considered in the optimization problem, resulting in a probability distribution.
We limit the range of values and ignore anything outside of that range in the optimization problem.
The use of probability distributions allows for the computation of error and loss functions, with a preference for squared error unless there are outliers, in which case offsets are added.
The speaker discusses the use of robust least squares with a weighted B-squares kernel function for graph-based SLAM, but highlights issues with parameter estimation and sensitivity to initial guess, suggesting an alternative approach using expectation maximization to iteratively estimate and optimize the alpha parameter while keeping the other parameters fixed.
54:20 Using a robust loss function in SLAM improves alignment accuracy by treating outliers separately, demonstrated in a car tracking example, and the adaptive kernel approach in graph-based SLAM provides better state estimation by iteratively estimating the kernel and unknown parameters, adapting to outlier situations without changing the optimization problem.
Using a robust loss function in SLAM can improve the accuracy of alignment by treating outliers as separate entities, as demonstrated in a car tracking example.
The Alpha parameter changes and in certain outlier situations, the value drops to the minimum value of minus 10, as demonstrated in a small example of a car driving and aligning itself with another car.
The adaptive kernel approach in graph-based SLAM allows for better state estimation by iteratively estimating the kernel and unknown parameters, providing better results than joint optimization and adapting to the current outlier situation without changing the least squares optimization problem.
Different methods for dealing with outliers in optimization depend on the error distribution, with the max mixture model being recommended for multi-modal constraints and dynamic covariance scaling being a popular choice for fixed kernel problems in simultaneous localization and mapping.
Adaptive kernels are recommended for estimating outlier distributions in graph-based SLAM, as they allow for flexibility when the shape of the outlier distribution is unknown, and can be more effective than the standard least squares method, particularly for bundle adjustment problems.
Use the adaptive kernel approach with e/m based estimation to handle outliers in data association for graph-based SLAM.




[[Robotics Engineering]]

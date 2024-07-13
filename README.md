# Forward-Inverse-Kinematics-For-3DOF-Robot-Arm
# Forward Kinematics (FK)
Forward kinematics involves calculating the position and orientation of the robot's end-effector given the joint parameters (angles for revolute joints, positions for prismatic joints).

## Example: 3-DoF Robot Arm
Assume we have a 3-DoF robot arm with the following configuration:

- Joint 1: Revolute (rotational around the z-axis)
- Joint 2: Revolute (rotational around the y-axis)
- Joint 3: Revolute (rotational around the y-axis)
## Denavit-Hartenberg (DH) Parameters
We use the DH convention to describe the robot's configuration.  
#### 
#### The DH parameters are:

- 𝜃𝑖: Joint angle  
- 𝑑𝑖: Link offset  
- 𝑎𝑖: Link length  
- 𝛼𝑖: Link twist  
#### 

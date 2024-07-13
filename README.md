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
Let's define the DH parameters for our 3-DoF robot as follows:
![image](https://github.com/user-attachments/assets/dcd98dbd-9669-450a-a3f0-76a946730900)
Transformation Matrices
The transformation matrix for each joint can be represented as:
![image](https://github.com/user-attachments/assets/b8de9155-957d-47a5-8d6d-85e854c03a8a)
For our 3-DoF robot, the transformation matrices are:
- T1:
![image](https://github.com/user-attachments/assets/d51a0e07-3e68-45e7-8138-be2c9741ebbf)
- T2:
![image](https://github.com/user-attachments/assets/f3e4616f-f1c9-4133-87c6-7a4db7318b7c)
- T3:
![image](https://github.com/user-attachments/assets/6f557c7a-460a-4ece-b035-8cab99decfc0)
The overall transformation matrix from the base to the end-effector is the product of these matrices:
![image](https://github.com/user-attachments/assets/be866b1a-547a-45f9-9671-257bcb134d64)
Multiply the matrices to get the final transformation matrix 𝑇0_3, which gives the position and orientation of the end-effector.

## Inverse Kinematics (IK)
Inverse kinematics involves calculating the joint parameters given the desired position and orientation of the end-effector.

For a 3-DoF robot, we aim to find 𝜃1, 𝜃2, and 𝜃3.
### Steps for Inverse Kinematics
- Calculate Position of the End-Effector: Use the desired position (𝑥,𝑦,𝑧)
- Solve for 𝜃1: Use the projection of the end-effector position on the 𝑥𝑦-plane:
![‏‏لقطة الشاشة (1987)](https://github.com/user-attachments/assets/c6373e86-e146-4d9f-8e81-84e5ec68626a)
- Solve for 𝜃2:
Use the coordinates (𝑥′,𝑦′,𝑧′) after considering 𝑑1from 𝑧:
![‏‏لقطة الشاشة (1988)](https://github.com/user-attachments/assets/5ffcb7e6-0860-4707-8b41-73b10810f58a)
- Calculate 𝑟:
![‏‏لقطة الشاشة (1989)](https://github.com/user-attachments/assets/cc6f1e4f-35b6-4a4b-aa78-4d882df9f35c)
- Use the law of cosines:

![‏‏لقطة الشاشة (1990)](https://github.com/user-attachments/assets/10f9edab-15cd-45b5-a757-b7c2d7e7942b)
Solve for 𝜃3:
- Compute 𝑎=𝑎3 cos(𝛼3) and 𝑏=𝑎3 sin(𝛼3), where 𝛼3 is the twist angle for joint 3.
- Use the coordinates (𝑥′,𝑦′,𝑧′) adjusted for 𝑑1:

![‏‏لقطة الشاشة (1991)](https://github.com/user-attachments/assets/81223d96-3062-42b0-877e-d89d4e6af1d2)
- Calculate 𝑟:
![‏‏لقطة الشاشة (1992)](https://github.com/user-attachments/assets/b372b91a-5475-4115-a715-4d1930a3f6bd)
- Use the law of cosines to find 𝜃3:
![‏‏لقطة الشاشة (1993)](https://github.com/user-attachments/assets/85baddb5-8b43-458d-be05-4743f908c8d0)

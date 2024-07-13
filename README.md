# Forward & Inverse Kinematics For a 3 DOF Robotic Arm
## Task Description:-
To Calculate Forward and Inverse Kinematics for a Robot with 3 Degrees of Freedom
## Forward Kinematics:-
#### 
Forward kinematics involves calculating the position and orientation of the robot's end-effector given the joint parameters (angles for revolute joints, positions for prismatic joints).
####
## Joints' configuration:-
####
Assume we have a 3-DOF robot arm with the following configuration:
####
- Joint 1: Revolute (rotational around the z-axis)
- Joint 2: Revolute (rotational around the y-axis)
- Joint 3: Revolute (rotational around the y-axis)
####
### Denavit-Hartenberg (DH) Parameters:
####
We use the DH convention to describe the robot's configuration.  
#### 
#### The DH parameters are:
####
- 𝜃𝑖: Joint angle  
- 𝑑𝑖: Link offset  
- 𝑎𝑖: Link length  
- 𝛼𝑖: Link twist  
#### 
Let's define the DH parameters for our 3-DOF robot as follows:
####
![image](https://github.com/user-attachments/assets/dcd98dbd-9669-450a-a3f0-76a946730900)
####
### Transformation Matrices:-
####
The transformation matrix for each joint can be represented as:
####
![image](https://github.com/user-attachments/assets/b8de9155-957d-47a5-8d6d-85e854c03a8a)
####
For our 3-DOF robot, the transformation matrices are:
####
- T1:
####
![image](https://github.com/user-attachments/assets/d51a0e07-3e68-45e7-8138-be2c9741ebbf)
####
- T2:
####
![image](https://github.com/user-attachments/assets/f3e4616f-f1c9-4133-87c6-7a4db7318b7c)
####
- T3:
####
![image](https://github.com/user-attachments/assets/6f557c7a-460a-4ece-b035-8cab99decfc0)
####
The overall transformation matrix from the base to the end-effector is the product of these matrices:
####
![image](https://github.com/user-attachments/assets/be866b1a-547a-45f9-9671-257bcb134d64)
####
Multiply the matrices to get the final transformation matrix 𝑇0_3, which gives the position and orientation of the end-effector.
####
## Inverse Kinematics:-
####
Inverse kinematics involves calculating the joint parameters given the desired position and orientation of the end-effector.
####
For a 3-DOF robot, we aim to find 𝜃1, 𝜃2, and 𝜃3.
####
### Steps for Inverse Kinematics:-
####
- Calculate Position of the End-Effector:
Use the desired position (𝑥,𝑦,𝑧)
####
- Solve for 𝜃1:
####
Use the projection of the end-effector position on the 𝑥𝑦-plane:
####
![‏‏لقطة الشاشة (1987)](https://github.com/user-attachments/assets/c6373e86-e146-4d9f-8e81-84e5ec68626a)
####
- Solve for 𝜃2 and 𝜃3:
####
Use the geometric approach or algebraic equations derived from the transformation matrices.
For example, consider the 2D projection of the arm in the 𝑥𝑧-plane:
####
![‏‏لقطة الشاشة (2000)](https://github.com/user-attachments/assets/9bde5631-33f3-4d14-8e05-033732f2ce5e)
####
1- Solve for 𝜃3:
####
![2001](https://github.com/user-attachments/assets/a1391cff-6655-4e79-b86e-7c8745964878)
####
2- Solve for 𝜃2 using the law of cosines and sines:
####
![2002](https://github.com/user-attachments/assets/b7caf745-35fb-48b0-af99-728a5bd34066)
####
### Example Calculation:
####
Suppose we have the following desired end-effector position (𝑥,𝑦,𝑧) and robot parameters:
####
- 𝑥=3
- 𝑦=4
- 𝑧=5
- 𝑑1=1
- 𝑎1=1
- 𝑎2=1
- 𝑎3=1
####
1- Calculate 𝜃1:
####
![‏‏لقطة الشاشة (1994)](https://github.com/user-attachments/assets/1210fb79-0bf3-49e1-ab91-98d2f60c6d15)
####
2- Calculate 𝑟 and 𝑠:
####
![‏‏لقطة الشاشة (1995)](https://github.com/user-attachments/assets/c0f74663-64de-413f-9e85-64625f8a8b86)
![‏‏لقطة الشاشة (1996)](https://github.com/user-attachments/assets/755e4caf-40d7-49fd-a6d8-7dac8ce44cde)
####
3- Calculate 𝐷:
####
![‏‏لقطة الشاشة (1997)](https://github.com/user-attachments/assets/2f46942d-b12c-4c88-a04f-2bb3ab8a881f)
####
4- Calculate 𝜃3:
####
![‏‏لقطة الشاشة (1998)](https://github.com/user-attachments/assets/861af133-6164-4883-80a0-9da381589357)
####
5- Calculate 𝜃2:
####
![‏‏لقطة الشاشة (1999)](https://github.com/user-attachments/assets/027ab0c7-550d-41c1-90f3-589fd9243b06)
####
### This is a high-level overview. The exact calculations might vary depending on the robot's configuration and link parameters.
#### 
## Conclusion:-
Forward kinematics provides the end-effector position given the joint parameters, while inverse kinematics provides the joint parameters given the end-effector position. Both processes are essential for controlling robotic arms and require a solid understanding of the robot's geometry and kinematics.

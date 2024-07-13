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
### Denavit-Hartenberg (DH) Parameters

We use the DH convention to describe the robot's configuration. The DH parameters are:
- \( \theta_i \): Joint angle
- \( d_i \): Link offset
- \( a_i \): Link length
- \( \alpha_i \): Link twist

Let's define the DH parameters for our 3-DoF robot as follows:

<table>
  <tr>
    <th>Joint \( i \)</th>
    <th>\( \theta_i \) (variable)</th>
    <th>\( d_i \) (constant)</th>
    <th>\( a_i \) (constant)</th>
    <th>\( \alpha_i \) (constant)</th>
  </tr>
  <tr>
    <td>1</td>
    <td>\( \theta_1 \)</td>
    <td>\( d_1 \)</td>
    <td>\( a_1 \)</td>
    <td>0</td>
  </tr>
  <tr>
    <td>2</td>
    <td>\( \theta_2 \)</td>
    <td>0</td>
    <td>\( a_2 \)</td>
    <td>0</td>
  </tr>
  <tr>
    <td>3</td>
    <td>\( \theta_3 \)</td>
    <td>0</td>
    <td>\( a_3 \)</td>
    <td>0</td>
  </tr>
</table>

### Transformation Matrices

The transformation matrix for each joint can be represented as:


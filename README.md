# arti_hardware  [Transcend Robotics](http://transcendrobotics.com/)
The Hardware ROS package for ARTI3 robot
## How to install
```
sudo apt-get install ros-$ROS_DISTRO-serial
cd "your_workspace"/src
git clone https://github.com/transcendrobotics/arti_hardware.git
cd ..
catkin_make
```
## How to use it
Once you have the robot, and installed ROS and this package, you can simply do
```
roslaunch arti_hardware arit_base.launch
```
## How to control the robot
Simply just publish veloctiy command on /cmd_vel you should be able to control the robot, for example:
```
sudo apt-get install ros-$ROS_DISTRO-teleop-twist-keyboard
rosrun teleop_twist_keyboard teleop_twist_keyboard.py
```
Use the instruction to control the robot.
## Notes
1. The code was capable with odometry from encoder but we don't want to use encoder anymore because track robots slip a lot.
2. The hardware doesn't have velocity control, the command sends to the robot is open loop, works as voltage command.

## Parameters
 Parameter                    |           Description                                       |              Value          
------------------------------|-------------------------------------------------------------|-------------------------    
port                          | The port address of the hardware                            | string               
baud_rate                     | Hardware Baudrate, Change with caution                      | double
body_width                    | The width of the body                                       | double
serial_time_out               | Serial Communication Timeout                                | double
cmd_time_out                  | Command Timeout                                             | double
control_rate                  | The rate of sendiing command to hardware                    | double
odom_rate                     | The rate of publishing odom                                 | double
odom_window                   | Odometry smooth window size                                 | int
wheel_multiplier              | The multiplier for wheel                                    | double
flip_lr                       | Whether to flip the direction of left and right wheel       | bool        
publish_tf                    | Whether to publishing TF                                    | bool        
odom_bias                     | the bias of odometry reading on left wheel                  | bool        

## Aurthor: [Di Zeng](https://www.linkedin.com/in/dizeng)

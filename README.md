# DR2
> ISR-Lab project 2017

### Project purpose:
The robot we are working on is Kobuki. /
We developed all the software environment to easily work on kobuki with ROS (both in a simulation and in the real world), integrating Prolog and Datalog solvers with the other technologies. /
We provided Kobuki depth camera data, in order to use it in AI (so it will be compatible with SWI-Prolog, Datalog, SICStus Prolog and DALI).

### Needed hardware:
1. Kobuki robot
2. JetsonTK1 board
3. Orbbec Astra 3D Camera

### Software constraints:
- We will use Python (2 and 3), Prolog and ROS.
- We are going to follow the Sense-Think-Act paradigm.
- We will use Docker, in simulation, to avoid compatibility conflicts.
- We will use ROS Indigo due to JetsonTK1 driver limitation (at the moment Ubuntu 16 has some problem)


![](header.png)

![](nodeDiagram.png)


### Project Goals:
1. Reconfigure JetsonTK1 board (Done)
2. Configure Orbbec Astra 3D Camera (Done)
3. Create a communication channel between the camera and ROS environment (Done)
4. Create a Docker container with all the needed environment in it to avoid compatibility conflicts (Done)
5. Integrate Prolog and Datalog in ROS environment (Done)
6. Create a simulation and run it on the robot (Working with a dummy simulation. We will add some effort here. Done)
7. (Additional) Take camera timestamps and images (Done)
8. (Optional) Facial recognition ability

### Use case 1:
Kobuki goes around into the room, avoiding obstacles thanks to the bumper sensor.
Kobuki is able to forward camera data to proper ROS topics.

### (Optional) Use case 2:
Kobuki goes around into the room, avoiding obstacles and "looking" around thanks to the camera.
Kobuki is able to forward camera data to its Prolog brain.
Kobuki is able to detect people face and to recognize them (by making queries to its Prolog brain).

### Links:
-  http://www.nvidia.it/object/jetson-tk1-embedded-dev-kit-it.html
-  https://developer.nvidia.com/embedded/jetpack
-  https://demotomohiro.github.io/hardware/jetson_tk1/setup/recovery_mode.html
#### Software Links:
-  https://github.com/agnsal/docker-IndigoROSdisPyPl: we have to use ROS Indigo (inside a Docker container, because Indigo is not compatible with Ubuntu 16.04, that we have on our PCs); we have Ubuntu 14.04 on JetsonTK1 board, because it is needed by CUDA.
-  http://wiki.ros.org/kinetic/Installation/Ubuntu
-  https://www.generationrobots.com/blog/en/2015/02/robotic-simulation-scenarios-with-gazebo-and-ros/
-  https://www.youtube.com/watch?v=9U6GDonGFHw&t=796s
-  http://wiki.ros.org/ROS/Tutorials/CreatingMsgAndSrv
-  http://wiki.ros.org/kobuki/Tutorials/Kobuki%27s%20Control%20System

## (OPTIONAL, if you have all the needed hardware, so you don't want to make a simulation only) Robot Instructions:
1. Start with a clean Ubuntu 14 installation on jetson TK1, theb follow the instructions at:** \
  https://gitlab.com/Centofanti/JetsonTK1-ROS-Kobuki-install
2. Now you have a full working Ros Indigo installation wich is able to talk with kobuki base and Astra camera and a pre-configured catkin workspace at ~/catkin_ws
3. It is recommended to connect to jetson using different instance of [putty client](http://www.putty.org/) to manage ROS modules.

**N.B.** Due to some incompatibility packages, it has not been possible to install ros-turtlebot packages on Jetson TK1. Ubunti dpkg has some missing packages and can not complete the apt-get installation. (Maybe some further time-costly investigations can fix this problem)

## PC Instructions:
1. To have and use an Indigo ROS container, follow the instructions at: https://github.com/agnsal/docker-IndigoROSdisPyPl
2. To Install turtlebot ROS packages:
```sh
sudo apt-get install ros-indigo-turtlebot ros-indigo-turtlebot-apps ros-indigo-turtlebot-interactions 
ros-indigo-turtlebot-simulator ros-indigo-kobuki-ftdi ros-indigo-rocon-remocon ros-indigo-rocon-qt-library 
ros-indigo-ar-track-alvar-msgs
```
3. To run the ROS core:
```sh
roscore
```
4. To launch the simulation in Gazebo:
```sh
roslaunch turtlebot_gazebo turtlebot_world.launch
```
5. (TEST) To give commands to the Gazebo turtlebot manually (via keyboard):
```sh
roslaunch turtlebot_teleop keyboard_teleop.launch
```
6. To download Turtlebot code into the workspace, build it and run it, follow the instructions at: https://github.com/agnsal/kobukiROSindigo
7. (IMPORTANT) To save all your work on the container, you have to exit it and save its state:
```sh
exit
docker commit "IndigoROSdisPyPl"
```  


## Screenshots:

![](screen1.png)

![](screen2.png)

![](screen3.png)

# DR2
ISR-Lab project 2017

### What we are going to do:
The robot we are going to work on is the Kobuki.
We are going to use its depth camera with ROS environment, in order to use it in AI (so it will be compatible with SWI-Prolog, SICStus Prolog and DALI).

### Needed hardware:
1. Kobuki robot
2. JetsonTK1 board
3. Orbbec Astra 3D Camera

### Software constraints:
We will use Python, Prolog and ROS.
We are going to follow the Sense-Think-Act paradigm.

### TO DO:
1. Reconfigure JetsonTK1 board
2. Configure Orbbec Astra 3D Camera
3. Create a communication channel between the camera and ROS environment
4. Integrate Prolog in ROS environment
5. (Optional) Facial recognition ability

### Use case 1:
Kobuki goes around into the room, avoiding obstacles and "looking" around thanks to the camera.
Kobuki is able to forward camera data to its Prolog brain.

### (Optional) Use case 2:
Kobuki goes around into the room, avoiding obstacles and "looking" around thanks to the camera.
Kobuki is able to forward camera data to its Prolog brain.
Kobuki is able to detect people face and to recognize them (by making queries to its Prolog brain).

### Links:
-  http://www.nvidia.it/object/jetson-tk1-embedded-dev-kit-it.html
-  https://developer.nvidia.com/embedded/jetpack
-  https://demotomohiro.github.io/hardware/jetson_tk1/setup/recovery_mode.html
#### Software Links:
-  http://wiki.ros.org/indigo/Installation/UbuntuARM (we have to use ROS Indigo, because we have Ubuntu 14.04, that is needed by CUDA)

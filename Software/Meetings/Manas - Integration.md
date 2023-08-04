# August 4, 2023
### Naman Mishra
Aditya Gupta, Naman, Sacchit and Sirjan met with Manas Juvvi, a B.Tech
research intern at RBCCPS.

The agenda was to discuss how sensors such as LIDAR and actuators such as the
motor integrate together in a physical robot.
The key points that emerged were:
- Learn ROS. A single person proficient in ROS is enough to hold the project
together, but being able to work your way through ROS is essential for working
on any piece of software.
- Most of the integration will be handled by ROS and tested in Gazebo. If we
still wish to work on an actual robot, we can test it out on the robots he's
working with.
- The Raspberry Pi may be overkill for our purposes, and may also not have
enough pins to control 6 motors. He has recommended using a microcontroller
like TEENSY 4.0. It is similar to Arduino and has a clock frequency of 1 GHz.
For the prototype we can possibly work with ESP 32, and shift to TEENSY later.
We will need to look into this further.

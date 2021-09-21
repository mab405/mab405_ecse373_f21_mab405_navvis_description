# mab405_ecse373_f21_mab405_navvis_description
Navvis Description assignment for ECSE373 at CWRU
Some lab terminology was changed. For convenience I didn't add a separate launch directory and instead included my launch files in the project package
Named launch file as .txt for my own conveneince. Lab didn't specify until the end so I thought this was a student choice based on our preference. I wanted to clarify however.
must first run <~$ source devel/setup.bash>
Followed by running <~catkin_ws source devel/setup.bash>


Within the navvis_description directory the following code can be used to launch robot
cd ~/catkin_make/src/naavis_description

Launches the static version of the robot with no wheels added (with configured rviz file)
roslaunch improved_launch_file.txt &

launches the robot with wheels and joint_state_publisher_gui (with configured rviz file)
roslaunch improved_launch_file.txt use_xacro:=true &

launches the robot with wheels and no joint sate publisher (with configured rviz file)
roslaunch improved_launch_file.txt use_xacro:=true gui:=false &

Also included file robot_description_xacro.bak which is my robot_description file before the 'include other xacro files' section of the lab.
This file uses static block representations rather than actual sensors.


launch_file.txt has no functionality for running xacro files and instead only runs the basic configured rviz file and the robot_description.urdf
rviz was configured to:
1). Add a robot model
2). Name robot model robot_description
3). Set parameters of robot based on robot_description.urdf or robot_description.xacro based on launch file
4). Configured text from 'map' to 'base

joint_state_publisher_gui rotates wheels from -pi to pi and can be automatically configured

robot_description.xacro includes the use of xacro to add in sensors though they don't read data at this time

CMakeLists.txt and package.xml have dependencies on both gazebo_plugins and velodyne_description
velodyne_description must be installed <sudo apt-get install ros-melodic-velodyne-description>

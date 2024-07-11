# Control-Robot-Arm-with-Joint-State-Publisher
1. Set Up ROS Environment:
```ruby
source /opt/ros/noetic/setup.bash

mkdir -p ~/catkin_ws/src
cd ~/catkin_ws/
catkin_make
```
<img src="https://github.com/DeemaEssam/DeemaEssam.github.io/assets/106381596/485db32d-0524-4e54-8600-e9070a451e24" data-canonical-src="https://gyazo.com/eb5c5741b6a9a16c692170a41a49c858.png" width="500" height="300" />

```ruby
source devel/setup.bash
echo "source ~/catkin_ws/devel/setup.bash" >> ~/.bashrc
```
2. install the packages
```ruby
cd ~/catkin_ws/src
sudo apt install git
git clone https://github.com/smart-methods/arduino_robot_arm

cd ~/catkin_ws
rosdep install --from-paths src --ignore-src -r -y
sudo apt-get install ros-noetic-moveit ros-noetic-joint-state-publisher ros-noetic-joint-state-publisher-gui
sudo apt-get install ros-noetic-gazebo-ros-control ros-noetic-ros-controllers ros-noetic-ros-control

catkin_make
```
<img src="https://github.com/DeemaEssam/DeemaEssam.github.io/assets/106381596/969e9009-9de4-42af-970f-5f672e93be17" data-canonical-src="https://gyazo.com/eb5c5741b6a9a16c692170a41a49c858.png" width="500" height="300" />

```ruby
roslaunch robot_arm_pkg check_motors.launch

rostopic echo /joint_states

cd ~/catkin_ws/src/arduino_robot_arm/robot_arm_pkg/scripts
sudo chmod +x joint_states_to_gazebo.py

roslaunch robot_arm_pkg check_motors_gazebo.launch
rosrun robot_arm_pkg joint_states_to_gazebo.py
```


<img src="https://github.com/DeemaEssam/DeemaEssam.github.io/assets/106381596/2e951ca3-f108-4a55-9209-8d13cb296475" data-canonical-src="https://gyazo.com/eb5c5741b6a9a16c692170a41a49c858.png" width="500" height="300" />
<img src="https://github.com/GDHadeel/Robot-Arm-Control-with-Joint-State-Publisher-and-MoveIt/assets/106381596/b31f8de7-d330-401f-82cb-84df4acfb888" data-canonical-src="https://gyazo.com/eb5c5741b6a9a16c692170a41a49c858.png" width="500" height="300" />
![movingArm1](https://github.com/GDHadeel/Robot-Arm-Control-with-Joint-State-Publisher-and-MoveIt/assets/106381596/b31f8de7-d330-401f-82cb-84df4acfb888)




# MoveIt
1. Prerequisites:
```ruby
sudo apt-get install ros-noetic-moveit
```
2. Install the MoveIt Package:
```ruby
cd ~/catkin_ws/src
git clone https://github.com/smart-methods/arduino_robot_arm
cd ~/catkin_ws
rosdep install --from-paths src --ignore-src -r -y
```
3. Running the MoveIt Package:

<img src="https://github.com/DeemaEssam/DeemaEssam.github.io/assets/106381596/770371d4-9671-45b3-8bf2-b20ad5f77df4" data-canonical-src="https://gyazo.com/eb5c5741b6a9a16c692170a41a49c858.png" width="500" height="300" />

```ruby
catkin_make
```

<img src="https://github.com/DeemaEssam/DeemaEssam.github.io/assets/106381596/c696b707-9b0e-439b-8239-b062b0d0e956" data-canonical-src="https://gyazo.com/eb5c5741b6a9a16c692170a41a49c858.png" width="500" height="300" />

```ruby
roslaunch moveit_pkg demo.launch
roslaunch moveit_pkg demo_gazebo.launch
```

<img src="https://github.com/GDHadeel/Robot-Arm-Control-with-Joint-State-Publisher-and-MoveIt/assets/106381596/b7811037-b293-4551-994c-10e265f49634" data-canonical-src="https://gyazo.com/eb5c5741b6a9a16c692170a41a49c858.png" width="500" height="300" />
![moveArm2](https://github.com/GDHadeel/Robot-Arm-Control-with-Joint-State-Publisher-and-MoveIt/assets/106381596/b7811037-b293-4551-994c-10e265f49634)

# caatingarobotics jazzy/harmonic test repo

Clone.

``` bash
git clone https://github.com/ilovemicroplastics/caatingarobotics_harmonic_port_test.git
cd caatingarobotics_harmonic_port_test
```

What I use to build this.

```bash
source /opt/ros/jazzy/setup.bash
rosdep update
rosdep install --from-paths src --ignore-src -r -y
colcon build --symlink-install
source install/setup.bash
```

To run when already built.

```bash
source /opt/ros/jazzy/setup.bash
source install/setup.bash
ros2 launch agro_robot_sim fazenda_completa.launch.py
```
Test drive. (in a new terminal)

```bash
cd caatingarobotics_harmonic_port_test
source /opt/ros/jazzy/setup.bash
source install/setup.bash
ros2 run teleop_twist_keyboard teleop_twist_keyboard --ros-args --remap cmd_vel:=/cmd_vel
```

# differences to original
- sim.launch.py changed completely to fit gazebo harmonic
- agro_robot.urdf.xacro , is robo_caatinga.xacro modified to run in harmonic
- sdf file contains sensor plugins

# future work
- change the URDF to look like the real robot
- implement lcas?
- are all the sensors properly set up with the changes? I think it's fine but I haven't looked at those modules to conclusively say it works 100%

# personal caution
- If this is supposed to be a reflection of the feldfreund, shouldn't the ros2 topics match? I haven't checked that properly but this is important to go sim2real with the program smoothly

BK

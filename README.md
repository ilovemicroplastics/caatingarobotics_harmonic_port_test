Experimental Jazzy build . Untested!

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
ros2 launch agro_robot_sim sim.launch.py
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
- empty.sdf , is an empty sdf file, which also contains sensor plugins

# future work
- figure out which repo we will stick to, it confuses me, I assume the original caatinga repo
- the other launch files need to be adjusted to properly work with the new sim.launch.py
- the world filepath should not be hardcoded
- the world should have crop rows, and not be empty
- implement lcas

# personal caution
- If this is supposed to be a reflection of the feldfreund, shouldn't the ros2 topics match? I haven't checked that properly but this is important to go sim2real with the program smoothly

BK

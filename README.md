# tb4_cpp_prac6

ROS 2 (ament_cmake, C++17) package implementing a custom Adaptive Monte Carlo
Localisation (AMCL) node — `iar_amcl` — for the TurtleBot4, built on the
`nav2_amcl` particle filter. Practical 6 for Curtin Colombo ICTE4001.

## Package layout

- `src/`, `include/iar_amcl/` — `iar_amcl` node and KD-tree particle filter implementation
- `launch/localisation_launch.py` — brings up `map_server`, `iar_amcl`, and the Nav2 lifecycle manager
- `config/localisation.yaml` — AMCL and map server parameters
- `map/` — simulation map (`office_ICTE4001_sim`)

## Build

From a ROS 2 workspace `src/` directory:

```bash
colcon build --packages-select tb4_cpp_prac6
source install/setup.bash
```

## Run

```bash
ros2 launch tb4_cpp_prac6 localisation_launch.py
```

Launch arguments: `namespace`, `map`, `use_sim_time`, `autostart`, `params_file`, `log_level`.

## Dependencies

ROS 2 with Nav2 (`nav2_common`, `nav2_util`, `nav2_msgs`, `nav2_amcl`), `rclcpp`, `rclcpp_lifecycle`, `tf2`/`tf2_ros`, `message_filters`, `sensor_msgs`, `nav_msgs`, `geometry_msgs`, `std_srvs`.

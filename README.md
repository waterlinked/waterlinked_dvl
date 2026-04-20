# Water Linked DVL API

waterlinked_dvl is a C++ library and ROS 2 driver designed to interface with
[Water Linked DVL devices](https://waterlinked.com/dvl), including the DVL-A50
and DVL-A125. Get started with waterlinked_dvl by installing the project,
exploring the implemented library [examples](https://github.com/waterlinked/waterlinked_dvl/tree/main/libwaterlinked/examples),
or by launching the ROS 2 driver.

> [!NOTE]
> This project was graciously donated to us by the [Robotic Decision Making Lab](https://github.com/Robotic-Decision-Making-Lab).

## Installation

To install waterlinked_dvl, first clone the repository to the `src/` directory
of your ROS 2 workspace

```bash
git clone git@github.com:waterlinked/waterlinked_dvl.git
```

Then install the project dependencies using vcstool and rosdep

```bash
vcs import src < src/waterlinked_dvl/ros2.repos && \
rosdep install --from paths src -y --ignore-src --skip-keys nlohmann_json
```

Finally, build the workspace using colcon

```bash
colcon build && source install/setup.bash
```

## Usage

Prior to using waterlinked_dvl, first ensure that you can successfully connect
to your respective device. For additional information, please refer to the
Water Linked [networking documentation](https://docs.waterlinked.com/dvl/networking/).
After verifying the network connection, the DVL ROS 2 driver can be launched
with the following command:

```bash
ros2 launch waterlinked_dvl_driver dvl.launch.py
```

A sample configuration file can be found in `waterlinked_dvl_driver/config/dvl.yaml`,
and the full list of parameters can be found in `waterlinked_dvl_driver/src/waterlinked_dvl_driver_parameters.yaml`.
Refer to the [protocol documentation](https://docs.waterlinked.com/dvl/dvl-protocol/)
for descriptions of all the DVL configuration parameters.

## Getting help

If you have questions regarding usage of waterlinked_dvl or regarding contributing
to this project, please contact our [customer support](https://www.waterlinked.com/support)

## License

waterlinked_dvl is released under the MIT license.

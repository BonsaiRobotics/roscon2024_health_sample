# Bonsai ROS Health Sample Application

```
colcon build

export RMW_IMPLEMENTATION=rmw_cyclonedds_cpp
export RMW_IMPLEMENTATION_WRAPPER=rmw_stats_shim

ros2 launch sample_health_app sample.launch telegraf_uri:=telegraf
```

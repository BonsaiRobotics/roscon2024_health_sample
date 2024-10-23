# Bonsai ROS Health Sample Application

Sample entrypoint, as discussed in Roscon2024 talk "ROS Robot Application Health Monitoring: a Bonsai Approach"

For using the components from https://github.com/BonsaiRobotics/ros_health_components

NOTE: Vimeo Link to the Roscon2024 talk will be added here when available.

Provides:
* [sample_health_app](./src/sample_health_app/) - Within this repository, provides some rosdep dependencies and `sample.launch`
* [workspace.repos](./workspace.repos) to clone the relevant other repositories
* [tig_sample](./tig_sample/) - Docker-compose based Telegraf+InfluxDB+Grafana end-to-end setup, with sample dashboard you can run with one command
* [Sample Foxglove Layout](./roscon2024_health_foxglove.json) - Foxglove layout you can import to get the same views as in the presentation

## Basic Usage

### Run the ROS components

```
vcs import src < workspace.repos
colcon build
source install/setup.bash

export RMW_IMPLEMENTATION=rmw_cyclonedds_cpp
export RMW_IMPLEMENTATION_WRAPPER=rmw_stats_shim

ros2 launch sample_health_app sample.launch
```

### Run the TIG stack locally

```
cd tig_sample
docker-compose up
```

Now navigate to [localhost:3000](http://localhost:3000)
* Password: `admin`
* Username: `admin`
* Go to Dashboards and find "Sample Vehicle Dashboard"

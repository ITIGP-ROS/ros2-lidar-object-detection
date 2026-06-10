
# ROS 2 Lidar Object Detection Package

ROS 2 node wrapper around the [PyTorch implementation](https://github.com/zhulf0804/PointPillars) of PointPillars that is modified to work with the KITTI dataset bag files that are created using [kitti_to_ros2bag](https://github.com/Chris7462/kitti_to_ros2bag).

## Tested Setup:
- **OS:** Ubuntu 22.04  
- **ROS 2:** Humble  
- **Python:** 3.10.12  
- **CUDA:** 13.2  
- **PyTorch:** 2.12.0+cu132 (CUDA-enabled build)


> **TODO:** Test on Jetson Devices


## Build Instructions:

1. Clone the repo

```bash
git clone https://github.com/ITIGP-ROS/ros2-lidar-object-detection.git

cd ros2-lidar-object-detection
```

2. Get the Ros2 dependencies using rosdep

```bash
rosdep update
rosdep install --from-paths src --ignore-src -r -y
```

3. Build the package

```bash
cd <your_ros2_workspace>

colcon build --symlink-install
```
4. Build CUDA-related Packages
```bash
cd ros2-lidar-object-detection/src/lidar_object_detection/lidar_object_detection/lidar_object_detection/ops

python3 setup.py build_ext --inplace
```
5. Source the workspace

```bash
source install/local_setup.bash
```


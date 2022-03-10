# TC-IMU-LIO-SAM

**LIO-SAM with Tightly Coupled IMU Code Implementation**

The code was written for the result of tightly-coupled via IMU Factor. Specifically, this repository addresses the issue on that link (https://github.com/TixiaoShan/LIO-SAM/issues/51). The graph optimization presented in the paper in the LIO-SAM code is handled in the mapOptimization.cpp file. However, as mentioned in the link above, LIO-SAM separates it into two graphs for quick optimization, and unlike the paper, it has a loosely-coupled effect. Therefore, we implemented IMU Factor in mapOptimization.cpp using the code of imuPreintegration.cpp. For details, please refer to the addImuFactor function. Except for this part, all the code is the same as that of LIO-SAM, so it would be better to refer to the LIO-SAM repository if an issue arises about usage rather than an issue about addImuFactor.


## Dependency

Same as LIO-SAM original. Please see this webpage(https://github.com/TixiaoShan/LIO-SAM).

## Install

Use the following commands to download and compile the package.

```
cd ~/catkin_ws/src
https://github.com/minwoo0611/TC-IMU-LIO-SAM
cd ..
catkin_make
```

## Service
  - /lio_sam/save_map
    - save map as a PCD file.
      ``` bash
        rosservice call [service] [resolution] [destination]
      ```
      - Example:
      ``` bash
        $ rosservice call /lio_sam/save_map 0.2 "/Downloads/LOAM/"
      ```


## Paper 

Part of the code is adapted from [LIO-SAM](https://github.com/TixiaoShan/LIO-SAM)
```
@inproceedings{liosam2020shan,
  title={LIO-SAM: Tightly-coupled Lidar Inertial Odometry via Smoothing and Mapping},
  author={Shan, Tixiao and Englot, Brendan and Meyers, Drew and Wang, Wei and Ratti, Carlo and Rus Daniela},
  booktitle={IEEE/RSJ International Conference on Intelligent Robots and Systems (IROS)},
  pages={5135-5142},
  year={2020},
  organization={IEEE}
}
```
## Related Package

  - [LIO-SAM](https://github.com/TixiaoShan/LIO-SAM)

## Acknowledgement

  - TC-IMU-LIO-SAM is based on LIO-SAM.

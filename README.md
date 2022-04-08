
# pcl-learning 

## Environment Setup

system : ubuntu 20.04 arm64 + ros-noetic

    sudo apt-get install libpcl-dev pcl-tools

dependencies : 
    
    sudo apt-get update  
    sudo apt-get install git build-essential linux-libc-dev
    sudo apt-get install libusb-1.0-0-dev libusb-dev libudev-dev
    sudo apt-get install mpi-default-dev openmpi-bin openmpi-common 
    sudo apt-get install libflann1.9 libflann-dev
    sudo apt-get install libeigen3-dev
    sudo apt-get install libboost-all-dev
    sudo apt-get install libvtk7.1p-qt
    sudo apt-get install libvtk7.1p 
    sudo apt-get install libvtk7-qt-dev
    sudo apt-get install libqhull* libgtest-dev
    sudo apt-get install freeglut3-dev pkg-config
    sudo apt-get install libxmu-dev libxi-dev
    sudo apt-get install mono-complete
    sudo apt-get install openjdk-8-jdk openjdk-8-jre

## Compile

    mkdir build
    cd build
    cmake ..
    make

## pcl_viewer

**Notes : [PCL(Point Cloud Library)（2021）](https://www.yuque.com/huangzhongqing/pcl)**

## Contents

* [00base](00base)

##### step1

* [01common](01common )

##### step2

* [02kdtree](02kdtree)
* [03octree](03octree)
* [04search](04search)
* [05sample consensus](05sampleconsensus抽样一致性模块)
* [06range-images](06range-images深度图像)

##### step3

* [08 io 输入输出](08IO输入输出)
* [09 filters 滤波](09filters滤波)
* [10 features 特征](10features特征)

##### step4

* [11 surface表面 ](11surface表面 )
* [12 segmentation分割](12segmentation分割)
* [13 recognition识别](13recognition识别)
* [14 registration配准](14registration配准)
* [15 visualization可视化](15visualization可视化)
* [16 keypoints关键点](16keypoints关键点)
* [17tracking](17tracking )


## 实战项目

不理解的地方,欢迎提issue: https://github.com/HuangCongQing/pcl-learning/issues

* 3D-MOT(多目标检测和追踪)
  * https://github.com/HuangCongQing/3D-LIDAR-Multi-Object-Tracking/tree/kitti
* 3D点云目标检测&语义分割-SOTA方法,代码,论文,数据集等
  * https://github.com/HuangCongQing/3D-Point-Clouds

## 相关链接

* 公众号：点云PCL
* https://github.com/Yochengliu/awesome-point-cloud-analysis
* https://github.com/QingyongHu/SoTA-Point-Cloud
* https://github.com/PointCloudLibrary/pcl
* 参考书籍：点云库PCL学习教程，朱德海，北京航空航天大学出版社

- **视频**：[bilibili-PCL点云库官网教程](https://space.bilibili.com/504859351/channel/detail?cid=130387)

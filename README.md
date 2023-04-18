# cyberdog_towr

小米铁蛋towr

## 环境

Ubuntu-20.04+ROS-Noetic

## 部署

```bash
mkdir towr_ws && cd towr_ws
mkdir src && cd src
git clone https://github.com/ethz-adrl/ifopt.git
git clone https://github.com/fan-ziqi/towr.git
git clone https://github.com/fan-ziqi/xpp.git
cd ..
catkin build
source ./devel/setup.bash
```

## 使用
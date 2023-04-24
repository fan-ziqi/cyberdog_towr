# cyberdog_towr

小米铁蛋towr离线规划

## 环境

测试通过：Ubuntu-20.04+ROS-Noetic

## 部署

```bash
mkdir -p towr_ws/src && cd towr_ws/src
git clone https://github.com/ethz-adrl/ifopt.git
git clone https://github.com/fan-ziqi/towr.git
git clone https://github.com/fan-ziqi/xpp.git
cd ..
catkin build
source ./devel/setup.bash
```

## 使用

```bash
roslaunch towr_ros towr_ros.launch
```

## 更换求解器

如果你安装了Ipopt求解器，可以接入。在`.bashrc`中写入

```bash
export IPOPT_DIR=xxx/Ipopt-xxx
```

在代码中替换`mumps`为`ma27`或`ma57`

## 将rosbag存储为csv

先查看bag信息

```bash
rosbag info xxx.bag
```

将rosbag存储为csv

```bash
rostopic echo -b xxx.bag -p /topic_name > xxx.csv
```

注：xpp_bag的内容：

* base
  * pose
    * position (x y z)
    * orientation (x y z w)
  * twist
    * linear (x y z)
    * angular (x y z)
  * accel
    * linear (x y z)
    * angular (x y z)
* ee_motion (0 1 2 3)
  * pos (x y z)
  * vel (x y z)
  * acc (x y z)
* ee_forces (0 1 2 3)  (x y z)
* ee_contact (0 1 2 3)
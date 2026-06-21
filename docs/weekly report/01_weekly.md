# Week 1

本周进度如下:

1.完成上周未完成的takler 和 listener的测试
 
知道了在终端中要搭建环境才能执行命令:
source /opt/ros/humble/setup.bash

说写代码为:
source /opt/ros/humble/setup.bash
ros2 run demo_nodes_py talker 和 listener
<img width="600" height="400" alt="image" src="https://github.com/Xiongqx9/xqx-project/blob/3a4e121eea3fc5082e32d1b11e1c4c81156a4b32/19b8fe18054d61beacb480a124ab2776.png"/>

关闭终端 ctrl+c

2.尝试了海龟模拟器---turtlesim

运行代码:

展开图板 ros2 run turtlesim turtlesim_node

遥控海龟 ros2 run turtlesim turtle_teleop_key

<img width="600" height="400" alt="image" src="https://github.com/Xiongqx9/xqx-project/blob/a6bbd90f700b21616b2bda9d99459063657659ec/03c50d59bedc4cea0475143c4e4a183e.png" />


3.Python 发布节点 publisher.py 和 订阅节点 subscriber.py
以及多节点启动 launch 文件 talk_listen.launch.py （以听说为例）
<img width="600" height="400" alt="image" src=" https://github.com/Xiongqx9/xqx-project/blob/10380c974b6dc7ac67e1fe27067050f12df1ac81/0bad31b9c30ce2e977faabce6988668a.png"/>


4.package 创建与编译指令

创建工作空间

mkdir -p ~/ros2_ws/src && cd ~/ros2_ws/src

创建Python功能包

ros2 pkg create --build-type ament_python my_pkg --dependencies rclpy std_msgs

将上面publisher.py、subscriber.py放入my_pkg/my_pkg/

在my_pkg下新建launch文件夹，放入launch文件

编译+刷新环境

cd ~/ros2_ws

colcon build --symlink-install

source install/setup.bash

一键启动两个节点

ros2 launch my_pkg talk_listen.launch.py

5.认识概念

Node（节点）

ROS2 最小独立可执行程序进程，机器人所有功能都封装在节点中，如发布消息、接收消息、导航、视觉识别都是独立节点。

Topic（话题）

异步发布 - 订阅通信通道，发布节点持续循环推送数据，多个订阅节点可同时接收；无应答机制，适合高频传感器流式数据（雷达、图像）。

Service（服务）

同步一问一答通信，客户端发起单次请求，服务端计算完成后返回一次结果；适合瞬时指令，如查询设备状态、单次坐标获取。

Action（动作）

面向长耗时任务的通信机制，支持请求、实时进度反馈、最终结果、中途取消；适合机械臂运动、自主导航这类长时间执行任务。

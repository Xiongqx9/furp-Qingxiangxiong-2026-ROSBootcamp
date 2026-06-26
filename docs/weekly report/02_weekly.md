# Week 2

本周学习并且尝试

1.打开本地小车 ROS2 工程nota_carter_mini_ros2，梳理 src 下 3 个功能包分工：机器人模型描述包、Mujoco 仿真包、SLAM 建图包

<img width="600" height="400" alt="image" src="https://github.com/Xiongqx9/xqx-project/blob/099f7934c69a43417816e939411badf8c2275151/43b1a4064dd35c3892c2934886282929.png"/>

2.对小车完整工作空间执行colcon build --symlink-install编译，刷新setup.bash环境，验证三个机器人功能包正常识别

3.给slam tool 骨架补充并调试了参数，使仿真小车可以正常在迷宫上行走，并且可以测绘map

<img width="600" height="400" alt="image" src="https://github.com/Xiongqx9/xqx-project/blob/099f7934c69a43417816e939411badf8c2275151/203b25b3b576aa892c683ea636a8c01b.png"/>

os:仍有些问题需解决：map的绘制为什么会重复，是不是编写NaV2导航后就可以解决，下周继续学习并完成map的绘制

# 矿洞自主巡检

基于 BUNKER MINI、XT16 激光雷达和 D435i，验证重复巡检建图、地图对齐与环境变化定位。

**当前状态：仅有工程结构。代码、Docker 配置和脚本均为空占位，暂不能构建或运行。**

## 开发环境

- 开发电脑：Ubuntu 22.04 + NVIDIA 独显，使用 Docker 开发。
- 容器目标：Ubuntu 20.04 + ROS Noetic + Gazebo Classic 11。
- 实机目标：Jetson Nano + Ubuntu 20.04 + ROS Noetic，后续单独适配和验证。

## 目录说明

| 路径 | 用途 |
| --- | --- |
| `docker/` | 镜像构建与容器入口脚本 |
| `compose.yaml` | 容器启动、GPU、显示和目录挂载配置 |
| `src/mine_description/` | 机器人模型与传感器安装关系 |
| `src/mine_simulation/` | 巷道场景与 Gazebo 启动文件 |
| `src/xt16_simulator/` | XT16 点云生成与适配 |
| `src/mine_slam/` | SLAM 参数与启动文件 |
| `src/mine_map_compare/` | 地图对齐与变化检测 |
| `scripts/` | 构建、录包与评估脚本 |
| `docs/` | 协作规范、接口说明与实验记录 |

空目录使用 `.gitkeep` 保留；这些目录尚未初始化为可编译的 ROS 包。

## 首阶段目标

跑通巷道与机器人仿真，检查点云、TF 和仿真时间，完成录包重放，再接入 SLAM 与地图比较。

参与开发前请阅读 [协作开发规范](docs/contributing.md)。

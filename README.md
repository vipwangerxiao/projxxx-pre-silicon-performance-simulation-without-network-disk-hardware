# projxxx-pre-silicon-performance-simulation-without-network/disk-hardware

## 项目名称

在缺少网络/磁盘的硬件环境中进行硅前性能模拟

## 项目描述

处理器设计中，在硅前投片前，希望可以预估芯片性能，电子设计自动化(EDA) 工具可以提供寄存器传输级(RTL) 的仿真，即通过一些硬件辅助可以仿真 CPU cycle 级的运行，并能够启动 OS 运行软件。但此类 EDA 工具价格昂贵，通常不会仿真网络/磁盘等外设，只有 CPU 和内存等基础硬件，而实际应用不可避免会用到网络/磁盘设备，因此需要考虑缺少网络/磁盘外设环境中应用的性能失真情况。

本项目考虑如何在 OS 中等效网络/磁盘的影响，同时模拟其它部分的性能表现。性能模拟是不断逼近的过程，一种基础的模拟方法是，使用 loopback 设备代替实际网卡进行本地网络通信，使用基于内存的存储替代磁盘进行存储，同学们可以基于此方案进改进优化，也可以尝试其它方案。

可自选实际应用如 Nginx/Redis/MySQL 等，在具备网络/磁盘的真实完整环境中测试应用性能，然后在相同的硬件环境中，不使用实际网络/磁盘设备，修改 OS 进行模拟并测试应用性能，对比性能差异，重点关注除网络/磁盘外系统性能的表现差异，网络/磁盘模拟部分作为应用运行的支撑即可。

本项目可以帮助同学们了解常见的性能分析指标，同时熟悉网络/磁盘 IO 的相关知识，涉及面比较广，可以选择部分内容进行分析

评价标准：

1、各维度模拟指标的相似度，如端到端性能 TPS/RPS、热点函数占比、PMU 关键性能指标如 cache/branch miss

2、环境模拟完整/完成度，有些应用如 Nginx 网络部分占主导，可以不关注磁盘模拟部分

## 所属赛道

2024 全国大学生操作系统比赛的“OS功能挑战”赛道

## 参赛要求

- 以小组为单位参赛，最多三人一个小组，且小组成员是来自同一所高校的学生（本科生/研究生均可）
- 如学生参加了多个项目，参赛学生选择一个自己参加的项目参与评奖
- 请遵循“2024国大学生操作系统比赛”的章程和技术方案要求

## 项目导师

王鹏 :  rocking@linux.alibaba.com

## 难度

高

## License

GPLv2

## 开发环境

可以选择阿里云倚天实例 Anolis/Alinux 系统，也可以基于其它环境

## 预期目标

1. 学习了解性能/网络/磁盘相关知识
2. 选择一个应用在模拟环境和实际环境进行性能对比, 关键指标相似度达到 80%



## 参考资料

[localhost 本地网络通信](https://en.wikipedia.org/wiki/Localhost)

[基于内存的块设备模拟 null block](https://docs.kernel.org/block/null_blk.html)

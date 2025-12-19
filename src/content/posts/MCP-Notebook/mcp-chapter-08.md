---
title: MCP-Chapter-08
date: 2025-12-15
description: Studying Several Common Interface Chips with Richer Functions and Stronger Performance
tags:
  - 2025-autumn
  - MCP
  - Notebook
image: "[[../attachments/cover-088.png]]"
imageAlt: ""
imageOG: true
hideCoverImage: false
hideTOC: false
targetKeyword: ""
draft: true
---
# 8255A 芯片

## 并行接口

并行接口就是数据在多根线上同时传送。并行接口的特点：

- 具有端口寄存器

- 与CPU和外设进行联络的控制端

- 中断控制端

- 可编程（方便修改功能）

## 结构及其功能

![](../attachments/8255A%20内部结构.png)
*8255A 内部结构*

|    引脚     | 信号/端口名称 |             方向/功能说明              |
| :-------: | :-----: | :------------------------------: |
| PA0 ~ PA7 |   端口A   | 8位通用I/O端口，连接外部设备。输入/输出方向可通过编程设定。 |
| PB0 ~ PB7 |   端口B   | 8位通用I/O端口，连接外部设备。输入/输出方向可通过编程设定。 |
| PC0 ~ PC7 |   端口C   | 8位通用I/O端口，连接外部设备。输入/输出方向可通过编程设定。 |
|  D0 ~ D7  |  数据总线   |      双向8位数据总线，连接CPU，用于数据传输。      |
|  A0, A1   |  端口地址线  |    输入，连接CPU，用于==选择内部端口或寄存器==     |
|    WR#    |   写使能   |        输入，低电平有效，来自CPU的写信号        |
|    RD#    |   读使能   |        输入，低电平有效，来自CPU的读信号        |
|    CS#    |   片选    |         输入，低电平有效，使能芯片操作。         |
|    VCC    |   电源    |             芯片电源输入。              |
|    GND    |    地    |               电源地。               |
### 端口选择

| CS# | A0  | A1  | 端口      |
| --- | --- | --- | ------- |
| 0   | 0   | 0   | PA      |
| 0   | 0   | 1   | PB      |
| 0   | 1   | 0   | PC      |
| 0   | 1   | 1   | 内部控制寄存器 |
| 1   | /   | /   | /       |
一共需要两根地址线，所以在8086系统中，8255A的A1接地址线A2，A0接A1，剩下的12位地址线参加译码。


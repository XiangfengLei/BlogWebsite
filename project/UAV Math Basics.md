---
title: 2 UAV Math Basics
date: 2019-1-3 19:50:34  
tags: BlogSpace 
mathjax: ture
categories:  
- Item
- UAV Control

---

二、数学基础知识
------
2.1 地球固联坐标系与机体坐标系
------
地球固联坐标系：以飞机起飞位置或者地心作为坐标原点og，先让x轴指向任意方向，zg轴垂直于地面向下，按右手定则确定yg轴。如下图：　　  

![](https://i.imgur.com/G7j5qBD.jpg)  
    　　
机体坐标系：以无人机的重心作为坐标原点ob，xb轴指向无人机的头部（左右两边对称），zb轴在平面内垂直向下，按上述右手定则确定yb轴。     
        　     　　
![](https://i.imgur.com/hXff0LC.jpg)　　　  

2.2　欧拉角/姿态角
------
定义：机体坐标系与地球固联坐标系之间的夹角。   
（1）偏航角ψ(yaw)：如图（a）,绕轴e3(z轴)顺时针旋转（朝轴e1方向向右旋转）为正，轴e1、e2、e3对应对地坐标系x、y、z轴，x轴为机头方向。    
（2）俯仰角θ(pitch)：如图（b）,绕轴k2(y轴)逆时针旋转（朝k1轴方向向上旋转）为正，轴k1，k2，k3对应对地坐标系x、y、z轴。  
（3）翻滚角Φ(roll)：如图（c），绕轴n1逆时针旋转(向右旋转)为正,轴n1，n2，n3对应对地坐标系x、y、z轴。    
 ![](https://i.imgur.com/mboqoiK.png)

2.3 欧拉角变化率与角速度关系
------
若机体旋转的角速度为：

$$\mathbf{\omega}_b = {\lbrack\mathbf{\omega}_{\mathbf{x}_{\mathbf{b}}},\mathbf{\omega}_{\mathbf{y}_{\mathbf{b}}},\mathbf{\omega}_{\mathbf{z}_{\mathbf{b}}}\rbrack}^{T}$$
2.4 旋转矩阵
------

2.5 四元素
------

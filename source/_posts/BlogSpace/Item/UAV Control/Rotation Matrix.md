---
title: Rotation Matrix
date: 2018-5-2 16:50:34  
toc: true
tags: BlogSpace
mathjax: ture
categories:
- Item   
- UAV Control

---

一、定义
---
1、如下图，在迪卡坐标系下，起始时矩阵为$V_A$={$X_A,Y_A,Z_A$};进过旋转得到$V_B$={$X_B，Y_B，Z_B$}，则存在$V_B=R V_A$，那么R就是旋转矩阵。
![](https://i.imgur.com/2q77ct2.png)  
<!--more-->   
2、单位矩阵$X_A$={1,0,0}、$Y_A$={0,1,0}、$Z_A$={0,0,1},则$X_B=R X_A，Y_B=R Y_A，Z_B=R Z_A$。得R={$X_B,Y_B,Z_B$}.  
3、旋转后的向量$X_B$的三个分量分别为$X_B$在$X_A$、$Y_A$、$Z_A$轴上投影的模，如下图：  
![](https://i.imgur.com/n1jhjz1.png)  
二、性质
---
1、旋转矩阵是正交矩阵。  	  
	如果：AA'=E（E为单位矩阵，A'表示“矩阵A的转置”。）则n阶实矩阵A称为正交矩阵   
正交矩阵有如下性质：  
	（1）每一行（列）都是单位矩阵，并且两两正交（任意两行或两列相互垂直）。最简单的正交矩阵就是单位阵。  
	（2）正交矩阵的逆（inverse）等于正交矩阵的转置（transpose）。同时可以推论出正交矩阵的行列式的值肯定为正负1的。   
		AA^T=E,取行列式为|A||A^T|=1,由于|A^T|=|A|,因此|A|^2=1,于是|A|=1或-1.  
注：若内积空间中两向量的内积为0，则称它们是正交的。如果能够定义向量间的夹角，则正交可以直观的理解为垂直。  
2、旋转矩阵的逆和转置相同。$R^{-1} = R^T$。上面一条已说明。如下图：   
![](https://i.imgur.com/NZtQMLx.png)  
三、例子
---
现在以三个欧拉角中的RotX为例（其余两个欧拉角以此类推），结合下图，计算出RotX的旋转矩阵Rrotx。  
（1）由于X轴是垂直于YoZ平面的，所以$X_A$和$Y_B$，$Z_B$的点乘结果为0，同时$X_B$和$Y_A$，$Z_A$的点乘结果也为0。  
（2）由于$X_A$，$X_B$都是单位向量，所以$X_A$和$X_B$的点乘结果为1。  
（3）由于绕x轴旋转，所以我们观察$Y_B$和$Z_B$分别在$Y_A$和$Z_A$上的投影情况。  
![](https://i.imgur.com/tgxydLi.png)   

四、参考文献
---
1、http://www.cnblogs.com/caster99/p/4703033.html  
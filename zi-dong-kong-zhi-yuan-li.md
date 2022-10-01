---
description: 自动控制原理学习
---

# 自动控制原理

## 自动控制系统的数学模型

### 控制系统的微分方程

`线性元件的微分方程`：举例包括RLC串联电路，弹簧质量阻尼器系统，机械传动系统，电机

也讲述了<mark style="color:orange;">`微分方程的增量化表示`</mark>和`非线性微分方程的线性化`

### 传递函数

<mark style="color:red;background-color:purple;">**重要章节！！！重要章节！！！重要章节！！！**</mark>

传递函数离不开[拉氏变换](ji-fen-bian-huan.md#la-pu-la-si-bian-huan)

主要讲述了电路的传递函数：比例环节，积分环节，惯性环节，振荡环节，微分环节，延迟环节

### 控制系统的结构图

主要讲述了结构图的表示和化简，挺简单的，主要留意反馈环节的等效

### 自动控制系统的传递函数

讲述了`系统的开环传递函数`，`闭环系统的传递函数`，`闭环系统的偏差传递函数`

### 信号流图

信号流图类似于结构图只不过它能应用<mark style="color:orange;">`梅逊(Mason)公式`</mark>来求解

### 脉冲响应

简述了利用脉冲响应函数逆求解传递函数

## 自动控制系统的时域分析

### 稳定性和代数稳定判据

根据`劳斯(Routh)稳定判据`判断系统是否稳定，改变系统稳定性可以通过积分环节变惯性环节或者引入比例微分环节

### 典型输入信号和阶跃响应性能指标

典型的输入信号有单位阶跃函数，单位斜坡函数，单位抛物线函数

### 一阶系统的动态性能指标

若自动控制系统的传递函数分母阶次为1，则称为一阶系统，假设其闭环传递函数为

$$
\Phi(s)=\frac{K}{Ts+1}
$$

忽略K,对阶跃响应

$$
C(s)=\Phi(s)R(s)=\frac{1}{Ts+s}\cdot\frac{1}{s}=\frac{1}{s}-\frac{1}{s+\frac{1}{T}} \\ c(t)=\mathscr{L}^{-1}[C(s)]=(1-e^{-t/T})\cdot1(t) \\ 瞬态响应c_t(t)=-e^{-t/T}\cdot1(t) \\ 稳态响应c_{ss}(t)=1(t)
$$

​一阶系统的动态性能指标：过程过渡时间$t_s=3T$

### 二阶系统的动态性能指标

<mark style="color:red;background-color:purple;">**重要章节！！！重要章节！！！重要章节！！！**</mark>

若自动控制系统的传递函数分母阶次为2，则称为二阶系统，假设其闭环传递函数为

$$
\Phi(s)=\frac{K}{T^2s^2+2\zeta Ts+1} \\ 或写为\Phi(s)=\frac{w_n^2}{s^2+2\zeta w_ns+w_n^2}
$$

​对阶跃响应：

$$
C(s)=\frac{1}{s}-\frac{s+2\zeta w_n}{s^2+2\zeta w_ns+w_n^2} \\ c_ss(t)=1 \\ c_t(t)=\mathscr{L}^{-1}[-\frac{s+2\zeta w_n}{s^2+2\zeta w_ns+w_n^2}]
$$

当$\zeta$取不同的值时

$$
\zeta=0,c_t=-cosw_nt \\ 0<\zeta<1,c_t(t)=-\frac{1}{\sqrt{1-\zeta^2}}e^{-\zeta w_nt}sin(w_n\sqrt{1-\zeta^2}t+arctan\frac{\sqrt{1-\zeta^2}}{\zeta})=-\frac{1}{\sqrt{1-\zeta^2}}e^{-\zeta w_nt}sin(w_dt+\beta) \\ \zeta=1,c_t(t)=-(1+\frac{t}{T}e^{-t/T}) \\ \zeta>1,c_t(t)=-\frac{-\zeta+\sqrt{\zeta^2-1}}{2\sqrt{\zeta^2-1}}exp[-(\zeta+\sqrt{\zeta^2-1})t/T]+\frac{-\zeta-\sqrt{\zeta^2-1}}{2\sqrt{\zeta^2-1}}exp[-(\zeta-\sqrt{\zeta^2-1})t/T]
$$


---
title: 今天数理方程期末考试一道题不会写TAT
layout: post
author: "Hao Zhang"
categories: math
---

$$u_t=a^2u_{xx}+bu_x^2+cu_y$$

$$(x,y)\in\mathbb R,t>0$$

的初值问题

考试没有写出来TAT

许轶臣的解法如下：

令

$$u = f(v)$$

有

$$u_t=f'(v)v_t$$

$$u_y=f'(v)v_y$$

$$u_x=f'(v)v_x$$

$$u_{xx}=f'(v)v_{xx}+f''(v)v_x^2$$

所以

$$f'(v)v_t=a^2(f'(v)v_{xx}+f''(v)v_x^2)+b(f'(v)v_x)^2+cf'(v)v_y$$

$$f'(v)v_t=a^2f'(v)v_{xx}+a^2f''(v)v_x^2+bf'(v)^2v_x^2+cf'(v)v_y$$

令

$$a^2f''(v)v_x^2+bf'(v)^2v_x^2=0$$

即

$$a^2f''(v)+bf'(v)^2=0$$

解得

$$f(v)=\frac{a^2}{b}\ln\frac{bv}{a^2}$$

$$f'(v)=\frac{a^2}{bv}$$

带入原方程

得到

$$v_t=a^2v_{xx}+cv_y$$


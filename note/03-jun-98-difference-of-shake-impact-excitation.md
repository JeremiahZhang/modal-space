# 03 模态试验中激振器激励和力锤激励的差别

- [June 98 Is there any difference between a modal test with a shaker excitation or impact excitation? ](https://www.uml.edu/docs/jun98_tcm18-189814.pdf)
    - 理论上误差
    - 实际中有差别

## 理论无差别

系统运动方程在 Laplace域的表达式如下

$$\left[[M]s^2 + [C]s + [K]\right]{X(s)} = {F(s)} 
===> 
[B(s)]{X(s)} = {F(s)}$$

质量、阻尼、刚度矩阵[M], [C], [K] 都是对称矩阵。

传递函数：

$$[B(s)]^{-1} = {H(s)} = \frac {Adj[B(s)]} {det[B(s)]} = \frac {[A(s)]} {det[B(s)]}$$

其中：`Adj[B(s)]` 为 `B(s)` 的伴随矩阵，`det[B(s)]` 为矩阵行列式。 这就是矩阵行列式求法。

`s = jw`

$$[H(s)]_{s=jw} = [H(jw)] = \sum_{k=1}^m \left(\frac {[A_k]} {(jw-p_k)} + \frac {[A_k^{\star}]} {(jw - p_k^{\star}}) } \right)$$

分项表示：

$$h_{ij}(jw) =  \sum_{k=1}^m \left( \frac {a_{ijk}} {(jw-p_k)} + \frac {a_{ijk}^{\star}}} {(jw-p_k^{\star}})} \right)$$

因为传递函数也是对阵矩阵，传递函数对称性 ---> 对等性： 

j点激励 i点响应的传递函数 = i点激励 j点响应的传递函数 

$$
h_{ij} = h_{ji}
$$

看下面的图一目了然

![impact h_3i](https://raw.githubusercontent.com/JeremiahZhang/modal-space/master/img/03-impact-test-h.JPG)

![shaker h_i3](https://raw.githubusercontent.com/JeremiahZhang/modal-space/master/img/03-shaker-test-h.JPG)

## 实际中差别

1. 结构不一样了
    - 力锤激励和激振器激励整体结构是不同的
    - 质量影响 和 刚度影响 势必造成结果不同
2. 激振器还要考虑如下差别
    - 如果采用移动传感器，那么结构局部质量不同
        - 解决：贴上所有传感器
        - 或附上与传感器质量相同的质量物
    - 顶杆的影响

## Log

2019-03-27

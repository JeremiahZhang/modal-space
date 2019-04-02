# 04 移动力锤和移动加速度的差别

作者图解: 

![04-configure-setup](https://raw.githubusercontent.com/JeremiahZhang/modal-space/master/img/04-roving-hammer-and-accelerometer.JPG)

## Test 1(想象)

移动力锤, 得到FRFs (9x/1z, 9x/2z, ..., 9y/1z, 9y/2z, ... , 9z/9z)

- Ref: 移动力锤, 只在平板 Z 向敲击(9个点 z向)
- Res: 固定传感器第9点, 三向加速度传感器(XYZ) 响应(9x, 9y, 9z)

传递函数矩阵:

![04-setup01](https://raw.githubusercontent.com/JeremiahZhang/modal-space/master/img/04-setup01-roving-hammer.JPG)

## Test 2(想象)

固定力锤, 移动传感器, 得到FRFs

- Ref: 固定力锤激励, 9z点
- Res: 移动传感器(三向XYZ), 遍历1-9点,总9个点 27个方向响应

传递函数矩阵:

![04-setup-02](https://raw.githubusercontent.com/JeremiahZhang/modal-space/master/img/04-setup02-roving-accelerometer.JPG)

## Difference

从上面两个想象中的测试(Test 1 和 Test 2)得到传递函数矩阵是不一样的. 所以上面上面的移动力锤和移动传感器测试的结果是由差异的.

解决办法:

1. 在Test1中, 力锤敲击每个点的x,y,z方向, 传感器只测量9点z向的振动. 这样的话, 得到的传递函数为最后一行, 与 Test2 得到的正好因互换对称性而结果相同(理论上).
2. Test 1 和 Test 2都改变, 得到传递函数, 在互换对称性而相同(理论上)
    - Test 1 中, 力锤在每个点位都敲击x,y,z方向 (传递函数矩阵的最后三行)
    - Test 2 中, 力锤在第9点都敲击x,y,z方向 (传递函数矩阵的最后三列)

看 FRF 频响函数在矩阵中的位置, 两次测试得到的传递函数可以根据传递函数矩阵的互换对称, 得到相同的结果.

## 备注: 传递函数矩阵

传递函数：

```math
\left[[M]s^2 + [C]s + [K]\right]{X(s)} = {F(s)} 
===> 
[B(s)]{X(s)} = {F(s)}

H(jw) = B^{-1}(jw) = X(jw)/F(jw) 

H_{Response, Reference}  

H_{Res, Ref}
```

```
Res: Response Point (响应点)
Ref: Reference Point (参考点:激励点)
```

## ChangeLog

```
2019-04-02 Done
```
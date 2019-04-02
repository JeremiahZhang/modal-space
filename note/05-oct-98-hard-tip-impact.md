# 05 总用硬锤头, 好不好呢?

- [October 98 Should I always use a hard tip for impact testing so the input spectrum is flat over all frequencies](https://www.uml.edu/docs/oct98_tcm18-189815.pdf)

前三段, 写得真好.

> For some reason, everyone thinks that the input spectrum should be flat over the whole frequency range of interest whenperforming an impact test.  But what do we mean by "flat" anyway.  Well, it would be better to say that the input spectrum should be "reasonably flat" over all frequencies with "no significant drop-outs or zeros" in the frequency spectrum.  So what does that mean.

> Basically, we want the input spectrum to have sufficient, fairly even excitation over the frequency range of concern.  If the input spectrum were to completely drop off to zero, then the structure would not be excited at that frequency which is not desirable.  I use the words "reasonably flat" to allow for some engineering judgment as to what is acceptable.

> Of course, many times people don't like engineers to use judgment, so they identify specific criteria or limits to force the situation to be controlled.  At times, specifications have been written with specific criteria such as "the input spectrum should roll-off no more than 3 dB over the FFT analysis frequency range".  This is a very specific requirement which does not allow the engineer to think.  It just forces him to follow a rule without thinking.  A criteria like this one may force a poor measurement to be made.  **But if we don't have to think (or are not allowed to think) then inappropriate measurements could beacquired.**

勤思考. 

## 锤头的简单讨论

- 输入力谱(the input force spectrum): 与锤头刚度和被敲击结构的刚度有关
- 受敲击脉冲时间相关: 时间越短, 频带越宽. (隐含前提: 同一锤头和同一结构)

`黑色: FRF, 红色: coherence 相干系数, 蓝色: 输出力谱`

![05-soft-tip](https://raw.githubusercontent.com/JeremiahZhang/modal-space/master/img/05-soft-tip.JPG)

自己观察, 相干系数.

![05-hard-tip](https://raw.githubusercontent.com/JeremiahZhang/modal-space/master/img/05-hard-tip.JPG)

输出力谱虽非常宽, 但是相干系数不高. 激起的过多高阶模态影响.

> The problem here is that there is too much excitation at higher frequencies causing all the modes of the structure to respond. 

如果改用锤头, 相对理想的效果如下图3所示. 相干系数曲线在频带内简直完美, 这也是理想状态, 实际从我从来没遇到过(读注).

![05-right-tip](https://raw.githubusercontent.com/JeremiahZhang/modal-space/master/img/05-right-tip.JPG)

> The drop off of the coherence is fully acceptable at these frequencies since the structure is non-resonant (anti-resonant) at these frequencies.  This means that there is no response to measure so the coherence is expected to drop here. This is a good measurement.

为什么力激起的频带宽, 影响测量呢? 作者解释:

![05-outside-band](https://raw.githubusercontent.com/JeremiahZhang/modal-space/master/img/05-outside-band.JPG)

关注 128Hz 频带内, 但是力锤也激起了 128Hz - 400Hz 频带内的模态. 这些振动能量都被振动传感器拾取到. 而 关注频带内的能量可能只占了1/3, 这不就影响测量么?!

>  So the structure responds well past 128 Hz because the input force excites all of those modes - *even though I might not be interested in those frequencies*.

解决: 使用适当的锤头能激起关注频带内的振动, 而不激发过多的模态.

这就涉及到过载.

> If the signal is not analog filtered before it reaches the analyzer, then the ADC may need to set excessively high to avoid apotential overload.  

## ChangeLog

```
2019-04-02 Done
```
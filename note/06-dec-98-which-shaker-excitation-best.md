# 06 哪种激振器最好？有什么差异么？

- [Which shaker excitation is best? Is there any difference? ](https://www.uml.edu/docs/dec98_tcm18-189813.pdf)

## 激励技术

- 随机激励（non-deterministic excitations or random） --- 非线性系统中
    - random
    - burst random
- 确定性激励（deterministic excitations） --- 线性系统中
    - sine chirp
    - digital stepped sine

区分：确定性信号可以以数学函数表示任意一点的值，防止，无法以数学函数表示的就是随机信号。

## 随机激励 Random excitation

> But it is notconsidered one of the best techniques for acquiring FRF measurements for modal testing (although it is still often used).

> The random nature of the signal excites the structure with varying amplitude and phase as averages are collected.  This tends to average any slight nonlinearities that may exist in thestructure. 

优点：平均化结构中的非线性。

> While this is a benefit, the signal nevers satisfies theperiodicity requirement of the FFT process.  Therefore, leakageis a tremendous problem.

缺电：信号无法满足FFT的周期性要求，产生信号泄漏问题。即使加了汉宁窗，FRF 也会存在泄漏问题。

>  Even with a Hanning window applied, the resulting FRFs will always suffer from leakage; **the peak amplitude will be affected and there will be an appearance of more damping in the structure due to the leakage and windowing effects.**

![1](https://raw.githubusercontent.com/JeremiahZhang/modal-space/master/img/06-01-random-exicition.JPG)

![2](https://raw.githubusercontent.com/JeremiahZhang/modal-space/master/img/06-02-random-exicition-frf.JPG)

![3](https://raw.githubusercontent.com/JeremiahZhang/modal-space/master/img/06-03-random-measurement-seq.JPG)

## Burst random

>  The only difference is that the random signal is only used during aportion of the data capture. If a pretrigger delay is also used, then the signal is totally observed within one sample interval.

> This signal is well suited for averaging out slight nonlinearities that may be found in the measurement.  

Burst random 与 random 激励的唯一区别：随机信号只在数据采集时激励。这样的激励满足FFT的周期性要求。所以没有泄漏发生也没有必要加窗函数。

![4](https://raw.githubusercontent.com/JeremiahZhang/modal-space/master/img/06-04-burst-random.JPG)

可与图2对比。

> The peaks are much sharper and better defined; the coherence is especially good at the resonances.

## Sine chirp

> The sine chirp is a fast sweep from low to high frequency within one sample interval of the analyzer.

一个样本周期内，快速扫频。满足周期性要求，FFT没有泄漏。

频响函数及相干系数：

![5](https://raw.githubusercontent.com/JeremiahZhang/modal-space/master/img/06-05-sine-chirp.JPG)

## Digital stepped sine 

> the digital stepped sine technique requires that a singlefrequency, coincident with an analyzer spectral line, is used to excite the system. 

周期性，FFT 无泄漏。

> Since it is not broadband in nature, this technique is the slowest of all techniques because each spectral line is evaluated individually.  However, it is excellent for documenting nonlinearities and is likely to produce the best measurement of all the excitation techniques above.

## Sum

- Linear system:
    - Burst random, sine chirp: similar results.
- Random excitation:
    - always suffer form leakage
    - measuresment will suffer
- Burst random better than random

Random 和 Burst Random 共振峰对比，发现其泄漏。

![6](https://raw.githubusercontent.com/JeremiahZhang/modal-space/master/img/06-06-frf-random-burst-random.JPG)

## ChangeLog

2019-05-05 read and note
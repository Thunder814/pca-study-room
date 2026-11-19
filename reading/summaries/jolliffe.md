# 短总结 2：Jolliffe 第八章 / Summary 2: Jolliffe, Principal Components in Regression

**书目信息：**I. T. Jolliffe (2002), *Principal Component Analysis*, 2nd edition, Springer。第 8 章 “Principal Components in Regression Analysis”，印刷页 167–198；本次重点 §§8.1–8.2（168–176），相关比较在 §8.3。提供文件的 PDF 页码为印刷页码加 31。

**短总结（中文）：**第八章研究如何用主成分代替原预测变量进行回归。使用全部主成分只是正交换坐标，等价于普通最小二乘；删去某些成分才会改变估计。小特征值方向会放大回归系数估计的方差，删除它们可提高稳定性，但通常引入偏差。核心提醒是：预测变量中方差小的方向，仍可能与响应高度相关，因此不能只按 PCA 的解释率决定回归保留哪些成分。本章通过公式、选成分策略和实际案例展示稳定性与预测信息之间的取舍，是 PCR 教程的理论补充。

**Brief summary (English):** Chapter 8 explains regression on principal-component scores. Retaining all components gives the same fitted model as ordinary least squares, while discarding components changes the estimator. Small-eigenvalue directions can cause large coefficient variance, so truncation may improve stability at the cost of bias. Crucially, a low-variance component can still be strongly related to the response. The chapter therefore distinguishes variance preservation from predictive usefulness and discusses component-selection strategies and examples.
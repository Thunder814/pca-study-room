# 短总结 1：Bishop 第十二章 / Summary 1: Bishop, Continuous Latent Variables

**书目信息：**Christopher M. Bishop (2006), *Pattern Recognition and Machine Learning*, Springer, Chapter 12 “Continuous Latent Variables”，印刷页 559–604。重点阅读 §12.1 PCA（561–570）、§12.2 Probabilistic PCA（570–586）、§12.3 Kernel PCA（586–590）。提供的扫描本 PDF 页码通常为印刷页码加 20；文字 OCR 有错误，以页面图像为准。

**短总结（中文）：**本章把 PCA 放在连续潜变量模型的框架下。它先证明最大投影方差与最小平方重建误差会得到相同主子空间，再说明带各向同性高斯噪声的线性潜变量模型在最大似然下恢复该子空间。概率形式提供密度、EM 估计、缺失数据和混合模型等扩展。核 PCA 则把线性 PCA 搬到隐式非线性特征空间，利用核矩阵计算。对本项目最有用的是把几何、线性代数与统计建模接起来，同时提醒我们：普通 PCA 的计算并不要求数据高斯，而 PPCA 的概率解释确实依赖相应分布假设。

**Brief summary (English):** Chapter 12 connects PCA with continuous latent-variable models. The maximum-variance and minimum-reconstruction-error formulations lead to the same principal subspace. A linear Gaussian latent-variable model with isotropic noise recovers that subspace through maximum likelihood and supports extensions such as EM estimation, missing-data treatment and mixtures. Kernel PCA extends the geometry to an implicit feature space. The chapter is particularly useful for distinguishing the algebraic properties of ordinary PCA from the probabilistic assumptions introduced by PPCA.
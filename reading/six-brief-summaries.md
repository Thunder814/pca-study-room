# 六份材料的独立短总结 / Six brief summaries

## 短总结 1：Bishop 第十二章

**书目信息：**Christopher M. Bishop (2006), *Pattern Recognition and Machine Learning*, Springer, Chapter 12 “Continuous Latent Variables”，印刷页 559–604。重点阅读 §12.1 PCA（561–570）、§12.2 Probabilistic PCA（570–586）、§12.3 Kernel PCA（586–590）。提供的扫描本 PDF 页码通常为印刷页码加 20；文字 OCR 有错误，以页面图像为准。

**短总结（中文）：**本章把 PCA 放在连续潜变量模型的框架下。它先证明最大投影方差与最小平方重建误差会得到相同主子空间，再说明带各向同性高斯噪声的线性潜变量模型在最大似然下恢复该子空间。概率形式提供密度、EM 估计、缺失数据和混合模型等扩展。核 PCA 则把线性 PCA 搬到隐式非线性特征空间，利用核矩阵计算。对本项目最有用的是把几何、线性代数与统计建模接起来，同时提醒我们：普通 PCA 的计算并不要求数据高斯，而 PPCA 的概率解释确实依赖相应分布假设。

**Brief summary (English):** Chapter 12 connects PCA with continuous latent-variable models. The maximum-variance and minimum-reconstruction-error formulations lead to the same principal subspace. A linear Gaussian latent-variable model with isotropic noise recovers that subspace through maximum likelihood and supports extensions such as EM estimation, missing-data treatment and mixtures. Kernel PCA extends the geometry to an implicit feature space. The chapter is particularly useful for distinguishing the algebraic properties of ordinary PCA from the probabilistic assumptions introduced by PPCA.

## 短总结 2：Jolliffe 第八章

**书目信息：**I. T. Jolliffe (2002), *Principal Component Analysis*, 2nd edition, Springer。第 8 章 “Principal Components in Regression Analysis”，印刷页 167–198；本次重点 §§8.1–8.2（168–176），相关比较在 §8.3。提供文件的 PDF 页码为印刷页码加 31。

**短总结（中文）：**第八章研究如何用主成分代替原预测变量进行回归。使用全部主成分只是正交换坐标，等价于普通最小二乘；删去某些成分才会改变估计。小特征值方向会放大回归系数估计的方差，删除它们可提高稳定性，但通常引入偏差。核心提醒是：预测变量中方差小的方向，仍可能与响应高度相关，因此不能只按 PCA 的解释率决定回归保留哪些成分。本章通过公式、选成分策略和实际案例展示稳定性与预测信息之间的取舍，是 PCR 教程的理论补充。

**Brief summary (English):** Chapter 8 explains regression on principal-component scores. Retaining all components gives the same fitted model as ordinary least squares, while discarding components changes the estimator. Small-eigenvalue directions can cause large coefficient variance, so truncation may improve stability at the cost of bias. Crucially, a low-variance component can still be strongly related to the response. The chapter therefore distinguishes variance preservation from predictive usefulness and discusses component-selection strategies and examples.

## 短总结 3：R-bloggers 的 PCR 教程

**书目信息：**Michy Alice, “Performing Principal Components Regression (PCR) in R”, R-bloggers / MilanoR，网页显示 2016 年 7 月 20 日。它是教学博客，不是同行评审研究论文。

**短总结（中文）：**文章介绍先把 predictors 转成主成分、再用选定成分做线性回归的 PCR 流程。它使用 iris 和 R 的 pls 包，演示 pcr、交叉验证、RMSEP、预测和回归系数图，并提醒 PCA 方向不使用响应，因此高解释率不保证预测效果。教程适合作为软件入口，但示例代码有需修正的地方：训练集与测试集都包含第 120 行，按行号切分又遇到 iris 按品种排序；示例还把 Species 纳入公式并产生虚拟变量。复现时应明确 predictors、使用不重叠且适合任务的划分，并通过训练内验证选择成分数。

**Brief summary (English):** The tutorial demonstrates PCR with the pls package using iris, including fitting, cross-validation, RMSEP and prediction. It correctly highlights the distinction between predictor variance and response relevance. The example should nevertheless be read critically: row 120 appears in both training and test sets, the split follows the ordered iris rows, and the formula includes Species through dummy coding. A careful reproduction should define the predictors explicitly, prevent overlap and choose model complexity using training-data validation.

## 短总结 4：Tipping 与 Bishop 的概率 PCA

**书目信息：**Michael E. Tipping and Christopher M. Bishop (1999), “Probabilistic principal component analysis”, *Journal of the Royal Statistical Society: Series B*, 61(3), 611–622。正文关键为 §3（概率模型与最大似然）和 §4（例子）；附录 A 讨论似然驻点，附录 B 给 EM。

**短总结（中文）：**论文为 PCA 建立线性高斯潜变量模型：观测由低维潜变量经线性映射后加各向同性噪声生成。作者证明最大似然解的载荷矩阵张成普通 PCA 的主子空间，噪声方差为舍弃特征值的平均，并给出 EM 算法。这一概率解释使 PCA 能用于密度建模、含缺失值的数据和多个局部模型的混合。文中用 Tobamovirus 数据展示这些用途。关键限制是线性结构和各向同性高斯噪声；PPCA 的后验均值坐标一般并不等于普通 PCA scores，单个 PPCA 也不是自动非线性的。

**Brief summary (English):** The paper derives PCA as maximum-likelihood estimation in a linear latent-variable model with isotropic Gaussian noise. The fitted loading matrix spans the principal eigenspace, and the estimated noise variance is the mean of the discarded eigenvalues. An EM algorithm and examples illustrate missing-data analysis, mixtures and constrained density modelling. The model retains linear and Gaussian assumptions, and its posterior latent coordinates are generally not the ordinary PCA scores. Its contribution is a probabilistic framework, rather than a universal improvement in reconstruction accuracy.

## 短总结 5：Kernel Principal Component Analysis

**书目信息：**Bernhard Schölkopf, Alexander Smola and Klaus-Robert Müller (1997), “Kernel Principal Component Analysis”, *Artificial Neural Networks—ICANN ’97*, LNCS 1327, pp.583–588。用户提供的是这篇 6 页会议论文，不是同作者 1998 年更长的 “Nonlinear Component Analysis as a Kernel Eigenvalue Problem”。

**短总结（中文）：**论文把 PCA 推广到通过非线性映射得到的特征空间。关键是把算法写成样本之间内积的形式，再用核函数直接计算这些内积，从而不必显式构造可能极高维的特征。算法对中心化核矩阵求特征向量，按特征空间单位长度要求归一化，并通过与训练样本的核值计算新样本坐标。论文用合成例子和 USPS 手写数字说明非线性特征的作用。优势依赖核与任务；计算仍需处理样本数平方级的核矩阵，而且特征空间中的重建通常难以直接映回输入空间。

**Brief summary (English):** The paper extends PCA to a nonlinear feature space by expressing the required computations through inner products and replacing them with kernel evaluations. Principal coordinates can be obtained from a centred Gram matrix without explicitly constructing the feature map. Toy examples and USPS digit experiments illustrate the usefulness of nonlinear features. The approach still depends on the kernel choice and sample-size costs, while reconstruction in the original input space is generally difficult. Its optimality concerns variance in the chosen feature space, not every downstream task.

## 短总结 6：Andrecut 的迭代 PCA 与 GPU

**书目信息：**M. Andrecut (2009), “Parallel GPU Implementation of Iterative PCA Algorithms”, *Journal of Computational Biology*, 16(11), 1593–1599，DOI 10.1089/cmb.2008.0221。PDF 共 8 页，最后一页为空白/下载标记；正文为 7 个印刷页。

**短总结（中文）：**文章关注大矩阵 PCA 的计算效率与数值正交性。NIPALS 逐个迭代估计主成分，但浮点误差可能使先后得到的载荷和得分不再充分正交。作者提出在迭代中对两侧向量进行 Gram–Schmidt 再正交化的 GS-PCA，并用 NVIDIA CUBLAS 在 GPU 上实现两种算法。论文在指定 2009 年硬件和随机矩阵测试中报告最高约 12 倍 CPU/GPU 时间比，GS-PCA 额外耗时约 5–7%。贡献是保留 PCA 目标的计算改进；这些结果不能直接推广到今天的小型 Wine 数据或所有硬件。

**Brief summary (English):** The paper addresses the speed and numerical orthogonality of iterative PCA for large matrices. It augments sequential NIPALS-style computation with Gram–Schmidt re-orthogonalisation of the left and right vectors, and implements the algorithms using GPU CUBLAS. The reported benchmark achieves up to about twelve-fold speed-up over the specified CPU implementation, with a modest additional cost for GS-PCA. The contribution concerns computation rather than a new statistical PCA objective; the timing results depend on matrix size, implementation and hardware.
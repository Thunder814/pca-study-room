# 短总结 4：Tipping 与 Bishop 的概率 PCA / Summary 4: Tipping & Bishop (1999), Probabilistic PCA

**书目信息：**Michael E. Tipping and Christopher M. Bishop (1999), “Probabilistic principal component analysis”, *Journal of the Royal Statistical Society: Series B*, 61(3), 611–622。正文关键为 §3（概率模型与最大似然）和 §4（例子）；附录 A 讨论似然驻点，附录 B 给 EM。

**短总结（中文）：**论文为 PCA 建立线性高斯潜变量模型：观测由低维潜变量经线性映射后加各向同性噪声生成。作者证明最大似然解的载荷矩阵张成普通 PCA 的主子空间，噪声方差为舍弃特征值的平均，并给出 EM 算法。这一概率解释使 PCA 能用于密度建模、含缺失值的数据和多个局部模型的混合。文中用 Tobamovirus 数据展示这些用途。关键限制是线性结构和各向同性高斯噪声；PPCA 的后验均值坐标一般并不等于普通 PCA scores，单个 PPCA 也不是自动非线性的。

**Brief summary (English):** The paper derives PCA as maximum-likelihood estimation in a linear latent-variable model with isotropic Gaussian noise. The fitted loading matrix spans the principal eigenspace, and the estimated noise variance is the mean of the discarded eigenvalues. An EM algorithm and examples illustrate missing-data analysis, mixtures and constrained density modelling. The model retains linear and Gaussian assumptions, and its posterior latent coordinates are generally not the ordinary PCA scores. Its contribution is a probabilistic framework, rather than a universal improvement in reconstruction accuracy.
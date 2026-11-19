# 短总结 6：Andrecut 的迭代 PCA 与 GPU / Summary 6: Andrecut (2009), iterative PCA on GPUs

**书目信息：**M. Andrecut (2009), “Parallel GPU Implementation of Iterative PCA Algorithms”, *Journal of Computational Biology*, 16(11), 1593–1599，DOI 10.1089/cmb.2008.0221。PDF 共 8 页，最后一页为空白/下载标记；正文为 7 个印刷页。

**短总结（中文）：**文章关注大矩阵 PCA 的计算效率与数值正交性。NIPALS 逐个迭代估计主成分，但浮点误差可能使先后得到的载荷和得分不再充分正交。作者提出在迭代中对两侧向量进行 Gram–Schmidt 再正交化的 GS-PCA，并用 NVIDIA CUBLAS 在 GPU 上实现两种算法。论文在指定 2009 年硬件和随机矩阵测试中报告最高约 12 倍 CPU/GPU 时间比，GS-PCA 额外耗时约 5–7%。贡献是保留 PCA 目标的计算改进；这些结果不能直接推广到今天的小型 Wine 数据或所有硬件。

**Brief summary (English):** The paper addresses the speed and numerical orthogonality of iterative PCA for large matrices. It augments sequential NIPALS-style computation with Gram–Schmidt re-orthogonalisation of the left and right vectors, and implements the algorithms using GPU CUBLAS. The reported benchmark achieves up to about twelve-fold speed-up over the specified CPU implementation, with a modest additional cost for GS-PCA. The contribution concerns computation rather than a new statistical PCA objective; the timing results depend on matrix size, implementation and hardware.
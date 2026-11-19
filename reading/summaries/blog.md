# 短总结 3：R-bloggers 的 PCR 教程 / Summary 3: the R PCR tutorial, read critically

**书目信息：**Michy Alice, “Performing Principal Components Regression (PCR) in R”, R-bloggers / MilanoR，网页显示 2016 年 7 月 20 日。它是教学博客，不是同行评审研究论文。

**短总结（中文）：**文章介绍先把 predictors 转成主成分、再用选定成分做线性回归的 PCR 流程。它使用 iris 和 R 的 pls 包，演示 pcr、交叉验证、RMSEP、预测和回归系数图，并提醒 PCA 方向不使用响应，因此高解释率不保证预测效果。教程适合作为软件入口，但示例代码有需修正的地方：训练集与测试集都包含第 120 行，按行号切分又遇到 iris 按品种排序；示例还把 Species 纳入公式并产生虚拟变量。复现时应明确 predictors、使用不重叠且适合任务的划分，并通过训练内验证选择成分数。

**Brief summary (English):** The tutorial demonstrates PCR with the pls package using iris, including fitting, cross-validation, RMSEP and prediction. It correctly highlights the distinction between predictor variance and response relevance. The example should nevertheless be read critically: row 120 appears in both training and test sets, the split follows the ordered iris rows, and the formula includes Species through dummy coding. A careful reproduction should define the predictors explicitly, prevent overlap and choose model complexity using training-data validation.
### Dose predict 
### 问题
- 训练集损失和测试集损失差距大  
  数据标准化或归一化做的不对，是因为仅对单个样本进行标准化或归一化。应对训练集整体进行归一化或标准化。再用训练集标准化或归一化的参数（均值，方差）去标准化测试集。
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEyODMzNzk0MjRdfQ==
-->
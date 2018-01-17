#Google Vizier:A Service for Black-Box Optimization

# 简介
Google Vizier是一个谷歌内部服务，用于谷歌内部机器学习模型的HyperParameter(超参)调试。

#什么是黑盒模型

相比传统机器学习，深度学习具有不可解释性。也就是我知道模型有效果，但是不知道为什么有效果。
黑盒调参在业界一直是一个难点。复杂模型的训练时间非常长，调参代价高，尤其是深层神经网络。
所以如何选择超参就变得很重要


# 相关研究
* Bayesian Optimization
https://papers.nips.cc/paper/4443-algorithms-for-hyper-parameter-optimization.pdf


# 传统调参方法
随机搜索 --  NP完全问题  
网格搜索 --  先验经验

# 设计目标和原则
* 易使用
* 最先进的黑盒优化算法
* 高可用
* 容易实验新算法
* 容易调试生产环境的算法 

设计原则和一般的架构差不多。

# WorkFlow
```
client.LoadStudy(study_config,worker_handle)
while (not client.StudyIsDone()):
  trail = client.GetSuggestion()
  metrics = RunTrial(trial)
  client.CompleteTrial(trial,metrics)

```

提交-> 学习 -> 反馈

关键点：
1、并行->大规模集群，数据并行，模型并行。并行调参，benchMark

算法：

* 迁移学习

* 贝叶斯估计

* 网格搜索

* 随机搜索

##论文地址

https://static.googleusercontent.com/media/research.google.com/zh-CN//pubs/archive/bcb15507f4b52991a0783013df4222240e942381.pdf
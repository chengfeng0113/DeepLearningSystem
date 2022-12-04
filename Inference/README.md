# 推理引擎

训练过程通过设定数据处理方式，并设计合适的网络模型结构以及损失函数和优化算法，在此基础上将数据集以小批量（mini-batch）反复进行前向计算并计算损失，然后反向计算梯度利用特定的优化函数来更新模型，来使得损失函数达到最优的结果。训练过程最重要的就是梯度的计算和反向传播。

而推理就是在训练好的模型结构和参数基础上，做一次前向传播得到模型输出的过程。相对于训练而言，推理不涉及梯度和损失优化。推理的最终目标是将训练好的模型部署生产环境中。真正让 AI 能够运用起来。

移动端的推理引擎应该挺多的了，google在2017年推出了TF-Lite，腾讯在2017年推出了ncnn，Apple在2017也推出了CoreML，阿里在2018年推出了MNN，华为2019年推出了MindSpsore-Lite。距今已经过去了快5年的时间，技术上也接近收敛。下面让我们一起打开推理引擎的技术吧！

## 课程部分

||||||
|---|---|---|---|---|
|编号|名称|内容|资源|备注|
|1|推理引擎|推理引擎简介|slide, video||
| |推理引擎|生命周期管理|slide, video||
| |推理引擎|推理引擎专用芯片|slide, video||
|2|离线优化|低比特量化|slide, video||
| |离线优化|二值化网络|slide, video||
| |离线优化|网络剪枝|slide, video||
| |离线优化|模型蒸馏|slide, video||
|3|部署优化|图转换与优化|slide, video||
| |部署优化| |slide, video||
| |部署优化| |slide, video||
|4|运行时优化|并发执行|slide, video||
| |运行时优化|动态Batch|slide, video||
| |运行时优化|内存分配|slide, video||
||||||

## 项目背景

近年来人工智能特别是深度学习技术得到了飞速发展，这背后离不开计算机硬件和软件系统的不断进步。在可见的未来，人工智能技术的发展仍将依赖于计算机系统和人工智能相结合的共同创新模式。需要注意的是，计算机系统现在正以更大的规模和更高的复杂性来赋能于人工智能，这背后不仅需要更多的系统上的创新，更需要系统性的思维和方法论。与此同时，人工智能也反过来为设计复杂系统提供支持。

我们注意到，现在的大部分人工智能相关的课程，特别是深度学习和机器学习相关课程主要集中在相关理论、算法或者应用，与系统相关的课程并不多见。我们希望人工智能系统这门课能让人工智能相关教育变得更加全面和深入，以共同促进人工智能与系统在开源方面的共同学习和讨论。

（原谅我复制粘贴微软[AI-System](https://github.com/microsoft/AI-System)的介绍，人家写得很好啦；另外推荐一个很好学习参考项目，公司跟英国麦络老师（爱丁堡大学）合作的[机器学习系统：设计和实现](https://github.com/openmlsys/openmlsys-zh)。）
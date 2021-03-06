简介
========================================

模糊测试
----------------------------------------
总的来说，模糊测试，是通过不断用生成的输入来运行程序，观察程序状态来查找漏洞的过程。不管是在二进制程序的漏洞挖掘，还是渗透测试中模糊测试都是非常重要的技术。

模糊测试是一种侧重于发现软件安全漏洞的方法。典型的Fuzz测试过程是通过自动的或半自动的方法，反复驱动目标软件运行，并为其提供特别构造的输入数据，同时监控软件运行的异常，进而根据异常结果及输入数据查找软件的安全漏洞。谷歌、微软、思科等公司都使用模糊测试作为软件安全开发流程的一部分。

目标
----------------------------------------
模糊测试的目标多为找到软件的缺陷。常用的自动化判断软件缺陷的方式有：基于crash、基于各种sanitizer，基于差分测试等。

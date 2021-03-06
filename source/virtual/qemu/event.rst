事件处理机制
========================================

简介
----------------------------------------
QEMU是事件处理设计架构，所有的事件都在事件循环中被处理。实现基础就是Glib事件循环。Glib的核心是poll机制，通过poll检查用户注册的事件源，并执行对应的回调。

主事件循环
----------------------------------------
QEMU的主事件循环是 ``main_loop_wait()`` ，它执行以下任务：

- 等待文件描述符变得可读或可写
- 运行到期的计时器，计时器使用 ``qemu_mod_timer()`` 函数添加
- 运行 bottom-halves

状态机
----------------------------------------
Glib对一个事件源的处理分为4个阶段：初始化、准备、poll和调度。每个阶段都提供了接口供用户注册处理函数，分别为prepare、query、check、dispatch，函数在事件后被调用。

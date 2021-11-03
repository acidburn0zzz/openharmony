# IPC与RPC通信概述

- [基本概念](#基本概念)
- [约束与限制](#约束与限制)
- [相关模块](#相关模块)

## 基本概念

IPC（Inter-Process Communication）与RPC（Remote Procedure Call）机制用于实现跨进程通信，不同的是前者使用Binder驱动，用于设备内的跨进程通信，而后者使用软总线驱动，用于跨设备跨进程通信。IPC和RPC通常采用客户端-服务器（Client-Server）模型，服务请求方（Client）可获取提供服务提供方（Server）的代理 （Proxy），并通过此代理读写数据来实现进程间的数据通信。通常，Server会先注册系统能力（System Ability）到系统能力管理者（System Ability Manager，缩写SAMgr）中，SAMgr负责管理这些SA并向Client提供相关的接口。Client要和某个具体的SA通信，必须先从SAMgr中获取该SA的代理，然后使用代理和SA通信。下文使用Proxy表示服务请求方，Stub表示服务提供方。


## 约束与限制

目前暂不支持的场景：

跨设备RPC


## 相关模块

分布式任务调度子系统
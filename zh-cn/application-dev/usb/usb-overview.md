# USB服务开发概述

## 基本概念

OpenHarmony USB服务是应用访问底层的一种设备抽象概念。开发者根据提供的USB API，可以获取设备列表、控制设备访问权限、以及与连接的设备进行数据传输、控制命令传输等。


## 运作机制

OpenHarmony USB服务系统包含USB API、USB Service、USB HAL。

**图2** USB服务运作机制

![zh-cn_image_0000001237821727](figures/zh-cn_image_0000001237821727.png)

- USB API：提供USB的基础API，主要包含查询USB设备列表、批量数据传输、控制命令传输、权限控制等。

- USB Service：主要实现HAL层数据的接收、解析、分发，前后台的策略管控以及对设备的管理等。

- USB HAL层：提供给用户态可直接调用的驱动能力接口。
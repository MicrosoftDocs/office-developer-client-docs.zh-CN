---
title: FtgRegisterIdleRoutine
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.FtgRegisterIdleRoutine
api_type:
- COM
ms.assetid: 8d9557ba-7919-42c6-9e2f-f10214437d53
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b45b80f09efbd4f05aabc2c868d5bd8eb5fa4cce
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327991"
---
# <a name="ftgregisteridleroutine"></a>FtgRegisterIdleRoutine

**适用于**：Outlook 2013 | Outlook 2016 
  
向 MAPI 系统添加基于[FNIDLE](fnidle.md)函数的空闲例程。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
   
```cpp
FTG FtgRegisterIdleRoutine(
  PFNIDLE pfnIdle,
  LPVOID pvIdleParam,
  short priIdle,
  ULONG csecIdle,
  USHORT iroIdle
);
```

## <a name="parameters"></a>参数

_pfnIdle_
  
> 实时指向空闲例程的指针。 
    
_pvIdleParam_
  
> 实时一个指针, 指向空闲引擎在其调用时作为参数传递给空闲例程的内存块。 
    
_priIdle_
  
> 实时空闲例程的初始优先级。 实现定义的例程的可能优先级大于或小于零, 但不能为零。 为用户事件 (如鼠标单击或 WM_PAINT 邮件) 保留零优先级。 大于零的优先级代表优先级高于用户事件且作为标准 Windows 消息泵循环的一部分进行调度的后台任务。 优先级小于零表示仅在消息泵空闲时运行的空闲任务。 优先级如下所示的示例: 1 表示前台提交, 2 表示加电编辑字符插入, 3 用于下载新邮件。
    
_csecIdle_
  
> 实时用于指定空闲例程参数的初始时间值, 以百分之一秒为单位。 初始时间值的意义各不相同, 具体取决于在_iroIdle_参数中传递的内容。 含义可以是下列之一: 
    
  - MAPI 空闲引擎首次呼叫空闲例程之前必须经过的最小用户 inaction, 如果_iroIdle_中设置了 FIROWAIT 标志。 在此时间过后, 空闲引擎可以根据需要频繁地调用空闲例程。 
    
  - 如果在_iroIdle_中设置了 FIROINTERVAL 标志, 则调用 idle 例程之间的最小间隔。 
    
_iroIdle_
  
> 实时用于设置空闲例程的初始选项的标志位掩码。 可以设置以下标志:
    
  FIRONOADJUSTMENT
    
  > 使用此标志指定不应为睡眠或恢复调整空闲例程计时器。 不带此标志的默认行为是在计算已用时间时排除休眠时间。 如果传递了 FIRONOADJUSTMENT, 则在计算经过的时间时将包含休眠时间。
      
  FIRODISABLED
    
  > 应在注册时禁用空闲例程。 默认操作是在**FtgRegisterIdleRoutine**注册时启用空闲例程。 
      
  FIROINTERVAL 
    
  > 由_csecIdle_参数指定的时间是对 idle 例程的连续调用之间的最小时间间隔。 
      
  FIROONCEONLY 
    
  > 已过时。 不得使用。 
      
  FIROPERBLOCK 
    
  > 已过时。 不得使用。 
      
  FIROWAIT 
    
  > _csecIdle_参数指定的时间是 MAPI idle engine 首次调用空闲例程之前必须经过的用户 inaction 的最小周期。 在此时间过后, 空闲引擎可以根据需要频繁地调用空闲例程。 
    
## <a name="return-value"></a>返回值

**FtgRegisterIdleRoutine**函数返回一个函数标记, 该标记标识已添加到 MAPI 系统中的空闲例程。 如果**FtgRegisterIdleRoutine**无法为客户端应用程序或服务提供商注册空闲例程 (例如, 由于内存问题), 它将返回 NULL。 
  
## <a name="remarks"></a>注解

以下函数处理 MAPI 空闲引擎和基于[FNIDLE](fnidle.md)函数原型的空闲例程。 
  
|**Idle 例程函数**|**使用**|
|:-----|:-----|
|[ChangeIdleRoutine](changeidleroutine.md) <br/> |更改已注册的空闲例程的特征。  <br/> |
|[DeregisterIdleRoutine](deregisteridleroutine.md) <br/> |从 MAPI 系统中删除已注册的空闲例程。  <br/> |
|[EnableIdleRoutine](enableidleroutine.md) <br/> |禁用或重新启用已注册的空闲例程, 而不将其从 MAPI 系统中删除。  <br/> |
|**FtgRegisterIdleRoutine** <br/> |将空闲例程添加到 MAPI 系统中 (无论是否启用)。  <br/> |
|[MAPIDeInitIdle](mapideinitidle.md) <br/> |关闭呼叫应用程序的 MAPI 空闲引擎。  <br/> |
|[MAPIInitIdle](mapiinitidle.md) <br/> |初始化调用应用程序的 MAPI 空闲引擎。  <br/> |
   
**ChangeIdleRoutine**、 **DeregisterIdleRoutine**和**EnableIdleRoutine**采用**FtgRegisterIdleRoutine**返回的函数标记作为输入参数。 
  
当平台的所有前台任务都变为空闲时, MAPI 空闲引擎将调用准备执行的最高优先级空闲例程。 在具有相同优先级的空闲例程之间, 不能保证呼叫顺序。 
  
以下是在_iroIdle_参数中使用 FIRONOADJUSTMENT 标志的示例。 
  
1. 使用5分钟的延迟注册空闲例程。
    
2. 在1分钟后休眠/睡眠计算机 (计时器剩余4分钟)。
    
3. 稍后再将计算机恢复10分钟。
    
没有 FIRONOADJUSTMENT 的默认行为是, 您仍需要等待4分钟才能运行例程。 也就是说, 对计时器进行了调整, 以允许计算机休眠的时间长度。 但是, 如果传递 FIRONOADJUSTMENT, 则您的空闲例程将立即运行, 因为实时时间超过5分钟。
  


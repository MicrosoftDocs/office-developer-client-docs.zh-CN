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
ms.openlocfilehash: 1775e5ea79fc71ac64a4536d3866b9a75ed96a6b
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22566270"
---
# <a name="ftgregisteridleroutine"></a>FtgRegisterIdleRoutine

**适用于**： Outlook 2013 |Outlook 2016 
  
向 MAPI 系统[FNIDLE](fnidle.md)基于函数的空闲例程。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
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
  
> [in]指向空闲例程的指针。 
    
_pvIdleParam_
  
> [in]一个指向某一空闲引擎应作为参数传递给空闲例程时调用的内存。 
    
_priIdle_
  
> [in]空闲例程初始优先级。 实现定义例程可能优先级为大于或小于零，而不为零。 零优先级供用户事件如鼠标单击或 WM_PAINT 消息。 优先级大于零表示背景任务的优先级高于用户事件调度标准 Windows 消息抽取循环的一部分。 优先级小于 0 表示空闲只能在消息抽取空闲时间运行的任务。 优先级的示例如下所示： 前景提交的 1、 电源编辑字符插入 2 和 3 用于下载新邮件。
    
_csecIdle_
  
> [in]中的第二，用于指定空闲例行参数形式的初始时间值。 初始时间值的含义有所不同，具体取决于_iroIdle_参数中传递的内容。 含义可以是下列选项之一： 
    
  - 用户不采取行动 MAPI 之前必须经过的最小段空闲引擎将调用空闲例程第一次，如果_iroIdle_中设置 FIROWAIT 标志。 超过此时间后，空闲引擎可以根据需要通常调用空闲例程。 
    
  - 调用空闲例程，如果_iroIdle_中设置 FIROINTERVAL 标志之间的最小间隔。 
    
_iroIdle_
  
> [in]用于设置初始选项空闲例程的标志位掩码。 可以设置以下标志：
    
  FIRONOADJUSTMENT
    
  > 使用此标志指定空闲例行计时器应不调整为休眠或恢复。 如果没有此标志的默认行为是计算已用时间时，不包括休眠时间。 如果传递 FIRONOADJUSTMENT 然后休眠时间时将包括计算经过的时间。
      
  FIRODISABLED
    
  > 注册时，应禁用空闲例程。 默认操作是**FtgRegisterIdleRoutine**将注册它时启用空闲例程。 
      
  FIROINTERVAL 
    
  > _CsecIdle_参数指定的时间是连续调用空闲例程之间的最小间隔。 
      
  FIROONCEONLY 
    
  > 已过时。不得使用。  
      
  FIROPERBLOCK 
    
  > 已过时。不得使用。  
      
  FIROWAIT 
    
  > 用户不采取行动 MAPI 空闲引擎为第一次调用空闲例程之前必须经过的最小期间_csecIdle_参数指定的时间。 超过此时间后，空闲引擎可以根据需要通常调用空闲例程。 
    
## <a name="return-value"></a>返回值

**FtgRegisterIdleRoutine**函数将返回标识已添加到 MAPI 系统空闲例程函数标记。 如果**FtgRegisterIdleRoutine**无法注册的客户端应用程序或服务提供商的空闲例程，例如内存问题，因为它返回 NULL。 
  
## <a name="remarks"></a>注解

下面的函数处理与 MAPI 空闲引擎和基于[FNIDLE](fnidle.md)函数原型的空闲例程。 
  
|**空闲例行函数**|**使用情况**|
|:-----|:-----|
|[ChangeIdleRoutine](changeidleroutine.md) <br/> |更改已注册的空闲例程的特征。  <br/> |
|[DeregisterIdleRoutine](deregisteridleroutine.md) <br/> |从 MAPI 系统中删除已注册的空闲例程。  <br/> |
|[EnableIdleRoutine](enableidleroutine.md) <br/> |禁用或重新启用注册空闲例程，但不从 MAPI 系统中移除它。  <br/> |
|**FtgRegisterIdleRoutine** <br/> |将一个空闲例程添加到 MAPI 系统，使用或不启用它。  <br/> |
|[MAPIDeInitIdle](mapideinitidle.md) <br/> |关闭调用应用程序的 MAPI 空闲引擎。  <br/> |
|[MAPIInitIdle](mapiinitidle.md) <br/> |初始化调用应用程序的 MAPI 空闲引擎。  <br/> |
   
**ChangeIdleRoutine**、 **DeregisterIdleRoutine**和**EnableIdleRoutine**接受作为输入参数的函数标记，则由**FtgRegisterIdleRoutine**返回。 
  
当平台的所有前景任务都变为空闲时，MAPI 空闲引擎将调用已准备好执行的最高优先级空闲例程。 不没有呼叫之间空闲例程的相同的优先级顺序不做任何担保。 
  
下面是使用 FIRONOADJUSTMENT 标志_iroIdle_参数中的示例。 
  
1. 一个空闲例程注册 5 分钟的延迟。
    
2. 休眠/休眠计算机后 1 分钟 （保留在计时器 4 分钟）。
    
3. 恢复计算机更高版本 10 分钟。
    
默认行为，而 FIRONOADJUSTMENT，不是您仍需要等待 4 的详细分钟，以便您例程，以运行。 即您计时器已被调整以允许计算机已休眠多长时间。 但是，如果传递 FIRONOADJUSTMENT 您空闲例程将立即运行因为已超过 5 分钟的实时。
  


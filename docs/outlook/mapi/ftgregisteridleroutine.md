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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418519"
---
# <a name="ftgregisteridleroutine"></a>FtgRegisterIdleRoutine

**适用于**：Outlook 2013 | Outlook 2016 
  
将 [基于 FNIDLE](fnidle.md) 函数的空闲例程添加到 MAPI 系统。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
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
  
> [in]指向空闲引擎在调用空闲例程时应作为参数传递的内存块的指针。 
    
_priIdle_
  
> [in]空闲例程的初始优先级。 实现定义的例程的可能优先级大于或小于零，但不大于零。 为用户事件保留零优先级，如鼠标单击或WM_PAINT消息。 大于零的优先级表示优先级高于用户事件的后台任务，并作为标准邮件循环的一Windows调度。 小于零的优先级表示仅在邮件空闲时间期间运行的空闲任务。 优先级示例如下：1 表示前台提交，2 表示 power-edit 字符插入，3 表示下载新邮件。
    
_csecIdle_
  
> [in]指定空闲例程参数时所使用的初始时间值（以百分之几秒表示）。 初始时间值的含义会有所不同，具体取决于  _一节参数中传递_ 的值。 含义可以是下列内容之一： 
    
  - 在 MAPI 空闲引擎首次调用空闲例程之前必须经过的最小用户不操作时段（如果 FIROWAIT 标志在  _创建Idle_ 中设置）。 此时间结束后，空闲引擎可以在必要时经常调用空闲例程。 
    
  - 如果 FIROINTERVAL 标志在  _分流Idle_ 中设置，则对空闲例程的调用之间的最小间隔。 
    
_一体式_
  
> [in]用于设置空闲例程的初始选项的标志的位掩码。 可以设置以下标志：
    
  FIRONOADJUSTMENT
    
  > 使用此标志指定不应针对睡眠或恢复调整空闲例程计时器。 没有此标志的默认行为是在计算已用时间时排除睡眠时间。 如果传递 FIRONOADJUSTMENT，则计算已用时间时将包含睡眠时间。
      
  FIRODISABLED
    
  > 注册时应禁用空闲例程。 默认操作是在 **FtgRegisterIdleRoutine** 注册空闲例程时启用该例程。 
      
  FIROINTERVAL 
    
  > _csecIdle_ 参数指定的时间是连续调用空闲例程之间的最小间隔。 
      
  FIROONCEONLY 
    
  > 已过时。不得使用。  
      
  FIROPERBLOCK 
    
  > 已过时。不得使用。  
      
  FIROWAIT 
    
  > _csecIdle_ 参数指定的时间是在 MAPI 空闲引擎首次调用空闲例程之前必须经过的最小用户不操作时段。 此时间结束后，空闲引擎可以在必要时经常调用空闲例程。 
    
## <a name="return-value"></a>返回值

**FtgRegisterIdleRoutine** 函数返回一个函数标记，该标记标识已添加到 MAPI 系统的空闲例程。 如果 **FtgRegisterIdleRoutine** 无法注册客户端应用程序或服务提供商的空闲例程，例如，由于内存问题，它将返回 NULL。 
  
## <a name="remarks"></a>备注

以下函数基于 [FNIDLE](fnidle.md) 函数原型处理 MAPI 空闲引擎和空闲例程。 
  
|**空闲例程函数**|**使用情况**|
|:-----|:-----|
|[ChangeIdleRoutine](changeidleroutine.md) <br/> |更改已注册的空闲例程的特征。  <br/> |
|[DeregisterIdleRoutine](deregisteridleroutine.md) <br/> |从 MAPI 系统中删除注册的空闲例程。  <br/> |
|[EnableIdleRoutine](enableidleroutine.md) <br/> |禁用或重新启用注册的空闲例程，而不将其从 MAPI 系统中删除。  <br/> |
|**FtgRegisterIdleRoutine** <br/> |将空闲例程添加到 MAPI 系统，启用或不启用它。  <br/> |
|[MAPIDeInitIdle](mapideinitidle.md) <br/> |关闭调用应用程序的 MAPI 空闲引擎。  <br/> |
|[MAPIInitIdle](mapiinitidle.md) <br/> |初始化调用应用程序的 MAPI 空闲引擎。  <br/> |
   
ChangeIdleRoutine、DeregisterIdleRoutine 和 **EnableIdleRoutine** 将 **FtgRegisterIdleRoutine** 返回的函数标记作为输入参数。  
  
当平台的所有前台任务变为空闲时，MAPI 空闲引擎将调用已准备好执行的最高优先级空闲例程。 无法保证在优先级相同的空闲例程之间调用顺序。 
  
下面是在  _一_ 半参数中使用 FIRONOADJUSTMENT 标志的示例。 
  
1. 将空闲例程注册为 5 分钟延迟。
    
2. 休眠/睡眠 1 分钟之后，在计时器 (4 分钟后使计算机) 。
    
3. 10 分钟后恢复计算机。
    
如果没有 FIRONOADJUSTMENT，默认行为是，您仍必须再等待 4 分钟，例程才能运行。 即，已调整计时器以允许计算机运行多长。 但是，如果你通过 FIRONOADJUSTMENT，你的空闲例程将立即运行，因为经过 5 分钟以上的时间。
  


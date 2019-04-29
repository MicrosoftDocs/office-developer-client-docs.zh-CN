---
title: ChangeIdleRoutine
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- ChangeIdleRoutine
api_type:
- HeaderDef
ms.assetid: 0a24fe3b-a1ef-4748-b3b3-3bf747473c9d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: cfec9356a866c79b687497c3af007c046a20a75e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418265"
---
# <a name="changeidleroutine"></a>ChangeIdleRoutine

**适用于**：Outlook 2013 | Outlook 2016 
  
更改基于[FNIDLE](fnidle.md)的空闲例程的部分或全部特征。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
   
```cpp
VOID ChangeIdleRoutine(
  FTG ftg,
  PFNIDLE pfnIdle,
  LPVOID pvIdleParam,
  short priIdle,
  ULONG csecIdle,
  USHORT iroIdle,
  USHORT ircIdle
);
```

## <a name="parameters"></a>参数

_ftg_
  
> 实时用于标识空闲例程的 Function 标记。 
    
_pfnIdle_
  
> 实时指向空闲例程的指针。 
    
_pvIdleParam_
  
> 实时指向调用实现为空闲例程分配的新内存块的指针。 
    
_priIdle_
  
> 实时表示空闲例程的新优先级的值。 实现定义的例程的可能优先级大于或小于零, 但不能为零。 值为0时为用户事件 (如鼠标单击或 WM_PAINT 邮件) 保留。 大于零的值表示优先级高于用户事件且作为标准 Windows 消息泵循环的一部分进行调度的后台任务的优先级。 小于零的值表示仅在消息泵空闲时运行的空闲任务的优先级。 优先级的示例为: 1 表示前台提交, 1 表示加电编辑字符插入, 3 用于下载新邮件。
    
_csecIdle_
  
> 实时应用于空闲例程的新时间, 以百分之一秒为单位。 初始时间值的意义各不相同, 具体取决于在_iroIdle_参数中传递的内容。 它可以是: 
    
  - MAPI 空闲引擎首次呼叫空闲例程之前必须经过的最小用户 inaction, 如果_iroIdle_中设置了 FIROWAIT 标志。 在此时间过后, 空闲引擎可以根据需要频繁地调用空闲例程。 
    
  - 如果在_iroIdle_中设置了 FIROINTERVAL 标志, 则调用 idle 例程之间的最小间隔。 
    
_iroIdle_
  
> 实时指示调用空闲例程的新选项的标志的位掩码。 必须仅设置以下任一标志:
    
  - FIROINTERVAL: _csecIdle_参数指定的时间是对 idle 例程的连续调用之间的最小时间间隔。 
      
  - FIROONCEONLY: 已过时。 请勿使用。 
      
  - FIROPERBLOCK: 已过时。 请勿使用。 
      
  - FIROWAIT: _csecIdle_参数指定的时间是 MAPI idle engine 首次调用空闲例程之前必须经过的用户 inaction 的最小周期。 在此时间过后, 空闲引擎可以根据需要频繁地调用空闲例程。 
    
_ircIdle_
  
> 实时标记的位掩码, 用于指示对空闲例程所做的更改。 可以按任意组合设置以下标志:
    
  - FIRCCSEC: 与空闲例程关联的时间的更改, 即由_csecIdle_参数中传递的值指示的更改。 
      
  - FIRCIRO: 对 idle 例程的选项的更改, 即由_iroIdle_参数中传递的值指示的更改。 
      
  - FIRCPFN: 对 idle 例程指针的更改, 即由_pfnIdle_参数中传递的值指示的更改。 
      
  - FIRCPRI: 对 idle 例程的优先级的更改, 即由_priIdle_参数中传递的值指示的更改。 
      
  - FIRCPV: 对 idle 例程内存块的更改, 即由_pvIdleParam_参数中传递的值指示的更改。 
    
## <a name="return-value"></a>返回值

无。
  
## <a name="remarks"></a>说明

以下函数处理 MAPI 空闲引擎和基于[FNIDLE](fnidle.md)函数原型的空闲例程: 
  
|**Idle 例程函数**|**使用**|
|:-----|:-----|
|**ChangeIdleRoutine** <br/> |更改已注册的空闲例程的特征。  <br/> |
|[DeregisterIdleRoutine](deregisteridleroutine.md) <br/> |从 MAPI 系统中删除已注册的空闲例程。  <br/> |
|[EnableIdleRoutine](enableidleroutine.md) <br/> |禁用或重新启用已注册的空闲例程, 而不将其从 MAPI 系统中删除。  <br/> |
|[FtgRegisterIdleRoutine](ftgregisteridleroutine.md) <br/> |将空闲例程添加到 MAPI 系统中 (无论是否启用)。  <br/> |
|[MAPIDeInitIdle](mapideinitidle.md) <br/> |关闭呼叫应用程序的 MAPI 空闲引擎。  <br/> |
|[MAPIInitIdle](mapiinitidle.md) <br/> |初始化调用应用程序的 MAPI 空闲引擎。  <br/> |
   
**ChangeIdleRoutine**、 **DeregisterIdleRoutine**和**EnableIdleRoutine**采用**FtgRegisterIdleRoutine**返回的函数标记作为输入参数。 
  
当平台的所有前台任务都变为空闲时, MAPI 空闲引擎将调用准备执行的最高优先级空闲例程。 在具有相同优先级的空闲例程之间, 不能保证呼叫顺序。 
  


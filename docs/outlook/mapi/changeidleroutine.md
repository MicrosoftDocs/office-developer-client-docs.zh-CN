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
  
更改基于 [FNIDLE](fnidle.md) 的空闲例程的一些或所有特征。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
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
  
> [in]标识空闲例程的函数标记。 
    
_pfnIdle_
  
> [in]指向空闲例程的指针。 
    
_pvIdleParam_
  
> [in]指向调用实现为空闲例程分配的新内存块的指针。 
    
_priIdle_
  
> [in]表示空闲例程的新优先级的值。 实现定义的例程的可能优先级大于或小于零，但不大于零。 为用户事件保留值 0，如鼠标单击或WM_PAINT消息。 大于零的值表示优先级高于用户事件的后台任务的优先级，并作为标准邮件循环循环Windows调度。 小于零的值表示仅在消息处理空闲时间期间运行的空闲任务的优先级。 优先级的示例包括：1 表示前台提交，1 表示 power-edit 字符插入，3 表示下载新邮件。
    
_csecIdle_
  
> [in]应用于空闲例程的新时间（以百分之几秒计）。 初始时间值的含义会有所不同，具体取决于  _一节参数中传递_ 的值。 它可以是： 
    
  - 在 MAPI 空闲引擎首次调用空闲例程之前必须经过的最小用户不操作时段（如果 FIROWAIT 标志在  _创建Idle_ 中设置）。 此时间结束后，空闲引擎可以在必要时经常调用空闲例程。 
    
  - 如果 FIROINTERVAL 标志在  _分流Idle_ 中设置，则对空闲例程的调用之间的最小间隔。 
    
_一体式_
  
> [in]指示用于调用空闲例程的新选项的标志的位掩码。 必须准确设置以下标志之一：
    
  - _FIROINTERVAL：csecIdle_ 参数指定的时间是连续调用空闲例程之间的最小间隔。 
      
  - FIROONCEONLY：已过时。 请勿使用。 
      
  - FIROPERBLOCK：已过时。 请勿使用。 
      
  - _FIROWAIT：csecIdle_ 参数指定的时间是在 MAPI 空闲引擎首次调用空闲例程之前必须经过的最小用户不操作时段。 此时间结束后，空闲引擎可以在必要时经常调用空闲例程。 
    
_ircIdle_
  
> [in]用于指示对空闲例程所做的更改的标志的位掩码。 可以任意组合设置以下标志：
    
  - FIRCCSEC：与空闲例程关联的时间更改，即由  _csecIdle_ 参数中传递的值指示的变化。 
      
  - FIRC一：对空闲例程的选项更改，即由  _传入 创建 id 参数的值指示_ 的变化。 
      
  - FIRCPFN：对空闲例程指针的变更，即由  _pfnIdle_ 参数中传递的值指示的变化。 
      
  - FIRCPRI：对空闲例程的优先级更改，即由  _在 priIdle_ 参数中传递的值指示的变化。 
      
  - FIRCPV：对空闲例程的内存块的变更，即  _由 pvIdleParam_ 参数中传递的值指示的变化。 
    
## <a name="return-value"></a>返回值

无。
  
## <a name="remarks"></a>说明

以下函数基于 [FNIDLE](fnidle.md) 函数原型处理 MAPI 空闲引擎和空闲例程： 
  
|**空闲例程函数**|**使用情况**|
|:-----|:-----|
|**ChangeIdleRoutine** <br/> |更改已注册的空闲例程的特征。  <br/> |
|[DeregisterIdleRoutine](deregisteridleroutine.md) <br/> |从 MAPI 系统中删除注册的空闲例程。  <br/> |
|[EnableIdleRoutine](enableidleroutine.md) <br/> |禁用或重新启用注册的空闲例程，而不将其从 MAPI 系统中删除。  <br/> |
|[FtgRegisterIdleRoutine](ftgregisteridleroutine.md) <br/> |将空闲例程添加到 MAPI 系统，启用或不启用它。  <br/> |
|[MAPIDeInitIdle](mapideinitidle.md) <br/> |关闭调用应用程序的 MAPI 空闲引擎。  <br/> |
|[MAPIInitIdle](mapiinitidle.md) <br/> |初始化调用应用程序的 MAPI 空闲引擎。  <br/> |
   
ChangeIdleRoutine、DeregisterIdleRoutine 和 **EnableIdleRoutine** 将 **FtgRegisterIdleRoutine** 返回的函数标记作为输入参数。  
  
当平台的所有前台任务变为空闲时，MAPI 空闲引擎将调用已准备好执行的最高优先级空闲例程。 无法保证在优先级相同的空闲例程之间调用顺序。 
  


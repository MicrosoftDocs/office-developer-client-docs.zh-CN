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
ms.openlocfilehash: 49682007946a4c5dda3800751deaebcc0e1e5740
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579450"
---
# <a name="changeidleroutine"></a>ChangeIdleRoutine

**适用于**： Outlook 2013 |Outlook 2016 
  
更改部分或全部[FNIDLE](fnidle.md)基于空闲例程的特征。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
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
  
> [in]指向空闲例程。 
    
_pvIdleParam_
  
> [in]对新块的调用实现空闲例程分配内存的指针。 
    
_priIdle_
  
> [in]表示空闲例程的新优先级值。 实现定义例程可能优先级为大于或小于零，而不为零。 值为零供用户事件如鼠标单击或 WM_PAINT 消息。 值大于零表示背景任务的优先级高于用户事件的标准 Windows 消息抽取循环一部分调度的优先级。 小于零表示空闲只能在消息抽取空闲时间运行的任务的优先级值。 优先级的示例包括： 前景提交的 1、 电源编辑字符插入 1 和 3 用于下载新邮件。
    
_csecIdle_
  
> [in]中的第二、 要应用于空闲例程形式的新时间。 初始时间值的含义有所不同，具体取决于_iroIdle_参数中传递的内容。 它可以是： 
    
  - 用户不采取行动 MAPI 之前必须经过的最小段空闲引擎将调用空闲例程第一次，如果_iroIdle_中设置 FIROWAIT 标志。 超过此时间后，空闲引擎可以根据需要通常调用空闲例程。 
    
  - 调用空闲例程，如果_iroIdle_中设置 FIROINTERVAL 标志之间的最小间隔。 
    
_iroIdle_
  
> [in]指示呼叫处于空闲状态例程的新选项标志的位掩码。 必须设置完全以下标志之一：
    
  - FIROINTERVAL: _csecIdle_参数指定的时间是连续调用空闲例程之间的最小间隔。 
      
  - FIROONCEONLY： 已过时。 请勿使用。 
      
  - FIROPERBLOCK： 已过时。 请勿使用。 
      
  - FIROWAIT: _csecIdle_参数指定的时间是用户不采取行动 MAPI 空闲引擎为第一次调用空闲例程之前必须经过的最小期间。 超过此时间后，空闲引擎可以根据需要通常调用空闲例程。 
    
_ircIdle_
  
> [in]位掩码用于指示所做的更改的标志对空闲例程。 以下标志可以设置以任意组合：
    
  - FIRCCSEC： 对空闲例程，也就是说，更改由_csecIdle_参数中传递的值与关联的时间的更改。 
      
  - FIRCIRO： 更改该空闲例程的选项，即更改由值指示在参数中传递_iroIdle_ 。 
      
  - FIRCPFN： 更改为空闲例行指针，也就是说，更改由值指示在参数中传递_pfnIdle_ 。 
      
  - FIRCPRI： 空闲例程的优先级更改也就是说，更改由值指示在参数中传递_priIdle_ 。 
      
  - FIRCPV： 对空闲例程的内存块的更改，即更改由值指示在参数中传递_pvIdleParam_ 。 
    
## <a name="return-value"></a>返回值

无。
  
## <a name="remarks"></a>注解

下面的函数处理与 MAPI 空闲引擎和基于[FNIDLE](fnidle.md)函数原型的空闲例程： 
  
|**空闲例行函数**|**使用情况**|
|:-----|:-----|
|**ChangeIdleRoutine** <br/> |更改已注册的空闲例程的特征。  <br/> |
|[DeregisterIdleRoutine](deregisteridleroutine.md) <br/> |从 MAPI 系统中删除已注册的空闲例程。  <br/> |
|[EnableIdleRoutine](enableidleroutine.md) <br/> |禁用或重新启用注册空闲例程，但不从 MAPI 系统中移除它。  <br/> |
|[FtgRegisterIdleRoutine](ftgregisteridleroutine.md) <br/> |将一个空闲例程添加到 MAPI 系统，使用或不启用它。  <br/> |
|[MAPIDeInitIdle](mapideinitidle.md) <br/> |关闭调用应用程序的 MAPI 空闲引擎。  <br/> |
|[MAPIInitIdle](mapiinitidle.md) <br/> |初始化调用应用程序的 MAPI 空闲引擎。  <br/> |
   
**ChangeIdleRoutine**、 **DeregisterIdleRoutine**和**EnableIdleRoutine**接受作为输入参数的函数标记，则由**FtgRegisterIdleRoutine**返回。 
  
当平台的所有前景任务都变为空闲时，MAPI 空闲引擎将调用已准备好执行的最高优先级空闲例程。 不没有呼叫之间空闲例程的相同的优先级顺序不做任何担保。 
  


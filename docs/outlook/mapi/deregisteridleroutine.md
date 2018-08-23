---
title: DeregisterIdleRoutine
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.DeregisterIdleRoutine
api_type:
- COM
ms.assetid: a8ada6fe-9963-4c25-b4b4-db77f9517368
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 78d499dabe60a8051c6a2a77abad4b7d6f2ed159
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22591952"
---
# <a name="deregisteridleroutine"></a>DeregisterIdleRoutine

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
删除[FNIDLE](fnidle.md)基于从 MAPI 系统空闲例程。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
VOID DeregisterIdleRoutine(
  FTG ftg
);
```

## <a name="parameters"></a>参数

 _ftg_
  
> [in]标识要删除的空闲例程的函数标记。
    
## <a name="return-value"></a>返回值

无。
  
## <a name="remarks"></a>注解

客户端应用程序或服务提供程序中的任何任务可以取消注册它具有有效_ftg_参数为其任何空闲例程。 具体而言，空闲例程可以取消注册自身。 
  
下面的函数处理与 MAPI 空闲引擎和基于[FNIDLE](fnidle.md)函数原型的空闲例程： 
  
|**空闲例行函数**|**使用情况**|
|:-----|:-----|
|[ChangeIdleRoutine](changeidleroutine.md) <br/> |更改已注册的空闲例程的特征。  <br/> |
|**DeregisterIdleRoutine** <br/> |从 MAPI 系统中删除已注册的空闲例程。  <br/> |
|[EnableIdleRoutine](enableidleroutine.md) <br/> |禁用或重新启用注册空闲例程，但不从 MAPI 系统中移除它。  <br/> |
|[FtgRegisterIdleRoutine](ftgregisteridleroutine.md) <br/> |将一个空闲例程添加到 MAPI 系统，使用或不启用它。  <br/> |
|[MAPIDeInitIdle](mapideinitidle.md) <br/> |关闭调用应用程序的 MAPI 空闲引擎。  <br/> |
|[MAPIInitIdle](mapiinitidle.md) <br/> |初始化调用应用程序的 MAPI 空闲引擎。  <br/> |
   
 **ChangeIdleRoutine**、 **DeregisterIdleRoutine**和**EnableIdleRoutine**接受作为输入参数的函数标记，则由**FtgRegisterIdleRoutine**返回。 
  
当平台的所有前景任务都变为空闲时，MAPI 空闲引擎将调用已准备好执行的最高优先级空闲例程。 不没有呼叫之间空闲例程的相同的优先级顺序不做任何担保。 
  
空闲例程取消注册后，空闲引擎不调用它再次。 调用**DeregisterIdleRoutine**任何实现必须释放空闲引擎要在其原始调用**FtgRegisterIdleRoutine**函数中使用的指针传送到任何内存块。 
  


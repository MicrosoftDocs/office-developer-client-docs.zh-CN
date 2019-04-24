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
ms.openlocfilehash: 62231a900dbe01ebe1e848355226c0589072cd42
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316798"
---
# <a name="deregisteridleroutine"></a>DeregisterIdleRoutine

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
从 MAPI 系统中删除基于[FNIDLE](fnidle.md)的空闲例程。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
   
```cpp
VOID DeregisterIdleRoutine(
  FTG ftg
);
```

## <a name="parameters"></a>参数

 _ftg_
  
> 实时用于标识要删除的空闲例程的 Function 标记。
    
## <a name="return-value"></a>返回值

无。
  
## <a name="remarks"></a>注解

客户端应用程序或服务提供程序中的任何任务都可以取消注册其具有有效_ftg_参数的任何空闲例程。 特别是, 空闲例程可以自行取消注册。 
  
以下函数处理 MAPI 空闲引擎和基于[FNIDLE](fnidle.md)函数原型的空闲例程: 
  
|**Idle 例程函数**|**使用**|
|:-----|:-----|
|[ChangeIdleRoutine](changeidleroutine.md) <br/> |更改已注册的空闲例程的特征。  <br/> |
|**DeregisterIdleRoutine** <br/> |从 MAPI 系统中删除已注册的空闲例程。  <br/> |
|[EnableIdleRoutine](enableidleroutine.md) <br/> |禁用或重新启用已注册的空闲例程, 而不将其从 MAPI 系统中删除。  <br/> |
|[FtgRegisterIdleRoutine](ftgregisteridleroutine.md) <br/> |将空闲例程添加到 MAPI 系统中 (无论是否启用)。  <br/> |
|[MAPIDeInitIdle](mapideinitidle.md) <br/> |关闭呼叫应用程序的 MAPI 空闲引擎。  <br/> |
|[MAPIInitIdle](mapiinitidle.md) <br/> |初始化调用应用程序的 MAPI 空闲引擎。  <br/> |
   
 **ChangeIdleRoutine**、 **DeregisterIdleRoutine**和**EnableIdleRoutine**采用**FtgRegisterIdleRoutine**返回的函数标记作为输入参数。 
  
当平台的所有前台任务都变为空闲时, MAPI 空闲引擎将调用准备执行的最高优先级空闲例程。 在具有相同优先级的空闲例程之间, 不能保证呼叫顺序。 
  
在空闲例程取消注册后, 空闲引擎不会再次调用它。 任何调用**DeregisterIdleRoutine**的实现都必须释放其向其传递了空闲引擎的指针的任何内存块, 以便在其对**FtgRegisterIdleRoutine**函数的原始调用中使用。 
  


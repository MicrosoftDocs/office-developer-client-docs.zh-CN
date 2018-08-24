---
title: FNIDLE
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.FNIDLE
api_type:
- COM
ms.assetid: f6b31bb4-69dd-43de-b62b-abfa99557641
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: cbad4b903592f83fc7d72fde21f149c9835f2e23
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22575635"
---
# <a name="fnidle"></a>FNIDLE
 
**适用于**：Outlook 2013 | Outlook 2016 
  
定义一个空闲例程 MAPI 空闲引擎定期调用根据优先级。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|通过实施定义的函数：  <br/> |客户端应用程序和服务提供商  <br/> |
|定义的函数调用：  <br/> |MAPI  <br/> |
|相应的指针类型：  <br/> |PFNIDLE  <br/> |
   
```cpp
BOOL (STDAPICALLTYPE FNIDLE)(
  LPVOID lpvContext
);
```

## <a name="parameters"></a>参数

 _lpvContext_
  
> [in]指向某一内存 MAPI 传递给空闲例程每次调用它。 此指针[FtgRegisterIdleRoutine](ftgregisteridleroutine.md)由传递到 MAPI 空闲引擎_pvIdleParam_参数中。 内存块中的数据可以提供上下文，用于调用空闲例程，例如，正常工作的对象或冗长的操作的当前状态。
    
## <a name="return-value"></a>返回值

FALSE 
  
> 具有**FNIDLE**原型空闲例程应始终返回 FALSE。 
    
## <a name="remarks"></a>注解

空闲例程的特定功能由实现客户端应用程序或服务提供商。 
  
在客户端或提供程序必须限制空闲例程的每个状态的执行时间。 每个状态应该执行最少的处理，更新所指的_lpvContext_，上下文数据中的当前状态并返回到 MAPI 空闲引擎。 
  
在客户端或提供程序必须 MAPI 函数[MAPIInitIdle](mapiinitidle.md)之前调用它可以与对[FtgRegisterIdleRoutine](ftgregisteridleroutine.md)函数的调用中注册其自己的空闲例程。 
  
下面的函数处理与 MAPI 空闲引擎和基于 FNIDLE 函数原型的空闲例程： 
  
|**空闲例行函数**|**使用情况**|
|:-----|:-----|
|[ChangeIdleRoutine](changeidleroutine.md) <br/> |更改已注册的空闲例程的特征。  <br/> |
|[DeregisterIdleRoutine](deregisteridleroutine.md) <br/> |从 MAPI 系统中删除已注册的空闲例程。  <br/> |
|[EnableIdleRoutine](enableidleroutine.md) <br/> |禁用或重新启用注册空闲例程，但不从 MAPI 系统中移除它。  <br/> |
|[FtgRegisterIdleRoutine](ftgregisteridleroutine.md) <br/> |将一个空闲例程添加到 MAPI 系统，使用或不启用它。  <br/> |
|[MAPIDeInitIdle](mapideinitidle.md) <br/> |关闭调用应用程序的 MAPI 空闲引擎。  <br/> |
|[MAPIInitIdle](mapiinitidle.md) <br/> |初始化调用应用程序的 MAPI 空闲引擎。  <br/> |
   
**ChangeIdleRoutine**、 **DeregisterIdleRoutine**和**EnableIdleRoutine**接受作为输入参数的函数标记，则由**FtgRegisterIdleRoutine**返回。 
  
当平台的所有前景任务都变为空闲时，MAPI 空闲引擎将调用已准备好执行的最高优先级空闲例程。 不没有呼叫之间空闲例程的相同的优先级顺序不做任何担保。 
  


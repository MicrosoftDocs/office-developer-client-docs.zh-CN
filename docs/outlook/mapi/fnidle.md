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
ms.openlocfilehash: 534f4da15bba5f38bec4cde91206694f8691cbc6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342243"
---
# <a name="fnidle"></a>FNIDLE
 
**适用于**：Outlook 2013 | Outlook 2016 
  
定义 MAPI 空闲引擎根据优先级定期呼叫的空闲例程。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil  <br/> |
|定义的函数实现者:  <br/> |客户端应用程序和服务提供程序  <br/> |
|定义的函数调用者:  <br/> |MAPI  <br/> |
|相应的指针类型:  <br/> |PFNIDLE  <br/> |
   
```cpp
BOOL (STDAPICALLTYPE FNIDLE)(
  LPVOID lpvContext
);
```

## <a name="parameters"></a>参数

 _lpvContext_
  
> 实时一个指针, 指向 MAPI 在每次呼叫时传递给空闲例程的内存块。 此指针通过[FtgRegisterIdleRoutine](ftgregisteridleroutine.md)传递给_pvIdleParam_参数中的 MAPI 空闲引擎。 内存块中的数据可提供对空闲例程 (如要对其执行操作的对象) 或较长操作的当前状态的调用的上下文。
    
## <a name="return-value"></a>返回值

FALSE 
  
> 具有**FNIDLE**原型的空闲例程应始终返回 FALSE。 
    
## <a name="remarks"></a>注解

空闲例程的特定功能由实现客户端应用程序或服务提供程序决定。 
  
客户端或提供程序必须限制空闲例程的每个状态的执行时间。 每种状态都应执行最少的处理, 更新_lpvContext_指向的上下文数据中的当前状态, 然后返回到 MAPI 空闲引擎。 
  
客户端或提供程序必须调用 MAPI 函数[MAPIInitIdle](mapiinitidle.md) , 然后它才能使用对[FtgRegisterIdleRoutine](ftgregisteridleroutine.md)函数的调用注册其自己的空闲例程。 
  
以下函数处理 MAPI 空闲引擎和基于 FNIDLE 函数原型的空闲例程: 
  
|**Idle 例程函数**|**使用**|
|:-----|:-----|
|[ChangeIdleRoutine](changeidleroutine.md) <br/> |更改已注册的空闲例程的特征。  <br/> |
|[DeregisterIdleRoutine](deregisteridleroutine.md) <br/> |从 MAPI 系统中删除已注册的空闲例程。  <br/> |
|[EnableIdleRoutine](enableidleroutine.md) <br/> |禁用或重新启用已注册的空闲例程, 而不将其从 MAPI 系统中删除。  <br/> |
|[FtgRegisterIdleRoutine](ftgregisteridleroutine.md) <br/> |将空闲例程添加到 MAPI 系统中 (无论是否启用)。  <br/> |
|[MAPIDeInitIdle](mapideinitidle.md) <br/> |关闭呼叫应用程序的 MAPI 空闲引擎。  <br/> |
|[MAPIInitIdle](mapiinitidle.md) <br/> |初始化调用应用程序的 MAPI 空闲引擎。  <br/> |
   
**ChangeIdleRoutine**、 **DeregisterIdleRoutine**和**EnableIdleRoutine**采用**FtgRegisterIdleRoutine**返回的函数标记作为输入参数。 
  
当平台的所有前台任务都变为空闲时, MAPI 空闲引擎将调用准备执行的最高优先级空闲例程。 在具有相同优先级的空闲例程之间, 不能保证呼叫顺序。 
  


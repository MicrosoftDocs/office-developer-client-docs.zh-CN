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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412378"
---
# <a name="fnidle"></a>FNIDLE
 
**适用于**：Outlook 2013 | Outlook 2016 
  
定义 MAPI 空闲引擎根据优先级定期调用的空闲例程。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil.h  <br/> |
|定义的函数实现方：  <br/> |客户端应用程序和服务提供商  <br/> |
|由调用的已定义函数：  <br/> |MAPI  <br/> |
|相应的指针类型：  <br/> |PFNIDLE  <br/> |
   
```cpp
BOOL (STDAPICALLTYPE FNIDLE)(
  LPVOID lpvContext
);
```

## <a name="parameters"></a>参数

 _lpvContext_
  
> [in]指向 MAPI 每次调用空闲例程时传递给该例程的内存块的指针。 此指针由 [FtgRegisterIdleRoutine](ftgregisteridleroutine.md)传递到 _pvIdleParam_ 参数中的 MAPI 空闲引擎。 内存块中的数据可提供对空闲例程的调用的上下文，如要操作的对象或长时间操作的当前状态。
    
## <a name="return-value"></a>返回值

FALSE 
  
> 具有 **FNIDLE** 原型的空闲例程应始终返回 FALSE。 
    
## <a name="remarks"></a>备注

空闲例程的特定功能由实现客户端应用程序或服务提供商确定。 
  
客户端或提供程序必须限制空闲例程的每个状态的执行时间。 每个状态都应执行最少的处理，更新  _lpvContext_ 指向的上下文数据中的当前状态，并返回到 MAPI 空闲引擎。 
  
客户端或提供程序必须先调用 MAPI 函数 [MAPIInitIdle，](mapiinitidle.md) 然后才能通过调用 [FtgRegisterIdleRoutine](ftgregisteridleroutine.md) 函数注册自己的空闲例程。 
  
以下函数基于 FNIDLE 函数原型处理 MAPI 空闲引擎和空闲例程： 
  
|**空闲例程函数**|**使用情况**|
|:-----|:-----|
|[ChangeIdleRoutine](changeidleroutine.md) <br/> |更改已注册的空闲例程的特征。  <br/> |
|[DeregisterIdleRoutine](deregisteridleroutine.md) <br/> |从 MAPI 系统中删除注册的空闲例程。  <br/> |
|[EnableIdleRoutine](enableidleroutine.md) <br/> |禁用或重新启用注册的空闲例程，而不将其从 MAPI 系统中删除。  <br/> |
|[FtgRegisterIdleRoutine](ftgregisteridleroutine.md) <br/> |将空闲例程添加到 MAPI 系统，启用或不启用它。  <br/> |
|[MAPIDeInitIdle](mapideinitidle.md) <br/> |关闭调用应用程序的 MAPI 空闲引擎。  <br/> |
|[MAPIInitIdle](mapiinitidle.md) <br/> |初始化调用应用程序的 MAPI 空闲引擎。  <br/> |
   
ChangeIdleRoutine、DeregisterIdleRoutine 和 **EnableIdleRoutine** 将 **FtgRegisterIdleRoutine** 返回的函数标记作为输入参数。  
  
当平台的所有前台任务变为空闲时，MAPI 空闲引擎将调用已准备好执行的最高优先级空闲例程。 无法保证在优先级相同的空闲例程之间调用顺序。 
  


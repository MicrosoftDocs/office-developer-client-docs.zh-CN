---
title: MAPIInitIdle
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.MAPIInitIdle
api_type:
- COM
ms.assetid: b6de7c6a-f2e7-4248-adea-d354924a8bbf
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b07c40882c0b9974c71eeb03123e7025b948a75e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32346653"
---
# <a name="mapiinitidle"></a>MAPIInitIdle

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
初始化调用应用程序的 MAPI 空闲引擎。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
   
```cpp
LONG MAPIInitIdle(
  LPVOID lpvReserved
);
```

## <a name="parameters"></a>参数

 _lpvReserved_
  
> 实时保留必须为零。
    
## <a name="return-value"></a>返回值

如果初始化成功, 则**MAPIInitIdle**函数返回零, 否则返回1。 如果多次调用**MAPIInitIdle** , 则所有其他调用都将成功, 但会被忽略, 除非递增引用计数。 
  
## <a name="remarks"></a>注解

在调用任何其他 idle 引擎函数之前, 客户端应用程序或服务提供程序必须调用**MAPIInitIdle** 。 
  
每次调用**MAPIInitIdle**时, 都必须通过对[MAPIDeInitIdle](mapideinitidle.md)的后续调用进行匹配, 否则会为调用应用程序保持空闲引擎的运行状态。 
  
以下函数处理 MAPI 空闲引擎和基于[FNIDLE](fnidle.md)函数原型的空闲例程: 
  
|**Idle 例程函数**|**使用**|
|:-----|:-----|
|[ChangeIdleRoutine](changeidleroutine.md) <br/> |更改已注册的空闲例程的特征。  <br/> |
|[DeregisterIdleRoutine](deregisteridleroutine.md) <br/> |从 MAPI 系统中删除已注册的空闲例程。  <br/> |
|[EnableIdleRoutine](enableidleroutine.md) <br/> |禁用或重新启用已注册的空闲例程, 而不将其从 MAPI 系统中删除。  <br/> |
|[FtgRegisterIdleRoutine](ftgregisteridleroutine.md) <br/> |将空闲例程添加到 MAPI 系统中 (无论是否启用)。  <br/> |
|[MAPIDeInitIdle](mapideinitidle.md) <br/> |关闭呼叫应用程序的 MAPI 空闲引擎。  <br/> |
|**MAPIInitIdle** <br/> |初始化调用应用程序的 MAPI 空闲引擎。  <br/> |
   
当平台的所有前台任务都变为空闲时, MAPI 空闲引擎将调用准备执行的最高优先级空闲例程。 在具有相同优先级的空闲例程之间, 不能保证呼叫顺序。 
  


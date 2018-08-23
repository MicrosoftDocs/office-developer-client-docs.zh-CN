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
ms.openlocfilehash: fd9a91b089bb06e6dfe34a1a144245d404adb270
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569223"
---
# <a name="mapiinitidle"></a>MAPIInitIdle

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
初始化调用应用程序的 MAPI 空闲引擎。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
LONG MAPIInitIdle(
  LPVOID lpvReserved
);
```

## <a name="parameters"></a>参数

 _lpvReserved_
  
> [in]保留;必须为零。
    
## <a name="return-value"></a>返回值

如果初始化成功，和 1 否则，则**MAPIInitIdle**函数将返回零。 如果多次调用**MAPIInitIdle** ，则所有其他呼叫成功，但会忽略除以增加引用计数。 
  
## <a name="remarks"></a>注解

客户端应用程序或服务提供商必须调用任何其他空闲引擎函数之前调用**MAPIInitIdle** 。 
  
每次调用**MAPIInitIdle**必须匹配通过后续调用[MAPIDeInitIdle](mapideinitidle.md)，或空闲引擎仍在运行调用应用程序。 
  
下面的函数处理与 MAPI 空闲引擎和基于[FNIDLE](fnidle.md)函数原型的空闲例程： 
  
|**空闲例行函数**|**使用情况**|
|:-----|:-----|
|[ChangeIdleRoutine](changeidleroutine.md) <br/> |更改已注册的空闲例程的特征。  <br/> |
|[DeregisterIdleRoutine](deregisteridleroutine.md) <br/> |从 MAPI 系统中删除已注册的空闲例程。  <br/> |
|[EnableIdleRoutine](enableidleroutine.md) <br/> |禁用或重新启用注册空闲例程，但不从 MAPI 系统中移除它。  <br/> |
|[FtgRegisterIdleRoutine](ftgregisteridleroutine.md) <br/> |将一个空闲例程添加到 MAPI 系统，使用或不启用它。  <br/> |
|[MAPIDeInitIdle](mapideinitidle.md) <br/> |关闭调用应用程序的 MAPI 空闲引擎。  <br/> |
|**MAPIInitIdle** <br/> |初始化调用应用程序的 MAPI 空闲引擎。  <br/> |
   
当平台的所有前景任务都变为空闲时，MAPI 空闲引擎将调用已准备好执行的最高优先级空闲例程。 不没有呼叫之间空闲例程的相同的优先级顺序不做任何担保。 
  


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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432441"
---
# <a name="mapiinitidle"></a>MAPIInitIdle

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
初始化调用应用程序的 MAPI 空闲引擎。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
LONG MAPIInitIdle(
  LPVOID lpvReserved
);
```

## <a name="parameters"></a>参数

 _lpvReserved_
  
> [in]保留;必须为零。
    
## <a name="return-value"></a>返回值

如果 **初始化成功，MAPIInitIdle** 函数将返回零，否则返回 1。 如果 **多次调用 MAPIInitIdle，** 则所有其他调用将成功，但会被忽略，但增加引用计数除外。 
  
## <a name="remarks"></a>备注

客户端应用程序或服务提供商必须先调用 **MAPIInitIdle，** 然后才能调用任何其他空闲引擎功能。 
  
对 **MAPIInitIdle 的** 每次调用都必须与 [对 MAPIDeInitIdle](mapideinitidle.md)的后续调用匹配，否则空闲引擎将保持为调用应用程序运行。 
  
以下函数基于 [FNIDLE](fnidle.md) 函数原型处理 MAPI 空闲引擎和空闲例程： 
  
|**空闲例程函数**|**使用情况**|
|:-----|:-----|
|[ChangeIdleRoutine](changeidleroutine.md) <br/> |更改已注册的空闲例程的特征。  <br/> |
|[DeregisterIdleRoutine](deregisteridleroutine.md) <br/> |从 MAPI 系统中删除注册的空闲例程。  <br/> |
|[EnableIdleRoutine](enableidleroutine.md) <br/> |禁用或重新启用注册的空闲例程，而不将其从 MAPI 系统中删除。  <br/> |
|[FtgRegisterIdleRoutine](ftgregisteridleroutine.md) <br/> |将空闲例程添加到 MAPI 系统，启用或不启用它。  <br/> |
|[MAPIDeInitIdle](mapideinitidle.md) <br/> |关闭调用应用程序的 MAPI 空闲引擎。  <br/> |
|**MAPIInitIdle** <br/> |初始化调用应用程序的 MAPI 空闲引擎。  <br/> |
   
当平台的所有前台任务变为空闲时，MAPI 空闲引擎将调用已准备好执行的最高优先级空闲例程。 无法保证在优先级相同的空闲例程之间调用顺序。 
  


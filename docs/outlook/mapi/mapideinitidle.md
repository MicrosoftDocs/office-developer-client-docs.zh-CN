---
title: MAPIDeInitIdle
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.MAPIDeInitIdle
api_type:
- COM
ms.assetid: f7b04486-bc48-4ba4-9f35-f021e06124bf
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 74bba3ea9982838f0d010bbf106c1132df1c2c25
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408206"
---
# <a name="mapideinitidle"></a>MAPIDeInitIdle

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
关闭呼叫应用程序的 MAPI 空闲引擎。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
   
```cpp
void MAPIDeInitIdle( void );
```

## <a name="parameters"></a>参数

无。 
  
## <a name="return-value"></a>返回值

无。
  
## <a name="remarks"></a>说明

客户端应用程序或服务提供商应在不再需要空闲引擎时调用**MAPIDeInitIdle** , 例如, 当即将停止处理时。 
  
每次调用[MAPIInitIdle](mapiinitidle.md)时, 都必须通过对**MAPIDeInitIdle**的后续调用进行匹配, 否则会为调用应用程序保持空闲引擎的运行状态。 
  
以下函数处理 MAPI 空闲引擎和基于[FNIDLE](fnidle.md)函数原型的空闲例程: 
  
|**Idle 例程函数**|**使用**|
|:-----|:-----|
|[ChangeIdleRoutine](changeidleroutine.md) <br/> |更改已注册的空闲例程的特征。  <br/> |
|[DeregisterIdleRoutine](deregisteridleroutine.md) <br/> |从 MAPI 系统中删除已注册的空闲例程。  <br/> |
|[EnableIdleRoutine](enableidleroutine.md) <br/> |禁用或重新启用已注册的空闲例程, 而不将其从 MAPI 系统中删除。  <br/> |
|[FtgRegisterIdleRoutine](ftgregisteridleroutine.md) <br/> |将空闲例程添加到 MAPI 系统中 (无论是否启用)。  <br/> |
|**MAPIDeInitIdle** <br/> |关闭呼叫应用程序的 MAPI 空闲引擎。  <br/> |
|[MAPIInitIdle](mapiinitidle.md) <br/> |初始化调用应用程序的 MAPI 空闲引擎。  <br/> |
   
当平台的所有前台任务都变为空闲时, MAPI 空闲引擎将调用准备执行的最高优先级空闲例程。 在具有相同优先级的空闲例程之间, 不能保证呼叫顺序。 
  


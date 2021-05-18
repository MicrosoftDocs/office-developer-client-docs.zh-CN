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
  
关闭调用应用程序的 MAPI 空闲引擎。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
void MAPIDeInitIdle( void );
```

## <a name="parameters"></a>参数

无。 
  
## <a name="return-value"></a>返回值

无。
  
## <a name="remarks"></a>说明

客户端应用程序或服务提供商在不再需要空闲引擎（例如，即将停止处理）时，应调用 **MAPIDeInitIdle。** 
  
对 [MAPIInitIdle 的](mapiinitidle.md) 每次调用都必须与 **对 MAPIDeInitIdle** 的后续调用匹配，否则空闲引擎将保持为调用应用程序运行。 
  
以下函数基于 [FNIDLE](fnidle.md) 函数原型处理 MAPI 空闲引擎和空闲例程： 
  
|**空闲例程函数**|**使用情况**|
|:-----|:-----|
|[ChangeIdleRoutine](changeidleroutine.md) <br/> |更改已注册的空闲例程的特征。  <br/> |
|[DeregisterIdleRoutine](deregisteridleroutine.md) <br/> |从 MAPI 系统中删除注册的空闲例程。  <br/> |
|[EnableIdleRoutine](enableidleroutine.md) <br/> |禁用或重新启用注册的空闲例程，而不将其从 MAPI 系统中删除。  <br/> |
|[FtgRegisterIdleRoutine](ftgregisteridleroutine.md) <br/> |将空闲例程添加到 MAPI 系统，启用或不启用它。  <br/> |
|**MAPIDeInitIdle** <br/> |关闭调用应用程序的 MAPI 空闲引擎。  <br/> |
|[MAPIInitIdle](mapiinitidle.md) <br/> |初始化调用应用程序的 MAPI 空闲引擎。  <br/> |
   
当平台的所有前台任务变为空闲时，MAPI 空闲引擎将调用已准备好执行的最高优先级空闲例程。 无法保证在优先级相同的空闲例程之间调用顺序。 
  


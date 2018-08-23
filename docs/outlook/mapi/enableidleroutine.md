---
title: EnableIdleRoutine
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.EnableIdleRoutine
api_type:
- COM
ms.assetid: 332ea831-bdf9-4dbd-b9c7-a80f8ba11b3b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c53bd63e60281e999d0d379913b3609e9472a40e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579275"
---
# <a name="enableidleroutine"></a>EnableIdleRoutine

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
启用或禁用[FNIDLE](fnidle.md)基于空闲例程。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
VOID EnableIdleRoutine(
  FTG ftg,
  BOOL fEnable
);
```

## <a name="parameters"></a>参数

 _ftg_
  
> [in]标识非处于空闲状态的例程，以启用或禁用的函数标记。 
    
 _fEnable_
  
> [in]包含 TRUE，则空闲引擎应启用空闲例程或 FALSE，如果它应禁用。
    
## <a name="return-value"></a>返回值

无。
  
## <a name="remarks"></a>注解

下面的函数处理与 MAPI 空闲引擎和基于[FNIDLE](fnidle.md)函数原型的空闲例程： 
  
|**空闲例行函数**|**使用情况**|
|:-----|:-----|
|[ChangeIdleRoutine](changeidleroutine.md) <br/> |更改已注册的空闲例程的特征。  <br/> |
|[DeregisterIdleRoutine](deregisteridleroutine.md) <br/> |从 MAPI 系统中删除已注册的空闲例程。  <br/> |
|**EnableIdleRoutine** <br/> |禁用或重新启用注册空闲例程，但不从 MAPI 系统中移除它。  <br/> |
|[FtgRegisterIdleRoutine](ftgregisteridleroutine.md) <br/> |将一个空闲例程添加到 MAPI 系统，使用或不启用它。  <br/> |
|[MAPIDeInitIdle](mapideinitidle.md) <br/> |关闭调用应用程序的 MAPI 空闲引擎。  <br/> |
|[MAPIInitIdle](mapiinitidle.md) <br/> |初始化调用应用程序的 MAPI 空闲引擎。  <br/> |
   
 **ChangeIdleRoutine**、 **DeregisterIdleRoutine**和**EnableIdleRoutine**接受作为输入参数的函数标记，则由**FtgRegisterIdleRoutine**返回。 
  
当平台的所有前景任务都变为空闲时，MAPI 空闲引擎将调用已准备好执行的最高优先级空闲例程。 不没有呼叫之间空闲例程的相同的优先级顺序不做任何担保。 
  


---
title: IPSTX2SetSpoolSuspendState
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IPSTX2.SetSpoolSuspendState
api_type:
- COM
ms.assetid: 396db029-1d4a-203d-2256-3353d03c6767
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: b6a36c1e0c3854342b627b6fddd6eb5459211f62
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22590426"
---
# <a name="ipstx2setspoolsuspendstate"></a>IPSTX2::SetSpoolSuspendState

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
在后台处理程序上设置的挂起的状态。
  
```cpp
void SetSpoolSuspendState( 
    ULONG ulState 
);
```

## <a name="parameters"></a>参数

 _ulState_
  
> [in]要设置为后台处理程序的状态。 它必须是下列值之一：
    
 **SS_ACTIVE**
  
> 
    
 **SS_SUSPENDED**
  
> 
    
## <a name="see-also"></a>另请参阅



[MAPI 常量](mapi-constants.md)


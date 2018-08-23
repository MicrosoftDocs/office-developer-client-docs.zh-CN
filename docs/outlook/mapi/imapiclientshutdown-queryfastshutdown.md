---
title: IMAPIClientShutdownQueryFastShutdown
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIClientShutdown.QueryFastShutdown
api_type:
- COM
ms.assetid: b743b5b6-4a7c-46b8-99eb-afd13ee947db
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 784a2f497811ba7c4ba0abf260ff32fde75de76a
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584931"
---
# <a name="imapiclientshutdownqueryfastshutdown"></a>IMAPIClientShutdown::QueryFastShutdown

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
查询的 MAPI 子系统的快速关闭支持提供的加载 MAPI 提供程序。
  
```cpp
HRESULT QueryFastShutdown ();
```

## <a name="return-value"></a>返回值

S_OK
  
> MAPI 子系统支持 MAPI 客户端执行快速关闭。
    
MAPI_E_NO_SUPPORT
  
> MAPI 提供程序不支持 MAPI 客户端执行快速关闭。
    
## <a name="remarks"></a>注解

MAPI 子系统是否支持 MAPI 客户端执行快速关闭取决于用户的 Windows 注册表设置或 MAPI 客户端的快速关闭的默认行为。 它还依靠加载 MAPI 提供程序支持快速关闭的能力。 有关详细信息，请参阅[Fast 关闭用户选项](fast-shutdown-user-options.md)。
  
## <a name="see-also"></a>另请参阅



[IMAPIClientShutdown : IUnknown](imapiclientshutdowniunknown.md)


[MAPI 中的客户端关闭](client-shutdown-in-mapi.md)


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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 6a76488f56f9d1eb1b344c01de2615627dd5d3ec
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418146"
---
# <a name="imapiclientshutdownqueryfastshutdown"></a>IMAPIClientShutdown::QueryFastShutdown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
查询 MAPI 子系统，了解加载的 MAPI 提供程序提供的快速关闭支持。
  
```cpp
HRESULT QueryFastShutdown ();
```

## <a name="return-value"></a>返回值

S_OK
  
> MAPI 子系统支持 MAPI 客户端执行快速关闭。
    
MAPI_E_NO_SUPPORT
  
> MAPI 提供程序不支持 MAPI 客户端执行快速关闭。
    
## <a name="remarks"></a>备注

MAPI 子系统是否支持 MAPI 客户端执行快速关闭取决于用户的 Windows 注册表设置或 MAPI 客户端用于快速关闭的默认行为。 它还取决于已加载的 MAPI 提供程序支持快速关闭的能力。 有关详细信息，请参阅快速 [关闭用户选项](fast-shutdown-user-options.md)。
  
## <a name="see-also"></a>另请参阅



[IMAPIClientShutdown : IUnknown](imapiclientshutdowniunknown.md)


[MAPI 中的客户端关闭](client-shutdown-in-mapi.md)


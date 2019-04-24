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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32350867"
---
# <a name="imapiclientshutdownqueryfastshutdown"></a>IMAPIClientShutdown::QueryFastShutdown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
查询 mapi 子系统以获取加载的 mapi 提供程序提供的快速关闭支持。
  
```cpp
HRESULT QueryFastShutdown ();
```

## <a name="return-value"></a>返回值

S_OK
  
> mapi 子系统支持 mapi 客户端执行快速关闭。
    
MAPI_E_NO_SUPPORT
  
> mapi 提供程序不支持 mapi 客户端执行快速关闭。
    
## <a name="remarks"></a>注解

mapi 子系统是否支持对 mapi 客户端进行快速关闭取决于用户的 Windows 注册表设置或 mapi 客户端的默认行为以便快速关闭。 它还取决于加载的 MAPI 提供程序支持快速关闭的功能。 有关详细信息, 请参阅[Fast Shutdown User Options](fast-shutdown-user-options.md)。
  
## <a name="see-also"></a>另请参阅



[IMAPIClientShutdown : IUnknown](imapiclientshutdowniunknown.md)


[MAPI 中的客户端关闭](client-shutdown-in-mapi.md)

